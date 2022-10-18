# Deployment Script

Post-merge, edit prod files as follows.

## Repoint Dev datasources to Prod

ActionsApp/Connections/Connections.json

Change this:
```JSON
"datasets": {
      "https://apacheixdev.sharepoint.com/sites/PowerPlatformDevelopmentTEST": {
        "dataSources": {
          "Actions": {
            "tableName": "5a9f794d-c663-4fa5-9859-4a437ccde392"
          },
          "People": {
            "tableName": "77c0b1a5-69d0-493d-be8c-0c8b07825f93"
          },
          "Projects": {
            "tableName": "f0ca4540-a97d-444a-aa82-aef990d6cf46"
          }
        }
      }
    },
```
To this:
```JSON
"datasets": {
      "https://apacheix.sharepoint.com/sites/everyone": {
        "dataSources": {
          "Actions": {
            "tableName": "a71708ca-51bc-46e5-b58a-3dbbbb3dbcbe"
          },
          "People": {
            "tableName": "2dbf9551-a7b3-4fec-9b3d-a6b71266bd16"
          },
          "Projects": {
            "tableName": "99b01ea7-77ec-4565-9b19-8975e7c473f6"
          }
        }
      },
```


## Update the Release Type

Update ActionsApp/Src/App.fx.yaml

From:
```
APP_RELEASE = { Type: "Dev", Release: 0, Fix: 0 };
```
To:
```
APP_RELEASE = { Type: "Prod", Release: 0, Fix: 0 };
```
