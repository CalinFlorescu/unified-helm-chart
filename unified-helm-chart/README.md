# service-templates

![Version: 0.3.24](https://img.shields.io/badge/Version-0.3.24-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 1.16.0](https://img.shields.io/badge/AppVersion-1.16.0-informational?style=flat-square)

Helm chart that contains all the required templates for Haiilo services

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| config | object | `{"binaryData":null,"data":null,"immutable":false,"test_enabled":false}` | Object that configures config map instance |
| config.binaryData | string | `nil` | Config map binary data |
| config.data | string | `nil` | Config map data |
| config.immutable | bool | `false` | decide if the data is immutable or not |
| config.test_enabled | bool | `false` | Variable used for testing purposes |
| database | object | `{"availabilityType":"","backup":{},"credentialsSecret":"","flags":[],"instanceResources":{"cpu":2,"memory":7680},"maxResize":0,"maxSize":0,"namespace":"","region":"","test_enabled":false}` | Object that configures a cloud sql instance |
| database.availabilityType | string | `""` | Sql instance availability type |
| database.backup | object | `{}` | This object configures a backup behaviour for the SQL instance |
| database.credentialsSecret | string | `""` | Name of the secret in which the connection credentials will be stored |
| database.flags | list | `[]` | List of database flags that can be added |
| database.instanceResources | object | `{"cpu":2,"memory":7680}` | Specify CPU and Memory resources for the sql instances |
| database.instanceResources.cpu | int | `2` | Specify CPU resource for the sql instances |
| database.instanceResources.memory | int | `7680` | Specify Memory resource for the sql instances |
| database.maxResize | int | `0` | Storage limit to which the sql instance will scale in GB |
| database.maxSize | int | `0` | Maximum disk size for sql instance in GB |
| database.namespace | string | `""` | Namespace in which the sql instance object will be created |
| database.region | string | `""` | Region in which the sql instance will be created |
| database.test_enabled | bool | `false` | Variable used for testing purposes |
| deployment | object | `{"affinity":null,"containers":[],"gcpEnvVars":[],"image":{"pullPolicy":null,"repository":"","tag":""},"imagePullSecrets":null,"initContainers":[],"livenessProbe":{},"maxUnavailablePods":null,"minReadySeconds":null,"nodeSelector":null,"podAnnotations":null,"podSecurityContext":null,"readinessProbe":{},"replicaCount":null,"resources":{"limits":{"cpu":null,"memory":null},"requests":{"cpu":null,"memory":null}},"serviceAccountName":null,"skipSyncConfigs":true,"skipSyncSecrets":true,"strategy":null,"terminationGracePeriod":null,"test_enabled":false,"tolerations":[],"topologySpreadConstraints":[],"volumes":null}` | Object that configures Deployment instance |
| deployment.affinity | string | `nil` | Specify node affinity |
| deployment.containers | list | `[]` | List of containers that should be created in the pod |
| deployment.gcpEnvVars | list | `[]` | Define env vars for gcp cloud (they are going to be merged with the default ones defined under container args) |
| deployment.image | object | `{"pullPolicy":null,"repository":"","tag":""}` | Override default container image format |
| deployment.image.pullPolicy | string | `nil` | Variable used to control when the image should be fetched |
| deployment.image.repository | string | `""` | Image repository |
| deployment.image.tag | string | `""` | Image tag |
| deployment.imagePullSecrets | string | `nil` | Image pull secrets |
| deployment.initContainers | list | `[]` | List of init containers that should be created |
| deployment.livenessProbe | object | `{}` | Definition of the liveness probe |
| deployment.maxUnavailablePods | string | `nil` | Specify maximum umber of allowed unavailable pods |
| deployment.minReadySeconds | string | `nil` | Define minimum number of seconds for which the pod should be running without crushing before being considered healthy |
| deployment.nodeSelector | string | `nil` | Specify node selector |
| deployment.podAnnotations | string | `nil` | Pod annotations |
| deployment.podSecurityContext | string | `nil` | Security context in which the pod should run |
| deployment.readinessProbe | object | `{}` | Definition of the readiness probe |
| deployment.replicaCount | string | `nil` | Number of replicas that will be created |
| deployment.resources | object | `{"limits":{"cpu":null,"memory":null},"requests":{"cpu":null,"memory":null}}` | Configure container's resource request and limits |
| deployment.resources.limits | object | `{"cpu":null,"memory":null}` | Defines a hard ceiling on resource use |
| deployment.resources.limits.cpu | string | `nil` | Defines a hard ceiling on how much CPU time that the container can use |
| deployment.resources.limits.memory | string | `nil` | Defines a hard ceiling on how much Memory time that the container can use |
| deployment.resources.requests | object | `{"cpu":null,"memory":null}` | Resources that the container is guaranteed to get |
| deployment.resources.requests.cpu | string | `nil` | CPU that the container is guaranteed to get |
| deployment.resources.requests.memory | string | `nil` | Memory that the container is guaranteed to get |
| deployment.serviceAccountName | string | `nil` | SA name that the pod should use |
| deployment.skipSyncConfigs | bool | `true` | Decide if the pods should be restarted if you have configs used as env vars and they are updated |
| deployment.skipSyncSecrets | bool | `true` | Decide if the pods should not be restarted if you have secrets used as env vars and they are updated |
| deployment.strategy | string | `nil` | Update strategy |
| deployment.terminationGracePeriod | string | `nil` | Specify termination grace period |
| deployment.test_enabled | bool | `false` | Variable used for testing purposes |
| deployment.tolerations | list | `[]` | Sepcify node tolerations |
| deployment.topologySpreadConstraints | list | `[]` | Define topology spread constraints that will be applied |
| deployment.volumes | string | `nil` | Define volumes to be attached to the pods (https://kubernetes.io/docs/concepts/storage/volumes/) |
| fullnameOverride | string | `"service-template"` | Used to generate labels and names |
| grafanaDashboards | object | `{"folderName":"","path":"","test_enabled":false}` | Onject that configures grafana dashboards |
| grafanaDashboards.folderName | string | `""` | Custom name for the Grafana folder |
| grafanaDashboards.path | string | `""` | Path to the folder containing the dashboards |
| grafanaDashboards.test_enabled | bool | `false` | Variable used for testing purposes |
| ingress | object | `{"annotations":{},"hosts":[],"isOtc":false,"test_enabled":false,"tls":[]}` | Object that configures Ingress instance |
| ingress.annotations | object | `{}` | Specify custom annotations |
| ingress.hosts | list | `[]` | Specify hosts that ingress should match |
| ingress.isOtc | bool | `false` | Differentiate between OTC and GCP implementations |
| ingress.test_enabled | bool | `false` | Variable used for testing purposes |
| ingress.tls | list | `[]` | Define tls configurations |
| mongodb | object | `{"arbiters":null,"authenticationModes":[],"dataStorage":{"size":null},"exporter":{"annotations":null,"deployment":{"affinity":{},"annotations":{},"env":{},"extraArgs":[],"imagePullSecrets":null,"livenessProbe":{},"nodeSelector":{},"podAnnotations":{},"port":"9216","priorityClassName":null,"readinessProbe":{},"replicas":null,"resources":{"limits":{"cpu":"20m","memory":"128Mi"},"requests":{"cpu":"20m","memory":"128Mi"}},"securityContext":{},"tolerations":{},"volumeMounts":{},"volumes":{}},"enabled":true,"existingSecret":null,"existingSecretKey":null,"service":{"name":null,"port":null,"type":null},"serviceMonitor":{"enabled":true,"interval":null,"metricRelabelings":{},"namespace":null,"scheme":null,"scrapeTimeout":null,"targetLabels":{},"tlsConfig":{}}},"logStorage":{"size":null},"members":null,"name":null,"resources":{},"statefulSet":{"affinity":{},"containers":[],"serviceAccount":null,"storageClass":null,"tolerations":{},"topologySpreadConstraints":[],"volumeClaimTemplates":[]},"test_enabled":false,"users":[],"version":null}` | Object that configures mongodb operator |
| mongodb.arbiters | string | `nil` | List of arbiters |
| mongodb.authenticationModes | list | `[]` | List of ways to authenticate to the db |
| mongodb.dataStorage | object | `{"size":null}` | Override default data-volume size |
| mongodb.exporter | object | `{"annotations":null,"deployment":{"affinity":{},"annotations":{},"env":{},"extraArgs":[],"imagePullSecrets":null,"livenessProbe":{},"nodeSelector":{},"podAnnotations":{},"port":"9216","priorityClassName":null,"readinessProbe":{},"replicas":null,"resources":{"limits":{"cpu":"20m","memory":"128Mi"},"requests":{"cpu":"20m","memory":"128Mi"}},"securityContext":{},"tolerations":{},"volumeMounts":{},"volumes":{}},"enabled":true,"existingSecret":null,"existingSecretKey":null,"service":{"name":null,"port":null,"type":null},"serviceMonitor":{"enabled":true,"interval":null,"metricRelabelings":{},"namespace":null,"scheme":null,"scrapeTimeout":null,"targetLabels":{},"tlsConfig":{}}}` | Configure exporter |
| mongodb.exporter.annotations | string | `nil` | Add exporter annotations |
| mongodb.exporter.deployment | object | `{"affinity":{},"annotations":{},"env":{},"extraArgs":[],"imagePullSecrets":null,"livenessProbe":{},"nodeSelector":{},"podAnnotations":{},"port":"9216","priorityClassName":null,"readinessProbe":{},"replicas":null,"resources":{"limits":{"cpu":"20m","memory":"128Mi"},"requests":{"cpu":"20m","memory":"128Mi"}},"securityContext":{},"tolerations":{},"volumeMounts":{},"volumes":{}}` | Configure Exporter deployment |
| mongodb.exporter.enabled | bool | `true` | Enable exporter creation |
| mongodb.exporter.existingSecret | string | `nil` | Configure exporter secret to source data from |
| mongodb.exporter.existingSecretKey | string | `nil` | Configure exporter secret key to source data from |
| mongodb.exporter.service | object | `{"name":null,"port":null,"type":null}` | Configure Exporter Service |
| mongodb.exporter.service.name | string | `nil` | Configure Exporter Service Name |
| mongodb.exporter.service.port | string | `nil` | Configure Exporter Service Port |
| mongodb.exporter.service.type | string | `nil` | Configure Exporter Service Type |
| mongodb.exporter.serviceMonitor | object | `{"enabled":true,"interval":null,"metricRelabelings":{},"namespace":null,"scheme":null,"scrapeTimeout":null,"targetLabels":{},"tlsConfig":{}}` | Configure Exporter Service Monitor |
| mongodb.logStorage | object | `{"size":null}` | Verride default log-volume size |
| mongodb.members | string | `nil` | List of members |
| mongodb.name | string | `nil` | Override default instance name |
| mongodb.resources | object | `{}` | Configure container resources |
| mongodb.statefulSet | object | `{"affinity":{},"containers":[],"serviceAccount":null,"storageClass":null,"tolerations":{},"topologySpreadConstraints":[],"volumeClaimTemplates":[]}` | Stateful set configuration object (optional) |
| mongodb.statefulSet.affinity | object | `{}` | Affinity settings for mongodb object |
| mongodb.statefulSet.containers | list | `[]` | List of containers that should run in the pods |
| mongodb.statefulSet.serviceAccount | string | `nil` | Service account to be used by the mongodb object |
| mongodb.statefulSet.storageClass | string | `nil` | Storage class |
| mongodb.statefulSet.tolerations | object | `{}` | Tolerations for mongodb operator containers |
| mongodb.statefulSet.topologySpreadConstraints | list | `[]` | Topology Spread Constraints |
| mongodb.statefulSet.volumeClaimTemplates | list | `[]` | Volume claim templates |
| mongodb.users | list | `[]` | Db users |
| mongodb.version | string | `nil` | Database version |
| repository | string | `"service-templates"` | Used to generate container images |
| roleBinding | object | `{"roleName":null,"roleType":null,"subjects":[],"test_enabled":false}` | Object that configures Role Binding instance |
| roleBinding.roleName | string | `nil` | Name of the role that is going to be binded to subjects |
| roleBinding.roleType | string | `nil` | Type of the role to be attached (Role or ClusterRole) |
| roleBinding.subjects | list | `[]` | List of subjects that will be provided with the role |
| roleBinding.test_enabled | bool | `false` | Variable used for testing purposes |
| scaler | object | `{"advanced":{},"cooldownPeriod":null,"fallback":{},"k8sTriggers":[],"maxReplicas":null,"minReplicas":null,"pollingInterval":null,"prometheusTriggers":[],"targetResource":{},"test_enabled":false}` | Object that configures a Keda Autoscaler instance |
| scaler.advanced | object | `{}` | Advanced configurations for the scaler |
| scaler.cooldownPeriod | string | `nil` | The period to wait after the last trigger reported active before scaling the resource back to 0 |
| scaler.fallback | object | `{}` | Fallback values for the scaler |
| scaler.maxReplicas | string | `nil` | The maximum number of replicas that the targeted resource can have |
| scaler.minReplicas | string | `nil` | The minimum number of replicas that the targeted resource should have |
| scaler.pollingInterval | string | `nil` | This is the interval to check each trigger on |
| scaler.prometheusTriggers | list | `[]` | Custom trigger definitions for the targeted object |
| scaler.targetResource | object | `{}` | Data about the target resource that should be scaled |
| scaler.test_enabled | bool | `false` | Variable used for testing purposes |
| secret | object | `{"data":null,"stringData":null,"test_enabled":false,"type":"Opaque"}` | Object that configures Secret instance |
| secret.data | string | `nil` | Contains the secret data |
| secret.stringData | string | `nil` | StringData allows specifying non-binary secret data in string form |
| secret.test_enabled | bool | `false` | Variable used for testing purposes |
| secret.type | string | `"Opaque"` | Secret type (https://kubernetes.io/docs/concepts/configuration/secret/#secret-types) |
| service | object | `{"ports":[],"test_enabled":false,"type":null}` | Object that configures Service instance |
| service.ports | list | `[]` | List of ports exposed by the service |
| service.test_enabled | bool | `false` | Variable used for testing purposes |
| service.type | string | `nil` | Type of the service |
| serviceAccount | object | `{"annotations":null,"test_enabled":false}` | Object that configures Service Account instance |
| serviceAccount.annotations | string | `nil` | Service Account annotations |
| serviceAccount.test_enabled | bool | `false` | Variable used for testing purposes |
| storage | object | `{"acl":[],"backup":{"enabled":false,"ransomStartDate":[],"startDate":[]},"cors":{},"location":"","name":"","namespace":"","test_enabled":false,"versioning":false}` | Object that configures a cloud storage instance |
| storage.acl | list | `[]` | Object that configures user permission to the bucket |
| storage.backup | object | `{"enabled":false,"ransomStartDate":[],"startDate":[]}` | Config backup behaviour for bucket |
| storage.backup.enabled | bool | `false` | Decide if the backups should be enabled or not |
| storage.backup.ransomStartDate | list | `[]` | Set backups interval for ransomware package |
| storage.backup.startDate | list | `[]` | Set backups interval |
| storage.cors | object | `{}` | Object that configures cors access to the created bucket |
| storage.location | string | `""` | GCP location in which the Bucket will be created |
| storage.name | string | `""` | Bucket name |
| storage.namespace | string | `""` | Namespace in which the bucket object will be created |
| storage.test_enabled | bool | `false` | Variable used for testing purposes |
| storage.versioning | bool | `false` | Decide if the versioning should be enabled or not for the bucket |

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.11.0](https://github.com/norwoodj/helm-docs/releases/v1.11.0)
