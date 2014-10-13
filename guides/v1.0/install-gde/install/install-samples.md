---
layout: howtom2instgde_chapters
title: Sample installation commands
---

<h1 id="instgde-install-samples">{{ page.title }}</h1>

<p><a href="{{ site.githuburl }}install-gde/install/install-samples.md" target="_blank"><em>Help us improve this page</em></a>&nbsp;<img src="{{ site.baseurl }}common/images/newWindow.gif"/></p>

<h2 id="instgde-install-samples-basic">Typical Magento 2 installations</h2>

<div class="bs-callout bs-callout-info" id="info">
  <img src="{{ site.baseurl }}common/images/icon_note.png" alt="note" align="left" width="40" />
<span class="glyphicon-class">
  <p>All instalation commands must be entered on one line. They are shown here on multiple lines because of space limitations.</p></span>
</div>

This section discusses some typical installations using mostly required commands.

<h3 id="instgde-install-samples-basic1">Example: localhost installation</h3>

The following example installs Magento with the following options:

*	Base URL is `localhost` and the path to the Magento Admin is `admin`; therefore:

	Your storefront URL is `http://www.example.com` and you can access the Magento Admin at `http://www.example.com/admin`
	
*	The database server is on the same host as the web server.

	The database name is `magento` and its password is `magento`
	
*	The Magento administrator has the following properties:

	*	First and last name are is `Magento User`
	*	User name is `admin` and the password is `iamtheadmin`
	*	E-mail address is `user@example.com`

*	Default language is `en_us` (U.S. English)
*	Default currency is U.S. dollars
*	Default time zone is U.S. Central (America/Chicago)

<pre>php -f index.php install --db_host=localhost --db_name=magento 
	--db_user=magento --db_pass=magento 
	--base_url=localhost --backend_frontname=admin 
	--admin_firstname=Magento --admin_lastname=User 
	--admin_email=user@example.com 	--admin_username=admin 
	--admin_password=iamtheadmin --language=en_us 
	--currency=USD --timezone=America/Chicago</pre>

<h3 id="instgde-install-samples-basic1">Example: host name or IP address installation</h3>

The following example installs Magento with the following options:

*	Base URL is `http://www.example.com` and the path to the Magento Admin is `admin`; therefore:

	Your storefront URL is `http://www.example.com` and you can access the Magento Admin at `http://www.example.com/admin`
	
*	The database server is on the same host as the web server.

	The database name is `magento` and its password is `magento`
	
*	The Magento administrator has the following properties:

	*	First and last name are is `Magento User`
	*	User name is `admin` and the password is `iamtheadmin`
	*	E-mail address is `user@example.com`

*	Default language is `en_us` (U.S. English)
*	Default currency is U.S. dollars
*	Default time zone is U.S. Central (America/Chicago)

<pre>php -f index.php install --db_host=localhost --db_name=magento 
	--db_user=magento --db_pass=magento 
	--base_url=http://www.example.com --backend_frontname=admin 
	--admin_firstname=Magento --admin_lastname=User 
	--admin_email=user@example.com 	--admin_username=admin 
	--admin_password=iamtheadmin --language=en_us 
	--currency=USD --timezone=America/Chicago</pre>
	
<h2 id="instgde-install-samples-adv">Advanced Magento 2 installations</h2>

The examples in this section use a combiantion of requred, optional, and advanced installation options.

