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

```
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

```



