# Indexupdater

## First install and update in an Openshift Environment

All necessary components of the application are configured in the template indexupdater.yaml
Set environment and desired version of the image for test,integration and production environment
```
oc process -p env=test -p version=latest -p CPU_LIMIT="0" -p CPU_REQUEST="0" -p MEMORY_LIMIT="0" -p MEMORY_REQUEST="0" -f indexupdater.yaml  | oc apply -f-
oc process -p env=integration -p version=22 -p CPU_LIMIT="800m" -p CPU_REQUEST="20m" -p MEMORY_LIMIT="500Mi" -p MEMORY_REQUEST="250Mi" -f indexupdater.yaml  | oc apply -f-
oc process -p env=production -p version=22 -p CPU_LIMIT="800m" -p CPU_REQUEST="20m" -p MEMORY_LIMIT="500Mi" -p MEMORY_REQUEST="500Mi" -f indexupdater.yaml  | oc apply -f-
```

