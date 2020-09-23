<div align="center">

## File uploader/indexer


</div>

### Description

This code indexs files, uploads, and deletes. PLease vote for me!
 
### More Info
 
It out puts a table to the browser that shows each file.

none as of now


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[InteractiveWebGuys](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/interactivewebguys.md)
**Level**          |Intermediate
**User Rating**    |4.4 (137 globes from 31 users)
**Compatibility**  |PHP 3\.0, PHP 4\.0
**Category**       |[Files](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/files__8-2.md)
**World**          |[PHP](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/php.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/interactivewebguys-file-uploader-indexer__8-594/archive/master.zip)

### API Declarations

copyright 2001-2002 Interactive web Guys


### Source Code

```
<?php
error_reporting(0);
//this turns off error reporting we dothis so that we don't get a warning for the $action variable
$destination=".";
//the directory that the script index's if you want the current directory put a "." if you want another folder
//put "foldername"
if ($action=='delete')
{
$del = unlink("./$destination/$fle");
}
echo '<FONT SIZE="+2" COLOR="FF9A00"><CENTER>File manager</CENTER></FONT><BR><BR><TABLE BORDER=0 CELLSPACING=0 CELLPADDING=o><TR><TD ALIGN=center WIDTH=200 bgcolor=FFECCE><CENTER>Filename:</CENTER></TD><TD ALIGN=center WIDTH=200 bgcolor=FFECCE><CENTER>Functions:</CENTER></TD><TD ALIGN=center WIDTH=200 bgcolor=FFECCE><CENTER>Filesize(in bytes):</CENTER></TD><TD ALIGN=center WIDTH=150 bgcolor=FFECCE><CENTER>Filetype:</CENTER></TD><TD ALIGN=center WIDTH=150 bgcolor=FFECCE><CENTER>Created on:</CENTER></TD></TABLE>';
 $directory = opendir($destination);
 while( $file = readdir( $directory ) )
 {
 $file_ar[] = $file;
 }
 foreach( $file_ar as $file )
 {
 if( $file == ".." || $file == "." )
 {
 continue;
 }
$type= strrchr($file,'.');
$name=$file;
$name2=$destination."/".$file;
if($type==''){$type='dir';}
$sizeoff=filesize($name2);
$time=date("D M j Y",filectime($name2));
if($time=='Wed Dec 31 1969'){$time='Unknown';}
if($sizeoff==''){$sizeoff='Unknown';}
if($sizeoff=='0'){$sizeoff='Unknown';}
$file2 = dirname($name2);
 if($color == "FF9A00") {
 $color = "FFECCE";
 } else {
 $color = "FF9A00";
 }
echo"<TABLE BORDER=0 CELLSPACING=0 CELLPADDING=o><TR><TD ALIGN=center WIDTH=200 bgcolor='$color'><a href='$uname/$file' target=_blank>$name</a></font></TD><TD ALIGN=center WIDTH=200 bgcolor='$color'><A HREF='$PHP_SELF?action=delete&fle=$file&der=$uname'>Delete</A><TD ALIGN=center WIDTH=200 bgcolor='$color'>$sizeoff</TD> <TD ALIGN=center WIDTH=150 bgcolor='$color'>$type</TD><TD ALIGN=center WIDTH=150 bgcolor='$color'>$time</TD></TABLE>";
}
echo "<CENTER><FONT SIZE='+2' COLOR=\"FF9A00\"><BR><BR>Uploader</FONT></CENTER><BR><BR><FORM ACTION='$PHP_SELF' METHOD=post enctype=\"multipart/form-data\">File:<BR><INPUT TYPE='file' size='20' name='filename'><BR><CENTER> <input type=\"hidden\" name=\"action\" value=\"uploadProg\"><INPUT TYPE='hidden' name='action' value='upload'><INPUT TYPE='submit' value='Upload File'></CENTER></FORM>";
closedir($directory);
if($action==''){$action='noaction';}else{$action=$action;}
if($action=='upload')
{
 $filename==$filename_name;
 $action=('uploadprog');
 $destination=".";
 copy($filename,$destination."/".$filename_name);
 echo "<h2>File Uploaded.</h2>";
 echo "<HEAD><META HTTP-EQUIV='Refresh' CONTENT=1></HEAD>";
 }
 if ($filename=="none") {echo("<h1>No File Selected....</h1>"); break;}
 uploadProg($filename,$filename_name);
 break;
?>
```

