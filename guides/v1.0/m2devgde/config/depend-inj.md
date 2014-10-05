---
layout: howtom2devgde_chapters
title: Dependency injection
---

<h1 id="m2devgde-dep-inj">{{ page.title }}</h1>

<p><a href="{{ site.githuburl }}m2devgde/config/depend-inj.md" target="_blank"><em>Help us improve this page</em></a>&nbsp;<img src="{{ site.baseurl }}common/images/newWindow.gif"/></p>

<h2 id="dep-inj-intro">Introduction</h2>

Dependency injection in Magento 2 is the alternative to the `Mage` class used in Magento 1. With dependency injection, an object does not need to locate an object or value on which it depends. Instead, a PHP class declares its dependencies in a constructor&mdash;a process referred to as *constructor dependency injection*.

The following example defines a constructor dependency on `SomeServiceInterface`:

<blockquote>
<pre>
public function __construct(\Magento\Module\Service\V1\SomeServiceInterface $service)
{
	$this->service = $service;
}
public function doSomething()
{
&nbsp;&nbsp;&nbsp;&nbsp;$data = array();
&nbsp;&nbsp;&nbsp;&nbsp;...
&nbsp;&nbsp;&nbsp;&nbsp;$this->service->something($data);
}</pre>
</blockquote>

The benefit of constructor dependency injection is that the object is immutable.

(A second type of dependency injection, *method injection*, is discussed later in this topic.)

The <a href="{{ site.mage2000url }}blob/master/lib/internal/Magento/Framework/ObjectManager/ObjectManager.php" target="_blank">object manager</a> specifies the dependency environment. It's a separate object to avoid having to repeat the same code over and over again.

This page uses the following terms:

Factory

:	Object that creates the objects of a specific type. Unlike business objects, a factory can be dependent on the object manager.

Proxy

:	Object that implements the same interface as the original object, but unlike this original object has only one dependency&mdash;the object manager. A proxy is used for lazy loading of optional dependencies.

<h2 id="dep-inj-mod">Using Dependency Injection in Your Module</h2>

The object manager needs the following configurations:

*	Class definitions for retrieving the types and numbers of class dependencies
*	Instance configurations for retrieving how the objects are instantiated and for defining their lifecycle
*	Abstraction-implementation mappings (that is, interface preferences) for defining what implementation is to be used upon request to an interface

The Magento software uses class constructor signatures to retrieve information about class dependencies; that is, to define what dependencies are to be passed to an object.

The Magento software reads constructors using reflection and we recommend you use the Magento compiler tool to pre-compiled class definitions for better performance.

<h3 id="dep-inj-mod-config">Dependency injection type configurations</h3>

Dependency injection is configuration-based; configurations are validated by <a href="{{ site.mage2000url }}blob/master/lib/internal/Magento/Framework/ObjectManager/etc/config.xsd" target="_blank">config.xsd</a>.

Object manager configurations can be specified at any of the following levels:

*	Global configurations for a module (`app/etc/di/*.xml`)
*	Global configurations for a module (`[your module directory]/etc/di.xml`)
*	Area-specific configurations for a module (`[your module directory]/etc/[your area code]/di.xml`)

	The area-specific configurations fall into the application areas' configurations (`frontend`, `adminhtml`, and so on). For example, here is the <a href="{{ site.mage2000url }}blob/master/app/code/Magento/Customer/etc/adminhtml/di.xml" target="_blank">Magento Customer module's adminhtml di.xml</a>.

	The application area-specific configurations are loaded separately as necessary.

#### Related topics:
