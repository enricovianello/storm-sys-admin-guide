## General YAIM variables

There are some YAIM variables that are used to configure more than one service, different from StoRM ones. These _general_ variables are summarized in Tab.1. 

Edit your **storm.def** file by providing a value to these general YAIM variables:

<div class="table-responsive">
	<table class="table table-hover small">
		<thead>
			<tr>
				<th class="col-sm-3">Var. Name</th>
				<th class="col-sm-6">Description</th>
				<th class="col-sm-1">Default</th>
			</tr>
		</thead>
		<tbody>
			<tr>
				<td>
					<strong>SITE_NAME<span class="mandatory">\*</span></strong>
				</td>
				<td>
					It's the human-readable name of your site used to set the Glue-SiteName attribute.
					<br/><i>Example:</i>
					<code class="table-code">SITE_NAME="INFN EMI TESTBED"</code>
				</td>
				<td class="text-center">
					<strong>-</strong>
				</td>
			</tr>
			<tr>
				<td>
					<strong>BDII_HOST<span class="mandatory">\*</span></strong>
				</td>
				<td>
					BDII hostname. 
					<br/><i>Example:</i>
					<code class="table-code">BDII_HOST="emitb-bdii-site.cern.ch"</code>
				</td>
				<td class="text-center">
					<strong>-</strong>
				</td>
			</tr>
			<tr>
				<td>
					<strong>JAVA_LOCATION</strong>
				</td>
				<td>
					Sets JAVA_HOME environment variable to its value. <span class="mandatory">Mandatory</span> if JAVA_HOME is not set.
					<br/><i>Example for SL5:</i><br/>
					<code class="table-code">JAVA_LOCATION="/usr/lib/jvm/java-1.6.0-openjdk-1.6.0.0.x86_64/jre"</code>
					<br/><i>Example for SL6 and >SL5.9:</i><br/>
					<code class="table-code">JAVA_LOCATION=/usr/lib/jvm/java</code>
				</td>
				<td class="text-center">
					<strong>-</strong>
				</td>
			</tr>
			<tr>
				<td>
					<strong>NTP_HOSTS_IP<span class="mandatory">\*</span></strong>
				</td>
				<td>
					Space separeted list of the IP addresses of the NTP servers (preferably set a local ntp server and a public one, e.g. pool.ntp.org).
					<br/><i>Example:</i>
					<code class="table-code">NTP_HOSTS_IP="131.154.1.103"</code>
				</td>
				<td class="text-center">
					<strong>-</strong>
				</td>
			</tr>
			<tr>
				<td>
					<strong>USERS_CONF<span class="mandatory">\*</span></strong>
				</td>
				<td>
					Path to the file containing the pool account of Linux users that have to be created (a plain list of the users and their IDs). This file must be defined by the site administrator. An example of this configuration file is provided at <code>/opt/glite/yaim/examples/users.conf</code>. More details can be found in the User configuration section in the YAIM guide.
				</td>
				<td class="text-center">
					<strong>-</strong>
				</td>
			</tr>
			<tr>
				<td>
					<strong>GROUPS_CONF<span class="mandatory">\*</span></strong>
				</td>
				<td>
					Path to the file containing information on the mapping between VOMS groups and roles to local groups. An example of this configuration file is given in <code>/opt/glite/yaim/examples/groups.conf</code>.
					More details can be found in the Group configuration section in the YAIM guide.
				</td>
				<td class="text-center">
					<strong>-</strong>
				</td>
			</tr>
			<tr>
				<td>
					<strong>MYSQL_PASSWORD<span class="mandatory">\*</span></strong>
				</td>
				<td>
					MySQL root password.
				</td>
				<td class="text-center">
					<strong>-</strong>
				</td>
			</tr>
			<tr>
				<td>
					<strong>VOS<span class="mandatory">\*</span></strong>
				</td>
				<td>
					List of supported VOs.
					<br/><i>Example:</i>
					<code class="table-code">VOS="testers.eu-emi.eu dteam"</code>
				</td>
				<td class="text-center">
					<strong>-</strong>
				</td>
			</tr>
		</tbody>
		<tfoot>
			<tr>
				<td colspan="3">
					<span class="mandatory very-small">* mandatory variables</span>
				</td>
			</tr>
		</tfoot>
	</table>
	<div class="col-md-12 text-center table-caption">
		<p>
			<strong>Table 1</strong>: General YAIM Variables.
		</p>
	</div>
</div>


If you have a distributed scenario, these general variables *must* be defined on each **storm.def** file of each host involved.

|STORM\_BE\_XMLRPC\_TOKEN   |Token used in communication to the StoRM Backend | Yes


