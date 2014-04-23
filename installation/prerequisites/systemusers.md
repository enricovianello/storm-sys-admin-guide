## System users and file limits

The StoRM Frontend and Backend services run by default as user **storm** (to 
change the default settings see [Backend Configuration]({{ basePath }}/configuration/)), while the StoRM GridHTTPs server runs as user **gridhttps** (see [GridHTTPs Configuration]({{ basePath }}/configuration/yaim/gridhttps) to learn how to configure it). 

It's recommended:
- to create StoRMs users before installing StoRM services;
- to set StoRM users' file limits properly.

### Create users

To create the default StoRM users, launch the following commands:

```bash
# add storm user (-M means without an home directory)
$ useradd -M storm
# add gridhttps user (specifying storm as group)
$ useradd gridhttps -M -G storm
```

If you need to specify particular user or group IDs:

```bash
$ useradd -M storm -u <MY_STORM_UID> -g <MY_STORM_GID>
$ useradd gridhttps -M -G storm -u <MY_GHTTPS_UID> -g <MY_GHTTPS_GID>
```

> Change the text contained in angled brackets with the appropriate
numerical value for your installation.

<span class="label label-info">Important</span><br/>
Keep UIDs and GIDs aligned for the StoRM users and groups on distributed deployments (i.e. when the services are installed on different machines). 
This can be done using NIS (see a tutorial [here](http://www.tldp.org/HOWTO/NIS-HOWTO/index.html)) or LDAP (see [this example](#TOFIX)).

### File limits

The following settings are recommended to safely run the StoRM services.  Put
these settings in ```/etc/security/limits.conf``` or in a '.conf' file contained in the directory ```/etc/security/limits.d``` (recommended):

```bash
# StoRM frontend and backend services
storm hard nofile 8192
storm soft nofile 8192
# StoRM GridHTTPs service
gridhttps hard nofile 65535
gridhttps soft nofile 65535
```

If you want to use the same user, for example ```storm```, for all the components, set its values higher.