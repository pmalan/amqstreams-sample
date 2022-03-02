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
_
Note the __strimzi.io/use-connector-resources: 'true'__ _ to indicate an image should be build, with the specified resources in __build:__ and __plugins__ 
_

We are using the Red Hat supported connectors.
### 4. Connector
#### 4.1 MySQL
#### 4.2 Oracle
