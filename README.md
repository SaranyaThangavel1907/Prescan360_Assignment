# Prescan360_Assignment
The scenario:
We would like to run some C++ and Go (Golang) experiment in the cloud.
We are running the experiment on a Ubuntu host, in a CentOS container. The application may require hardware accelerated graphics support (VGA passthrough) so a graphics driver needs to be installed on the host.

The Terraform template main.tf creates ubuntu vm with a single Tesla V100 GPU, the disk Standard_NC6s_v3 comes with NVIDIA Tesla V100 GPUs
password authentication has been disabled and accessible only with SSH. 
