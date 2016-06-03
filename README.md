*THIS IS A WORK IN PROGESS*
===========================

```
IBM Platform LSF is a powerful workload management platform for demanding, 
distributed HPC environments. It provides a comprehensive set of intelligent,
policy-driven scheduling features that enable you to utilise all of your 
compute infrastructure resources and ensure optimal application performance.

Obtaining job status is usually via poll based bjobs request. As clusters and
user numbers continue to grow, this process becomes limiting and not a 
practical programmitc interface for pipeline structures or workload management.

This script should provide job data directly from the lsb.stream file. All 
LSF status data is captured, along with job resource usage and requirements. 
```

Setup
=====

```
The lsf_log_watch.py script requires a host running LSF 9.x with read access 
to lsb.streams and the IBM platform python api installed. 

A functioning Rabbit AMQP server with configured accounts and basic queue 
in place. The AMQP setup is outside the scope here.

The platform python LSF api is available from here:
https://github.com/PlatformLSF/platform-python-lsf-api

Outside of basic modules the script also requires:

pika
pigtail
```

Recommened run methodology
==========================

Configure virtualenv
--------------------

```
Install virtualenv within your local environment and add the required python
lsf api, pika, etc modules

source and confirm that these work as expected with:

source <virtualenv_dir>/bin/activate

Edit lsf_log_watch.py to reflect local directories and AMQP server details

run ./lsf_log_watch.py &
```

Example reader
-----------------------

```
an example reader script is included. As above, first edit the relevant 
AMQP connection details and then run ./reader_example.py
```
