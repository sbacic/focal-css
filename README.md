Focal-CSS
===========
Focal-CSS is a CSS-only solution to maintaining image focal points in different resolutions. By default, images resize/crop from the top left corner regardless of where the image's focal (or center of attention) point is.

Installation
------------
Just add `<link rel="stylesheet" href="focal.min.css" media="screen" charset="utf-8">` to
your HTML. If you're using SASS, you can import `focal.sass` into your main `.sass` file.

Usage
-----
Focal-CSS should be placed on div elements and affects both the div's background-image
and any child img elements. Here are some examples:

Background image:
```
<div class="focal-22" style="background-image: url("example.jpg");"></div>
```

Image tag:
```
<div class="focal-22">
  <img src="example.png" alt="An example image.">
</div>
```

Let's imagine that your "focal grid" is composed of 3 rows and 3 columns, for a
total of 9 focal points (if you're having trouble visualizing, think of an old fashioned phone keypad). So `.focal-22` means 2nd row, 2nd column, or right in the middle of your image.

You can see a more concrete example in `example.html`.

Advanced
--------

The default grid size (64) should be enough for most use cases. If it doesn't fit your particular use case, you can change the number of rows and columns in `focal.sass`. When deciding on a custom grid size, always start with the smallest resolution - if it fits well there, it will fit well on the bigger ones as well.

You can also create multiple grids by calling the focal() mixin in `focal.sass` with different arguments (this is also useful in case of naming conflicts).

A little note about performance - it makes no sense to leave unused classes in your css file, so best run focal.css through a script that removes unused css classes from stylesheets. You'll save a lot of space.

License
-------
MIT
