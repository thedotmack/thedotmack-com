title: Dead Simple Bootstrap LESS Media Query Mixins for Responsive Layouts
id: 162
categories:
  - Uncategorized
date: 2013-11-18 10:50:39
tags:
---

I've been hunting down a solution to this for a while, and as it turns out, it was right under my nose the whole time.

LESS supports [media query "bubbling"](https://github.com/SomMeri/less4j/wiki/Less-language-Media-Bubbling-and-Merging "Media Query Bubbling and Merging"); this is a fancy term for throwing the media queries outside of the declaration. I took that concept and combined it with [Bootstrap 3.0](http://getbootstrap.com "Bootstrap 3.0")'s breakpoints from [variables.less](https://github.com/twbs/bootstrap/blob/master/less/variables.less):

``` less
@xxs: ~'max-width: 377px';
@xs:  ~'max-width: @{screen-xs-max}';
@sm:  ~'max-width: @{screen-sm-max}';
@md:  ~'max-width: @{screen-md-max}';
```

Then, I simply throw this in wherever I need to adjust for screen size:

``` less
#dat-element { 
    ...
    @media(@xs) { 
        ...
    }
    @media(@sm) {
        ...
    }
    @media(@md) {
        ...
    }
}
```

Before anyone gets all crazy up in the comments, I know there are many ways to accomplish this. I prefer this way since it's easy to remember the syntax and simple to use.

That's the end of today's lesson. Shout out to [Jason Lengstorf](http://copterlabs.com "Rad Web Design") for helping me formulate this little snippet of awesome.
<br>

---

*Note: I set up my media queries to be based on max-width, even though bootstrap is mobile first. I haven't been working with mobile first for a while now so I'm confortable with this method. If you want to set up your media queries for mobile first, change all the "max"s to "min"s like so:*

```
@xxs: ~'min-width: 377px';
@xs:  ~'min-width: @{screen-xs-min}';
@sm:  ~'min-width: @{screen-sm-min}';
@md:  ~'min-width: @{screen-md-min}';
```
