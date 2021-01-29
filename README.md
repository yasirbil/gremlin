# Gremlin Helm Charts

This repository hosts the official **Gremlin Helm Charts** to deploy **Gremlin** products to [Kubernetes](https://kubernetes.io/)

## Install Helm

Get the latest [Helm release](https://github.com/kubernetes/helm#install).

## Install Charts

Pre-requisites
Description: Gremlin is a test tool for performance testing in stage environment
Navigate to Gremlin.com and set up a new account
Create a team
Get team ID and generate Secret ID
Navigate to your GCP and create a new cluster with only two nodes. (Free version only allows two nodes. More than two nodes will be charged by Gremlin.)
In your new cluster terminal generate kube-config
Create gremlin namespace 
```kubectl namespace -n gremlin```
```git clone git@github.com:yasirbil/gremlin.git```
```cd /gremlin```
Run this command:

```
helm install gremlin \
    --namespace gremlin \
    --set gremlin.secret.managed=true \
    --set gremlin.secret.type=secret \
    --set gremlin.secret.teamID=YOUR-TEAM-ID \
    --set gremlin.secret.clusterID=YOUR-PROJECT-ID \
    --set gremlin.secret.teamSecret=YOUR-TEAM-SECRET .
```

For more detailed instructions, see the chart's documentation [here](https://github.com/gremlin/helm/blob/master/gremlin/README.md).

## Reporting Issues



Please report all issues via github issues [here](https://github.com/gremlin/helm/issues).
