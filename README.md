# Technology Add-on for pfsense

**Original Author:** Barakat A. B. Abweh
**Updated by:**  W. Scott Howard

**Version:**

* 3.0.0

**Supported products:**

* pfsense >= 2.5.0

**Supported CIM Version:**

* &gt;=4.0.0

**Supported CIM Datamodels:**

* Authentication
* Network Traffic

**Sourcetypes:**

* `pfsense:filterlog`
* `pfsense:filterdns`
* `pfsense:dhcpd`
* `pfsense:kea-dhcp4`
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
* Another way to ingest the logs is to send them to a syslog server and then send them using the universal forwarder with the sourcetype `pfsense`

## Extra Inputs
* Use syslog-ng package to send pfblockerng-devel logs to splunk
* ![image](https://github.com/user-attachments/assets/fce5fb20-d2f5-47a9-be07-30e7e354a5ae)
* ![image](https://github.com/user-attachments/assets/63c32996-d5bf-4cc7-b384-bcd9d4a1347e)
* ![image](https://github.com/user-attachments/assets/c4ddd605-6f05-479f-8c73-aeaa2849c9f1)
* ![image](https://github.com/user-attachments/assets/da246111-4c51-4699-8f7f-2738d31f39b2)
* ![image](https://github.com/user-attachments/assets/8b23fea8-1929-4dbe-8313-f757bca55e5e)
* ![image](https://github.com/user-attachments/assets/c1dc1c58-fa2e-4a03-8636-f626bf872147)

## IDS/IPS Action
* Since IDS/IPS action is not found in snort's logs and also the action can be modified manually, I added a new lookup file to use for action based on the SID. So please make sure to update the lookup file based on your ruleset action
  * sid,interface_name,interface_description,action
  * xxx,lan(re0),lan,alert
 

## steps
* Log in to your firewall
* Go to Services->snort->interface and configure the IDS/IPS to work in inline mode
* Go to Services->snort->interface->interface_rules and modify the rules action based on your needs
* After that update the lookup file to match the sid,action pairs and the lookup will automatically work
* ![image](https://github.com/user-attachments/assets/a6e4939f-60a9-4de5-a9b2-967d53e4fe33)
  

## Compatibility

* Compatible with pfsense 23.09.01 or higher  (Not tested on older versions)

## Release Notes

* **2.0.0 / 2021-07-18**
* **3.0.0 / 2024-06-11**
