
# Jenkins on Kubernetes

## Overview
This project demonstrates deploying Jenkins on a Kubernetes cluster with persistent storage. It highlights skills in **DevOps**, **CI/CD**, and **container orchestration**.

Jenkins is deployed using a **Deployment**, a **Persistent Volume (PV) + Persistent Volume Claim (PVC)** for data persistence, and a **NodePort Service** to access Jenkins externally.

---

## Project Structure

1. **jenkins-pv.yaml**  
   Defines the Persistent Volume and Persistent Volume Claim for Jenkins data.

2. **jenkins-deployment.yaml**  
   Deploys Jenkins with a single replica and mounts the PV to `/var/jenkins_home`.

3. **jenkins-service.yaml**  
   Exposes Jenkins externally using a NodePort service.

---

## Setup Instructions

1. Apply the Persistent Volume and PVC:
   ```bash
   kubectl apply -f jenkins-pv.yaml
````

2. Deploy Jenkins:

   ```bash
   kubectl apply -f jenkins-deployment.yaml
   ```

3. Expose Jenkins via NodePort:

   ```bash
   kubectl apply -f jenkins-service.yaml
   ```

4. Access Jenkins in your browser:

   ```
   http://<Node-IP>:30000
   ```

5. Retrieve the initial admin password:

   ```bash
   kubectl exec -it <jenkins-pod-name> -- cat /var/jenkins_home/secrets/initialAdminPassword
   ```

---

## Skills Demonstrated

* Kubernetes Deployment and Service management
* Persistent storage setup with PV and PVC
* Running Jenkins in a containerized environment
* Exposing services externally via NodePort

---

## Notes

* This setup is for learning and demonstration purposes.
* For production, consider using **Ingress**, securing Jenkins with **TLS**, and implementing backup strategies.

```


*****************************


Here’s a concise, CV-friendly description for your Jenkins project:

**“Deployed Jenkins on a Kubernetes cluster with persistent storage (PV + PVC) and exposed it via NodePort. Implemented containerized CI/CD environment, demonstrating skills in Kubernetes, DevOps practices, and CI/CD pipeline management.”**

If you want, I can also make a slightly **shorter, punchier version** that fits neatly under “Projects” in a CV. Do you want me to do that?




```
