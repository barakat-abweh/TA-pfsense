# Technology Add-on for pfsense
# modified version of Gmbh TA-pfsense
**Author:** Barakat Abweh

**Version:**

* 1.0

**Supported products:**

* pfsense >= 2.5.0

**Supported CIM Version:**

* &gt;=4.0.0

**Supported CIM Datamodels:**

* Authentication
* Network Traffic
* Network Session
* Intrusion Detection
* Network Resolution

**Sourcetypes:**

* `pfsense:filterlog`
* `pfsense:dhcpd`
* `pfsense:openvpn`
* `pfsense:nginx`
* `pfsense:unbound`
* `pfsense:*`

**Add-on contains:**

* Search and Parsing-Time configuration

**Input requirements:**

* This release requires pfsense to send data in syslog format
* Adjust pfsense sed replacements to remove duplicate timestamps / or set `no_appending_timestamp = true` in inputs.conf for udp input
