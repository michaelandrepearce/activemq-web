      .maincontent { overflow:hidden; }   Apache ActiveMQ ™ -- Creating Distributions 

[ActiveMQ](http://activemq.apache.org/) [ASF](http://www.apache.org)

[Index](index.html) > [Developers](developers.html) > [Creating Distributions](creating-distributions.html)

[Download](download.html) | [API](api.html) | [Source](source.html) | [Forums](http://activemq.apache.org/discussion-forums.html) | [Support](support.html)

Creating a Distribution of ActiveMQ-CPP
---------------------------------------

This should give you an idea of the steps involved with creating a new distribution of ActiveMQ-CPP. This content was extracted from [http://www.apache.org/dev/mirror-guide-bodewig.html](http://www.apache.org/dev/mirror-guide-bodewig.html), so you may want to reference that for more information.

### A Little Background Info ...

Apache mirrors everything under /www.www.apache.org/dist. We have had the infrastructure team add a directory under there for activemq. All you need in order to write to this directory is to be a member of the activemq group. If you're not, you'll have to create an infrastructure issue to get yourself added. Under the dir activemq, there is a directory activemq-cpp/source for the source distributions of ActiveMQ-CPP.

Under the source dir, we just drop the archive files (*.zip, *.tar.gz, *.zip.asc, *.tar.gz.asc) for the release versions. (NOTE: After you add files here, you should wait about 24 hours before notifying the lists since it takes a while for all the mirrors to pick up the files).

The links on our download pages reference an apache CGI script to handle the mirrors. This is a quick and dirty way of doing this, but it works until we come up with a better way. An example usage of the link is the url below:

[http://www.apache.org/dyn/closer.cgi/activemq/activemq-cpp/source/activemq-cpp-1.1-src.zip](http://www.apache.org/dyn/closer.cgi/activemq/activemq-cpp/source/activemq-cpp-1.1-src.zip)

The cgi script "closer.cgi" takes a file resource relative to www/www.apache.org/dist and generates a download page for it with the list of mirrors.

To see this in action, go to the amq-cpp 1.1 download page here: [http://activemq.apache.org/activemq-cpp-11-release.html](http://activemq.apache.org/activemq-cpp-11-release.html)

... and click on one of the archives. You'll be taken to a generic-looking download page.

Like I said, this is a quick and dirty for now, but it works! ![(smile)](https://cwiki.apache.org/confluence/s/en_GB/5982/f2b47fb3d636c8bc9fd0b11c0ec6d0ae18646be7.1/_/images/icons/emoticons/smile.png)

### Product version, interface version and package name

The page [ActiveMQ-CPP product version number](activemq-cpp-product-version-number.html) has been created to specify the way version numbers are used in the project, with some examples.

[ActiveMQ-CPP, libtool and packaging notes](activemq-cpp-libtool-and-packaging-notes.html) discusses the way version numbers impact libtool and packaging, and make some recommendations for this project.

### Creating a Distribution (step-by-step)

*   Create a pre-release download page for your distribution. This should have a disclaimer that the release is not yet official and should have a temporary link to a pre-release distribution. For the pre-release, you do not need to have both zip and tar.gz, but a detached signature file (.asc) file should accompany any distribution. Below is an example of the disclaimer that should appear at the top of the download page:

The Release is still in progress

You are previewing the release page for unreleased version of yadda. The download links on the page below may not work until it is officially released.

Until the release is approved you could try the current source bundle:  
[http://people.apache.org/~myaccount/yadda.zip](http://people.apache.org/~myaccount/yadda.zip)

Here is the Wiki Test for the above:

{warning:title=The Release is still in progress}
 	You are previewing the release page for unreleased version of yadda. The download links on the page below may not work until it is officially released.
 	 
 	Until the release is approved you could try the current source bundle:
 	\[http://people.apache.org/~myaccount/yadda.zip\]
{warning}

*   Call a vote on the release of the distribution. This email typically has
    
    \[VOTE\]
    
    in the subject line and should provide a link to the download page and the pre-release distribution.
*   Wait 3 days. If there >= 3 +1's and no -1's, you can proceed with the release.
*   Create all of the distributions of the source (*.zip, *.tar.gz). Make sure that you remove the .svn directories from the directory before you create the archives. On *nix, this can be done with the command:

rm -rf \`find . -type d -name .svn\`

*   Sign your distribution files, creating an asc file for both the tar and zip files, see this page [http://www.apache.org/dev/release-signing.html](http://www.apache.org/dev/release-signing.html) for more information on release signing.

gpg --armor --output foo.tar.gz.asc --detach-sig foo.tar.gz
gpg --armor --output foo.zip.asc --detach-sig foo.zip

*   Copy the distribution files to **/www/www.apache.org/dist/activemq/activemq-cpp/source** on minotaur.
*   Wait 24 hours for the mirrors to be updated with the distribution.
*   Update the links on the download page to reference your distribution through the CGI script. This simply means that you precede the file names with the path [http://www.apache.org/dyn/closer.cgi/activemq/activemq-cpp/source/](http://www.apache.org/dyn/closer.cgi/activemq/activemq-cpp/source/).

i.e. http://www.apache.org/dyn/closer.cgi/activemq/activemq-cpp/source/activemq-cpp-1.1-src.zip

*   Generate the Doxygen API and place it under /www/activemq.apache.org/cms/api_docs.
*   Add the link to the release API to the [API](api.html) page.
*   Add a news item under the CMS space on the wiki about the release.
*   Send out an e-mail on both the dev and users list about the release.

### [Overview](index.html)

*   [Index](index.html)
*   [News](news.html)
*   [Getting Started](getting-started.html)
*   [Tutorials](tutorials.html)
*   [API](api.html)
*   [FAQ](faq.html)
*   [Download](download.html)

### [Connectivity](connectivity.html)

*   [Stomp](stomp-support.html)
*   [OpenWire](openwire-support.html)

### [Using ActiveMQ-CPP](using-activemq-cpp.html)

*   [Getting Started](getting-started.html)
*   [CMS API Overview](cms-api-overview.html)
*   [Example](example.html)
*   [Configuring](configuring.html)

### Search

    
  

### [Community](community.html)

*   [Support](support.html)
*   [Contributing](http://activemq.apache.org/contributing.html)
*   [Discussion Forums](http://activemq.apache.org/discussion-forums.html)
*   [Mailing Lists](http://activemq.apache.org/mailing-lists.html)
*   [IRC](irc://irc.codehaus.org/activemq)
*   [IRC Log](http://servlet.uwyn.com/drone/log/hausbot/activemq)
*   [Site](site.html)
*   [Team](http://activemq.apache.org/team.html)

### [Developers](developers.html)

*   [Source](source.html)
*   [Building](building.html)
*   [Creating Distributions](creating-distributions.html)

[Privacy Policy](http://activemq.apache.org/privacy-policy.html) \- ([edit this page](https://cwiki.apache.org/confluence/pages/editpage.action?pageId=52862))

© 2004-2011 The Apache Software Foundation.  
Apache ActiveMQ, ActiveMQ, Apache, the Apache feather logo, and the Apache ActiveMQ project logo are trademarks of The Apache Software Foundation. All other marks mentioned may be trademarks or registered trademarks of their respective owners.  
[Graphic Design By Hiram](http://hiramchirino.com)

var gaJsHost = (("https:" == document.location.protocol) ? "https://ssl." : "http://www."); document.write(unescape("%3Cscript src='" + gaJsHost + "google-analytics.com/ga.js' type='text/javascript'%3E%3C/script%3E")); var pageTracker = \_gat.\_getTracker("UA-1347593-1"); pageTracker.\_initData(); pageTracker.\_trackPageview();