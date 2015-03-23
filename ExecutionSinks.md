### Direct Execution Sinks ###

## Browser JavaScript execution sinks ##

The following JavaScript functions parse strings as JavaScript. If it is possible to control, even partially, the vulnerable argument, then it is possible to execute JavaScript.

| **Function Name** | **Argument** | **Browser** | Example |
|:------------------|:-------------|:------------|:--------|
| eval | first | **All** | eval("jsCode"+**usercontrolledVal** ) |
| Function | first if there's one, the last if >1 args | **All** | Function("jsCode"+**usercontrolledVal** ) , <br><br> Function("arg","arg2","jsCode"+<b>usercontrolledVal</b> ) <br>
<tr><td> setTimeout </td><td>  first <span title='if and only if'><i>IIF</i></span> it is a string   </td><td> <b>All</b> </td><td> setTimeout("jsCode"+<b>usercontrolledVal</b> ,timeMs) </td></tr>
<tr><td> setInterval </td><td>  first <span title='if and only if'><i>IIF</i></span> it is a string </td><td> <b>All</b> </td><td> setInterval("jsCode"+<b>usercontrolledVal</b> ,timMs) </td></tr>
<tr><td> setImmediate </td><td>  first <span title='if and only if'><i>IIF</i></span> it is a string </td><td> <b>IE 10+</b> </td><td> setImmediate("jsCode"+<b>usercontrolledVal</b> ) </td></tr>
<tr><td> execScript </td><td>  first </td><td> <b>IE 6+</b> </td><td> execScript("jsCode"+<b>usercontrolledVal</b> ,"JScript") </td></tr>
<tr><td> crypto.generateCRMFRequest </td><td> 5th </td><td> <b>Firefox 2+</b> </td><td> crypto.generateCRMFRequest('CN=0',0,0,null,'jsCode'+<b>usercontrolledVal</b>,384,null,'rsa-dual-use') </td></tr>
<tr><td> ScriptElement.src </td><td> assignedValue </td><td> <b>All</b> </td><td> script.src =  <b>usercontrolledVal</b>  </td></tr>
<tr><td> ScriptElement.text </td><td> assignedValue </td><td> <b>Explorer</b> </td><td> script.text = 'jsCode'+<b>usercontrolledVal</b>  </td></tr>
<tr><td> ScriptElement.textContent </td><td> assignedValue </td><td> <b>All but IE<9</b> </td><td> script.textContent = 'jsCode'+<b>usercontrolledVal</b>  </td></tr>
<tr><td> ScriptElement.innerText </td><td> assignedValue </td><td> <b>All but Firefox</b> </td><td> script.innerText = 'jsCode'+<b>usercontrolledVal</b>  </td></tr>
<tr><td> anyTag.<b>onEventName</b> </td><td> assignedValue </td><td> <b>All</b> </td><td> anyTag.onclick = 'jsCode'+<b>usercontrolledVal</b>  </td></tr></tbody></table>

(TBF)