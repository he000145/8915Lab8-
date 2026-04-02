# CST8915 Lab 8 Submission

## 1. YouTube Demo Video Link

🎥 [Watch Demo Video](https://youtu.be/NExBehF6808)

## 2. Written Explanation of Task 2

For Task 2, I updated the original deployment to make MongoDB and RabbitMQ stateful instead of temporary containers.

### MongoDB
- MongoDB was changed from the original single-replica setup to a StatefulSet-based deployment.
- Persistent storage was added so MongoDB data is stored on PVCs instead of being lost when Pods are recreated.
- A headless Service was used so each MongoDB Pod has a stable network identity.
- MongoDB was configured to run in replica set mode with three members.
- The replica set was initialized and the members were verified using MongoDB replica set commands.
- Persistence was verified by deleting a MongoDB Pod, waiting for it to be recreated, and then checking that the data still existed.

### RabbitMQ
- RabbitMQ was changed to use StatefulSet with persistent storage.
- A PVC was added so RabbitMQ state is not lost when the Pod is recreated.
- The management plugin was kept enabled for testing in the RabbitMQ UI.
- Persistence was verified by creating a durable test queue, deleting the RabbitMQ Pod, waiting for it to be recreated, and checking that the queue still existed.

## 3. Updated File Used for Task 1

Included in this repository:

- `aps-all-in-one-Task1.yaml`

This file is the Task 1 version used to deploy the Algonquin Pet Store application with updated container images.

## 4. Updated File Used for Task 2

Included in this repository:

- `aps-all-in-one-Task2.yaml`

This file is the Task 2 version used to prove MongoDB persistence + replica set and RabbitMQ persistence.