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

Openshift allows the developer to use both Docker Hub and the RedHat container site. However Openshift prefers to use container images from the Redhat website itself:
- Docker Hub: https://hub.docker.com/
- Red Hat Container: https://access.redhat.com/containers/?tab=overview&platform=openshift#/ 

## Playbooks
These playbooks are within the roles section, they are broken down into individual tasks so they can be re-used be a 'higher' playbook. This 'higher playbook' is on the root repository level, which allows us to add multiple roles within it to produce a singular task.

### Create
- [Create Project](../master/roles/Create_Project/tasks/main.yml)
- [Create Apache Project with pods](../master/roles/Create_Apache_project_with_pods)
- [Create Jenkins Project with pods](../master/roles/Create_Jenkins_project_with_pods)

### Delete
- [Delete Apache Project](../master/roles/Delete_Apache_project)
- [Delete Deployment & Pods](../master/roles/Delete_Deployment_and_Pods/tasks/main.yml)
- [Delete Jenkins Project](../master/roles/Delete_Jenkins_project)
- [Delete Project](../master/roles/Delete_Project/tasks/main.yml)
- [Delete Service](../master/roles/Delete_Service/tasks/main.yml)

### Other
- [Assign External IP to Image](../master/roles/Assign_External_IP_to_Image/tasks/main.yml)
- [Deploy an Image](../master/roles/Deploy_an_Image/tasks/main.yml)
- [Display Openshift Token](../master/roles/Display_Token)
- [Use specific project](../master/roles/Get_to_project)
- [Login to specific user account](../master/roles/Get_to_project)
- [Logout to specific user account](../master/roles/Logout_of_account)
