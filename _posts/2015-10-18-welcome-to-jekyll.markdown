---
layout: post
title:  "Welcome to Jekyll!"
date:   2015-10-18 10:19:13
categories: jekyll update
---
You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. You can rebuild the site in many different ways, but the most common way is to run `jekyll serve`, which launches a web server and auto-regenerates your site when a file is updated.

To add new posts, simply add a file in the `_posts` directory that follows the convention `YYYY-MM-DD-name-of-post.ext` and includes the necessary front matter. Take a look at the source for this post to get an idea about how it works.

Jekyll also offers powerful support for code snippets:

{% highlight ruby %}
def print_hi(name)
  puts "Hi, #{name}"
end
print_hi('Tom')
#=> prints 'Hi, Tom' to STDOUT.
{% endhighlight %}

{% highlight c %}
/* buffer sizes */
static const size_t _buffer_sizes[] = { 0, 512, 2048, 8192, 16384, };
static const size_t _buffer_sizes_count = sizeof(_buffer_sizes) /
		sizeof(_buffer_sizes[0]);

/* error generation function */
static telnet_error_t _error(telnet_t *telnet, unsigned line,
		const char* func, telnet_error_t err, int fatal, const char *fmt,
		...) {
	telnet_event_t ev;
	char buffer[512];
	va_list va;

	/* format informational text */
	va_start(va, fmt);
	vsnprintf(buffer, sizeof(buffer), fmt, va);
	va_end(va);

	/* send error event to the user */
	ev.type = fatal ? TELNET_EV_ERROR : TELNET_EV_WARNING;
	ev.error.file = __FILE__;
	ev.error.func = func;
	ev.error.line = line;
	ev.error.msg = buffer;
	telnet->eh(telnet, &ev, telnet->ud);
	
	return err;
}
{% endhighlight %}


Check out the [Jekyll docs][jekyll] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll’s dedicated Help repository][jekyll-help].

[jekyll]:      http://jekyllrb.com
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-help]: https://github.com/jekyll/jekyll-help
