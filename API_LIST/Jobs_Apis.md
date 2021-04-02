| API      | TYPE   | Link                                                                        | Description                                             |
|----------|--------|-----------------------------------------------------------------------------|---------------------------------------------------------|
| JOB      | GET    | /services/scheduler/api/v1/job                                              | API to list the job                                     |
| JOB      | POST   | /services/scheduler/api/v1/job                                              | API to create a job                                     |
| JOB      | PUT    | /services/scheduler/api/v1/job/pause/{job_id}                               | Endpoint to put job on hold                             |
| JOB      | PUT    | /services/scheduler/api/v1/job/resume/{job_id}                              | Endpoint to resume job                                  |
| JOB      | DELETE | /services/scheduler/api/v1/job/{job_id}                                     | Endpoint to delete a job                                |
| JOB      | GET    | /services/scheduler/api/v1/job/{job_id}                                     | API to read job                                         |
| JOB      | PUT    | /services/scheduler/api/v1/job/{job_id}                                     | API to update the job                                   |
| JOB RUN  | GET    | /services/scheduler/api/v1/job/{job_id}/run/{run_id}/retry/{retry}/download | API to download artifacts                               |
| JOB      | POST   | /services/scheduler/api/v1/job/trigger                                      | API to trigger job execution                            |
| JOB RUN  | GET    | /services/scheduler/api/v1/job/runs                                         | API to list the job for a project                       |
| JOB RUN  | POST   | /services/scheduler/api/v1/job/{job_id}/run                                 | API to create a job run                                 |
| JOB RUN  | GET    | /services/scheduler/api/v1/job/{job_id}/run/{run_id}/retry/{retry}/log      | API to download log                                     |
| PIPELINE | POST   | /services/scheduler/api/v1/job/pipeline                                     | API to create a pipeline                                |
| PIPELINE | PUT    | /services/scheduler/api/v1/job/pipeline/{job_id}                            | API to edit a pipeline                                  |
| OTHERS   | GET    | /services/scheduler/api/v1/others/flows                                     | API to pull list of flows associated with a project     |
| OTHERS   | GET    | /services/scheduler/api/v1/others/notebooks                                 | API to pull list of notebooks associated with a project |
