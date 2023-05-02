# 17. Log monitoring

## Deploy loki into cluster 

![argo_loki](https://github.com/VitaliGet/sa.it-academy.by/raw/md-sa2-23-23/Vitali_Getmanovich/17.Log_monitoring/argo_loki.png)

## Create dashboard Grafana

![logs_5m](https://github.com/VitaliGet/sa.it-academy.by/raw/md-sa2-23-23/Vitali_Getmanovich/17.Log_monitoring/logs.5m.png)

![logs_1h](https://github.com/VitaliGet/sa.it-academy.by/raw/md-sa2-23-23/Vitali_Getmanovich/17.Log_monitoring/logs.1h.png)

![logs_1d](https://github.com/VitaliGet/sa.it-academy.by/raw/md-sa2-23-23/Vitali_Getmanovich/17.Log_monitoring/logs.1d.png)

## json-file
```json
{
  "annotations": {
    "list": [
      {
        "builtIn": 1,
        "datasource": {
          "type": "loki",
          "uid": "UB02JdE4z"
        },
        "enable": true,
        "hide": true,
        "iconColor": "rgba(0, 211, 255, 1)",
        "name": "Annotations & Alerts",
        "target": {
          "limit": 1000,
          "matchAny": false,
          "tags": [],
          "type": "dashboard"
        },
        "type": "dashboard"
      }
    ]
  },
  "description": "",
  "editable": true,
  "fiscalYearStartMonth": 0,
  "graphTooltip": 0,
  "id": 3,
  "links": [],
  "liveNow": false,
  "panels": [
    {
      "datasource": {
        "type": "loki",
        "uid": "UB02JdE4z"
      },
      "fieldConfig": {
        "defaults": {
          "color": {
            "mode": "thresholds"
          },
          "mappings": [],
          "thresholds": {
            "mode": "absolute",
            "steps": [
              {
                "color": "green",
                "value": null
              },
              {
                "color": "red",
                "value": 80
              }
            ]
          }
        },
        "overrides": []
      },
      "gridPos": {
        "h": 6,
        "w": 12,
        "x": 0,
        "y": 0
      },
      "id": 10,
      "options": {
        "orientation": "auto",
        "reduceOptions": {
          "calcs": [
            "lastNotNull"
          ],
          "fields": "",
          "values": false
        },
        "showThresholdLabels": false,
        "showThresholdMarkers": true
      },
      "pluginVersion": "9.4.7",
      "targets": [
        {
          "datasource": {
            "type": "loki",
            "uid": "UB02JdE4z"
          },
          "editorMode": "code",
          "expr": "count_over_time({pod=\"grafana-5f9f96b65b-2n7mf\"}[$time] |= \"error\")",
          "queryType": "range",
          "refId": "A"
        }
      ],
      "title": "grafana",
      "type": "gauge"
    },
    {
      "datasource": {
        "type": "loki",
        "uid": "UB02JdE4z"
      },
      "fieldConfig": {
        "defaults": {
          "color": {
            "mode": "thresholds"
          },
          "mappings": [],
          "thresholds": {
            "mode": "absolute",
            "steps": [
              {
                "color": "green",
                "value": null
              },
              {
                "color": "red",
                "value": 80
              }
            ]
          }
        },
        "overrides": []
      },
      "gridPos": {
        "h": 6,
        "w": 12,
        "x": 12,
        "y": 0
      },
      "id": 4,
      "options": {
        "orientation": "auto",
        "reduceOptions": {
          "calcs": [
            "lastNotNull"
          ],
          "fields": "",
          "values": false
        },
        "showThresholdLabels": false,
        "showThresholdMarkers": true
      },
      "pluginVersion": "9.4.7",
      "targets": [
        {
          "datasource": {
            "type": "loki",
            "uid": "UB02JdE4z"
          },
          "editorMode": "code",
          "expr": "count_over_time({pod=\"ingress-nginx-controller-7578879f9f-vh76j\"}[$time] |= \"error\")",
          "queryType": "range",
          "refId": "A"
        }
      ],
      "title": "Ingress",
      "type": "gauge"
    },
    {
      "datasource": {
        "type": "loki",
        "uid": "UB02JdE4z"
      },
      "fieldConfig": {
        "defaults": {
          "color": {
            "mode": "thresholds"
          },
          "mappings": [],
          "thresholds": {
            "mode": "absolute",
            "steps": [
              {
                "color": "green",
                "value": null
              },
              {
                "color": "red",
                "value": 80
              }
            ]
          }
        },
        "overrides": []
      },
      "gridPos": {
        "h": 6,
        "w": 12,
        "x": 0,
        "y": 6
      },
      "id": 8,
      "options": {
        "orientation": "auto",
        "reduceOptions": {
          "calcs": [
            "lastNotNull"
          ],
          "fields": "",
          "values": false
        },
        "showThresholdLabels": false,
        "showThresholdMarkers": true
      },
      "pluginVersion": "9.4.7",
      "targets": [
        {
          "datasource": {
            "type": "loki",
            "uid": "UB02JdE4z"
          },
          "editorMode": "code",
          "expr": "count_over_time({pod=\"argocd-server-58b85dcfcc-6lnj8\"}[$time] |= \"error\")",
          "queryType": "range",
          "refId": "A"
        }
      ],
      "title": "ArgoCD",
      "type": "gauge"
    }
  ],
  "refresh": "",
  "revision": 1,
  "schemaVersion": 38,
  "style": "dark",
  "tags": [],
  "templating": {
    "list": [
      {
        "current": {
          "selected": true,
          "text": "1d",
          "value": "1d"
        },
        "hide": 0,
        "includeAll": false,
        "label": "time",
        "multi": false,
        "name": "time",
        "options": [
          {
            "selected": false,
            "text": "5m",
            "value": "5m"
          },
          {
            "selected": false,
            "text": "1h",
            "value": "1h"
          },
          {
            "selected": true,
            "text": "1d",
            "value": "1d"
          }
        ],
        "query": "5m, 1h, 1d",
        "queryValue": "",
        "skipUrlSync": false,
        "type": "custom"
      }
    ]
  },
  "time": {
    "from": "now-6h",
    "to": "now"
  },
  "timepicker": {},
  "timezone": "",
  "title": "Logs",
  "uid": "UweyQpEVz",
  "version": 17,
  "weekStart": ""
}
```