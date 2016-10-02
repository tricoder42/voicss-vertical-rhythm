Vertical Rhythm plugin
======================

This is an utility plugin: it doesn't output anything when imported.
It just provides variables, mixins, functions.

Introduction
------------

> Vertical Rhythm is a concept to keep elements aligned to a uniform, vertical grid.
> It's an application of repetition in design and it make content more readable.

More info:
 - [Why is Vertical Rhythm an Important Typography Practice?](http://zellwk.com/blog/why-vertical-rhythms/)
 - [Improving Layout With Vertical Rhythm](http://webdesign.tutsplus.com/articles/improving-layout-with-vertical-rhythm--webdesign-14070)

![Screencast](./intro.gif)

Quick start
-----------

1. Install `npm install voidcss-vertical-rhythm`

2. Import it:

   ```sass
   @import '~voidcss-vertical-rhythm';
   ```

3. Define base font size and line-height:

   ```sass
   $vr-font-size: 14px;   // Defaults to 1rem, which is 16px by default.
   $vr-line-height: 1.2;  // Defaults to 1.5. Depends on typeface.
   ```

4. Include `vr-init` in the root element (usually `html`):

   ```sass
   html {
     // Set default font-size and line-height.
     @include vr-init;
   }
   ```

5. Use `vr` function to calculate distances:

   ```sass
   // It's possible to use asymmetrical margins
   // as long as sum of vertical space inside element
   // is multiply of line-height.
   .lead {
     margin-top: vr(0.7);
     margin-bottom: vr(0.3);
   }
   ```

6. Use `vr-scale` to calculate line-height for different font sizes (eg. headings):

   ```sass
   h1 {
     $size: 36px;
     $baseline: vr-scale($size);

     font-size: $size;
     line-height: $baseline;

     margin-top: vr(0.7, $baseline);
     margin-bottom: vr(0.3, $baseline);
   }
   ```

7. Use `vr-grid` to display baseline grid for debugging:

   ```sass
   body {
     @include vr-grid;
   }
   ```

License
-------

[MIT](./LICENSE)
