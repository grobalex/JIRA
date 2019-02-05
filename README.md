# Jira-Scripts

[![Python 3.6](https://img.shields.io/badge/python-3.6-blue.svg)](https://www.python.org/downloads/release/python-360/)

Main Script: 
-------------------

###### Run:
1. Create a venv https://docs.python.org/3/tutorial/venv.html
2. pip install requirements.txt
3. python jira.py 

###### Contraints:
 1. You must have a CCIS-ID and password 
 2. YOU MUST BE A JIRA ADMIN USER

###### [OPTIONS]
* **--input** to manual input values to create a new project
* **--file** **[path_to_file]** to create projects based on a .xslx file
* **--add** **[group-name]** **[comma-seperated-list of CCIS-ID]** to add user(s) to a JIRA group


Jira: 
-------------------

###### How all the pieces fit together
Jira is built on the idea that each project has a permission scheme, granting groups or persons access to a specific project with the permissions defined in the permission scheme. A permission scheme can be applied to multiple projects but they will be linked together and not cloned. 

The approach that SD and MSD have taken in the past is that each project has a unique permission scheme and group associated with the scheme with similar naming e.g. Project-1, PermissionScheme-1 and Group-1. Note: A group can be either a local Jira group or an LDAP group. This allows for granular control over the project and prevents unauthorized access. Each permission scheme would have a second group added to it for TAs, so that they had overarching access to all student projects. It is recommended to follow this approach to prevent uninteded linking of projects. 

###### Relationships
* A project can only have one permission scheme
* A permission scheme can be used in multiple projects
* A permission scheme can have multiple groups or users 
* A group can be in multiple permission schemes 

###### Projects
A project can be either a Software or Business project. Jira supplies basic templates on how to setup projects:

* For Software
	* com.pyxis.greenhopper.jira:gh-scrum-template
	* com.pyxis.greenhopper.jira:gh-kanban-template
	* com.pyxis.greenhopper.jira:basic-software-development-template
 
* For Business 
	* com.atlassian.jira-core-project-templates:jira-core-project-management
	* com.atlassian.jira-core-project-templates:jira-core-task-management
	* com.atlassian.jira-core-project-templates:jira-core-process-management
