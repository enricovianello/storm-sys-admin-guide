## Repository settings

In order to install all the stuff requested by StoRM, some repositories have to be necessarily configured in the ```/etc/yum.repos.d``` directory. 
These are EPEL, EGI and EMI and have to be installed, as prerequisite, as we have already seen in the paragraph [General EMI 3](../prerequisites/emi3instructions.html) installation instructions.

### Common repository settings

To install **EPEL Repository** download and install the EPEL release file.

SL5:

```bash
$ wget http://archives.fedoraproject.org/pub/epel/5/x86_64/epel-release-5-4.noarch.rpm
$ yum localinstall --nogpgcheck epel-release-5-4.noarch.rpm
```

SL6:

```bash    
$ wget http://www.nic.funet.fi/pub/mirrors/fedora.redhat.com/pub/epel/6/x86_64/epel-release-6-8.noarch.rpm
$ yum localinstall --nogpgcheck epel-release-6-8.noarch.rpm
```

To install **EGI Trust Anchors Repository** follow [EGI instructions](https://wiki.egi.eu/wiki/EGI_IGTF_Release#Using_YUM_package_management).

You must disable the **DAG repository** if enabled. To check if it is enabled:

```bash 
$ grep enabled /etc/yum.repos.d/dag.repo
 enabled=0
```

To disable the DAG repository, if needed, you must set to 0 the enabled property in your /etc/yum.repos.d/dag.repo file:

```bash
$ vi /etc/yum.repos.d/dag.repo
  ...
 enabled=0
  ...
```

### EMI Repository settings

To install **EMI repository** download and install the EMI release file:

SL5:

```bash
$ wget http://emisoft.web.cern.ch/emisoft/dist/EMI/3/sl5/x86_64/base/emi-release-3.0.0-2.el5.noarch.rpm
$ yum localinstall --nogpgcheck emi-release-3.0.0-2.el5.noarch.rpm
```

SL6:

```bash
$ wget http://emisoft.web.cern.ch/emisoft/dist/EMI/3/sl6/x86_64/base/emi-release-3.0.0-2.el6.noarch.rpm
$ yum localinstall --nogpgcheck emi-release-3.0.0-2.el6.noarch.rpm
```

### StoRM Repository settings

StoRM can also be installed from StoRM PT own repositories.
Note that the StoRM PT repositories only provide the latest version of the certified StoRM packages.
You still need to install EMI3 repositories (as detailed above) for installations to work as expected.

To install the repository files, run the following commands (as root):

SL5:

```bash
$ wget http://italiangrid.github.io/storm/repo/storm_sl5.repo -O /etc/yum.repos.d/storm_sl5.repo
```

SL6:

```bash
$ wget http://italiangrid.github.io/storm/repo/storm_sl6.repo -O /etc/yum.repos.d/storm_sl6.repo
```
