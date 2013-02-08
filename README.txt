Smarty Templating for ProcessWire
=================================

This module allows you to use Smarty 3 template engine in ProcessWire CMS.


Installation
------------

Just copy the SmartyTemplating folder to your /wire/modules/ and the sample template
folder to your /site/templates. Then go to the admin panel and enable this module.
In the options you can enable Smarty caching and change the cache lifetime. Upon
saving, three folders should be created in your /site/assets/cache: SmartyCache,
SmartyConfigs and SmartyTemplates_c. Otherwise create them and give them chmod 777.


Quick tutorial
--------------

Don't use <?php ?> tags in your templates! (despite the default *.php template extension)
Instead use { } tags accordingly:

Smarty:                              PHP:
{$page->title}                       <?php echo $page->title; ?>
{$home=$pages->get("/")}             <?php $home=$pages->get("/"); ?>
{foreach $home->children as $child}  <?php foreach($home->children as $child): ?>
    <li>{$child->title}                  <li><?php echo $child->title; ?>
    {if $child->field}!!!{/if}</li>      <?php if($child->field): ?>!!!<?php endif; ?></li>
{/foreach}                           <?php endforeach; ?>
{* this is a comment *}              <?php /* this is a comment */ ?>
{include './head.inc'}               <?php include './head.inc'; ?>


Author
------

Jerzy G¸owacki