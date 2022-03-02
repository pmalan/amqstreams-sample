# amqstreams-sample

## AMQ Stream sample for Openshift with custom certificate and storage.

Red Hat Integration - AMQ Streams - Version 2.0.1-0  

Prerequisites:

* Namespace: amq-streams
* Storage Class configured

### 1. Operator Subscription

__amq-streams-subscription.yaml__

Register the AMQ Streams operator in a specific namespace, in this case amq-streams. 

_It is not required to install AMQ Streams operator into a specific namspace, but it gives you the flexibility to use multiple versions, if required, within the cluster, when operator is targeted at specific namespace._

### 2. AMQ Streams CRD
### 3. Kafka Connect
*Note the annotation *__strimzi.io/use-connector-resources: 'true'__ * indicates that we are going to use connector custom resources to define the connection details. The other way is to post a configuration JSON to connector. 

We are using the Red Hat supported connectors. Since we need the Oracle JDBC drivers, that is included from external Maven repository.
### 4. Kafka Connector
__amq-oracle-kafka-connector.yaml__ and __amq-mysql-coonector.yaml__

The label _strimzi.io/cluster: west-cluster-connect-cluster-2_ connects it to the Kafka connect instance as specified in the connect name - _name: west-cluster-connect-cluster-2_.

_class: _ specifies the connector implementation class, in case you want to use own implementation.
_tasksMax: 1_ specifies the threads you want to allocate.

#### 4.1 MySQL
#### 4.2 Oracle
__amq-oracle-kafka-connector.yaml__

