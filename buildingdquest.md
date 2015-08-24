# Building DQuest application #

This page teach you how to build an application using DQuest.

## Step 1 - Download the source code ##

You may download DQuest from source tarball or from launchpad (development code). As DQuest is still in alpha stage, it is recommended to get from launchpad which will have newest features and bug fixes.

Download from source tarball: ([Link](http://code.google.com/p/d-quest/downloads/list))

Checkout from launchpad:

- The source code of DQuest held in launchpad, you may get the source code by using Bazaar.

```
bzr branch lp:dquest 
```


## Step 2 - Build DQuest ##

It is an **_optional_** step. You don't really need to build DQuest library to link with your application. You could include it from source tree directly.

```
$ cd dquest/src
$ qmake
$ make INSTALL_ROOT=<the path your like> install
```

## Step 3 - Add dquest.pri into your project file ##

If you skipped the step 2 , you may add the following line to your .pro file.

```
include ($$DQUEST_PATH/src/dquest.pri)
```

Replace DQUEST\_PATH to the path of dquest source code, or pass it through qmake. It can be relative or absolute depend on your source tree.

If you have built and installed the library, you should add this line

```
include($$DQUEST_INSTALL_PATH/include/dquest.pri)
```

$$DQUEST\_INSTALL is the installation path of DQuest.

Then run qmake , then your application will able to build application with DQuest.

As you could see that , no matter what method is chosen , what you need is just to include dquest.pri into your project file.

**Next**
  * [Database model declaration](tutorial1.md)