[![](http://burzak.com/proj/drawform/docs/images/drawform.png)](http://burzak.com/proj/drawform/)

## Intro ##

Drawform is an element which enables you and visitors of your site to make drawings. The idea is an element similar to `textarea` but for making pictures.

Drawform's code is written in JavaScript with compiled size < 100kb. It have no special requirements or plugins (except Flash on Internet Explorer).

Drawform is based on latest web technologies such as HTML5 and Flash. It is reportedly working fine in all modern browsers (tested in IE8, Chrome, Opera 10, Firefox 3.5, iPhone/iPad). But it's not so excessive tested so if you find some bug please [report about it](http://code.google.com/p/drawform/issues/entry).

We also going to get some effort to get it working under Internet Explorer 6-7-9. Although IE8 is fine now.

Current status of the project is beta. In general it's very close to stable release.

While we are polishing API and documentation, source code is not available so far ... Soon we probably release it under the MIT license.

## Features ##

There are common tools available here:

  * Pencil
  * Pen
  * Path
  * Paint bucket
  * Eraser
  * Selection and moving tool
  * Image
  * Text
  * Rectangle and ellipse primitives

It's also saving changes history so undo and redo are there.

## Extending ##

Drawform's code have good architecture under the hood so it can be easily extended for special needs.

## Usage ##

Usage of the script is very simple: just add link to scripts into the page head and `drawform` element into  body:

```
<head>
    <script type="text/javascript" src="path/to/jooscript.js"></script>
    <script type="text/javascript" src="path/to/fxcanvas.js"></script>
    <!--[if IE]><script type="text/javascript" src="path/to/flash_backend.js"></script><![endif]-->
    <comment><script type="text/javascript" src="path/to/canvas_backend.js"></script></comment>
    <script type="text/javascript" src="path/to/drawform.js"></script>
...
<body>
    <form id="image-form" action="save_image.php" method="post">
        <drawform id="da" name="image" src="borders.png" width="300" height="400">
            Please enable JavaScript to make drawings.
        </drawform>
    </form>
...
```

To create drawform element inside script:

```
<script type="text/javascript">
  var da = document.createElement("drawform")
  var form = document.getElementById("image-form");
  form.appendChild(da)
  // note: set name after element inserted into parent node
  da.name = "image"
  da.width = 300
  da.height = 400
  da.src = "borders.png"
</script>
```

To get image data from drawform:

```
<script type="text/javascript">
  var da = document.getElementById("da");
  // toDataURL() is similar to canvas one
  da.toDataURL("image/png", function(data){
      trace(data)
  });
</script>
```

For advanced usage see source of [demo page](http://burzak.com/proj/drawform/test/drawform.html).

## Demo ##

Demo is [here](http://burzak.com/proj/drawform/test/drawform.html).

## Applications ##

[WordDraw](http://wordpress.org/extend/plugins/worddraw/) plugin for [WordPress](http://wordpress.org) is based on Drawform.

## Downloads ##

Download latest release from project [downloads](http://code.google.com/p/drawform/downloads/).

## Feedbacks and bugs ##

Common questions please mail to [mailing list](http://groups.google.com/group/drawform) and report bugs in [issue list](http://code.google.com/p/drawform/issues/list).