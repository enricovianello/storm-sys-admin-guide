# YAIM Configuration

StoRM services are usually configured via YAIM-StoRM component (a set of configuration scripts that read a set of configuration files), by providing a file with a list of configuration variables. 

YAIM StoRM is currently the most used way to configure StoRM services. 
See [Advanced Configuration](../advanced/README.html) section if you need to tune your configuration by editing the specific configuration files.

YAIM-StoRM is installed as dependencies for each StoRM component.
It adds functions and configuration files to YAIM service, useful to configure StoRM services.
For example, it adds the default _profile_ files for each service. They are located in ```/opt/glite/yaim/defaults``` and are the followings:
- ```se_storm_backend.pre```, 
- ```se_storm_frontend.pre```, 
- ```se_storm_gridftp.pre``` and 
- ```se_storm_gridhttps.pre```.
They contain the default values for the YAIM variables used to configure the StoRM services.
Other examples of configuration files (one for each service) are located in ```/opt/glite/yaim/examples/siteinfo/services/```.

How it works? The recommended way to use YAIM configuration is:
- don't modify the default profile files;
- write a unique site configuration file, **storm.def**, and set the values for the YAIM variables that you need to modify, for each service installed;
- launch ```/opt/glite/yaim/bin/yaim``` passing the settings file **storm.def** by using the ```-s``` option and specifying the profile names of the storm services that you need to configure. See [Launching YAIM configuration](launch.html) for further details.

><span class="label label-danger">IMPORTANT!</span>
>
>From here on, we will assume that to configure StoRM services via YAIM StoRM we will use a settings file, named **storm.def**, located into ```/etc/storm/siteinfo``` directory. 