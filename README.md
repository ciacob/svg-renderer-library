# svg-renderer-library
Detached fork of lucaslorentz/AS3SVGRenderer/SVGRenderer

---
AS3SVGRenderer
==============

An AS3 SVG Renderer for Flash Player.

It parses and translates svg elements to Flash display objects. Rendering it and letting you interact with the output.

Requirements:
* Flash Player 10+

Features:
* Supports basic shapes and paths.
* Supports texts, right-to-left scripts, subscript, superscript.
* Has 3 text renderers engines (TextField, TLF, FTE), supports CFF and non-CFF fonts.
* Supports coordinates system rules, transformations and units.
* Supports masking and clipping.
* Supports filling, strokes, gradients.
* Supports marker symbols.
* Supports basic document structure (g, defs, symbol, use, image).
* Supported filters: ColorMatrix, GaussianBlur.
* Rendered display objects keeps the svg structure, so you can code mouse/touch interactions with svg elements.
* AS3 only.
* Flex component.

Missing features:
* Text stroke.
* Some filters.
* Scripting.
* Animation.

INTRODUCTION
==============

The library has display classes that represents each SVG element.  
The SVGDocument class is the class responsible to hold the SVG display object tree.  
The library has an asynchronously parser that processes the SVG file and create all necessary display objects.  
You can listen to the RENDERED event to know when graphics was completely rendered for the first time.  

USAGE
==============

AS3 only (without flex)
----------

1. The first thing you have to do is initialize the ProcessExecutor, that class is responsible to distribute the library processing between frames, that way the application will not get frozen while showing large SVG files. You have to do that only once in the whole application.  
```AS3
ProcessExecutor.instance.initialize(stage);  
```

2. Now you can load any SVG file into the SVGDocument using the load method.  
```AS3
var svg:SVGDocument = new SVGDocument();  
svg.load(urlStringOrUrlRequest);  
addChild(svg);  
```
Or if you already have the svg content string, use the parse method of SVGDocument class.  
```AS3  
var svg:SVGDocument = new SVGDocument();  
svg.parse(myLoadedSVGString);  
addChild(svg);   
```
You can also pass an XML object to the parse method, but it isn't recommended since when the parse method gets a string it does extra things to better parse the string.


LICENSE
==============
Licensed under the MIT License.  
http://opensource.org/licenses/mit-license.php

