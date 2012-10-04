Bootjs
======

Javascript loader that uses window.localStorage for caching scripts and LAB.js for loading them.
Dependencies: jquery and LAB.js
<br>
<div align="center">
	<img src="http://blog.rememberthemilk.com/img/ninja.png"><br>
	<i>"A ninja must be patient and quiet in loading js files"</i>
</div>
<br>
<pre>
	<code>
		new Boot()
		.load('js/jquery.jvap.js', function () { // load jquery
			console.log('typeof jQuery.jvap is: '+typeof jQuery.jvap);			
			this.load('js/json2.min.js', function () { // some js that is dependent on jQuery.jvap
				console.log('typeof JSON.stringify is: '+typeof JSON.stringify);
			});
		})
		// load script that has no depandencies //
		.load('js/dont_cache.js', false)
		.load('js/jquery.someplugin.js')
		.load('js/jquery.js')
		.load('js/script1.js')
		.load('js/script2.js?boot=100412.2'); // load script that has no depandencies	
	</code>
</pre>
<u style="font-weight: bold;">Road Map 2.0<u><br>
<ul>
	<li> Add a checked if the localStorage is already full. >5mb - ✓
	<li> Versioning control on the scripts by adding a "?boot=XX" query string to the script name. - ✓
	<li> Strip down the script name to its basename when saved as a localstorage key. - ✓
	<li> New key will be generated prefixed with "bootjs~" and a timestamp. - ✓
		 <br>   See: https://github.com/zazl/lsjs/wiki/Getting-Started
		 <br>   See: https://github.com/zazl/lsjs/wiki/Timestamp-Checking-Protocol
	<li> Add an expires capability where bootjs will check if the script is one month old, if so then remove it from storage
		 and download a new one. - ✓
</ul>
