---
title: Compare implementation methods
description: See the advantages of each method sending data to Adobe Analytics.
exl-id: 19353255-6356-4426-a2ef-5a2672a00eca
---
# Compare implementation methods

See how each method of implementing Adobe Analytics compares to each other. You can use this table to help your organization determine the most ideal way to send data to Adobe.

| | AppMeasurement | Adobe Analytics extension | Web SDK | Web SDK extension |
| --- | --- | --- | --- | --- |
| Implementation requirements | Reference `AppMeasurement.js` on each page, define variables, send data using `s.t()` | Reference tag loader on each page, use the Data Collection UI to define variables and send data to Adobe | Reference `Alloy.js` on each page, use `alloy("sendEvent",{})` to send a JSON object containing the desired data | Reference tag loader on each page, use the Data Collection UI to establish the JSON object to send data |
| Data destination | Sent directly to Adobe Analytics | Sent directly to Adobe Analytics | Sent to Adobe Experience Platform Edge, which forwards data to Adobe Analytics | Sent to Adobe Experience Platform Edge, which forwards data to Adobe Analytics |
| Difficulty making implementation adjustments | Requires access to website code for every implementation change | Change the website code once to install the loader tag; all further implementation updates can be made in the Data Collection UI | Requires access to website code for every implementation change | Change the website code once to install the loader tag; all further implementation updates can be made in the Data Collection UI |
| How A4T is handled | A4T calls are included in hits sent to Adobe | A4T calls are included in hits sent to Adobe | A4T calls are sent as separate hits | A4T calls are sent as separate hits |
| Context Data | Use `s.contextData`. | Use `s.contextData` in custom code blocks | All unmapped fields are automatically sent as `a.x.*` context data variables. | All unmapped fields are automatically sent as `a.x.*` context data variables. |

{style="table-layout:auto"}
