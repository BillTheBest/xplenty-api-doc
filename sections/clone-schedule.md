## Clone schedule

### Description
This call clones the given schedule.


A successful call returns the following details for the schedule after the changes.

* **id** the numeric schedule ID
* **name** the name given to the schedule upon creation
* **description** the description given to the schedule upon creation
* **owner_id** the numeric user id of the package owner
* **status** the schdule's status. Possible values are:
    * **enabled**
    * **disabled**
* **start_at** the date and time when the schedule should start executing
* **next_run_at** the date and time the schedule's task will run next time
* **interval_amount** number of interval units between schedule's task executions
* **interval_unit** Possible values are:
    * **minutes**
    * **hours**
    * **days**
    * **weeks**
    * **months**
    * **years**
* **task**
* **last_run_at** the date and time when schedule's task run last time
* **last_run_status** status of the execution of the schedule's task
* **execution_count** number of times the schedule has ran
* **created_at** the date and time the schedule was created
* **updated_at** the date and time the schedule was updated
* **url** the schedule resource ID

### Input Parameters

| Name | Required? | Default | Description                          |
| ---- | --------- | ------- | -----------                          |
| id   | Y         | blank   | id of the schedule you want to clone |

### Request (Curl Call) Syntax
```shell
curl -X POST -H "Accept: application/vnd.xplenty+json" -u <APIkey>: "https://api.xplenty.com/<accountID>/api/schedules/<scheduleID>/clone"
```

### Response Example
```json
{
  "created_at": "2014-09-25T08:48:51Z",
  "day_of_week": null,
  "description": "dsada",
  "end_at": "2014-09-25T10:45:00Z",
  "execution_count": 0,
  "id": 2,
  "interval_amount": 34,
  "interval_unit": "days",
  "last_run_at": null,
  "last_run_status": null,
  "name": "Untitled",
  "next_run_at": "2014-12-02T08:33:00Z",
  "owner_id": 1,
  "recurrence_count": 2,
  "repeat_by": null,
  "start_at": "2014-09-25T08:33:00Z",
  "status": "enabled",
  "task": {
    "nodes": 3,
    "jobs": [
      {
        "job_id": "1",
        "variables": {
          "_MAX_COMBINED_SPLIT_SIZE": "67108864",
          "_BYTES_PER_REDUCER": "209715200",
          "_LINE_RECORD_READER_MAX_LENGTH": "1024000",
          "_DEFAULT_TIMEZONE": "+00:00",
          "_DEFAULT_PARALLELISM": "0",
          "_SHUFFLE_INPUT_BUFFER_PERCENT": "0.7"
        }
      }
    ],
    "reuse_cluster": true,
    "terminate_on_idle": true,
    "time_to_idle": 60
  },
  "updated_at": "2014-10-29T14:22:05Z",
  "url": "https://api.xplenty.com/xplenation/api/schedules/2"
}
```
