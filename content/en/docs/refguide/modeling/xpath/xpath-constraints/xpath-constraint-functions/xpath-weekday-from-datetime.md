---
title: "XPath weekday-from-dateTime"
url: /refguide/xpath-weekday-from-datetime/
tags: ["studio pro"]
---

## 1 Overview

The `weekday-from-dateTime()` function extracts the day of the week (as a number) from a **Date and time** attribute so it can be used to compare to a value. For running locally and deployment using a PostgreSQL database, such as that used in the Mendix Cloud, the values range from 1 to 7 (1 = Sunday, 7 = Saturday).

{{% alert color="warning" %}}
The range of values returned, and the day of the week corresponding to the lowest value returned depend on which database you are using.
{{% /alert %}}

## 2 Syntax

The syntax is as follows:

```
weekday-from-dateTime ( attribute [, timezone ] )
```

### 2.1 attribute

`attribute` specifies the attribute to extract the day from. Attribute must be of the **Date and time** type.

### 2.2 timezone

{{% alert color="info" %}}
The optional `timezone` parameter is available in [Studio Pro 9.22.0](/releasenotes/studio-pro/9.22/) and above. 
{{% /alert %}}

`timezone` specifies the time zone to use for the extraction. This parameter is optional and defaults to the local time zone. It should be a string literal containing an IANA time zone or `'UTC'`. GMT offset time zones are not supported.

## 3 Examples

This query returns all the logs where the day of the week in `DateAttribute` is 6 in the local time zone (Friday, for locally run apps or apps using a PostgreSQL database):

```java {linenos=false}
//Logging.Log[weekday-from-dateTime(DateAttribute) = 6]
```

This query returns all the logs where the day of the week in `DateAttribute` is 6 in the New York time zone (Friday, for locally run apps or apps using a PostgreSQL database):

```java {linenos=false}
//Logging.Log[weekday-from-dateTime(DateAttribute, 'America/New_York') = 6]
```
