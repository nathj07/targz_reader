# TARGX_Extractor

A simple library, with accompanying CLI to extract files from a `.tar.gz` archive.

What is particularly useful about both the library and the CLI is that you can specify not only the archive location and the unpack location, but also the file extensions you wish to unpack.

For example, consider the following archive - `~/myarchive.tar.gz`:
```
file_1.html
file_2.html
file_3.jpg
file_4.css
file_5.js
file_6.png
```
If you call the CLI as follows:

` ./targz_extractor --gzip ~/myarchive.tar.gz -- dest ~/Desktop --exts "css,js"`

The result would be:
```
~/Desktop/myarchive/file_4.css
~/Desktop/myarchive/file_5.js
```

This can be very useful when you only want certain files from the archive and the rest can be discarded without ever unpacking them.

In oder to use this in your own projects you simply need to import this package and call the `Extract/tarGz` function. The tests provide clear examples of how to use this; there is no need to instantiate any new objects or manipulate any news structs. The function signature is very simple so you could even add an interface definition in your code that this would implement in order to allow you to mock this should you need to.