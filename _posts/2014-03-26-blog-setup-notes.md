---
title: Blog set-up notes
layout: post
---

This blog is hosted by github. And despite their claims of this being a simple thing to do, I struggled. Things now seem to work, and I think I now have the hang of this. These are a series of notes to myself to remind me of the things I have learned.

Set-up
------

Create your github repository as you are [told to](http://pages.github.com/), and make sure you name it properly. The magic is that appropriately named and formatted page now pushed to this repository will be 'auto-magically' converted into a properly formatted HTML page.

This requires three elements.

1. A properly named page. `index.md` is OK. And posts will need to be saved into the `.\_posts` directory with `CCYY-MM-DD-title.md` as their name. I found that `index.md` didn't compile properly unless I had put the formatted date-time into it's YAML header (see below):

```yaml
        ---
        layout: default
        title: A little knowledge
        date: 2014-03-26 09:00:00 UTC
        ---
```

2. A YAML header at the top of the file. This is a list of key:value pairs on separate lines bounded above and below by three dashes `---`.

3. Some templates and resources that will act as default layouts. I don't know where I copied mine from originally.


Other notes
-----------

I bought the site name at [Hover](www.hover.com). I had to then modify the A record at Hover so that it pointed to the Github IP address which I found [here](https://help.github.com/articles/my-custom-domain-isn-t-working).

For reference, they were `192.30.252.153` and `192.30.252.154`. The A record prefix `@` points to the root of `alittleknowledge.net`, and the `*` prefix means any other subdomain will also be directed here (e.g. `www.alittleknowledge.net`).

In addition, I had to create a file named `CNAME` at the root of my repository that contains just the domain name `alittleknowledge.net`.

I pushed this all to the repository, and then added the `_site` subdirectory to `.gitignore`.

For local testing, if I navigate to the root folder and run `jekyll build`, and then `jekyll serve`, I can see my site at `localhost:4000`.

