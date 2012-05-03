clipper
=======

Flash based clipboard copier using Flex SDK. You need to install Flex SDK 4.6 to build the clipper.swf file on your machine. Or else you can use the pre-built binary from "build" directory.

The tool is inspired by the famous clippy - https://github.com/mojombo/clippy. Clippy requires haXe and swfmill to compile while clipper is built using Adobe's Flex SDK.

compile
-------
mxmlc -output build\clipper.swf clipper.mxml

usage
-----

Usage of this tools is similar to clippy (https://github.com/mojombo/clippy). I am pasting the Rails (Ruby) example here for convinience.

```ruby
def clipper(text, bgcolor='#FFFFFF')
  html = <<-EOF
    <object classid="clsid:3B09234A-06D7-4DC5-9FC0-A60713666622"
            width="110"
            height="14"
            id="clipper" >
    <param name="movie" value="build/clipper.swf"/>
    <param name="allowScriptAccess" value="always" />
    <param name="quality" value="high" />
    <param name="scale" value="noscale" />
    <param NAME="FlashVars" value="text=#{text}">
    <param name="bgcolor" value="#{bgcolor}">
    <embed src="build/clipper.swf"
           width="110"
           height="14"
           name="clipper"
           quality="high"
           allowScriptAccess="always"
           type="application/x-shockwave-flash"
           pluginspage="http://www.macromedia.com/go/getflashplayer"
           FlashVars="text=#{text}"
           bgcolor="#{bgcolor}"
    />
    </object>
  EOF
end
```

License
-------

MIT License (see LICENSE file)
