# Windows-Linux

Note: Ansible cannot be installed on windows, instead we used a virtual machine and installed Ubuntu Servers Edition 18.04.1. We referenced the guides found [here](https://code-maven.com/ansible) for this assignment.

**Step 1:**
Follow these instructions to set up the Ubuntu environment of Windows.

**Step 2:**
it’s time to install Ansible. I have set up 4 Linux VMs: 1 host and 3 guests. I will install Ansible on the host machine. But first I will install Virtualenv which creates an isolated Python environment that has its own installation directories and doesn’t access the globally installed libraries either. To do this run the following commands

`$ sudo apt-get install virtualenv python3-virtualenv python3-pip
$ virtualenv venv --python=python3
$ source venv/bin/activate`

**Step 3:**
Now create the virtualenv folder, load the Python virtualenv, and finally install ansible

`$ virtualenv venv
$ source venv/bin/activate
$ pip install ansible`

**Step 4:**
create the inventory.cfg file

*Note: For the remainder of this assignment I will use IP 192.168.56.11 (aka guest-ansible-1) as my guest machine. The line ansible_python_interpreter=/usr/bin/python3 tells Ansible to use Python 3.*

**Step 5:**
Create the static_site.cfg configuration file

**Step 6:**
Create a folder called static-site-src and place the index.html file in it.

**Step 7:**
Now to create the nginx.yml playbook to set up Nginx

**Step 8:**
Now run this command:

`$ ansible-playbook -i inventory.cfg --limit 192.168.56.11 nginx.yml`


**Step 9:**
Now run:

`$ curl http://192.168.56.11`

**Step 10:**
With Putty, connect to your host VM (in this case 192.168.2) and then navigate to http://192.168.56.11 on your browser

**Step 11:**
To stop the web server create the nginx_uninstall.yml playbook and terminate with the following command:

`$ ansible-playbook -i inventory.cfg nginx_uninstall.yml -b`
