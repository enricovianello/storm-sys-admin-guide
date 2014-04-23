## Frontend configuration

Tab. 2 summarizes YAIM variables for StoRM Frontend component.

<div class="table-responsive">
    <table class="table table-hover small">
        <thead>
            <tr>
                <th class="col-sm-2">Var. Name</th>
                <th class="col-sm-6">Description</th>
                <th class="col-sm-2">Default</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>
                    <strong>ARGUS_PEPD_ENDPOINTS</strong>
                </td>
                <td>
                    The complete service endpoint of Argus PEP server. <span class="mandatory">Mandatory</span> if <strong>STORM_FE_USER_BLACKLISTING</strong> is true. 
                    <br/><i>Example:</i>
                    <code class="table-code">ARGUS_PEPD_ENDPOINTS="https://host.domain:8154/authz"</code>
                </td>
                <td>
                    <strong>-</strong>
                </td>
            </tr>
            <tr>
                <td>
                    <strong>STORM_BACKEND_REST<br/>_SERVICES_PORT</strong>
                </td>
                <td>
                    StoRM Backend server rest port.
                </td>
                <td>
                    <strong>9998</strong>
                </td>
            </tr>
            <tr>
                <td>
                    <strong>STORM_BE_XMLRPC_PATH</strong>
                </td>
                <td>
                    StoRM Backend XMLRPC server path.
                </td>
                <td>
                    <strong>/RPC2</strong>
                </td>
            </tr>
            <tr>
                <td>
                    <strong>STORM_BE_XMLRPC_PORT</strong>
                </td>
                <td>
                    StoRM Backend XMLRPC server port.
                </td>
                <td>
                    <strong>8080</strong>
                </td>
            </tr>
            <tr>
                <td>
                    <strong>STORM_BE_XMLRPC_TOKEN<span class="mandatory">\*</span></strong>
                </td>
                <td>
                    Token used in communication to the StoRM Backend.
                </td>
                <td>
                    <strong>-</strong>
                </td>
            </tr>
            <tr>
                <td>
                    <strong>STORM_CERT_DIR<span class="mandatory">\*</span></strong>
                </td>
                <td>
                    Host certificate directory for StoRM Frontend service.
                </td>
                <td>
                    <strong>/etc/grid-security/$STORM_USER</strong>
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
</div>


|   Var. Name                           |   Description |
|:--------------------------------------|:--------------|

|STORM\_CERT\_DIR                       |Host certificate directory for StoRM Frontend service. Optional variable. Default value: **/etc/grid-security/${STORM\_USER}**
|STORM\_DB\_HOST                        |Host for database connection. <br/>Optional variable. Default value: **localhost**
|STORM\_DB\_PWD                         |Password for database connection. **Mandatory**.
|STORM\_DB\_USER                        |User for database connection. Default value: **storm**
|STORM\_FE\_ENABLE\_MAPPING             |Enable the check in gridmapfile for client DN. <br/>Optional variable. Available values: true, false. Default value: **false**
|STORM\_FE\_ENABLE\_VOMSCHECK           |Enable the check in gridmapfile for client VOMS attributes. <br/>Optional variable. Available values: true, false. Default value: **false**
|STORM\_FE\_GSOAP\_MAXPENDING           |Max number of request pending in the GSOAP queue. Optional variable. Default value: **2000**
|STORM\_FE\_LOG\_FILE                   |StoRM frontend log file.<br/>Optional variable. Default value: **/var/log/storm/storm-frontend.log**
|STORM\_FE\_LOG\_LEVEL                  |StoRM Frontend log level.<br/>Optional variable. Available values: KNOWN, ERROR, WARNING, INFO, DEBUG, DEBUG2.<br/>Default value: **INFO**
|STORM\_FE\_MONITORING\_DETAILED        |Flag to enable/disable detailed SRM requests Monitoring. Optional variable. Available values: true, false. Default value: **false**
|STORM\_FE\_MONITORING\_ENABLED         |Flag to enable/disable SRM requests Monitoring.<br/>Optional variable. Available values: true, false. Default value: **true**
|STORM\_FE\_MONITORING\_TIME\_INTERVAL  |Time intervall in seconds between each Monitoring round. Optional variable. Default value: **60**
|STORM\_FE\_THREADS\_MAXPENDING         |Max number of request pending in the Threads queue. Optional variable. Default value: **200**
|STORM\_FE\_THREADS\_NUMBER             |Max number of threads to manage user's requests. Optional variable. Default value: **50**
|STORM\_FE\_USER\_BLACKLISTING          |Flag to enable/disable user blacklisting.<br/>Optional variable. Available values: true, false. Default value: **false**
|STORM\_FE\_WSDL                        |WSDL to be returned to a GET request.<br/>Optional variable. Default value: **/usr/share/wsdl/srm.v2.2.wsdl**
|STORM\_FRONTEND\_OVERWRITE             |This parameter tells YAIM to overwrite storm-frondend.conf configuration file.<br/>Optional variable. Available values: true, false. Default value: **true**
|STORM\_FRONTEND\_PORT                  |StoRM Frontend service port. Optional variable. Default value: **8444**
|STORM\_PEPC\_RESOURCEID                |Argus StoRM resource identifier. Optional variable. Default value: **storm**
|STORM\_PROXY\_HOME                     |Directory used to exchange proxies.<br/>Optional variable. Default value: **/etc/storm/tmp**
|STORM\_USER                            |Service user.<br/>Optional variable. Default value: **storm**

{% assign label_title="Table 2" %}
{% assign label_description="Specific StoRM Frontend Variables." %}
{% include documentation/label.html %}

**NOTE** - **_The following table contains the YAIM variables no more used from StoRM v.1.11.2_**:

|   Var. Name                   |   Description |
|:------------------------------|:--------------|
|STORM\_FE\_BE\_XMLRPC\_HOST    |**DELETED** It was used to tell to the Frontend the XMLRPC endpoint. But this endpoint, for the Frontend, is **always** the StoRM Backend hostname which value is already contained by STORM\_BACKEND\_HOST variable. So yaim now sets _be.xmlrpc.host_ frontend's variable with STORM\_BACKEND\_HOST.
|STORM\_FE\_BE\_XMLRPC\_PATH    |**RENAMED** into STORM\_BE\_XMLRPC\_PATH, see Table 2
|STORM\_FE\_BE\_XMLRPC\_PORT    |**RENAMED** into STORM\_BE\_XMLRPC\_PORT, see Table 2

{% assign label_title="Table 3" %}
{% assign label_description="YAIM variables no more used from StoRM v.1.11.2" %}
{% include documentation/label.html %}
