vCloud Sample Template
======================

This Maestro sample template provisions 3 server instances inside three Maestro services. It is very generic so that is can be used in a variety of vCloud installations. 

When the servers are provisioned, the Chef client is installed on each and a sample configuration file is written to the server. This could very easily be a Puppet install and additional software could be installed, configured, etc. For now we keep it simple. 

Prerequisites
-------------

A vCloud cloud account and endpoint must be configured prior to deploying this template. See the following link for information on setting up vCloud. 

http://docs.cloudsidekick.com/docs/cato/cloud/vcloud.html

The template in this directory must be imported into Maestro. See the README.md file in the main repo directory for information on importing Maestro templates.

Also, collect the following information from your vCloud vCenter application:

* A Virtual Datacenter name. This will be the datacenter where the virtual servers will be deployed.

* A Virtual Network name that dynamically assigns ip addresses that will be accessible via port 22 (ssh) from the Maestro server

* One or more linux vApp templates in an accessible vCloud Catalog.


vCloud Template Configuration
-----------------------------

The vCloud Sample Template must be configured slightly to work in your vCloud environment. Follow the steps below to perform this configuration. 

1. Login to the Cato application (default port 8082) and navigate to Maestro, Application Template in the menu. Edit "vCloud Sample Template" by clicking on the row.

2. In the template editor, expand the "Data" node and change the values for "datacenter" and "netname" from the Prerequisites section.

3. Expand the "Services" section. Under each of the defined services (named Service A, Service B and Service C) there is a "Data" section. Expand each data section and change the value for "vapptemplatename". The vapptemplatename will correspond to a linux vapp template found in one of the vCloud catalogs. For each service, you can elect to use the same vApp template or different one. However for this example they must be linux.

4. Click the Save button in the upper right corner of the template editor.


Starting a Deployment
---------------------

Once the template has been configured and the prerequisites done you can now login to Maestro (default port 8080) and select the template from the App Store. Click the Deploy button, then Submit. On the Sequence - Start dialogue that appears, select your vCloud cloud endpoint from the drop down list and click Submit. 

The Start Sequence log page will appear and will proceed through the steps to create the virtual servers, retrieve their ip addresses, login via ssh and configure the servers. Clicking on one of the boxes, then the Task Instance row will pop up the individual task logs for review. 

When the Start Sequence is complete, make sure to Terminate the deployment. 
