# Server Outage Incident report
> By Omolayo Temitayo (Sam-Rytech)

![](https://t3.ftcdn.net/jpg/04/92/09/72/240_F_492097246_yagE8x9Uk8M9IekPy7GBuE0x1Uoa7esD.jpg)

## Issue Summary
![](https://www.cienotes.com/wp-content/uploads/2019/07/summaryblackboard.jpg)

On May 10th, 2023 at 3:00 PM GMT + 1, users began experiencing intermittent issues accessing our web stack debugging platform. The outage lasted for approximately 2 hours and affected 80% of our users. During the outage, users were unable to access the platform, and those who could experienced significant latency and error messages

## Timeline (all time in GMT + 1)
![](https://www.ncbar.org/wp-content/uploads/2022/02/Timeline-Visual-300x145.png)

| Time (GMT + 1) | Actions |
| -------------- | -------- |
|3:00 PM | The issue was first detected when monitoring tools reported increased latency and error rates |
|3:05 PM | The on-call engineer was paged and began investigating the issue|
|3:10 PM | The engineer attempted to restart the web server but was unsuccessful in restoring service |
|3:20 PM | The engineer escalated the issue to the development team, who began investigating potential root causes |
|3:30 PM | The team began investigating the database, suspecting it may be causing the issue |
|3:40 PM | The team discovered a large number of connections were being opened and not closed, causing the database to become overwhelmed and unresponsive |
|4:00 PM | The team made adjustments to the connection pool settings to better manage database connections, which immediately restored service to the platform |
|4:30 PM | The development team implemented additional monitoring and alerting to detect similar issues in the future |


## Root cause
![](https://blog.systemsengineering.com/hs-fs/hubfs/blog-files/Root%20Cause.jpg?width=600&name=Root%20Cause.jpg)

The root cause of the outage was identified as an issue with the database connection pool settings. The connection pool was configured to allow an unlimited number of connections, resulting in a large number of open connections that were not being closed. This caused the database to become overwhelmed and unresponsive, resulting in the platform outage.

To resolve the issue, the development team adjusted the connection pool settings to better manage database connections. This immediately restored service to the platform.

## Preventive measures
![](https://cdn-ccchn.nitrocdn.com/eoxXytShChgscESECFYcqdYPaOaOGMwn/assets/images/optimized/rev-fbc0c0e/wp-content/uploads/2021/06/prevent-incidents.png)

To prevent similar issues from occurring in the future, the development team implemented additional monitoring and alerting to detect similar issues. They also put in place strict database connection limits to prevent an overload of connections.
