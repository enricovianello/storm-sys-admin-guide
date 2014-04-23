## Install StoRM nodes

In order to install StoRM components refresh the yum cache:

```bash
$ yum clean all
```

Install the StoRM metapackages you need in every node partecipating to the StoRM instance.

```bash
$ yum install emi-storm-backend-mp
   ...
$ yum install emi-storm-frontend-mp
   ...
$ yum install emi-storm-globus-gridftp-mp
   ...
$ yum install emi-storm-gridhttps-mp
   ...
```

The **storm-srm-client** is distributed with the UI EMI components, but if you need it on your node you can install it using the command:

```bash
$ yum install emi-storm-srm-client-mp
```

To verify StoRM services launch:

```bash
$ service storm-backend-server status
$ service storm-frontend-server status
$ service storm-globus-gridftp status
$ service storm-gridhttps-server status
```