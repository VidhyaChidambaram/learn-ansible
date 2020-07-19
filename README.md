# learn-ansible

## Purpose
Document Ansible notes used for learning the framework

# Ansible Overview
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



