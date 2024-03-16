### Retrieve Kafka Cluster Bootstrap Server Address

To fetch the external bootstrap server address of your Kafka cluster, use the following command:

```sh
kubectl get kafka kafka-cluster -o=jsonpath='{.status.listeners[?(@.type=="external")].bootstrapServers}{"\n"}'
```

### SSL Cluster Configuration: Creating Truststore and Keystore

Secure your Kafka cluster communications by creating a truststore and keystore. Execute the commands below to generate the necessary certificates and passwords:

```sh
# Extract and save the Cluster CA certificate and password
kubectl get secret kafka-cluster-cluster-ca-cert -o jsonpath='{.data.ca\.p12}' | base64 -d > ca.p12
kubectl get secret kafka-cluster-cluster-ca-cert -o jsonpath='{.data.ca\.password}' | base64 -d > ca.password

# Extract and save the user certificate and password
kubectl get secret super-user -o jsonpath='{.data.user\.p12}' | base64 -d > user.p12
kubectl get secret super-user -o jsonpath='{.data.user\.password}' | base64 -d > user.password
```

### Essential Kafka Management Commands

Manage your Kafka resources efficiently with these essential commands:

```sh
# Display Kafka cluster resources
oc get kafka
oc get kafkatopic
oc get kafkauser
oc get kafka kafka-cluster -o yaml

# Delete an existing Kafka cluster
oc delete kafka kafka-cluster
```

