      .maincontent { overflow:hidden; }   Apache ActiveMQ ™ -- How to enable SSL support on Windows 

[ActiveMQ](http://activemq.apache.org/) [ASF](http://www.apache.org)

[Index](index.html) > [Community](community.html) > [FAQ](faq.html) > [Building FAQs](building-faqs.html) > [OpenSSL Support](openssl-support.html) > [How to enable SSL support on Windows](how-to-enable-ssl-support-on-windows.html)

[Download](download.html) | [API](api.html) | [Source](source.html) | [Forums](http://activemq.apache.org/discussion-forums.html) | [Support](support.html)

To enable support for SSL on Windows you first need to obtain a build of the OpenSSL libraries for Windows (See the OpenSSL site for details). Once you have the OpenSSL package for Windows installed you need to add the HAVE_OPENSSL preprocessor directive to the ActiveMQ-CPP library build's project file and set the include and library paths there as well. When you link the library to your app and run you will need to have the location of the OpenSSL libraries on your PATH or copy the libraries to the System folder.

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

[Privacy Policy](http://activemq.apache.org/privacy-policy.html) \- ([edit this page](https://cwiki.apache.org/confluence/pages/editpage.action?pageId=21792513))

© 2004-2011 The Apache Software Foundation.  
Apache ActiveMQ, ActiveMQ, Apache, the Apache feather logo, and the Apache ActiveMQ project logo are trademarks of The Apache Software Foundation. All other marks mentioned may be trademarks or registered trademarks of their respective owners.  
[Graphic Design By Hiram](http://hiramchirino.com)

var gaJsHost = (("https:" == document.location.protocol) ? "https://ssl." : "http://www."); document.write(unescape("%3Cscript src='" + gaJsHost + "google-analytics.com/ga.js' type='text/javascript'%3E%3C/script%3E")); var pageTracker = \_gat.\_getTracker("UA-1347593-1"); pageTracker.\_initData(); pageTracker.\_trackPageview();