---
layout: post
title: How to start a blog with Jekyll
description: I created this simple and elegant blog using Jekyll!. Jekyll is a powerful blog generator which a huge community behind. Let's do it!
published: true
comments: true
category: Dev
tags: [webdev, jekyll, blog]
---

Jekyll is a powerful static site generator which means you don't need any database behind it making it simple and fast to set up.
I choose Jekyll because I heard about it before and since I wanted to have a little place on the internet where to store my memos it was a great choice as the set up is fast and is very customizable.
There are many tutorials on the internet about how to set Jekyll up with GitHub pages but since I have a server (Based on Ubuntu 15.04) where I use to test my applications I used to set Jekyll there.

# Setting up Jekyll on Linux (Ubuntu 15.04)

Jekyll runs in Ruby so the first step was install the necessary packages in the server. As long as I wanted to use the port 80 for the blog I didn't touch anything related to the firewall. By default Jekyll runs on the port 4000 so if you're using a firewall like ufw don't forget to add the proper rule to allow the connections.

Neccessary packages:
```sh
$ sudo apt-get update
$ sudo apt-get install ruby ruby-dev make gcc
$ sudo gem install jekyll bundler
```

UFW rule (optional)
```sh
$ sudo ufw allow 4000
```
# Choosing a template
There are a lot on the internet but [Poole/lanyon](https://github.com/poole/lanyon) is just perfect: simple and elegant. There are lot of themes in http://jekyllthemes.org/.
After choosing the template I forked the code to my own repository in GitHub. By doing that I'm able to write the posts in local and use Github to deploy the posts or changes in the server.

I created a new folder where to store my blog and connect it with the Github repository in the root of my user.
```sh
// Folder creation
$ mkdir jdecastroc-blog
// Github repository addition
$ git remote add origin https://github.com/jdecastroc/jdecastroc-blog.git
// Fetch to take the changes in the branch
$ git fetch --all
// Reset hard works in order to delete all the local changes without save and take
// the branch changes
$ git reset --hard origin/master
// To start the server on the port 80 where the IP is your server public IP
$ sudo jekyll serve --host=IP --port 80
```
Once finished these steps the blog is set up and is time to customize it.

# Customizing the blog

- Adding the proper gems to the *_config.yml*
```yml
# Gems
gems:
- jekyll-paginate
```
- Adding tag and category pages following the example of [CodinFox](https://codinfox.github.io/dev/2015/03/06/use-tags-and-categories-in-your-jekyll-based-github-pages/)
- Adding [disqus](https://disqus.com/) by singing up and following the steps. I had some problems with the code related to the comment section but I solved it by implementing a previous version:
```js
_includes/disqus.html

{% if page.comments %}
<div id="disqus_thread"></div>
    <script type="text/javascript">
        /* * * CONFIGURATION VARIABLES: EDIT BEFORE PASTING INTO YOUR WEBPAGE * * */
        var disqus_shortname = 'YOURFORUMSHORTNAME'; // required: replace example with your forum shortname
        // var disqus_developer = 1; // Comment out when the site is live
        var disqus_identifier = "{{ page.url }}";

        /* * * DON'T EDIT BELOW THIS LINE * * */
        (function() {
            var dsq = document.createElement('script'); dsq.type = 'text/javascript'; dsq.async = true;
            dsq.src = '//' + disqus_shortname + '.disqus.com/embed.js';
            (document.getElementsByTagName('head')[0] || document.getElementsByTagName('body')[0]).appendChild(dsq);
        })();
    </script>
    <noscript>Please enable JavaScript to view the <a href="http://disqus.com/?ref_noscript">comments powered by Disqus.</a></noscript>
    <a href="http://disqus.com" class="dsq-brlink">comments powered by <span class="logo-disqus">Disqus</span></a>
{% endif %}
```
- Adding Goolge analytics in all the pages. In order to accomplish this I put the provided google analytics script code into a new file located in *_include/analytics.html* and called that file by using the following code at the end of *_layouts/default.html*
```html
{% include analytics.html %}
```
- Creating a Gravattar account and adding the avatar to the sidebar by modification the *_config.yml* description
```yml
description: '<img src="<AVATAR OF GRAVATAR LINK>?size=350" style="border-radius: 25px; padding: 10px; title="View on Gravatar" alt="View on Gravatar">'
```
- Adding pages like *About me*, *Projects*...

It has been a good experience. The framework is perfectly modulated and except some exceptions it has not been difficult. The best thing I liked is that you're free to implement whatever you want like the modules of *disqus* or the google analytics script easily and fast thanks to that modulation. Besides if you don't want to go further by adding modules you can set up a simple and cool blog in a few minutes.

Sources:
- [Jekyll](https://jekyllrb.com/)
- [Poole theme](https://github.com/poole/lanyon)
- [Tags and categories without plugins](https://codinfox.github.io/dev/2015/03/06/use-tags-and-categories-in-your-jekyll-based-github-pages/)
- [Disqus](https://disqus.com/)
- [Google Analytics for Jekyll](https://michaelsoolee.com/google-analytics-jekyll/)

If you have any doubt about the process just let me know so that we can learn together!
