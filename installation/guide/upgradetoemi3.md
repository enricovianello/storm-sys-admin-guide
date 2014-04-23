## Upgrading to EMI3

In order to upgrade your current version of StoRM from EMI1 or EMI2 to EMI3 you need to install the EMI3 repos.

Depending on your platform, download and install the correct EMI release package, as described in the [Repository settings](emireposettings.html) section.

Then execute:

```bash
$ yum clean all
$ yum -y update
```

> <span class="label label-danger">IMPORTANT!</span>
> 
> If you are upgrading a StoRM installation that runs on top of GPFS, be sure to install the **storm-native-libs-gpfs** package after the update has completed, issuing the following command:
> 
> ```bash
> $ yum install storm-native-libs-gpfs
> ```

From StoRM v.1.11.x the StoRM GridHTTPs server component doesn't need tomcat. Therefore, if you want to upgrade the storm-gridhttps-server component and you are not using tomcat for other purposes, after the installation you can remove it:

```bash
$ yum remove tomcat5
```

Please take a look at the [YAIM Configuration](../../configuration/yaim/README.html) and [Launching YAIM configuration](../../configuration/yaim/launch.html) sections for further details on how to configure StoRM services.