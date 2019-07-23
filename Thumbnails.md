# ImageMagick thumbnail info disclosure
Information Exposure at ThumbnailImage function. 
Vulnerable code
https://github.com/ImageMagick/ImageMagick/blob/92a873d0873534bc6ad50e5509709919dccfbdb4/MagickCore/resize.c#L3738
Image property Thumb::URI may contains information about path to the processing file. Image property software may contains information about executable file path

## Steps to Reproduce
Generate thumbnail for any file, at my example:
```convert /Users/user/Work/path/output.png -thumbnail 64x64 test.png ```
The test.png file will contains information:
```
EXtdate:create2018-08-08T22:00:15+03:00??
4%tEXtdate:modify2018-08-08T22:00:15+03:00????RtEXtsoftware/usr/local/Cellar/imagemagick/7.0.8-8/share/doc/ImageMagick-7//index.html?.tEXtThumb::Document::Pages1???/tEXtThumb::Image::Height128C|A?tEXtThumb::Image::Width128Ѝ?tEXtThumb::Mimetypeimage/png??VNtEXtThumb::MTime1533754815??1tEXtThumb::Size386B?x=?2tEXtThumb::URIfile:///Users/user/Work/path/output.png??CIEND?B
```
## Severity: Minor
Full path disclosure, information disclosure
