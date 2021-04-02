| | | | |
|-|-|-|-|
|API|TYPE|Link|Description|
|CONDA|GET |/services/notebooks/api/v1/conda/search/{package_name}|API to search libraries in conda|
|CONDA|GET |/services/notebooks/api/v1/conda/version/{package_name}|API to search version of packages in conda|
|DOCKER IMAGE|GET|/services/notebooks/api/v1/docker-images|Endpoint to list the docker images|
|DOCKER IMAGE|POST|/services/notebooks/api/v1/docker-images|API to create a docker image|
|DOCKER IMAGE|GET|/services/notebooks/api/v1/docker-images/status/{docker_image_id}|Endpoint to check status of a docker image|
|DOCKER IMAGE|DELETE|/services/notebooks/api/v1/docker-images/{docker_image_id}|Endpoint to delete a docker image|
|DOCKER IMAGE|GET|/services/notebooks/api/v1/docker-images/{docker_image_id}|Endpoint to read a docker image|
|DOCKER IMAGE|PUT|/services/notebooks/api/v1/docker-images/{docker_image_id}|Endpoint to update the docker image|
|NOTEBOOK|GET|/services/notebooks/api/v1/notebooks|API to list the notebooks|
|NOTEBOOK|POST|/services/notebooks/api/v1/notebooks|API to create a notebook|
|NOTEBOOK|GET|/services/notebooks/api/v1/notebooks/running|API to fetch the list of running notebooks|
|NOTEBOOK|DELETE|/services/notebooks/api/v1/notebooks/sync|API to delete notebook metadata form Jupyter Lab|
|NOTEBOOK|POST|/services/notebooks/api/v1/notebooks/sync|API to create notebook metadata from Jupyter Lab|
|NOTEBOOK|PUT|/services/notebooks/api/v1/notebooks/sync|API to rename the notebook|
|NOTEBOOK|PATCH|/services/notebooks/api/v1/notebooks/timestamp|API to update the timestamp of notebook|
|NOTEBOOK|PUT|/services/notebooks/api/v1/notebooks/update/content/{notebook_name}|API to update the given notebook|
|NOTEBOOK|POST|/services/notebooks/api/v1/notebooks/upload|API to upload a notebook|
|NOTEBOOK|DELETE|/services/notebooks/api/v1/notebooks/{notebook_id}|API to delete a notebook by id|
|NOTEBOOK|GET|/services/notebooks/api/v1/notebooks/{notebook_id}|API to read the give notebook|
|NOTEBOOK|PUT|/services/notebooks/api/v1/notebooks/{notebook_id}|API to update the given notebook|
|NOTEBOOK|GET|/services/notebooks/api/v1/notebooks/{notebook_id}/splunk|Endpoint to fetch the splunk log url for notebook|
|NOTEBOOK|POST|/services/notebooks/api/v1/notebooks/{notebook_id}/start|API to start the given notebook by id|
|NOTEBOOK|DELETE|/services/notebooks/api/v1/notebooks/{notebook_id}/stop|Endpoint to stop notebook by id|
|NOTEBOOK|GET|/services/notebooks/api/v1/notebooks/{project_name}/{project_id}/{notebook_id}/history|Endpoint to fetch the history url for notebook|
|NOTEBOOK|GET|/services/notebooks/api/v1/notebooks/{project}/{project_id}/tree/|Endpoint to fetch folder structure from git|
|NOTEBOOK|GET|/services/notebooks/api/v1/notebooks/{project}/{project_id}/tree/{path}|Endpoint to fetch folder structure from git|
|PYPI|GET|/services/notebooks/api/v1/pypi/search/{package_name}|API to search libraries in pypi|
|PYPI|GET|/services/notebooks/api/v1/pypi/version/{package_name}|API to search version of packages in pypi|
