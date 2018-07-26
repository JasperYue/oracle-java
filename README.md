jasperyue.oracle-java for Ansible Galaxy
=========

## Summary

Role name in Ansible Galaxy: **[jasperyue.oracle-java](https://galaxy.ansible.com/jasperyue/oracle-java/)**

**This ansible role can be used to install java environment by using the java package end with tar.gz locally.**  
which is to say, you should download jdk package with the suffix of tar.gz from [oracle](http://www.oracle.com/technetwork/java/javase/downloads/index.html) in advance.

This ansible role has the following features for Oracle JDK:

 - Install JDK 7/8/9/10 or later version.
 - Install JDK or JRE or Server JRE
 - Install for CentOS 6/7

If you prefer OpenJDK, try alternatives such as [geerlingguy.java](https://galaxy.ansible.com/geerlingguy/java/) or [smola.java](https://galaxy.ansible.com/smola/java/).

If you prefer Oracle JDK download from offical site, try alternatives such as
[srsp.oracle-java](https://galaxy.ansible.com/srsp/oracle-java) or
[williamyeh.oracle-java](https://galaxy.ansible.com/williamyeh/oracle-java/)

Requirements
------------
min_ansible_version: 2.0

Role Variables
--------------

User-configurable defaults:

```yaml
# Absolute path JDK will be install to.
java_install_dir: "/opt"

# Which kind java you want to install, available list as follow:
# jdk: For Java Developers. Includes a complete JRE plus tools for developing, debugging, and monitoring Java applications.
# serverjre: For deploying Java applications on servers. Includes tools for JVM monitoring and tools commonly required for server applications, but does not include browser integration (the Java plug-in), auto-update, nor an installer.
# jre: Covers most end-users needs. Contains everything required to run Java applications on your system.
java_package: jdk

# In this case, java_version will be 8 and java_subversion will be 181
# jdk-8u181-linux-x64.tar.gz -> jdk-{{ java_version }}u{{ java_subversion }}-linux-x64.tar.gz
# In this case, java_version will be 10 and java_subversion will be 0.2
# jdk-10.0.2_linux-x64_bin.tar.gz -> jdk-{{ java_version }}.{{ java_subversion }}_linux-x64_bin.tar.gz
# Java primary version
java_version: 8

# Java sub version
java_subversion: 181

# Set as default if java has already installed
set_as_default: True
```

Example Playbook
----------------

```yaml
- hosts: all
  roles:
    - { role: jasper.oracle-java, java_version: 8, java_subversion: 171, java_install_dir: /opt}
```
License
-------

Licensed under the Apache License V2.0. See the [LICENSE file](LICENSE) for details.
