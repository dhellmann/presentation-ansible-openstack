============================
 OpenStack ATL Ansible Demo
============================

This repository contains ansible playbooks to demonstrate how to
configure a cloud server to prepare it to run devstack or ZNC.

Running the Devstack Demo
=========================

1. Check out the repository.

2. Change directory to the 'ansible' subdir.

3. Create a virtualenv::

    $ virtualenv venv

4. Activate the virtualenv::

    $ source venv/bin/activate

5. Install ansible and the other dependencies::

    $ pip install -r requirements.txt

6. Install the ansible roles::

    $ ansible-galaxy install -r requirements.yml

7. Edit 'keys.yml' to set the ssh key information to use for the
   server.

8. Set up your 'clouds.yaml' file and 'OS_CLOUD' environment variable.

9. Verify that authentication is working properly by running an
   openstack command::

    $ openstack server list

10. Edit clouddev.yml to set the private key file to one matching your
    cloud.

11. Run the playbook::

    $ ansible-playbook ./clouddev.yml

12. Note the IP address of the server in the output of ansible-playbook.

13. Use ssh to login to the server, using the private key specified
    and the user 'ubuntu'.

14. Run devstack::

    $ cd ~/devstack
    $ ./stack.sh
