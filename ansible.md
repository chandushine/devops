ansible
--------
what is ansible?
----------------
1. ansible is a configuration management tool.
2. Ansible is a simple, powerful, cross-platform, and agentless IT automation tool that everyone can use for their needs.(to do tasks atomatically)
what is configuration management tool?
-------------------------------------
* it is maintain number(100 and 1000's) of machines with automation
Why Ansible:
------------
 * Provisioning
 * Configuration Management
 * Continuous Deployment
 * Application Deployment
 * Security Compliance or Automation
 * Infrastructure Orchestration
 * IT automation
Advantages of Ansible:
-----------------------
 1. 

 
what it maintain ?
-------------------
* it maintain the system resources such as
    1. install a application
	2. configuration
	3. updates
	4. maintain and so on..
Features of Ansible:
--------------------
  * It's agentless, so you don't need to install and manage an agent on the servers you need to run ansible on.
  * It uses SSH to establish secure connections.
  * It follows push bases architecture.
  * It is built on top of python, so it has a lot of functionalities of python built-in.
Setup Password-less SSH Connection:
-----------------------------------
  * Public-Private key encryption
  * Generate keys using ssh-keygen command
  * Transfer keys using ssh-copy-id command: ssh-copy-id USER@SERVER_IP
  * Validate
why configuration management tool?
---------------------------------
* reduce management complexity
* save time
configuration management tools(CM):\
-----------------------------------
1. There are two types of CM
   1.Pull based CM
   2.Push Based CM
2. Direction of communication
  **PULL** => Node to CM server
  **Push** => CM Server to Node
What is required in PULL Based CM:
----------------------------------
* Agent needs to be installed with necessary credentials to connect to CM Server

What is required in Push Based CM:
----------------------------------

 1. List of nodes (inventory)
 2. Credentials to login into node
	puppet ----> 2005	pull
	chef ------->2008	pull
	ansible ----->2011	push
how ansible work?
-----------------
* ansible is working on push based mechanisam. push based means here server(master) will push the code into the nodes(slaves).
how the master communicate with slaves?
---------------------------------------
	with ssh public key & private key they communicate.
**we can work with ansible in 2 ways** -
 1. playbooks (all tasks place in one .yml file and run it)
  - We create a file where we express desired state
  - This is recommended approach for repetitive activites
 2. ad-hoc (on the command line we perform this)
  - We build a command for desired state

ansible playbooks:
------------------
**Q)what is playbook?**
1. the collection of play
2. playbook is a set of instructions file. to do a particular tasks on target(host) or group of target(hosts).
**Q)how playbook works?**
* playbook works with modules(yum,service,file,etc..), and inventory file(/etc/ansible/hosts) over ssh communication.
**Q)what we need to run playbook ?**
* we need to specify target, tasks in playbook with modules(apt oryum, file, etc..)
ansible role:
------------
1. place the group of playbooks in one file. it will help reduce the code complexity, and increase the code reusability.
2. There's a large playbook file with hundreds lines of code. It's frustrating to maintain, change, and support it. We must cut this huge file into smaller files and use a single master playbook to control these files using - include <playbook name> in the master playbook
**Ansible-Galaxy:-**
* Galaxy is your hub for finding, reusing and sharing the best Ansible content.
**Ansible-Inventory:**
* Inventory file (host file) contains the list of all the servers which you want to perform some tasks on them.
* **Advantage of inventry:**It's good to separate servers for their specific purposes on different groups, and add all servers in a single group so that you can access all of them at once.
 `example:/etc/ansible/hosts`
 * Inventory in Ansible represents the hosts which we need to connect to.
 * Ansible inventory is broadly classified into teo types
1. static inventory: where we mention the list of nodes to connect to in some file
     Static inventory can be mentioned in two formats
     * ini
     * yaml
2. dynamic inventory:  where we mention some script/plugin which will dynamically find out the nodes to connect to

Control Node:
-------------
* where we have Machine with Ansible installed
Managed Node(Master Node):
-------------
* Machines that you manage with Ansible
Inventory or Inventory file:
------------------------------
* List of managed nodes, default file location is /etc/ansible/hosts
Modules:
---------
* Unit of code that Ansible executes or In ansible the smallest unit of work is perfomed by module
Tasks:
-------
* Unit of action in Ansible

Playbooks:
-----------
* we have to excute Ordered list of tasks

Check for syntax of playbook
-----------------------------
* ansible-playbook -i <inventory-path> --syntax-check <playbook-path>












