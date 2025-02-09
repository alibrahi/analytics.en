---
description: Data that is collected from web sites, mobile apps, or is uploaded using web service APIs or data sources, is processed and stored in Adobe's Data Warehouse. This raw clickstream data forms the data set that is used by Adobe Analytics.
keywords: clickstream;data feed;datafeed;Data Feed
title: Analytics Data Feed overview
feature: Data Feeds
exl-id: 2cfff9ad-cdb5-4ae9-a266-4f3d3d046f0c
---
# Analytics Data Feed overview

>[!AVAILABILITY]
>
>Some of the destination types described on this page are in the Limited Testing phase of release and might not be available yet in your environment. This note will be removed when the functionality is generally available. For information about the Analytics release process, see [Adobe Analytics feature releases](/help/release-notes/releases.md).

Data feeds are a powerful way to get raw data out of Adobe Analytics. This raw data can be used in other platforms outside of Adobe to use at your organization's discretion. Data is delivered in hourly batches at the conclusion of each hour, or in daily batches at the conclusion of each day.

## Prerequisites

Make sure that you meet all the following requirements before using data feeds.

* A working implementation that sends data to Adobe data collection servers. See [Validate and publish an implementation](/help/implement/launch/validate-publish-prod.md) in the Implementation guide.
* Your account is an Analytics product admin, or your account belongs to a product profile with access to data feeds.
* A bucket configured on Amazon S3, Google Cloud Platform, Azure RBAC, or Azure SAS.
* (Legacy: Required only for legacy FTP and SFTP destination types) Have an FTP site and credentials handy (FTP credentials provided by your organization.)

## Recommended data feed resources

1. Log in to [experiencecloud.adobe.com](https://experiencecloud.adobe.com) using your Adobe ID credentials.
2. Click the 9-square icon in the upper right, then click the colored Analytics logo.
3. In the top navigation bar, navigate to Admin > Data feeds.
4. Click [!UICONTROL Add]. A new page appears with three main categories: [!UICONTROL Feed information], [!UICONTROL Destination], and [!UICONTROL Data Column Definitions].
5. Fill out [!UICONTROL Feed Information] fields.
   * Name: Any desired name, such as "Test data feed".
   * Report suite: Select the desired report suite.
   * Email when complete: Enter your email.
   * Feed interval: Select the desired interval (hourly or daily).
   * Delay processing: Can be left as [!UICONTROL No Delay].
   * Start & end dates: Select a start date from several days ago, and today as the end date.
6. Fill out [!UICONTROL Destination] fields.
   * Type: FTP
   * Host: Enter the desired FTP destination URL. For example, `ftp://ftp.omniture.com`.
   * Path: Can be left blank
   * Username: Enter the username to log in to the FTP site.
   * Password and confirm password: Enter the password to log in to the FTP site.
7. Fill out [!UICONTROL Data Column Definitions].
   * Select the latest 'All Adobe Columns' template in the drop-down list.
   * Compression format: Gzip
   * Packaging type: Multiple files
   * Manifest: No File
8. Click [!UICONTROL Save] in the top right.
9. Once saved, historical data processing begins. When data finishes processing for a day, the file is placed on the FTP site.
10. Log in to the FTP site using Windows Explorer or a dedicated FTP client.
11. Download the compressed data feed file to your local machine.
12. Unzip the compressed file using a program that supports `.tar.gz` file extensions.
13. Open the `hit_data.tsv` file in your spreadsheet or database application of choice to see raw data for that day.

## Next steps

Once you understand the basic workflow of obtaining data feeds, you can work with teams within your organization to store or ingest raw data into a database.

* [Data feed best practices](/help/export/analytics-data-feed/data-feeds-best-practices.md): Best practices for creating and managing data feeds.
* [Create a data feed](create-feed.md): Technical details for creating a data feed, explaining individual fields in more detail
* [Manage data feeds](df-manage-feeds.md): Learn more about navigating the data feed interface
* [Data feed contents](c-df-contents/datafeeds-contents.md): Understand what is inside the compressed file <!-- Is this still the output users can download from the destination? I aske Jun. -->
* [Data column definitions](c-df-contents/datafeeds-reference.md): A comprehensive list of all available columns.
* Video navigating the data feed interface:

  >[!VIDEO](https://video.tv.adobe.com/v/25452/?quality=12)

* Video on how to find your data feed ID:

  >[!VIDEO](https://video.tv.adobe.com/v/335747/?quality=12)