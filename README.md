# BPD Firebase

## Description

This is a storage repository for data from the Boston Police Department.

### Purpose

The City of Boston provides incident data to the public, but the delivery method
is so ridiculously obtuse that they cannot possibly be hoping anyone will use it.

In 2019, the office of Suffolk County District Attorney Rachel Rollins made
a request to Code for Boston to create a means of visualizing the incident data
that could be made available to the public. In response, a Code for Boston team
built a [project](https://github.com/filipemir/police-incident-dashboard-react) in
ReactJS which does exactly that. You can [use it right now](https://filipemir.github.io/police-incident-dashboard-react/).

However, one issue we noticed during development was that visualization and filtering
capabilities are somewhat limited. There are over 80 different Incident Groups, and no way
to group them together in any meaningful way, other than to manually select all the ones you want. Also, the app has very limited timeframe options: 1 day, 7 days, or 30 days. And while
you can filter incidents by district, you can't search geographically. Even though GPS data is provided for each incident.

All these limitations come from two basic facts:

- The current project consists entirely of a client-based application
- The underlying data provided by BPD is appallingly difficult to use

### Solution

By creating a Firebase storage container that updates as often as the BPD data (every 24 hours), we will be able to process and analyze the incident data in a less limited fashion.
Hopefully, this can provide the public with a better understanding of what is happening in
their community, and how their taxes are being spent.
