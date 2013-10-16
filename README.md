maestro-samples
===============

Sample Maestro templates

Download Sample Templates
-------------------------

The Maestro sample templates are available on Github. Either clone the repository or download a tarball.

```
git clone https://github.com/cloudsidekick/maestro-samples.git
```

or 

```
mkdir /tmp/maestro-samples
curl -L -o /tmp/maestro-samples.tar.gz https://github.com/cloudsidekick/maestro-samples/archive/master.tar.gz
tar -xvzf /tmp/maestro-samples.tar.gz -C /tmp/maestro-samples --strip-components=1
```

Setup Maestro Command Line Tools
--------------------------------

To import the sample templates into Maestro you will first need to have the command line tools installed. 

See the following documentation for the installation of the Maestro client tools...

http://docs.cloudsidekick.com/docs/maestro/client/maestro-client.html


Import Sample Templates
-----------------------

To import the sample templates, a template to install based on the directory name (-i parameter). The -A and -S parameters correspond to valid login credentials to cato/maestro. administrator will work as a default.

```
maestro-import-application-template -A apiuser -S apipass --url http://localhost:4001 --makeavailable -i /tmp/maestro-samples/vcloud-sample-1 --force
```

Now when you login to Maestro, the template will be available. 


Using Individual Samples
------------------------

Proceed with the instructions in the README in each template's directory for more information on how to proceed.

