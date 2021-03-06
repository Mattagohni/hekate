[![Build Status](https://travis-ci.org/solutionDrive/hekate.svg?branch=master)](https://travis-ci.org/solutionDrive/hekate)

# Hekate

Hekate is a commandline-application to manage repositories hosted on services like bitbucket from your local command line

At the moment the only supported Provider is Bitbucket. Others like github will follow

## Installation

###### Clone this repository
```bash
git clone https://github.com/solutionDrive/hekate.git
```
###### Install Dependencies via [composer](https://getcomposer.org/)
```bash
composer install --no-dev
```

## Usage

### I. Bitbucket
#### Commands

##### bitbucket:init
```bash
php bin/hekate bitbucket:init [-f|--force] [-c|--config=PATH_TO_CONFIGFILE]
```
will ask questions about setting-parameters and write it to the file hekate.yml in the root-folder.
If file already exists, no questions are asked and an info is displayed. With the --force option questions
and creation of a new config-file is enabled, even if a file already exists
 
The available settings for Hekate are:
 * Bitbucket-Account
 * Bitbucket-Username
 * Bitbucket-Password

##### bitbucket:repo-list
```bash
php bin/hekate bitbucket:repo-list [-u|--username=USERNAME] [-p|--password=PASSWORD] [-a|--account=ACCOUNT] [-k|--projectkey=PROJECTKEY] [-c|--config=PATH_TO_CONFIGFILE]
```
will get a List of all Repositories for repositorys for the given parameters.
All Parameters are optional for the commandline. 
The following Parameters will be asked if omitted:

* username
* password
* account



Changelog
---------
- UNRELEASED
    - [ADDED] Option to Commands for alternative config-files
    - [CHANGED] AbstractHekateCommand is now AbstractBitbucketCommand
- v0.1
    - [ADDED] Command for Config-Init
    - [ADDED] YAML-Component for reading / writing Config-Files
    - [ADDED] possibility to filter the repository-List for a given projectkey
    - [ADDED] added command to get a list of all repositories for a given account