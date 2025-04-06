# Quickstart Guide

## 1. Prerequisite

1.1. Create a K3Sphere Cloud account: [https://k3sphere.com](https://k3sphere.com)  
1.2. Install K3Sphere Podman: [https://github.com/k3sphere/podman](https://github.com/k3sphere/podman)

---

## 2. Add a New Cluster and Get Join Key

2.1. On the Dashboard, click the top-left menu to create a cluster.  
2.2. Refresh the page and select the newly created cluster from the top-left dropdown.  
2.3. From the left menu, click **Join Key**, create a join key, and copy it to the clipboard.

---

## 3. Create VMs and Join Virtual Network

3.1. Initialize the Podman machine:  
   - **Linux/MacOS**:  
     ```bash
     podman machine init
     podman machine init --user-mode-networking=true
     ```
   - **Windows**:  
     ```bash
     podman machine init --user-mode-networking=true
     ```

3.2. Configure the `JOIN_KEY` and `VLAN_PASSWORD` (keep these private):  
   - **Linux/MacOS**:  
     ```bash
     export JOIN_KEY=xxxxx
     export VLAN_PASSWORD=xxxxx
     ```
   - **Windows**:  
     ```bash
     set JOIN_KEY=xxxxx
     set VLAN_PASSWORD=xxxxx
     ```

3.3. Start the VM:  
   ```bash
   podman machine start
   ```

---

## 4. Deploy K3s Cluster

4.1. Run the create cluster command.  
4.2. Register the K3s cluster.  
4.3. Retrieve the K3s join key.  
4.4. Run the join K3s cluster command.

---

## 5. Deploy WordPress in K3s Cluster

5.1. Run the `kubeconfig.sh` command with arguments `cluster_name`, `client_id`, and `publicKey` (retrieve these values from the dashboard).  
5.2. Use `kubectl get nodes` to check the nodes.  
5.3. Deploy WordPress using the Helm values provided in the example.  
5.4. Open a web browser to check the WordPress page.


