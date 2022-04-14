
SSH into your Ansible Control Node (localhost in my case) Instance using Putty.

After login, if not installed, then install the Ansible. We can verify the ansible version by running this command: ansible --version

Now create a directory for our project named install-jenkins.

After changing the directory, let’s create our inventory.txt file that will include our Jenkins instance by running vi inventory.txt

Once in the vi text editor press i to enter insert mode and use the following:(make sure to replace the private IP with your Jenkins instance private IP address)

target ansible_host=<target private IP>

Now create file named install-jenkins.yml using the command vi install-jenkins.yml

Once in the text editor use the given github code to create the Ansible Playbook.

To run the Ansible Playbook targeting the Jenkins Instance run the following:

$ ansible-playbook install-jenkins.yml -i inventory.txt

Once the Ansible Playbook has finished, you should see that some tasks are yellow, showing that something was changed and some are green, showing that the task ran successfully.

Now navigate to http://<jenkins public ip>:8080(replace <jenkins public ip> with your own) and you will see that Jenkins server is installed. 

