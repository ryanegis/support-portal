# Papertrail Linux CLI command: pt

A command line interface to perform functions not found in the administrative GUI is available. It can also be used as part of a scripting process, e.g. bulk export/upload etc. This utility can be installed on Linux via pip (package management system to install Python software packages).

### Requirements:
It is not necessary for this program to be installed on the Papertrail server that you intend on connecting to. However, the following packages need to be installed on the Linux host where you intend on using the `pt` CLI command:
* Python
* Pip
* Git<br>

The installation of these packages may vary depending on the flavour of Linux running (e.g. *yum*, *rpm*, *apt-get*)

### Installation
Choose only one of the below options:

#### Option 1
* `sudo pip install git+ssh://git@github.com/egis/papertrail-python-cli.git`

#### Installation Option 2 (should you receive an access denied message when following Option 1)
 * Download the contents of `https://github.com/egis/papertrail-python-cli` (include sub-folders)
 * Transfer this to the Linux host (using WinSCP as an option)
 * Execute `sudo python setup.py install`

### Usage
 * Once installed, executing `pt --help` will bring up the available options and commands. Use `pt {command} --help` for more details on the specific command itself; e.g. `pt import --help`
 * To connect to a Papertrail host server:<br>
    `pt --host 192.168.1.10:8080 -- username admin --password 'mypassword'` (which will not execute an actual command)
 * Add onto the above for the specific function you wish to achieve, e.g.<br>
    `pt --host 192.168.1.10:8080 -- username admin --password 'mypassword' export User > users.yml`
 * Another example:<br>
    `pt --host 192.168.1.10:8080 -- username admin --password 'mypassword' import newusers.yml`

### Reference
 * The above 2 examples export and import users respectively based on the YAML format. See more [here](http://support.papertrail.co.za/Configuration/Yaml%20Config/?#yaml-import-and-export)
 * Further details specific to the user import and export process can be found [here](http://support.papertrail.co.za/Configuration/user-export-import)
