Bootjs 2.0
===========
<p>
Javascript loader that uses window.localStorage for caching scripts and LAB.js for loading them.
Dependencies: jquery and LAB.js
</p>
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

<h1>Bootjs 2.0 Features</h1>

<h2>Versioning</h2>
<p>
	You can control the version of the script being cached by adding the "boot=[ANY VALUE]" query string. When 
	adding this, Bootjs automatically deletes the old version of the script and caches the new one.
</p>
<pre>
	<code>
		new Boot().load('js/script2.js?boot=121812', function () {
			// Code for new version of script2.js
		});
	</code>
</pre>

<h2>Storage</h2>
<p>
	Bootjs script caches are stored using the HTML5 localStorage API. Bootjs caches will have 
	a key starting with "bootjs~" followed by the name of the script and the timestamp when it 
	was cached.
	
	Bootjs checks if the localStorage is full, if so then it will not cache anymore and outputs 
	a message in the browser console.
</p>

<h2>Expiration</h2>
<p>
	Bootjs automatically deletes cached scripts if they are more than a month old. Bootjs
	considers this scripts as stale and downloads those scripts again.
</p>

<br>
<h2>...Enjoy!</h2>