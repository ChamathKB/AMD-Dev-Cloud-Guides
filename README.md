# AMD-Dev-Cloud-Guides

Guides on AMD AI optimized developer cloud usecases.

## Getting Started

Follow these steps to set up your vLLM environment:

1.  **Create Droplet:**
    Provision a new droplet on the AMD Dev Cloud with bare-metal ubuntu 24.04 LTS server or the pre-built Docker image. AMD provides optimized Docker images for MI300X GPUs.

2.  **Add SSH Key:**
    Ensure your SSH key is added to the droplet for secure access.

3.  **Connect to the Droplet:**
    Connect to your droplet using either the web console or your terminal via SSH.

4.  **Access Jupyter Notebook:**
    You can access the Jupyter Notebook interface by opening a web browser and navigating to `http://<Your-Droplet-IP>:8888`.

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

## Acknowledgment

AMD and DigitalOcean for providing the cloud development environment ❤️.