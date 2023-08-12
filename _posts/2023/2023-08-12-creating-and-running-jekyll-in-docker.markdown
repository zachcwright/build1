---
layout: post
title:  "Creating and running jekyll in docker"
date:   2023-08-12 02:00:52 -0500
categories: jekyll docker
---
In this post we will go over how to initiate and run jekyll in docker.

1.To create jekyll template site use the command:
{% highlight bash %}
export site_name="my-blog" && export MSYS_NO_PATHCONV=1
docker run --rm \
  --volume="$PWD:/srv/jekyll" \
  -it jekyll/jekyll \
  sh -c "chown -R jekyll /usr/gem/ && jekyll new $site_name" \
  && cd $site_name 
  {% endhighlight %}

2.How to start Jekyll in docker on Windows in VSCode

* open the VSCode console by clicking: Ctrl+`
* paste in the terminal the next command: cd C:\Users\zachc\my-blog
* paste docker serve command in VSCode console: 
  {% highlight bash %}
  docker run --rm   --volume="${PWD}:/srv/jekyll:Z"
    -p 4000:4000   jekyll/jekyll:4.2.0   jekyll serve --watch --force_polling
  {% endhighlight %}
 * go to the browser and put in the address line: http://localhost:4000/my-blog/




