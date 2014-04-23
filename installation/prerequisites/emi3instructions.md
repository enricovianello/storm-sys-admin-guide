## General EMI 3

Official releases are done in the contest of the EMI project so follow the [general EMI 3 installation instructions](https://twiki.cern.ch/twiki/bin/view/EMI/GenericInstallationConfigurationEMI3) as first installation prerequisite.

In particular, check the followings:

1. [**NTP** service must be installed, running and started at boot](#p1)
2. [**hostname** must be a FQDN](#p2)
3. [host must have a valid **X.509 certificate**](#p3)



### 1. NTP service must be installed, running and started at boot <a href="#" name="p1"></a>

Check if ntp rpm is installed:

```bash
$ rpm -qa | grep ntp-
ntp-4.2.2p1-9.el5_4.1
```

If it's already installed, check if ntpd service is started at boot:

```bash
$ chkconfig --list | grep ntpd
ntpd            0:off   1:off   2:on    3:on    4:on    5:on    6:off
```
	
If it's not installed, run:

```bash
$ yum install ntp
$ chkconfig ntpd on
$ service ntpd restart
```

### 2. Hostname must be a FQDN <a href="#" name="p2"></a>

Hostname must be a *Fully Qualified Domain Name* (FQDN).

To check, run:

```bash
$ hostname -f
```

The command must return the FQDN.

If it doesn't, unless you are using bind or NIS for host lookups, you can change the FQDN and the DNS domain name, which is part of the FQDN, in the ```/etc/hosts``` file.

```bash
$ cat /etc/hosts

# Do not remove the following line, or various programs
# that require network functionality will fail.
127.0.0.1       MYHOSTNAME.MYDOMAIN MYHOSTNAME localhost.localdomain localhost
::1             localhost6.localdomain6 localhost6
```

Set your own ```MYHOSTNAME``` and ```MYDOMAIN``` and restart the network service:

```bash
$ service network restart
```

### 3. Host must have a valid X.509 certificate <a href="#" name="p3"></a>

Hosts participating to the StoRM-SE (which means hosts that run Frontend or Backend, GridHTTPs or GridFTP services) must be configured with X.509 certificates signed by a trusted Certification Authority (CA). 
Usually, the **hostcert.pem** and **hostkey.pem** certificates are located in the ```/etc/grid-security/``` directory, and they must have permission 0644 and 0400 respectively. Check their existence and permissions as follow:


```bash
$ ls -l /etc/grid-security/hostkey.pem
-r-------- 1 root root 887 Mar  1 17:08 /etc/grid-security/hostkey.pem
$ ls -l /etc/grid-security/hostcert.pem
-rw-r--r-- 1 root root 1440 Mar  1 17:08 /etc/grid-security/hostcert.pem
$ openssl x509 -checkend 0 -in hostcert.pem
```

If you need to set the correct permissions, run:

```bash
$ chmod 0400 /etc/grid-security/hostkey.pem
$ chmod 0644 /etc/grid-security/hostcert.pem
```
