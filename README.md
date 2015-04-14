# openwrt-fcgi

FastCGI
========
FastCGI is simple because it is actually CGI with only a few extensions.
  
  * Like CGI, FastCGI is also language-independent. For instance, FastCGI provides a way to improve the performance of the thousands of Perl applications that have been written for the Web.
  * Like CGI, FastCGI runs applications in processes isolated from the core Web server, which provides greater security than APIs. (APIs link application code into the core Web server, which means that a bug in one API-based application can corrupt another application or the core server; a malicious API-based application can, for example, steal key security secrets from another application or the core server.)
  * Although FastCGI cannot duplicate the universality of CGI overnight, the FastCGI developers are committed to propagating FastCGI as an open standard. To that end, free FastCGI application libraries (C/C++, Java, Perl, Tcl) and upgrade modules for popular free servers (Apache, ISS, Lighttpd) are available.
  * Like CGI, FastCGI is not tied to the internal architecture of any Web server and is therefore stable even when server technology changes. An API reflects the internal architecture of a Web server, so when that architecture changes, so does the API.



Install
-------
* OpenWRT

    * [Download precompiled] for OpenWRT trunk and CPU: ar71xx, brcm63xx,
      brcm47xx, ramips_24kec. Open an issue if you think your CPU is a popular
      one but not listed here.
    * If you use other CPU or other OpenWRT versions, build yourself:
      cd into [SDK] root, then

            pushd package
            git clone https://github.com/paradislover/openwrt-fcgi.git
            popd
            make menuconfig # select Libraries/fcgi
            make -j
            make V=99 package/fcgi/compile
