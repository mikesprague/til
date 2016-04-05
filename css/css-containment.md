# CSS Containment

The `contain` property is a primitive for isolating style, layout, and paint. The
`contain` property allows developers to limit a specific DOM sub-tree and the
rest of the document. You can think of it like an iframe. Much like an iframe,
this boundary establishes a new layout root, ensuring that DOM changes in the
sub-tree never trigger reflows in the parent document.

> **There are five different values for the `contain` property:**
>
>  * `none` no effect
>  * `layout` turns on layout containment
>  * `style` turns on style containment
>  * `paint` turns on paint containment
>  * `strict` layout, style and paint combined

## Use cases

So far we know that by using CSS containment we can isolate elements from the
rest of the document to mark them as independent parts. To show you where this
can be helpful here are some use cases:

### Widgets

When integrating third-party widgets you mostly don’t have much control and
they can decrease the site performance dramatically by doing expensive layout,
style or paint operations. To make them independent from our site we can set
`contain: strict;` for the most outer element of the third-party widget. This
way, they won’t affect the performance of all the other parts of the page.

### Off-Screen

If you build a off-screen navigation or similar, the browser paints the
content completely although it is not visible on load. By setting
`contain: paint;` the user agent can skip the paint off the off-screen element
and therefore paint all the other content faster.

### Container queries

As already mentioned in the beginning, `contain: strict;` can avoid many of
the problems of container queries. One of the "problems" of container queries
is that the children and their content can have an effect on the size of the
container. This can be avoided by using CSS containment.

### Why can’t the browser do it automatically

Browser engines already make a lot of optimization under the hood when possible,
but each engine has its differences. Using containment provides a standard
way for applications to indicate to the user agent that it can optimize certain
layout cases, which browser would otherwise not be able to optimize.

## Bottom line

If you build more complex sites, CSS containment will help to optimize the
performance. It is also a good idea to set `contain: strict;` for third-party
widgets to protect the performance of your site.

**Note**: At the moment (April, 2016) it is only fully supported in
[Chrome](https://www.chromestatus.com/feature/6522186978295808)
