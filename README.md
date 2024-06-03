# Kairos Overleaf Toolkit

This is a forked repository from the Overlead Toolkit which contain the tools to simply setup overleaf with Docker locally. More information can be found on the [Quick Start Guide](./doc/quick-start-guide.md) page. 

## Kairos Prerequisites

The overleaf toolkit requires the following:
- Access to KPInfr GitHub Repository 
- Bash
- [Docker](https://docs.docker.com/engine/install/)

Most recent version of Docker available on your system is recommended.

## Hardware Requirements

You can find the Hardware requirement information from this [link](https://github.com/overleaf/overleaf/wiki/Hardware-Requirements).

## Kairos Start Guide and install

Clone this repository locally: 
``` sh
git clone https://github.com/KPInfr/overleaf-toolkit.git
```

Change Directory:
``` sh
cd overleaf-toolkit
```

## Look Around
Let's take a look at the structure of the repository:

```sh
$ ls -l
```

Which will print something like this:

```
    bin
    CHANGELOG.md
    config
    data
    doc
    lib
    LICENSE
    README.md
```

The `README.md` file contains some useful information about the project, while the `doc` directory contains all of the documentation you will need to use the toolkit. The `config` directory will contain your own local configuration files (which we will create in just a moment), while the `bin` directory contains a collection of scripts that manage your overleaf instance.

## Kairos Configuration

Create local configuration:
``` sh
bin/init
```

Display content of the config directory:
``` sh
ls config
overleaf.rc     variables.env     version
```
These are the three configuration files you will interact with:

- `overleaf.rc` : the main top-level configuration file
- `variables.env` : environment variables loaded into the docker container
- `version` : the version of the docker images to use

## Kairos Starting up service:

Run:
``` sh
bin/up
```

You should see some log output from the docker containers, indicating that the containers are running. 
If you press `CTRL-C` at the terminal, the services will shut down.

If you would like to run without log being attached:
``` sh
bin/start
```

and stop with:
``` sh
bin/stop
```
## Create the first admin account

In a browser, open <http://localhost/launchpad>. You should see a form with email and password fields.
Fill these in with the credentials you want to use as the admin account, then click "Register".

Then click the link to go to the login page (<http://localhost/login>). Enter the credentials.
Once you are logged in, you will be taken to a welcome page.

Click the green button at the bottom of the page to start using Overleaf. 

## Create your first project

On the <http://localhost/project> page, you will see a button prompting you to create your first
project. Click the button and follow the instructions.

You should then be taken to the new project, where you will see a text editor and a PDF preview.

## Handy Tools
The Overleaf Toolkit comes with a handy tool for debugging your installation: `bin/doctor`

Let's run the `bin/doctor` script:

```sh
bin/doctor
```

We should see some output similar to this for Mac users:
```
====== Overleaf Doctor ======
- Host Information
    - Not Linux !
    - lsb_release not found !
- Dependencies
    - bash
        - status: present
        - version info: 3.2.57(1)-release
    - docker
        - status: present
        - version info: Docker version 26.1.1, build 4cf5afa
    - realpath
        - status: present
realpath: illegal option -- -
usage: realpath [-q] [path ...]
```

## More Informtion

For more information on setting up the [Overleaf](https://overleaf.com) local instance visit the [Toolkit](https://github.com/overleaf/toolkit).


## ---------------------------------------------------------------

# Overleaf Toolkit

This repository contains the Overleaf Toolkit, the standard tools for running a local
instance of [Overleaf](https://overleaf.com). This toolkit will help you to set up and administer both Overleaf Community Edition (free to use, and community supported), and Overleaf Server Pro (commercial, with professional support).

The [Developer wiki](https://github.com/overleaf/overleaf/wiki) contains further documentation on releases, features and other configuration elements.


## Getting Started

Clone this repository locally:

``` sh
git clone https://github.com/overleaf/toolkit.git ./overleaf-toolkit
```

Then follow the [Quick Start Guide](./doc/quick-start-guide.md).


## Documentation

See [Documentation Index](./doc/README.md)


## Contributing

See the [CONTRIBUTING](https://github.com/overleaf/overleaf/blob/main/CONTRIBUTING.md) file.


## Getting Help

Users of the free Community Edition should [open an issue on github](https://github.com/overleaf/toolkit/issues). 

Users of Server Pro should contact `support@overleaf.com` for assistance.

In both cases, it is a good idea to include the output of the `bin/doctor` script in your message.

