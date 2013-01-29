---
layout: post
title: "Compass学习笔记"
date: 2013-01-29 23:49
comments: true
categories: 
---

### [Compass CSS3](http://compass-style.org/reference/compass/css3/)

#### [Border Radius](http://compass-style.org/reference/compass/css3/border_radius/)

##### Configurable Variables

	* $default-border-radius 5px

##### Mixins

    * border-radius($radius, $vertical-radius)
	* border-corner-radius($vert, $horz, $radius)
	* border-top-left-radius($radius)
	* border-top-right-radius($radius)
	* border-bottom-left-radius($radius)
	* and so on...

#### [Text Shadow](http://compass-style.org/reference/compass/css3/text-shadow/)

##### Configurable Variables

	* $default-text-shadow-color #aaaaaa
	* $default-text-shadow-h-offset 0px
	* $default-text-shadow-v-offset 0px
	* $default-text-shadow-blur 1px
	* $default-text-shadow-spread false

##### Mixins

	* text-shadow($shadow-1, $shadow-2, $shadow-3, $shadow-4, $shadow-5, $shadow-6, $shadow-7, $shadow-8, $shadow-9, $shadow-10)
	* single-text-shadow($hoff, $voff, $blur, $spread, $color)
