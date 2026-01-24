# Lab 1: Node Isolation Using Taints in Kubernetes

## 📝 Lab Objectives
- Run a Kubernetes cluster with 2 nodes.
- Apply a Taint to a specific node to restrict Pod scheduling.
- Verify the isolation via node description.

## 🚀 Implementation Steps

### 1. Start Cluster with 2 Nodes
```bash
minikube start --nodes 2
```
![Nodes Ready](./screenshots/1-nodes-ready.png)

### 2. Apply Taint to Worker Node
- Applied a taint with key `node`, value `worker`, and effect `NoSchedule`:
```bash
kubectl taint nodes minikube-m02 node=worker:NoSchedule
```
![Taint Applied](./screenshots/2-apply-taint.png)

### 3. Verification
- Verified the taint by describing the node:
```bash
kubectl describe node minikube-m02 | grep -i Taints
```
![Taint Verified](./screenshots/3-verify-taint.png)
