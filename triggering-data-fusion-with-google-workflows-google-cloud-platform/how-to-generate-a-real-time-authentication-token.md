# How to generate a real-time authentication token

Before generating a real-time authentication token directly in the YAML script on Workflows, I was retrieving them manually using the following `gcloud` command: 

`gcloud auth application-default print-access-token`

This was definitely not ideal because the token was exposed in the script, which was a security concern. Furthermore, as the token expired every 60 minutes, I had to run the `gcloud` command and copy-paste the new token into the YAML script every hour. This is extremely unscalable and it is impossible for my workflow to go into production with this type of manual authentication. 

Therefore, after trying codes out, I finally had a solution. The code I used to automatically generate a real-time token that can last up to 12 hours and without exposing it in the script is as follows: 

```yaml
- fetchToken:
    call: http.post
    args:
        url: https://iamcredentials.googleapis.com/v1/projects/-/serviceAccounts/SA_2@PROJECT_ID.iam.gserviceaccount.com:generateAccessToken
        auth:
            type: OAuth2
        body:
            lifetime: "43200s"
            scope: "https://www.googleapis.com/auth/cloud-platform"
    result: output
    next: assign_authentication_token
- assign_authentication_token:
    assign:
        - token: ${"Bearer " + output.body.accessToken}
```

I use the `projects.serviceAccounts.generateAccessToken` HTTP method \[1\] to generate a new access token every time I execute the workflow. Since the endpoint for this API is googleapis.com, I can use the "auth" section to authorize it with OAuth2, which will use the credentials of the service account associated with the workflow to create an access token for the service account I mention in the URL. It will fetch an access token for the specified service account which I can then use later in the workflow.

Note: The service account associated with the workflow \(let's name this SA\_1\) must have the "Service Account Token Creator" role in order to call the generateAccessToken method for the service account I actually want the access tokens for \(let's call this SA\_2\). So SA\_1 uses the method to create a token for SA\_2.

The`lifetime` parameter of the token can be modified to up to 12 hours by adding the SA\_2 service account to the `constraints/iam.allowServiceAccountCredentialLifetimeExtension`list constraint. You can find more details on how to use this method here \[2\].

> By default, OAuth 2.0 access tokens are valid for a maximum of 1 hour \(3,600 seconds\). However, you can extend the maximum lifetime for these tokens to 12 hours \(43,200 seconds\). To do so, identify the service accounts that need an extended lifetime for tokens, then [add these service accounts to an organization policy](https://cloud.google.com/resource-manager/docs/organization-policy/restricting-service-accounts#setting_a_list_constraint) that includes the `constraints/iam.allowServiceAccountCredentialLifetimeExtension` list constraint. You can then specify a lifetime up to 43,200 seconds when you create a token for these service accounts.



**References**

\[1\] [https://cloud.google.com/iam/docs/reference/credentials/rest/v1/projects.serviceAccounts/generateAccessToken](https://cloud.google.com/iam/docs/reference/credentials/rest/v1/projects.serviceAccounts/generateAccessToken) 

\[2\]   
[https://cloud.google.com/iam/docs/creating-short-lived-service-account-credentials\#sa-credentials-oauth](https://cloud.google.com/iam/docs/creating-short-lived-service-account-credentials#sa-credentials-oauth)

