## Usage  

We use `Dockerfile_CGN` to build a docker image with Base image: CUDA 11.8 with cuDNN 8 on Ubuntu 22.04 for Contact-GraspNet. We use `run_docker.sh` to start the docker container, which at the same time mount the local workspace (i.e., `~/graspnet_ws/src`) from the host machine to the docker container.

- **Clone the Docker files** (CUDA 11.8 with cuDNN 8 on Ubuntu 22.04): 

	```bash
 	cd ~/graspnet_ws/src/contact_graspnet_ros2/
	git clone https://github.com/zhaohuajing/contact_graspnet_docker 
	```

- **Build the Docker image**:
	```bash
 	cd ~/graspnet_ws/src/contact_graspnet_ros2/contact_graspnet_docker
	docker build -t cuda118:contact_graspnet -f Dockerfile_CGN .
	```
	Alternatively, you may use the following command to pull the docker image for contact-graspnet from docker hub:
   ```
   docker pull zhaohuajing/cuda118:contact_graspnet
   ```

- **Start the Docker container**:  
   ```bash
   ./run_docker.sh
   ```
	This script launches the Contact-GraspNet container with the proper environment and names it as: `contact_graspnet_container`. Note that `run_docker.sh` script will mount the entire workspace (i.e., `~/graspnet_ws/src`) to the docker container through `-v ~/graspnet_ws:/root/graspnet_ws`; you may adjust the name of workspace to your local setup as needed.

