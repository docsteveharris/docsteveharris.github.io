---
layout: post
title: Adding comments to the blog
published: True
categories: []
tags: [howto, blog]
comments: true
---

Big day. I have added comments to the blog. Couldn't have been easier. Signed up for a [disqus](https://disqus.com/) account, and followed the instructions [here](https://help.disqus.com/customer/portal/articles/472138-jekyll-installation-instructions). The only small hint I can offer is that when you add the 'Universal Embed code' the tags need to be enclosed in curly braces `{` and `}`.

My `post.html` file looks like this:

```html
---
layout: default
---
{{ "{%"" }} include post.html %}

{{ "{%"" }} if page.comments %}
<div id="disqus_thread"></div>
<script type="text/javascript">
    /* * * CONFIGURATION VARIABLES: EDIT BEFORE PASTING INTO YOUR WEBPAGE * * */
    var disqus_shortname = 'alittleknowledgenet'; // required: replace example with your forum shortname

    /* * * DON'T EDIT BELOW THIS LINE * * */
    (function() {
        var dsq = document.createElement('script'); dsq.type = 'text/javascript'; dsq.async = true;
        dsq.src = '//' + disqus_shortname + '.disqus.com/embed.js';
        (document.getElementsByTagName('head')[0] || document.getElementsByTagName('body')[0]).appendChild(dsq);
    })();
</script>
<noscript>Please enable JavaScript to view the <a href="http://disqus.com/?ref_noscript">comments powered by Disqus.</a></noscript>

{{ "{%"" }} endif %}
```
