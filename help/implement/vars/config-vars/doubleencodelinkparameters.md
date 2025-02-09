---
title: doubleEncodeLinkParameters
description: Enable or disable AppMeasurement double encoding link tracking variables.
exl-id: 7a4cea23-5ae6-4a8b-82a6-c68f9a1f9c49
---
# doubleEncodeLinkParameters

The `doubleEncodeLinkParameters` variable is a boolean that determines if link tracking variables get encoded once (if set to `false`) or twice (if set to `true`). It impacts only `linkName` (part of the [`tl()`](../functions/tl-method.md) method) and [`linkURL`](linkurl.md). It requires AppMeasurement 2.23.1 or higher to use. The default value of this variable is `true`.

In previous versions of AppMeasurement, link tracking variables were always URL encoded twice. While not an issue for implementations that typically rely on single-byte characters, the double encoding created incorrectly encoded values for multi-byte characters in reports. Setting this variable to `false` encodes link tracking values once, which is typically the desired behavior.

* If your implementation uses multi-byte characters and link tracking variables are URL decoded to offset AppMeasurement's double encoding, set this variable to `true`. This value preserves existing AppMeasurement functionality.
* If your implementation uses multi-byte characters and you do not URL decode link tracking values, Adobe recommends setting this variable to `false`.
* If your implementation does not use multi-byte characters, this variable is not required. However, Adobe recommends setting this variable to `false` in cases where multi-byte characters might be sent.

## Double encode link parameters using the Web SDK

This variable is specific to AppMeasurement, and is not needed in any type of Web SDK implementation.

## Double encode link parameters using the Adobe Analytics extension

There is not a dedicated field in the Adobe Analytics extension to use this variable. Use the custom code editor, following AppMeasurement syntax.

## s.doubleEncodeLinkParameters in AppMeasurement and the Analytics extension custom code editor

The `s.doubleEncodeLinkParameters` variable is a boolean that determines if link tracking values get double encoded. If this variable is not defined, its default value is `true` to preserve functionality for existing implementations. Adobe recommends setting this value to `false` for all new implementations, especially if you see URL encoded values in link tracking reports.

```js
s.doubleEncodeLinkParameters = false;
```
