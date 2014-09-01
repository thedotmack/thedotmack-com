title: Responsive Typography Mixin for Bootstrap 3.x
date: 2014-09-01 11:51:50
tags: Bootstrap, Responsive, Typography
---

You can set up fully responsive bootstrap typography with the following code. You have to be rolling your own bootstrap based on the less files for this to work.

``` less
@xxs: ~'max-width: 377px';
@xs:  ~'max-width: @{screen-xs-max}';
@sm:  ~'max-width: @{screen-sm-max}';
@md:  ~'max-width: @{screen-md-max}';

.bs3-responsive-type(@mq, @font-size-base, @mq-size-percentage) {
    @media(@mq) {
        
        @font-size-large:    ceil((@font-size-base * 1.25)  * @mq-size-percentage);
        @font-size-small:    ceil((@font-size-base * 0.85)  * @mq-size-percentage);
        @font-size-h1:       floor((@font-size-base * 2.6)  * @mq-size-percentage);
        @font-size-h2:       floor((@font-size-base * 2.15) * @mq-size-percentage);
        @font-size-h3:       ceil((@font-size-base * 1.7)   * @mq-size-percentage);
        @font-size-h4:       ceil((@font-size-base * 1.25)  * @mq-size-percentage);
        @font-size-h5:       @font-size-base;
        @font-size-h6:       ceil((@font-size-base * 0.85)  * @mq-size-percentage);

        @import (multiple) "../../../hoverboard/bower_components/bootstrap/less/scaffolding.less";
        @import (multiple) "../../../hoverboard/bower_components/bootstrap/less/type.less";
    }
}

.bs3-responsive-type(@sm,  16px, 0.9);
.bs3-responsive-type(@xs,  15px, 0.85);
.bs3-responsive-type(@xxs, 14px, 0.8);

```
<br>

---

*Note: I set up my media queries to be based on max-width, even though bootstrap is mobile first. I haven't been working with mobile first for a while now so I'm confortable with this method. If you want to set up your media queries for mobile first, change all the "max"s to "min"s like so:*

``` less
@xxs: ~'min-width: 377px';
@xs:  ~'min-width: @{screen-xs-min}';
@sm:  ~'min-width: @{screen-sm-min}';
@md:  ~'min-width: @{screen-md-min}';
```
