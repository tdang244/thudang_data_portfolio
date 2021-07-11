# About the Project

### Context

During my work at Deloitte as an Analytics Consulting Intern, I worked on a project focusing on cloud migration and data modernization using Google Cloud Platform \(GCP\) for a logistics conglomerate. One of my tasks was to remotely trigger the Data Fusion pipelines to run using Workflows. After that, I was responsible for implementing an automatic authentication process for the workflow and engineering parallel execution in order to optimize the run time for my current workflow. 

_Note: Data Fusion and Workflows are GCP services._ 

When I worked on this task, I couldn't find any guiding materials as the services were fairly new at the time and there were barely any resources online. Therefore, I hope this blog post can be a reference material for those who try to accomplish similar tasks. 

### Result

* I managed to build a functional workflow to trigger Data Fusion pipelines remotely in 1.5 days without previous knowledge of these two services. 
* I successfully implemented an automatic authentication process in the current workflow. 
* I was able to cut down the run time by ~75% by implementing parallel execution for the codes. 

### Goals

My goal in this blog is to: 

* Document the technique that I used for educational purposes
* Create a resource for those who want to achieve similar tasks on GCP



