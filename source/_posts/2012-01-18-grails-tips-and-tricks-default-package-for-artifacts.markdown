---
layout: post
title: "Grails tips &amp; tricks: Default package for artifacts"
date: 2012-01-18 07:44
comments: true
categories: 
---

If you want a default package for your domain classes, controllers or any other artifacts,
you can simply use `grails.project.groupId` in your **Config.groovy** to achieve this.

{% codeblock %}
grails.project.groupId = 'fi.samimakela.application'
{% endcodeblock %}

If you use for example `create-domain-class` -command now, your domain class will be in `fi.samimakela.application` -package.

{% codeblock %}
grails create-domain-class Foo
{% endcodeblock %}

But it's not good to build a huge software having everything in the same package.
So you might want to do [packaging by feature](http://www.javapractices.com/topic/TopicAction.do?Id=205).

{% codeblock %}
grails create-domain-class ~.greatfeature.Bar
{% endcodeblock %}

Now you domain class will be in `fi.samimakela.application.greatfeature` -package. Just use tilde before your subpackage.

