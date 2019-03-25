# 4d-utility-classic-msc-log

Generate classic-style HTML verification/repair log.

Internally calls ``xsltproc``

```
$lang:=Get database localization(Default localization)  //thread-unsafe:Get database localization
$path:=Get 4D file(Repair log file;*)

If (Test path name($path)=Is a document)
	
	$html:=Get_html_verify_log ($path;$lang)
	$file:=Path to object($path)
	$path:=Temporary folder+$file.name+".html"
	TEXT TO DOCUMENT($path;$html;"utf-8")
	OPEN URL($path)
	
End if 
```

<img width="774" alt="スクリーンショット 2019-03-26 1 22 38" src="https://user-images.githubusercontent.com/1725068/54936426-cc562680-4f65-11e9-8039-4cc2f72696c2.png">
