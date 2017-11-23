<img src="https://www.openshift.com/images/logos/openshift/Logotype_RH_OpenShift_wLogo_RGB_Gray.png" width="400"/>  <img src="https://blogs.missouristate.edu/cio/files/2016/06/ansible-logo.png" width="200"/>

# Ansible-Deployment_to_OpenShift
This project will display how we can automatically: Create Projects, Deploy an Image, assign external IPs and to remove them all also within the Openshift testing environment

## Pre-Requisites
1) A deployed Openshift Environment
2) Linux machine (we are using Ubuntu Server 17.04)
3) Ansible installed on Linux machine
```yml
$ sudo apt-get install libssl-dev
$ sudo pip install ansible
$ pip list  # Check to see it has successfully installed
```
## Documentation
For the file and folder structures, please see the Wiki section for further documentation:

[Home of the Wikis](https://github.com/thopper91/Ansible-Deployment_to_OpenShift/wiki)

## Playbooks
These playbooks are within the roles section, they are broken down into individual tasks so they can be re-used be a 'higher' playbook. This 'higher playbook' is on the root repository level, which allows us to add multiple roles within it to produce a singular task.

### Create
- [Create Project](../master/roles/Create_Project/tasks/main.yml)

### Delete
- [Delete Deployment & Pods](../master/roles/Delete_Deployment_and_Pods/tasks/main.yml)
- [Delete Project](../master/roles/Delete_Project/tasks/main.yml)
- [Delete Service](../master/roles/Delete_Service/tasks/main.yml)

### Other
- [Assign External IP to Image](../master/roles/Assign_External_IP_to_Image/tasks/main.yml)
- [Deploy an Image](../master/roles/Deploy_an_Image/tasks/main.yml)
