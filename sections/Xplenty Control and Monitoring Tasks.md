Here are the main tasks you can perform with the Xplenty control and monitoring API.

## Cluster Management
The most common way to manage clusters is to [create a cluster](https://github.com/xplenty/xplentydoc/wiki/Create-Cluster) when you need to run one or more jobs, and [terminate the cluster](https://github.com/xplenty/xplentydoc/wiki/Terminate-Cluster) when the jobs are completed. 
When you create a cluster, you determine its size by specifying a cluster plan. You can [list the cluster plans](https://github.com/xplenty/xplentydoc/wiki/List-Cluster-Plans) to retrieve the cluster plan IDs.

After creating a cluster, poll its status by [retrieving the cluster information](https://github.com/xplenty/xplentydoc/wiki/Get-Cluster-Information) and checking its status value. When the status changes to "available", the cluster has finished initializing and is ready to run jobs.
After terminating a cluster, poll its status and verify that it changes to "terminated", to ensure that its resources have been released.

## Job Management
To process your data according to the Xplenty package you defined, you will need to [run a job](https://github.com/xplenty/xplentydoc/wiki/Run-Job). When you submit the job request, you pass values for the custom variables you have defined in the package you're running. Usually these will include (at least) values that determine which data will be processed and where to write the job's output. For example, you may define that the job should process certain S3 folders and that the output should be written to a different S3 folder every day. In this case, you'll need to pass the folder names in job variables when calling the run request.

Normally the job will run until its tasks are completed and then end, and there is no need to terminate the job via the API. You may want to actively [terminate a job](https://github.com/xplenty/xplentydoc/wiki/Terminate-Job) if you need its cluster resources for a more urgent job, or if the job is taking too long to complete. You can run several jobs on the same cluster.

After requesting to run a job, poll its status by [retrieving the job's information](https://github.com/xplenty/xplentydoc/wiki/Get-Job-Information) and checking its status value. When the status changes to "running", the job has been successfully launched. Continue to monitor a job's status while it runs, so that you can determine when a job has finished (its status changes to "completed"), detect and handle failed jobs, and detect jobs that are taking to long to complete and might need to be terminated. If you request to terminate a job, poll its status and verify that it changes to "stopped", to ensure that its resources have been released.

## Monitoring Jobs and Clusters
You can use the Xplenty monitoring API calls to monitor the progress of your data processing jobs, detect error conditions, and analyze and modify your resource usage. These calls allow you to retrieve information about a [single cluster](https://github.com/xplenty/xplentydoc/wiki/Get-Cluster-Information), [all clusters](https://github.com/xplenty/xplentydoc/wiki/List-Clusters), a [single job](https://github.com/xplenty/xplentydoc/wiki/Get-Job-Information), or [all jobs](https://github.com/xplenty/xplentydoc/wiki/List-Jobs). You can use the cluster information to see which clusters are active, how many jobs they're running and whether they have error conditions. You can use the job information to see which jobs are running, their status, their progress percentage, error conditions, and so on.