<div align="center">

## Popup Debug


</div>

### Description

response.write is okay for simple debugging but can become intrusive and cause formating problems itself. This simple script will display your debuging in a pop up window.
 
### More Info
 
A string to identify the debug message.

The value to be displayed in the popup window.

The ASP server side code generates simple client side javascript to display a popup winndow with the debug value in it.

As this inserts client side script it can sometimes confuse the browser.


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Chris Graham](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/chris-graham.md)
**Level**          |Advanced
**User Rating**    |5.0 (10 globes from 2 users)
**Compatibility**  |ASP \(Active Server Pages\)
**Category**       |[Debugging and Error Handling](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/debugging-and-error-handling__4-6.md)
**World**          |[ASP / VbScript](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/asp-vbscript.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/chris-graham-popup-debug__4-6511/archive/master.zip)





### Source Code

```
Include this function into your ASP page by pasting or prerably #include ing it.
'*************************************************
'* FUNCTION: popupDebug(name,value)
'*
'* PURPOSE: Displays a client side popup window with debug information
'*
'* INPUT:  name, used to identify debug. value, debug value to display
'*
'* RETURNS: None.
'*
'* NOTES:  Asterisks are displayed each side of the debug value for clarity
'*
'* AUTHOR:  Chris Graham
'*
'*************************************************
function popupDebug(name,value)
%>
<script type="text/javascript" Language="JavaScript"><!--
<!--
alert("popupDebug name=<%=name%> value=*<%=value%>*");
-->
</script>
<%
if response.buffer=true then response.flush
end function
'*************************************************
%>
Call it in the following way
<%
dim code
code=1
popupDebug "code should be 1",code
code=code+1
popupDebug "code should have incremented",code
%>
```

