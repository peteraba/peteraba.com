{
	"disqus_url" : "http://peteraba.com/post/dont-die/",
	"disqus_identifier" : "peteraba http://peteraba.com/?p=peteraba",
	"disqus_title" : "Don't die",
	"Title": "Don't die",
	"Description": "Using ",
	"Keywords": [
		"PHP"
		"xDebug"
	],
	"Tags": [
		"PHP"
		"xDebug"
	],
	"Pubdate": "2012-11-20",
	"Topics": [
		"PHP"
		"xDebug"
	],
	"Slug": "dont-die",
	"Section": "post",
	"Thumbnail": "/images/dont-die.png"
}
Your unit tests are broken, you need to figure out what happened. You analyze the stack trace and open up the file you feel to be guilty of the error. You put some var_dump statement - maybe you'll put it in some pre in there and then just die().

It doesn't help much, so you open up the next file and start again, maybe copy-paste your "debugger-statements".

We have all been there, but please, don't do it again!

I'm sure most PHP devs have some experience with real debuggers. Nowadays not only C and Java, but most JavaScript developers would instantly quite their jobs if they had no quality IDE/browser support for debugging. Even most PHP guys will have xDebug installed, because it adds a much nicer stack trace. Still, most of them will not worry about setting it up properly.

Don't get me wrong, I've been there, done that. Even a few weeks ago, since I work in a somewhat new environment. (vm, phpStorm) Still, it really isn't that big of a hassle to set up, even if your stack is a bit more complicated. Here are my settings for running php on a virtual machine and phpStorm on the host with port 9999 instead of the default 9000.

Here's what you should end up with:

PhpStorm xDebug in action

 

Here's my xdebug.ini:

zend_extension = /opt/php54/lib/php/extensions/no-debug-non-zts-20100525/xdebug.so

;http://xdebug.org/docs/all_settings

xdebug.remote_enable=1
;host: 10.10.4.1 - vm: 10.10.4.15
xdebug.remote_host=10.10.4.1
;you might want to keep the default 9000
xdebug.remote_port=9999
xdebug.remote_handler=dbgp
xdebug.remote_mode=req

xdebug.var_display_max_depth = 5
xdebug.collect_params=On
xdebug.show_local_vars=On
xdebug.remote_log=/var/log/xdebug.log
;remote connect also works, but stay at the safe side first
;xdebug.remote_connect_back=1
 

You should make sure you're server is set up correctly.

Server settings

 

You only need to worry about the xdebug port here, it defaults to 9000.

Debug settings

 

I think the IDE key is not important here, but it doesn't hurt any, so just set it as suggested.

Dbgp settings

 

Finally, my run/debug options:

Dbgp settings

 

I might eventually write a longer piece with a few IDE options, but I think this should also give you an idea, how to set it up in your environment.

Happy debugging everyone!