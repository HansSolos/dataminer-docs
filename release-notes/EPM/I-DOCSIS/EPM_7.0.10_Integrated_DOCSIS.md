---
uid: EPM_7.0.10_Integrated_DOCSIS
---

# EPM 7.0.10 Integrated DOCSIS - Preview

> [!IMPORTANT]
> We are still working on this release. Release notes may still be modified, added, or moved to a later release. Check back soon for updates!

## New features

#### New dashboard to monitor whether KPI exceeds threshold for specific period [ID 42406]

A new dashboard is now available with the name *US FN Breach Report (OFDMA)* and *US FN Breach Report (SC-QAM)*. It allows you to monitor whether a KPI is higher than a specific threshold for a specific period of time. It makes use a of new ad hoc data source (*EPM_I_DOCSIS_GQI_GET_BREACH_DATA*) that reports the fiber nodes that breached a threshold for a specific number of months in a row. This is checked in weekly increments. This means that if for example a month is selected, the dashboard will check whether for that period of time (i.e. a month), the threshold was breached at least once every week.

## Changes

### Enhancements

#### Cisco CBR-8 CCAP UTSC: Improved management of FTP settings to prevent data loss [ID 43203]

Up to now, after a reboot or software upgrade of the device , the Cisco CBR-8 CCAP UTSC connector removed FTP settings available in the *PNM Bulk Data Transfer Configuration Table* (SNMP OID: 1.3.6.1.4.1.4491.2.1.27.1.1.3.1). However, these define the destinations for telemetry data generated by the CCAP, including details about the PNM UTSC tests supported by this solution. This means that data could be lost after a reboot or upgrade.

To prevent this, the connector will now store and sync the FTP settings, ensuring they are always backed up and restored by DataMiner. If a reboot or upgrade happens, the settings stored in the UTSC element will automatically be pushed to the CCAP again.

In addition, users will now be able to configure the *PNM Bulk Data Transfer Configuration Table* directly from the CCAP UTSC element.

#### Cisco CBR-8 CCAP UTSC/Generic SFTP Client: Improved spectrum capture process [ID 43237]

Previously, when processing spectrum traces using the connectors Cisco CBR-8 CCAP UTSC and Generic SFTP Client, it could occur that it was not clear when all trace results were processed. To improve this, after a capture is triggered, the element using the Cisco CBR-8 CCAP UTSC connector will now wait for the duration that combines the configured free run duration, the repeat period, and a configurable delay. This will ensure that every capture file is safely written to the local storage on the DataMiner Agent where the spectrum capture was taken.
