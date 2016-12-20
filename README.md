# siphon-ansible
Instructions for setting up a server cluster for data extraction using SiphonJS and Ansible

##Below are the steps required to set up a remote data extraction cluser on Digital Ocean:

1. Generate an SSH key you will use to connect to your servers and an SSH key that will be used by your servers to connect to Github

2. Create a droplet/instance with Ubuntu 16.04 to run Redis using the first key you generated in step 1

3. Follow this tutorial to install and configure Redis: (remember the server IP and Redis port number)

4. Create however many droplets/instances you want, all with the first SSH key you generated

5. Install Ansible on all of the droplets

6. Install Ansible on your personal computer or remote server. Here is a tutorial for setting up ansible on a DO server, remember that this server needs a private SSH key to access the cluster

7. Add all of the droplets to your /etc/ansible/hosts file under the heading [siphon]

8. Fork and clone this repo to your computer/remote server and replace the fields marked by *   * with your information

9. Run the command "ansible-playbook siphon-app.yml" and watch your servers get configured

10. Start pushing jobs to your Redis server using the SiphonJS API!
