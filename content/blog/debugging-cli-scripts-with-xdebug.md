{
	"title": "Debugging CLI scripts with xDebug",
	"description": "",
	"keywords": [
		"php",
		"xdebug"
	],
	"tags": [
		"php",
		"xdebug"
	],
	"pubdate": "2012-11-27",
	"date": "2012-11-27",
	"topics": [],
	"slug": "debugging-cli-scripts-with-xdebug",
	"section": "blog",
	"thumbnail": "/images/debugging-cli-scripts-with-xdebug.png",
	"disqus_url" : "http://peteraba.com/post/debugging-cli-scripts-with-xdebug/",
	"disqus_identifier" : "peteraba http://peteraba.com/?p=peteraba",
	"disqus_title" : "Debugging CLI scripts with xDebug",
	"has_code": true
}
So you've set up your IDE to debug your webapp. Cool. It's time to set it up for command line scripts too. No worries, it's going to be a whole lot faster.

<pre><code class="bash">export XDEBUG_CONFIG="idekey=XDEBUG_PHPSTORM"</code></pre>