- Nestor Rafael Bolivar - Jun 2016
- Not production environments.
- REA Pre-interview test
	This piece of code will configure a Linux ditribution and will deploy
	the application from https://github.com/rea-cruitment/simple-sinatra-app.git

- Requirements
	RedHat or Debian based distributions 
	Tested  on:
		-Red Hat Enterprise Linux 7.2 (HVM), SSD Volume Type - ami-775e4f16 (AWS)
		-Ubuntu Server 14.04 LTS (HVM), SSD Volume Type - ami-9abea4fb (AWS)
		-CentOS 7 (x86_64) with Updates HVM (AWS://aws.amazon.com/marketplace/pp/B00O7WM7QW )

		-CentOS-7-x86_64-Minimal-1511.iso 
		-ubuntu-16.04-server-amd64.iso
		-ubuntu-14.04.4-server-amd64.iso
	2GB RAM
	1.5GHz intel based CPU
	Internet connection - GitHub access, RedHat and Debian Repos access.
	Root/Administration privileges

- Tar content 'installRea.tar.gz'

	installRea
	├── installRea.sh
	└── README.md

- Aplication content '/usr/local/rea_richmond'
	.
	├── bin
	│   ├── installRea.sh
	│   ├── reaRichmond.sh
	│   └── reaScreen.sh
	├── conf
	│   └── version_support.conf
	├── cookbooks
	│   └── docker_img
	│       ├── Berksfile
	│       ├── chefignore
	│       ├── metadata.rb
	│       ├── README.md
	│       ├── recipes
	│       │   ├── default.rb
	│       │   ├── rea_conf_app.rb
	│       │   ├── rea_hardening.rb
	│       │   ├── rea_prerequi.rb
	│       │   └── rea_services.rb
	│       ├── spec
	│       │   ├── spec_helper.rb
	│       │   └── unit
	│       │       └── recipes
	│       │           └── default_spec.rb
	│       ├── templates
	│       │   └── default
	│       │       ├── 000-default.conf.erb
	│       │       ├── passenger.conf.erb
	│       │       └── rea_iptables.erb
	│       └── test
	│           └── integration
	│               ├── default
	│               │   └── serverspec
	│               │       └── default_spec.rb
	│               └── helpers
	│                   └── serverspec
	│                       └── spec_helper.rb
	├── log
	│   └── info.log
	├── nodes
	│   ├── ip-172-31-17-147.us-west-2.compute.internal.json
	│   ├── ip-172-31-17-179.us-west-2.compute.internal.json
	│   ├── ip-172-31-19-152.us-west-2.compute.internal.json
	│   ├── ip-172-31-21-171.us-west-2.compute.internal.json
	│   ├── ip-172-31-29-30.us-west-2.compute.internal.json
	│   ├── localhost.json
	│   ├── rea.richmond.json
	│   ├── ubunto14.json
	│   ├── ubuntu-1604.json
	│   └── ubuntu.json
	├── pkgs
	└── README.md


- Instructions

	1.- Transfer tar.gz to you server (Read Requirement)
	2.- Untar source: 'tar xvfz ./reaRichmond.tar.gz'
	3.- Execute with administrative privilegies:

		./installRea.sh #User root
			or
		sudo ./reaInstaller.sh -a

	5.- Access the new web server http://your-server-ip
