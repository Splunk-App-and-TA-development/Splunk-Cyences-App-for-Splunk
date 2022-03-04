---
layout: default
title: Windows Defender
permalink: /configuration/data_onboarding/windows_defender/
nav_order: 6
parent: Data Onboarding
grand_parent: Configuration
---


## **Windows Defender**

To collect the Windows defender data, we'll be using below input stanza to collect the data. This data collection requires [TA for Microsoft Windows Defender](https://splunkbase.splunk.com/app/3734/) for data parsing and field extraction. 

Enable the input stanzas below for the Microsoft Windows Defender TA. Both stanzas are located in the inputs.conf file (create a local directory if necessary): 

    [WinEventLog://Microsoft-Windows-Windows Defender/Operational] 
    index = windefender 
    disabled = 0 
    renderXml = 1 

**Note:** Windows Defender logs are only tested in XML format (see renderXml = 1 in inputs.conf stanza).

## Estimated Data Size
The estimated data size depends on the number of hosts that are sending Windows Defender data. 

* Events: 150-300 per Windows machine (daily) 
* Licensing: < 5MB per Windows machine (daily)