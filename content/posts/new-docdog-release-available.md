---
title: "New Docdog Release Available"
date: 2021-05-05T14:25:12+02:00
tldr: "DocDog 0.6 Beta is available"
draft: false
tags: [docdog]
---
I added a new release of docdog.
There are tons of new features that will make the developers live easier.
<!--more-->

For all of you, who did not know DocDog:
It creates RAML 1.0 files from existing Java and Spring Boot sources. This little Software is writen in Go by Swen Kalski (me) and can be found on GitHub.
https://github.com/skalski/docdog

Features

* make RAML 1.0 files including scheme from plain JAVA
* make RAML 1.0 files including scheme without using tags from Spring Boot
* understand deeper structures of java including Interfaces and implementations
* generated files can used in API Console without hassle
* can pipe to CLI for other cmd tools
* It's BETA so everything that happen is a feature :-)


Features of 0.6-BETA:
* better handling of SpringBoot
* SpringBoot use now @NotNull, @notblank, @NotEmtpy annotations for Objects
* SpringBoot uses now @ignore and @JsonIgnore annotations for Objects
* Detect abstract classes.
* Usage the abstract if they are implemented.
* Also ignore Interfaces
* Add Logo
* add new -print flag to allow print the pure RAML result to CLI for piping purposes
* add new Error handling to show the user on what source the parsing was failing including line number if possible


Bugfixes of 0.6-BETA:
* For Java and Springboot now the Packages are scanned to avoid using same-named Objects from different Packages.
* set json/body representation from type: to schema:
* fix detection of final vars in springBoot analysis


The Binaries can be found here:
https://github.com/skalski/docdog/releases/tag/0.6
