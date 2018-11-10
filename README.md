# Emoncms Helm Chart

This repository contains a Kubernetes chart to deploy a private Emoncms server.

## Prerequisites Details

* PV support on underlying infrastructure (if persistence is required)

## Chart Details

This chart will do the following:

* Implement an Emoncms deployment

## Installing the Chart

To install the chart, use the following:

```console
git clone https://github.com/jutonz/emoncms-helm
cd emoncms-helm
helm install --name emoncms --namespace emoncms .
```

## Configuration

The following table lists the configurable parameters of the emoncms chart and
their default values.

| Parameter                       | Description                                          | Default                | 
| :-------------------------      | :----------------------------------------------      | :----------------      | 
| `db.mysqlDatabase`              | Name of the database to use                          | `emoncms`              | 
| `db.mysqlUser`                  | Name of the mysql user you want                      | `emoncms`              | 
| `db.mysqlPassword`              | Password for mysqlUser                               | `YOUR_SECURE_PASSWORD` | 
| `db.mysqlRandomRootPassword`    | Randomize the root password for the mysql container  | `true`                 | 
| `db.redisEnabled`               | Use redis as a temporary cache to decrease db writes | `true`                 | 
| `ingress.enabled`               | Expose the deployment with an ingress                | `false`                | 
| `ingress.hosts`                 | The domain on which the app will be exposed          | `emoncms.org`          | 
| `persistence.enabled`           | Whether to store data on volumes outside images      | `false`                | 
| `persistence.storageClassName`  | Custom storage class name                            | `false`                | 
| `persistence.dbSize`            | How large to make the volume for mysql               | `10Gi`                 | 
| `persistence.phpfiwaSize`       | How large to make the volume for phpfiwa             | `10Gi`                 | 
| `persistence.phpfinaSize`       | How large to make the volume for phpfina             | `10Gi`                 | 
| `persistence.phptimeseriesSize` | How large to make the volume for phptimeseries       | `10Gi`                 | 
| `persistence.redisSize`         | How large to make the volume for redis               | `100Mi`                | 

Specify each parameter using the `--set key=value[,key=value]` argument to
`helm install`.
