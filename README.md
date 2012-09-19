Bootjs
======

Javascript loader that uses window.localStorage for caching scripts and LAB.js for loading them.
Dependencies: jquery and LAB.js
<br>
<img src="http://blog.rememberthemilk.com/img/ninja.png">
<br>

<u style="font-weight: bold;">Road Map 2.0<u><br>
<ul>
	<li> Add a checked if the localStorage is already full. >5mb
	<li> Versioning control on the scripts by adding a "?boot=XX" query string to the script name.
	<li> Strip dowm the script name to its basename when saved as a localstorage key.
	<li> New key will be generated prefixed with "bootjs_" and a timestamp
	<li> Add an expires capability where bootjs will check if the script is one month old, if so then remove it from storage
		 and download a new one.
</ul>