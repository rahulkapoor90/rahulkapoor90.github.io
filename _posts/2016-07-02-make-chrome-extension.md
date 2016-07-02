---
layout: post
title: "Make Chrome Extension to Change Design of a Webpage"
date: 2014-04-30
---

When new developers try to make a google chrome extension they may find it difficult to get a headstart and same was the case for me. I was having real diffculty understanding how chrome extensions work but i finally managed to learn how exactly everything works. So, I decided to post my first tutorial on a simple and easily understandable tutorial on "How to make Chrome Extension to change Design of a webpage".

### Why I decided to choose "Change Design" for a chrome extension?

This is because most of the developers who want to make chrome extension usually start with the idea that they want to change the shitty design of a particular website. Well, this was the case for me but if you want to do anything else i will not certainly recommend this tutorial to you but for the rest of you, let's start.

### Step 1: Create Manifest.json File and rest of the things

This tutorial is not for providing a step by step guide to how first create a Manifest file, create stylesheets and js folder and i am assuming you all already know that.

### Consider a Webpage.

In this case i am considering a simple webpage which looks exactly like it is shown below.

<img src="https://raw.githubusercontent.com/rahulkapoor90/VITacademics-Enhancement-Suite/master/Media/logo.gif" width="500">

The source code for the webpage that concerns us is:

<pre>
<code>	
<table height="30" width="750" border="0" align="center" cellpadding="0" cellspacing="0">
  <tr>
	<td valign="top" width="10" bgcolor=#FFFFFF>
		&nbsp;
	</td>
	<td valign="top" width="740" bgcolor=#FFFFFF align="center">
	<center>
	<font size=2><b><u>FACULTY PROFILE</u></b></font>
	</center>
			
	<form name="facprofile">
		
		<table cellpadding=1 cellspacing=1 border=0 height="40" width="750" >
		<tr>
			<td width="205" height="10"><b>Search By Faculty Name</b></td>
			<td height="10"><b>:</b>&nbsp;
				<input type="text" class="textbox2" name="faculty" maxlength=30 size="30" tabindex="1">
				&nbsp;&nbsp;
				<input type="button" class="submit3" value="Search" tabindex="1" onclick="showfaculty()">
			</td>
		</tr>
		</table>
		
	</form>
	
	<span id="txtHint">
	</span>	

	</td>
  </tr>
</table>
</pre>
</code>

#### Here we want to change the whole form with the name="facprofile" as an example so let's begin.

### First Select the form and store it in a variable.

 We have added 0 in getElementByTagName because it is the first form that we are concerned with.

var f = document.getElementsByTagName('form')[0];

### Start The design

In order to change the design of a webpage we are concerned only with document.createElement and document.setAttribute

So, First create a 'from' element and add it's attribute but here if you want to add your own style in css or sass you can add it by adding a setAttribute id or class.

<pre>
<code>
var form = document.createElement("form");
form.setAttribute("name","facprofile");
form.setAttribute("class","form-wrapper cf");
</code>
</pre>

Finally, add the other div's or table that are needed for example:

var table = document.createElement("table");
table.setAttribute("cellpadding","1");
table.setAttribute("cellspacing","1");
table.setAttribute("border","0");
table.setAttribute("height","40");
table.setAttribute("width","750");
var tbo = document.createElement("tbody");
var tr = document.createElement("tr");
var td = document.createElement("td");
td.setAttribute("width","205");
td.setAttribute("height","10");
var b = document.createElement("b");
var t = document.createTextNode("");
var td1 = document.createElement("td");
td1.setAttribute("height","10");
var b1 = document.createElement("b");
var t1 = document.createTextNode("");

var inp = document.createElement("input");
inp.setAttribute("type","text");
//inp.setAttribute("class","textbox2");
inp.setAttribute("name","faculty");
inp.setAttribute("maxlength","30");
inp.setAttribute("size","30");
inp.setAttribute("tabindex","1");

var inp1 = document.createElement("input");
inp1.setAttribute("type","button");
//inp1.setAttribute("class","submit3");
inp1.setAttribute("value","Search");
inp1.setAttribute("onclick","showfaculty()");
inp1.setAttribute("tabindex","1");


### End.

In the end you just need to append all the element's in sequence and in the way you want. so, it would be better if you assign a unique name to elements so that you can easily understand everything.

b1.appendChild(t1);
td1.appendChild(b1);
td1.appendChild(inp);
td1.appendChild(inp1);

b.appendChild(t);
td.appendChild(b);
tr.appendChild(td);
tr.appendChild(td1);
tbo.appendChild(tr);
table.appendChild(tbo);
form.appendChild(inp);
form.appendChild(inp1);

After appending all the form elements you just need to append it to parent element i.e. variable f and hide the form that we are changing design for.

f.parentElement.insertBefore(form, f);
document.getElementsByTagName('form')[0].style.display = "none";


### Done, Thank You.


