Spark-Up
========
Spark-Up is a forthcoming toolkit for rapid deployment of varying Spark cluster
topologies using platform-agnostic infrastructure as code technologies. 

Spark-Up contains three components: 
* Packer VM image build configuration 
* Terraform Infrastructure-as-Code definitions
* Ansible provisioning scripts.

By splitting provisioning into a preparing static “baseline” virtual machine image and a runtime configuration step,
the cost of preparing new Spark clusters is reduced to approximately ten minutes.

Despite being designed around the OpenStack environment, the toolkit is still of use to other environments. Al-
though the Packer and Terraform configuration is tightly coupled to OpenStack out of necessity, porting to other
cloud environments should take no more than one or two hours. Finally, the Ansible scripting is designed for easy
reconfiguration – should it be necessary to use a nonstandard configuration, most relevant downstream parameters are
exposed as easily-overridable variables. Indeed, this project’s infrastructure uses this capability to create an asymmetrical
Spark/HDFS manager/worker configuration.
7

Flexible starter kit designed for non-production single-user use.

Watch this space: https://github.com/spark-up/spark-openstack


