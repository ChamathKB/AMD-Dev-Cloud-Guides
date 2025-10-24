# AMD Dev Cloud MX300 - vLLM Setup Guide

This guide provides instructions for setting up a vLLM environment on an AMD Dev Cloud MX300 instance.

### Hardware Specifications

| Component       | Specification                               |
| :-------------- | :------------------------------------------ |
| **GPU Type** | AMD MI300X                                  |
| **VRAM** | 192 GB                                      |
| **CPU Type** | INTEL(R) XEON(R) PLATINUM 8568Y+            |
| **vCPU** | 20                                          |
| **RAM** | 240 GB                                      |
| **Boot Disk** | 720 GB NVMe SSD                             |
| **Scratch Disk**| 5 TB NVMe SSD                               |

### Getting Started

Follow these steps to set up your vLLM environment:

1.  **Create Droplet with vLLM Docker Image:**
    Provision a new droplet on the AMD Dev Cloud with the pre-built vLLM Docker image. AMD provides optimized vLLM Docker images for MI300X GPUs.

2.  **Add SSH Key:**
    Ensure your SSH key is added to the droplet for secure access.

3.  **Connect to the Droplet:**
    Connect to your droplet using either the web console or your terminal via SSH.

4.  **Access Jupyter Notebook:**
    Once connected, you can access the Jupyter Notebook interface by opening a web browser and navigating to `http://<Your-Droplet-IP>:8888`.

5.  **Access Docker Container Shell:**
    To get a shell inside the vLLM Docker container, execute the following command in your droplet's terminal:

    ```bash
    docker exec -it rocm /bin/bash
    ```

6.  **Retrieve Jupyter Token:**
    Inside the Docker container's shell, list the running Jupyter servers to get the authentication token:

    ```bash
    jupyter server list
    ```

    Copy the token from the output.

7.  **Load Jupyter Notebook:**
    Paste the copied token into the Jupyter Notebook login page in your web browser to access your environment.

8.  **Monitor GPU Usage:**
    To view real-time GPU usage of your AMD MI300X, use `nvtop` :

    ```bash
    nvtop
    ```

### Additional Resources

For more detailed information on vLLM and AMD GPUs, refer to the following AMD ROCm blog post:

  * [Inferencing and serving with vLLM on AMD GPUs](https://rocm.blogs.amd.com/artificial-intelligence/vllm/README.html)

### Acknowledgment

These notebooks were inspired by and modified from guides originally created by AMD and vLLM. All credit for the work belongs to the original authors.