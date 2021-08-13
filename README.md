# AI API for dartflex
## Version: 1.0.0

Current base_url: api.nft.inga.technology
  
[Project swagger](https://api.nft.inga.technology/apidocs/) 

### /ping

#### GET
##### Summary

Send a ping to test the application

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | OK<br><br>**Example**<br><pre>{"status": "pong"}</pre> |

### /style_transfer

#### POST
##### Summary

Upload style and content image to get mixed result

##### Parameters

| Name | Located in | Type | Description | Required |
| ---- | ---------- | ----------- | -------- | ---- |
| content_image | formData | file | The content image file with to upload | Yes |
| style_image | formData | file | The style image file with to upload | Yes |
| priority | query | integer | Task priority in queue from 0 (lowest priority) to 10 (highest). Default 0 | No |
| end_scale | query | integer | Scale result image to this resolution. Default 512 | No |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | JSON response with 'task_id', 'status' and 'result' of new long-running task<br><br>**Example**<br><pre>{"result": null, "status": "PENDING", "task_id": "cb21d88f-0a28-4cc1-b0dc-a42b12aa8d17"}</pre> |

### /style_transfer/result/<task_id>/status_only

#### GET
##### Summary

Get status of result by task_id

##### Parameters

| Name | Located in | Type | Description | Required |
| ---- | ---------- | ----------- | -------- | ---- |
| task_id | path | string | The task ID | Yes |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | JSON response with 'task_id' and 'status' of this long-running task<br><br>**Example**<br><pre>{"status": "PENDING", "task_id": "cb21d88f-0a28-4cc1-b0dc-a42b12aa8d17"}</pre> |

### /style_transfer/result/<task_id>/image_only

#### GET
##### Summary

Generates a new image through random mutation of an existing one

##### Parameters

| Name | Located in | Type | Description | Required |
| ---- | ---------- | ----------- | -------- | ---- |
| task_id | path | string | The task ID | Yes |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | "image/jpeg" message of jpeg image file  |
| 404 | Empty response if image result is not ready or error has been occurred |
