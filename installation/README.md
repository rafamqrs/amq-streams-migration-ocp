## Installation of AMQ Stream on OCP 3 and OCP 4
At the moment i'm writing this README.md the supported version for AMQ Streams running on OCP3 is 1.6.x

### Starting the installation on OCP3
1. Download the AMQ Stream from the Red Hat.
https://access.redhat.com/jbossnetwork/restricted/listSoftware.html?downloadType=distributions&product=jboss.amq.streams
2. Unzip the package.
3. Edit the AMQ Streams installation files to use the namespace the Cluster Operator is going to be installed into.
```console
	sed -i 's/namespace: .*/namespace: my-cluster-operator-namespace/' install/cluster-operator/*RoleBinding*.yaml
```
4. Install the operator
```console
	oc apply -f install/cluster-operator -n my-cluster-operator-namespace
```
5. Create a Kafka Cluster persistent.
```console
	oc apply -f examples/kafka/kafka-persistent.yaml
```

### Starting the installation on OCP4
1. Installation from Operator Hub

