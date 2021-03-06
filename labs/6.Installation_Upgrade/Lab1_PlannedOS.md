## Lab 1 : Drain, Cordon, Uncordon

1- Remove the taint from the master node.

  <details><summary>Show</summary>
<p>

```bash
k taint node master01 node-role.kubernetes.io/master:NoSchedule
```

</p>
</details>

2- Deploy the yaml file for the lab.

3- How many nodes do you see in the cluster? Including the master/controlplane and workers.

  <details><summary>Show</summary>
<p>

```bash
k get nodes
```

</p>
</details>

4- How many applications/deployments are running in the cluster?

<details><summary>Show</summary>
<p>

```bash
k get deployments,pods
```

</p>
</details>
  

5- On which nodes are the applications hosted on?

  
<details><summary>Show</summary>
<p>

```bash
k get pods -o wide
```

</p>
</details>


6- Mark the worker node an unschedulable but keep running the existing pods

<details><summary>Show</summary>
<p>

```bash
kubectl cordon worker01
```

</p>
</details>

7- Bring back the worker node in the ready state

  <details><summary>Show</summary>
<p>

```bash
kubectl uncordon worker01 
```

</p>
</details>

8- Mark the worker node as scheduled for maintenance.

  
<details><summary>Show</summary>
<p>

```bash
kubectl drain <worker node name> --ignore-daemonsets
```

</p>
</details>


9- What nodes are the apps on now?

  <details><summary>Show</summary>
<p>

```bash
kubectl get pods -o wide
```

</p>
</details>


10- Configure the node to be schedulable again.

  <details><summary>Show</summary>
<p>

```bash
kubectl uncordon worker01
```

</p>
</details>

11- How many pods are scheduled on the worker node now?Why there are no pods on worker node.


<details><summary>Show</summary>
<p>

```bash
New pods will be scheduled on the worker node
```

</p>
</details>
