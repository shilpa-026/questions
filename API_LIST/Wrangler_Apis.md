| API      | TYPE   | Link                                                                                  | Description                                           |
|----------|--------|---------------------------------------------------------------------------------------|-------------------------------------------------------|
| WRANGLER | GET    | /services/wrangler/api/v1/config/{project_name}-{project_id}/wrangler_dag             | Get all Wrangler flow Config by project               |
| WRANGLER | POST   | /services/wrangler/api/v1/flow/run                                                    | Run Wrangler Flow                                     |
| WRANGLER | POST   | /services/wrangler/api/v1/config                                                      | Save Wrangler Flow                                    |
| WRANGLER | POST   | /services/wrangler/api/v1/config                                                      | Save Wrangler Flow                                    |
| WRANGLER | DELETE | /services/wrangler/api/v1/config/{project_name}-{project_id}/wrangler_dag/{configkey} | Delete Wrangler Flow                                  |
| WRANGLER | POST   | /services/wrangler/api/v1/flow/summary                                                | Summary Wrangler Flow with Run                        |
| WRANGLER | POST   | /services/wrangler/api/v1/flow/run                                                    | Run Wrangler Flow(TD)                                 |
| WRANGLER | POST   | /services/wrangler/api/v1/flow/publish?runtime=python                                 | Wrangler Flow with Publish (TD)                       |
| WRANGLER | POST   | /services/wrangler/api/v1/flow/summary                                                | Summary Wrangler Flow with Run with refresh and limit |
| WRANGLER | POST   | /services/wrangler/api/v1/flow/run?limit=500&plimit=500&pos=first&refresh=0           | Wrangler Flow with Run (GBIIO McQueen)                |
| WRANGLER | POST   | /services/wrangler/api/v1/flow/run?limit=5000&plimit=500&pos=first&refresh=0          | Wrangler Flow with Run (GBIIO McQueen → TD)           |
| WRANGLER | POST   | /services/wrangler/api/v1/flow/publish?runtime=python                                 | Wrangler Flow with Publish (GBIIO McQueen → TD)       |
| WRANGLER | POST   | /services/wrangler/api/v1/flow/publish?runtime=python                                 | Wrangler Flow with Publish (TD -> GBIIO McQueen)      |
| WRANGLER | POST   | /services/wrangler/api/v1/flow/run?limit=5000&plimit=500&pos=first&refresh=0          | Wrangler flow Run with Random data                    |
| WRANGLER | POST   | /services/wrangler/api/v1/flow/publish?runtime=python                                 | Publish (Random Data)                                 |
| WRANGLER | POST   | /services/wrangler/api/v1/flow/run?limit=5000&plimit=500&pos=first&refresh=0          | Wrangler Flow Run with lambda fx                      |
| WRANGLER | POST   | /services/wrangler/api/v1/flow/publish?runtime=python                                 | Wrangler Flow with Publish lambda fx                  |
| WRANGLER | POST   | /services/wrangler/api/v1/recipe/notebook                                             | API to open wrangler flow notebook                    |
| WRANGLER | POST   | /services/wrangler/api/v1/flow/graph?runtimes                                         | Import wrangler recipe to flows                       |
| WRANGLER | POST   | /services/wrangler/api/v1/flow/publish?runtime=python                                 | publish wrangler recipe in python mode                |
| WRANGLER | POST   | /services/wrangler/api/v1/flow/publish?runtime=spark                                  | publish wrangler recipe in spark mode                 |
| WRANGLER | POST   | /services/wrangler/api/v1/recipe/notebook                                             | API to open wrangler flow python notebook             |
| WRANGLER | POST   | /services/wrangler/api/v1/recipe/correlation                                          | Correlation                                           |
| WRANGLER | POST   | /services/wrangler/api/v1/recipe/features_importance?target_column=B0                 | features_importance                                   |
