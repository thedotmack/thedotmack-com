title: My own .clearfix concoction
tags:
  - clearfix
  - CSS
  - floats
  - navigation
  - tricks
id: 13
categories:
  - CSS
  - Nerdiness
date: 2010-05-09 15:38:06
---

I've been using this for years now. I just tried to use the more widely accepted clearfix to no avail. I like mine better. It always works.

<pre>br.clearfix, li.clearfix {
       	   display:block !important;
	   float:none !important;
	   height:0 !important;
	   line-height:0 !important;
	   font-size:1px !important;
	   clear:both !important;
}
</pre>

And I never have any trouble in any browser. There you go. Clear all the floats you want. Go ahead, see if I care.