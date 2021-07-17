# Technology Add-on for pfsense

**Author:** Barakat A. B. Abweh

**Version:**

* 2.0.0

**Supported products:**

* pfsense >= 2.5.0

**Supported CIM Version:**

* &gt;=4.0.0

**Supported CIM Datamodels:**

* Authentication
* Network Traffic

**Sourcetypes:**

* `pfsense:filterlog`
* * `pfsense:filterdns`
* `pfsense:dhcpd`
* `pfsense:openvpn`
* `pfsense:nginx`
* `pfsense:unbound`
* `pfsense:snort`
* `pfsense:suricata`
* `pfsense:*`

**Add-on contains:**

* Search and Parsing-Time configuration

**Input requirements:**

* This release requires pfsense to send data in syslog format
* Adjust pfsense sed replacements to remove duplicate timestamps / or set `no_appending_timestamp = true` in inputs.conf for udp input

## Using this Technology Add-on

* The add-on has to be installed on both indexers & Search Heads
* If data is collected through Intermediate Heavy Forwarders, it has to be installed on Heavy Forwarders, otherwise on indexers
* The add-on expects an initial sourcetype named `pfsense`, the sourcetype will be transformed into more specific ones (see sourcetype list)
* A sample `inputs.conf` is provided (`default/inputs.conf.sample`)

## Compatibility

* Compatible with pfsense 2.5.0 or higher

## Release Notes

* **2.0.0 / 2021-07-18**
