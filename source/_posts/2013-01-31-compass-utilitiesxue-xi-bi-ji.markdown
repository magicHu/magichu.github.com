---
layout: post
title: "Compass General Utilities学习笔记"
date: 2013-01-31 23:19
comments: true
categories: [Web, CSS, Compass, Compass Utilities]
---

### Hacks

* Configurable Variables
	$default-has-layout-approach zoom	# default has layout property, another is 'block'

* Mixins
	* has-layout($approach)		# "hasLayout" property in internet explorer
		@if $legacy-support-for-ie {
		    @if $approach == zoom {
		      @include has-layout-zoom;
		    } @else if $approach == block {
		      @include has-layout-block;
		    } @else {
		      @warn "Unknown has-layout approach: #{$approach}";
		      @include has-layout-zoom;
		    }
		  }
		@mixin has-layout-zoom {
		  @if $legacy-support-for-ie6 or $legacy-support-for-ie7 {
		    *zoom: 1;
		  }
		}

		@mixin has-layout-block {
		  @if $legacy-support-for-ie {
		    // This makes ie6 get layout
		    display: inline-block;
		    // and this puts it back to block
		    & { display: block; }
		  }
		}

		[what is has-layout in IE](http://adamghost.com/2009/03/ie-has-layout-and-bugs-zh/)
		sample: @include has-layout;
		  			=>
		{
			*zoom: 1;
		}


	* bang-hack($property, $value, $ie6-value)
		@if $legacy-support-for-ie6 {
		    #{$property}: #{$value} !important;
		    #{$property}: #{$ie6-value};
	  	}

		"bang-hack" just for resolve [IE6 min-width/min-height problem](http://www.iwms.net/n2282c40.aspx)
		sample: @include bang-hack(width, auto, 100px);
					 => 
		{
			width: auto !important;
			width: 100px;
		}