# Kubernetes Incident Response Lab

**Status: Planned**

The goal is to learn how to run, configure, and troubleshoot a container in Docker and Kubernetes. I'll use the stock NGINX image as a workload with a predictable result: an HTTP request returns the default welcome page.

## Milestones

1. **Run a Docker container.** Start NGINX, publish a local port, and request the welcome page. Inspect the running container and its logs. Explain the difference between the image and the container, and how the request reaches port 80 inside the container.
2. **Make the setup repeatable with Compose.** Write a Compose file for the same container and port mapping. Tear down and recreate the setup, then confirm the same request succeeds.
3. **Deploy to a local Kubernetes cluster.** Write a Deployment and a Service for the same image. Inspect the Pods and EndpointSlices, then use port forwarding to reach the Service from my computer. Explain how a Deployment, Pod, and Service work together.
4. **Diagnose a failing readiness probe.** Change the probe to request a missing path. Check why the container is running while the Pod is unready. Fix the probe and verify that the Pod is ready and serving traffic.
5. **Diagnose a Service selector mismatch.** Change the selector so it matches no Pods. Compare the selector, Pod labels, and EndpointSlices. Restore the selector and verify that traffic reaches NGINX again.

## What I'll document

I'll write the configuration and run the commands myself. I'll record a working request for each environment and write up both incidents with the symptom, evidence, root cause, fix, and recovery check.
