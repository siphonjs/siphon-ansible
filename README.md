# siphon-ansible
Instructions for setting up a server cluster for data extraction using SiphonJS and Ansible

##Below are the steps required to set up a remote data extraction cluster on DigitalOcean:

1. Generate an SSH key you will use to connect to your servers and an SSH key that will be used by your servers to connect to Github. Then create a droplet/instance with Ubuntu 16.04 to run Redis. Follow this tutorial for SSH and server setup: https://www.digitalocean.com/community/tutorials/initial-server-setup-with-ubuntu-16-04

2. Follow this tutorial to install and configure Redis: https://www.digitalocean.com/community/tutorials/how-to-install-and-configure-redis-on-ubuntu-16-04  (remember the server IP and Redis port number)

3. Create however many droplets/instances you want, all with the first SSH key you generated

4. Install Ansible on all of the droplets by logging in with SSH and typing the following 5 commands: "sudo apt-get update", "sudo apt-get install software-properties-common", "sudo apt-add-repository ppa:ansible/ansible", "sudo apt-get update", and "sudo apt-get install ansible"

5. Install Ansible on your personal computer or remote server. Here is a tutorial for setting up ansible on a DigitalOcean server, remember that this server needs a private SSH key to access the cluster: https://www.digitalocean.com/community/tutorials/how-to-install-and-configure-ansible-on-ubuntu-14-04

6. Add all of the droplets to your /etc/ansible/hosts file under the heading [siphon], the tutorial above covers this step

7. Fork and clone this repo to your computer/remote server and replace the fields marked by *   * with your information

8. Run the command "ansible-playbook siphon-app.yml" and watch your servers get configured

9. Start pushing jobs to your Redis server using the SiphonJS API!
