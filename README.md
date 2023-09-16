# wordpress-w3_css
**This is a modification of w3.css for compatibility with Wordpress**

The unmodified w3.css file can be downloaded from
https://www.w3schools.com/w3css/4/w3.css
or its
github repository at https://github.com/JaniRefsnes/w3css

Information about the original w3.css can be found at https://www.w3schools.com/w3css

wp-w3.css addresses the inherent incompatibility with w3.css
and many (*most? all?*) Wordpress themes.  It modifies the selectors found 
in the original w3.css so that element selectors no longer apply at the 
global scope, but must be contained within an element of class 
`wp-w3-container`.

The simplest way to use this css with your Wordpress plugin is 
probably to enclose all generated html within a `<div class=w3-css>`

 - Any html element that is **not** a child of a w3-css element will only
   see the effect of explicitly specified w3-*xxx* classes.

 - Any html element that **is a child** of a w3-css element will see all 
   the effects of w3.css even if it does not specify a w3-*xxx* class.

To include wp-w3.css with your Wordpress plugin, you will need to enqueue the style:

```
wp_enqueue_style(
  'wp-w3-css',
  'https://mikemayer67.github.io/wp-w3-css/wp-w3.css'
);
```

To include wp-w3.css in a non-Wordpress site, you will need to include it in the html header:

```
<link rel=stylesheet href='https://mikemayer67.github.io/wp-w3-css/wp-w3.css'>
```
