Installing ArangoDB on MacOS
============================

ArangoDB under MacOS can be installed via:

1. [Homebrew](#homebrew)
2. [*DMG* Package](#package-installation)
3. [*Tar.gz* Archive](#installing-using-the-archive)

{% hint 'info' %}
When installing ArangoDB via the macOS package manager Homebrew,
only the Community Edition is available.
{% endhint %}

Homebrew
--------

{% hint 'warning' %}
Please note that the homebrew installation is updated a few days after the
official release of a new version.
{% endhint %}

If you are using [_homebrew_](http://brew.sh/),
then you can install the latest released stable version of ArangoDB using *brew* as follows:

    brew install arangodb

This will install the current stable version of ArangoDB and all
dependencies within your Homebrew tree. Note that the server will be
installed as:

    /usr/local/arangodb/3.4.0/sbin/arangod

You can start the server by running the command `/usr/local/arangodb/3.4.0/sbin/arangod &`.

Configuration file is located at

    /usr/local/etc/arangodb3/arangod.conf

The ArangoDB shell will be installed as:

    /usr/local/arangodb/3.4.0/bin/arangosh

You can uninstall ArangoDB using:

    brew uninstall arangodb

However, in case you started ArangoDB using the _launchctl_, you
need to unload it before uninstalling the server:

    launchctl unload ~/Library/LaunchAgents/homebrew.mxcl.arangodb.plist

Then remove the LaunchAgent:

    rm ~/Library/LaunchAgents/homebrew.mxcl.arangodb.plist

**Note**: If the latest ArangoDB Version is not shown in homebrew, you
also need to update homebrew:

    brew update

### Known issues

- The Commandline argument parsing does not accept blanks in filenames; the CLI version below does.
- If you need to change server endpoint while starting _homebrew_ version, you can edit arangod.conf 
  file and uncomment line with endpoint needed, e.g.:
      
      [server]
      endpoint = tcp://0.0.0.0:8529

Package Installation
--------------------

Visit the official [Download](https://www.arangodb.com/download) page of the
ArangoDB web site and download the *DMG* Package for Mac OS X.

### Graphical App

We provide a graphical app. You can install the application *ArangoDB* in
your application folder.

### Command line App

We provide a command-line app. You can install the application *ArangoDB-CLI*
in your application folder.

Starting the application will start the server and open a terminal window
showing you the log-file.

    ArangoDB server has been started

    The database directory is located at
       '/Users/<user>/Library/ArangoDB/var/lib/arangodb3'

    The log file is located at
       '/Users/<user>/Library/ArangoDB/var/log/arangodb3/arangod.log'

    You can access the server using a browser at 'http://127.0.0.1:8529/'
    or start the ArangoDB shell
       '/Applications/ArangoDB3-CLI.app/Contents/Resources/arangosh'

    Switching to log-file now, killing this windows will NOT stop the server.


    2018-03-16T09:37:01Z [13373] INFO ArangoDB (version 3.3.4 [darwin]) is ready for business. Have fun!

Note that it is possible to install both, the _homebrew_ version and the command-line
app. You should, however, edit the configuration files of one version and change
the port used.

Installing using the archive
----------------------------

Visit the official [Download](https://www.arangodb.com/download) page of the ArangoDB
web site and download the *Tar.gz* Archive for Mac OS X.

Starting from 3.4.0 a _tar.gz_ package is also available for MacOS. To install ArangoDB
using the `tar.gz` archive, just extract it.
