Ansible
=======
A configuration management and provisioning tool.

Features
--------
* idempotent: the result of running it once is exactly the same as running it repeatedly.
* runs over ssh
* modules can be written in python, bash (or ruby, perl)


Concepts
--------
* actions     part of a task that specifies which modules to run and which arguments to pass to that module.
* facts       system and environment variables (context) discoverd about nodes.
* tasks       combine an action (a module and its arguments) with a name.
* handlers    tasks that will only run when called by other tasks
* modules     the units of work that are shipped out to remote machines.
* library     the collection of available modules.
* playbooks   orchestrate, configure, administer or deploy systems
* plays       map a group of hosts to some defined roles, represented by tasks
* roles       organize multiple related variables, tasks and handlers per group of hosts.
* groups      several hosts assigned to a pool that can be targeted together. (??? e.g. vagrant group, non-vagrant group)
* inventory   file to define servers managed by Ansible
* vault       store sensitive data in encrypted files
