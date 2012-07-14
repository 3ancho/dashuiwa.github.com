--- 
layout: post
title: Working with sencha touch 2 on OS X 10.6
tags: 
---
I failed many time to install the SDK tools for sencha touch 2. To clarify,
SDK tools is just some command line tools which accelerates the dev process.
Kinda like scaffolding in Ruby. SDK tools will be installed by a installer.
That is different from the actual package, which is a zip file downloaded. At
the time of writing, the extracted folder name is sencha-touch-2.0.1.1.

Ok, my first problem is: Unknown error running post-install step. Installation
may not complete correctly

Solution: Add following to zshrc (I am using zsh) export
PATH=/Applications/SenchaSDKTools-2.0.0-beta3/:$PATH export
PATH=/Applications/SenchaSDKTools-2.0.0-beta3/command:$PATH export
PATH=/Applications/SenchaSDKTools-2.0.0-beta3/jsbuilder:$PATH export
PATH=/Applications/SenchaSDKTools-2.0.0-beta3/appbuilder:$PATH

Second problem: [ERROR] Sencha SDK Tools 2.0.0-beta3 cannot be found from your
system (SENCHA_SDK_TOOLS_2_0_0_BETA3 environment variable is not set). Please
download and install version "2.0.0-beta3" of the tools from
[http://www.sencha.com/products/sdk-tools](http://www.sencha.com/products/sdk-
tools) . Close this terminal and open a new one after the installation is
complete.

Solution: Add following to zshrc (again) export
SENCHA_SDK_TOOLS_2_0_0_BETA3=/Applications/SenchaSDKTools-2.0.0-beta3/

For bash, may add those environment variables to the corresponding rc file.

Reference: [http://www.sencha.com/forum/showthread.php?200583-Couldn-t
-install-SDK-Tools-2.0.0-beta3-on-OSX&p=824752#post824752](http://www.sencha.c
om/forum/showthread.php?200583-Couldn-t-install-SDK-Tools-2.0.0-beta3-on-
OSX&p=824752#post824752) [http://www.sencha.com/forum/showthread.php?190083
-Unknown-error-running-post-install-step.-Installation-may-not-complete-
correctly](http://www.sencha.com/forum/showthread.php?190083-Unknown-error-
running-post-install-step.-Installation-may-not-complete-correctly)

