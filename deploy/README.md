## hackathon deployment instructions

### Overview
The steps for installing this hackathon environment are
- Deploy ODH 0.5.2 with JupyterHub, Spark and Kafka
- Deploy a postgresql database
- Install the ODH customization objects in this directory

### Deploy Open Data Hub
On OpenShift 4, ODH 0.5.2 is available via the operator catalog.
You can also perform a manual install by following these instructions:
- [ODH 0.5.2](https://gitlab.com/opendatahub/opendatahub-operator/-/blob/v0.5.2/docs/manual-installation.adoc)
- JupyterHub and Spark are enabled by selecting the corresponding `odh_deploy` attributes. You can use the CR `hackathon-odh-cr.yaml` in this directory in the manual instructions above.
- [ODH Kafka 0.5.2](https://gitlab.com/opendatahub/opendatahub-operator/-/blob/v0.5.2/docs/deploying-kafka.adoc)

### Deploying postgresql
Postgresql can be installed via the operator catalog on both OpenShift 3 and 4.
An ephemeral deployment is sufficient for this lab.
The hackathon deployment is not sensitive to the postgresql version.

### Deploying ODH custom objects
This hackathon assumes that the following files (in this directory) have also been installed using `oc apply -f`:
- `custom-spark-bc.yaml`
- `custom-spark-is.yaml`
- `spark-hackathon-notebook-bc.yaml`
- `spark-hackathon-notebook-is.yaml`
- `hackathon-singleuser-profiles-cm.yaml`

Check to verify that the build configurations above have run successfully. You may need to start the build configs manually in the console.

### Spark Cluster CR
The file `spark-cluster-hackathon-cm.yaml` will cause the Spark Operator to create a cluster if you deploy it, and it will tear down the spark cluster if you delete it. You can optionally use this to demonstrate the spark operator.
