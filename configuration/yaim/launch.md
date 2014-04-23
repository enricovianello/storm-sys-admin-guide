## Launching YAIM configuration

If you have defined your **storm.def** settings file, you're ready to launch YAIM to configure your services, as follow:

```bash
$ /opt/glite/yaim/bin/yaim -c -d 6 -s <site-info.def> -n <profile>
```

```-d``` option sets the log level.

If you need to configure more than a StoRM service on the same host, you have to provide **a unique storm.def** services file containing **all** the required YAIM variables. Then you can configure all service profiles at once with a single YAIM call:

```bash
$ /opt/glite/yaim/bin/yaim -c -d 6 -s /etc/storm/siteinfo/storm.def -n <profile_1> -n <profile_2> -n <profile_3>
```

where, for example, profile\_1 is ```se_storm_backend```, profile\_2 is ```se_storm_frontend``` and profile\_3 is ```se_storm_gridftp```.

> NOTE: if you need to configure both Backend and Frontend on the same host, you have to specify ```se_storm_backend``` before ```se_storm_frontend```. In short, Backend's profile needs to be the first of the list in case you are configure more than one services at once.

In case of a distributed deployment, you have to run yaim on each host involved, by specifying only the profiles of the installed components.
