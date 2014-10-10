Ansible-Kibana Role
===================
[![Build Status](https://travis-ci.org/yetu/ansible-kibana.svg?branch=master)](https://travis-ci.org/yetu/ansible-kibana)

[Kibana](http://www.elasticsearch.org/overview/kibana/) is an open source (Apache Licensed), browser based analytics and search dashboard for ElasticSearch.

Requirements
------------

 - tested on Ubuntu 12.04 and should work with others as well


Philosophy
---------

The role is designed to work without setting any variables. For flexibility nginx and ElasticSearch are not installed and not set in meta requirements.

Role Variables
--------------

### Defaults

The role has default value that should work without modification unless you want to

kibana version to install

	kibana_version          : "3.1.0" 	

Where to install kibabana

	kibana_base_dir         : "/opt/kibana"	

Elastic search server to use (by default the deployed server)

	es_host                 : http://{{ansible_hostname}}

nginx fqdn if your using my nginx role this will be used (by default the deployed server)

	kibana_fqdn             : "{{ansible_hostname}}"


#### Dashboards

You can deploy your dashboard as follow. 

To deploy dashboards 

	kibana_dashboard_inst   : true

Setup names and files of an array of dashboards

	kibana_dashboards :
                         - name: nginx.json
                           src : nginx.json 

                         - name: cool.json
                           src: /mnt/mydash/example.json



It is ideal to persist dashboards in a git repository.


Dependencies
------------
Dependecies are not enforced by the role and left for you to manage

* Nginx 
* Elasticsearch 



