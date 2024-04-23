This is a project in the DevOps track at ALX School. In this project, you will learn how to write Puppet manifests to manage your infrastructure. You will learn how to create files, install packages, and execute commands.

Tasks

Create a file

Using Puppet, create a file in /tmp.
The file path is /tmp/school.
The file permission is 0744.
The file owner is www-data.
The file group is www-data.
The file contains I love Puppet.
Install a package

Using Puppet, install flask from pip3.
The version must be 2.1.0.
Execute a command

Using Puppet, create a manifest that kills a process named killmenow.
The manifest must use the exec Puppet resource.
The manifest must use pkill.
Resources

Read or watch:
Intro to Configuration Management
Puppet resource type: file` (check “Resource types” for all manifest types in the left menu)
Puppet’s Declarative Language: Modeling Instead of Scripting
Puppet lint
Puppet emacs mode
Requirements:
General
All your files will be interpreted on Ubuntu 20.04 LTS
All your files should end with a new line
A README.md file at the root of the folder of the project is mandatory
Your Puppet manifests must pass puppet-lint version 2.1.1 without any errors
Your Puppet manifests must run without error
Your Puppet manifests first line must be a comment explaining what the Puppet manifest is about
Your Puppet manifests files must end with the extension .pp
Note on Versioning

Your Ubuntu 20.04 VM should have Puppet 5.5 preinstalled.
Install puppet:
apt-get install -y ruby=1:2.7+1 --allow-downgrades
apt-get install -y ruby-augeas
apt-get install -y ruby-shadow
apt-get install -y puppet
You do NOT need to attempt to upgrade versions. This project is simply a set of tasks to familiarize you with the basic level syntax which is virtually identical in newer versions of Puppet.
Puppet 5 Docs

Install puppet-lint:
gem install puppet-lintThis is a project in the DevOps track at ALX School. In this project, you will learn how to write Puppet manifests to manage your infrastructure. You will learn how to create files, install packages, and execute commands.
Tasks

Create a file

Using Puppet, create a file in /tmp.
The file path is /tmp/school.
The file permission is 0744.
The file owner is www-data.
The file group is www-data.
The file contains I love Puppet.
Install a package

Using Puppet, install flask from pip3.
The version must be 2.1.0.
Execute a command

Using Puppet, create a manifest that kills a process named killmenow.
The manifest must use the exec Puppet resource.
The manifest must use pkill.
Resources

Read or watch:
Intro to Configuration Management
Puppet resource type: file` (check “Resource types” for all manifest types in the left menu)
Puppet’s Declarative Language: Modeling Instead of Scripting
Puppet lint
Puppet emacs mode
Requirements:
General
All your files will be interpreted on Ubuntu 20.04 LTS
All your files should end with a new line
A README.md file at the root of the folder of the project is mandatory
Your Puppet manifests must pass puppet-lint version 2.1.1 without any errors
Your Puppet manifests must run without error
Your Puppet manifests first line must be a comment explaining what the Puppet manifest is about
Your Puppet manifests files must end with the extension .pp
Note on Versioning

Your Ubuntu 20.04 VM should have Puppet 5.5 preinstalled.
Install puppet:
apt-get install -y ruby=1:2.7+1 --allow-downgrades
apt-get install -y ruby-augeas
apt-get install -y ruby-shadow
apt-get install -y puppet
You do NOT need to attempt to upgrade versions. This project is simply a set of tasks to familiarize you with the basic level syntax which is virtually identical in newer versions of Puppet.
Puppet 5 Docs

Install puppet-lint:
gem install puppet-lint
