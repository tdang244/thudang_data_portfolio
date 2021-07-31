# Check Data Fusion pipeline run status to trigger the subsequent steps

In order to check the status of Data Fusion pipelines, I needed to call a check status API. Luckily, we can make some modifications to the trigger API and turn it into a check status API. 

```yaml
- checkstatusDataFusion_Pipeline: 
    call: http.get
    args:
        url: https://fusionpipeline-PROJECT-ID-dot-usw1.datafusion.googleusercontent.com/api/v3/namespaces/default/apps/NAME-OF-DATAFUSION-PIPELINE/workflows/DataPipelineWorkflow/runs?limit=1
        headers: 
            Authorization: ${token}     
```

To check the pipeline status, I used the `http.get` method. While I used `start` at the end of the trigger API, I used `runs?limit=1` at the end of the check status API, where: 

* runs: check the run status of the pipeline
* limit: maximum number of returned records. Here, with limit = 1, I pulled and checked the latest run record 

This will return a JSON list of all runs for the program, each with a start time, end time, and program status \(running/completed/failed\).

