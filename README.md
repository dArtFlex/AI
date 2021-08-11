# AI API for dartflex
## Version: 1.0.0

### /ping

#### GET
##### Summary

Send a ping to test the application

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | OK<br><br>**Example** (*status*):<br><pre>pong</pre> |

### /generate_image

#### POST
##### Summary

Generate new image

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| body | body | JSON parameters. | No |  |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | JSON response with base64 encoded 'image' and 'latent' fields. |

### /edit_image

#### POST
##### Summary

Generate new image based on existing one

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| body | body | JSON parameters. | No |  |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | JSON response with base64 encoded 'image' and 'latent' fields of new image |

### /child

#### POST
##### Summary

Generates a new image through random mutation of an existing one

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| body | body | JSON parameters. | No |  |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | JSON response with base64 encoded 'image' and 'latent' fields of new image |

### /crossbreed

#### POST
##### Summary

Generates a new image using a crossbreed of the existing two

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| body | body | JSON parameters. | No |  |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | JSON response with base64 encoded 'image' and 'latent' fields of new image |

### /project/upload

#### POST
##### Summary

Upload own image to get its projection for editing, creating children or crossbreeding

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| image | formData | The image file to upload. | No | file |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | JSON response with id of the long-running task and its current status |

### /project/result/{task_id}

#### GET
##### Summary

Get upload projection result by task_id

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | JSON response with id of the long-running task and its current status |
