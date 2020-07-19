# learn-ansible

## Purpose
Document Ansible notes used for learning the framework

## Ansible Overview
* 1800 modules
* Agentless (unlike puppet)
* Simple, declarative language
* Used for orchestrating the entire app lifecycle

### What can you do with Ansible
It provides a variety of modules that can be leveraged for a lot of automation tasks like cloud, 
containers, files, database, messaging, packaging, source control, system, testing and utilities.

## Core Ansible Engine
* Inventory - Collection of hosts (Nodes), groups
* Restful API (with UI) : This is a feature of RedHat Ansible tower that provides Restful API/UI
* Modules - Tools in the toolkit
* Plugins - Gears in engine


## Ansible Key Components

### Playbook
* Written in YAML
* Sequence on instructions to be executed for a specific step

### Modules (describe with examples)

* Modules are tools can be written with Python, powershell or bash or any programming language
* Represents the action to be executed in target declaration

### Examples of modules
- yum/apt-get
- deploy
- service
- deploy
- template
- uri

### Command Module

* Command : Executes the task by connecting to the provided system and performing the action
This is more secure and reliable
* Script: Executes a script after transferring to the host. Be careful in using scripts.
* Shell: Executes a shell command or bash script after connecting to machine
* Raw: Executes a raw script without taking advantage of ansible subsystem.

### Plugins

* Plugins in ansible are "code that is plugged into core engine" for adaptability for various platforms

### Inventory
* Collection of hosts (Nodes) that represent a application
* static / dynamic sources
* groups

-----------
## Ansible Engine

### Ansible Adhoc commands
* ansible - Run ansible command from command line to execute a single ansible task from command line
* plays - Ordered set of tasks to execute against given inventory
* playbooks - Files containing one or more plays

### Tasks
- file: Create directory
- yum: Install package
- service: Start service
- template: Render configuration file
- get_url: Fetch archive file from url
- git: clone source code repository

#### Handlers Task
Special tasks run at the end of the play if notified by another task when the change occurs
- Example : When package installation is complete, service restart handler task should be run.
- if the task update's package's configuration, notify appropriate handler

### What can be done with Ansible Playbook
- Use variables
- apply templates
- for loop
- conditionals
- apply tags
- create blocks

## Ansible Variables
Used for managing context from :
- Command line variables
- Plays
- Tasks
- Files
- Inventory
- Discovered Facts
- Roles

## Variable precedence
There is a good hierarchy resolution strategy available in case there is a same variable and it 
needs to be overwritten.

## Facts
A set of data extracted from an ansible command to be used for the subsequent task
For example : ansible localhost -m setup

## Templates
Ansible uses Jinja2 templating engine to dynamically
- set and modify play vars
- apply conditional logic
- Generate files such as configurations from variables

## Roles
- Closely related ansible content that can be shared easily rather than plays alone.
- Utility packages or projects grouped together
- Path resolution and default vars
- Readability and manage plays


For example:

```
site.yml
roles/
    common/
        files/
        templates/
        tasks/
        handlers/
        vars/
        meta/
        default/        
    apache/
        files/
        templates/
        tasks/
        handlers/
        vars/
        meta/
        default/
```

Example playbook using two roles:

``` 
#site.yml
---
- hosts: web
  roles:
    - common
    - apache
```

### Ansible Galaxy
- discover community contributed ansible roles
- cli tool for creating and managing roles



