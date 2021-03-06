OpenShift - Tomcat DIY - QuickStart [![Build Status](https://travis-ci.org/engapa/openshift-tomcat-diy-quickstart.png)](https://travis-ci.org/engapa/openshift-tomcat-diy-quickstart)
===================================
***

This git repository helps you get up and running quickly with a Tomcat 7.0.42 installation on OpenShift.

Create the server by RHC client
-------------------------------

<a href="https://broker.ose.hi.inet/">Create an account</a> and install the <a href="https://www.openshift.com/get-started">command-line client tools</a>.

Create a DIY application using **from-code** option:

    rhc app create -a tomcat -t diy-0.1 --from-code "https://github.com/engapa/openshift-tomcat-DIY-quickstart.git"

That's it, you can now checkout your tomcat at:
    http://tomcat-$yournamespace.rhcloud.com

The default managing account is **tomcat/tomcat**; this can be changed by altering the 
start action hook file, committing the change within your secure OpenShift
Git account and issuing another <code>git push</code>.

Create the server from web console
----------------------------------

Add this entry to file /etc/openshift/quickstarts.json in broker host :

```json
{"quickstart": {
    "id":"4",
    "href":"https://broker.ose.hi.inet/quickstarts/apache-tomcat",
    "name":"PDI - Apache Tomcat",
    "summary":"Apache Tomcat server on OpenShift.",
    "body":"Apache Tomcat server on OpenShift.",
    "cartridges":"diy-0.1",
    "website":"http://tomcat.apache.org/",
    "language":"Java",
    "tags":"tomcat, server, web",
    "initial_git_url":"https://github.com/engapa/openshift-tomcat-DIY-quickstart.git",
    "provider":"PDI",
    "admin_tags":[]
  }}
```

An <a href="https://broker.ose.hi.inet/console/application_types/quickstart!4">item for this QuickStart</a> should be appear in OpenShift web console. You must to provide the name of this application only.

License
-------
This code is dedicated to the PDI domain

