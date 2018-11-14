Ambari
====

* Dashboard gives you overview of cluster health
* Useable, dynamic and customisable front end
* Primarily used for installing Hadoop
  * Can set up Ambari on the master node, and install from there

## Services

* Lists all the services
* Also lists the config files for these services

## Hosts

* Lets you drill into each host in your cluster
* See what each host is doing
* Can remotely restart hosts if they are having issues

## Alerts

* Emails you when there are impending failures
* Can tailor these to really minimise false positives
  * They can fire on trends or specific machine failures

## Admin

* General administration panel
* It is good to log in to Ambari as 'admin' instead instead of maria_dev
  * Solves permission issues
* Open command line as maria_dev and change to root

`$ su root`

* Then reset the standard Ambari admin password

`$ ambari-admin-password-reset`

* This does the following
  * Resets the password for admin
  * Restarts Ambari and logs you in as admin
* Permissions for running certain tasks should now not present issues

## The Grid

* Lists different views of the HDFS system:
  * Files
  * Hive
  * Pig
  * Storm
  * Tez
