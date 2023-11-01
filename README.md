# Creating and Running Databricks Jobs

## Overview

In this lab, you will learn how to create and run Databricks jobs using the Jobs UI, CLI, and Jobs API. You will schedule jobs to run on a defined cadence using both the UI and API.

## Lab Steps

1. Create a job using the Jobs UI
   - Click "Jobs" in the left sidebar and select "Create Job"
   - Give the job a name and description
   - Add a notebook task, selecting a notebook from your workspace
   - Specify a new or existing cluster to run the task
   - Click "Create" to save the job
   
2. Run the job immediately using the UI
   - From the job page, click the "Runs" tab
   - Click "Run Now" to start a job run
   
3. Schedule the job using the UI
   - From the job page, click on the job name to open the configuration panel
   - Click "Add Schedule"
   - Select a cadence for the schedule, like hourly or daily
   - Click "Create" to save the schedule
   
4. Use the CLI to run the job
   - Run "databricks jobs run-now --job-id <job-id>" to start a run
   - The job-id can be found in the URL of the job page in the UI
   
5. Use the API to get the job ID
   - Make a GET request to "/jobs/list" to list all jobs
   - Find your job and note the "job_id" field
   
6. Use the API to schedule the job
   - Make a POST request to "/jobs/create" 
   - Set the "job_id" field to the job id you want to schedule
   - Specify the schedule using cron syntax in the "schedule" field
   - This will create a schedule for the existing job

7. Use the UI to monitor job runs
   - Go to the "Runs" tab of the job page
   - View the status and details of each run
   - Check that scheduled runs are triggering automatically
