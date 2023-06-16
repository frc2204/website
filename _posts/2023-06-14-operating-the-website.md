---
layout: post
title:  "Operating the Website"
date:   2023-06-14 15:46:38 -0700
categories: team
author: James Ding
---
This website uses [Markdown][markdown] and [Jekyll][jekyll] to format posts. Markdown is commonly used for formatting
text on the web, and is used on websites such as Github, Reddit, Stack Overflow, and even Discord.

Here's a quick overview of Markdown:
{% highlight markdown %}
# This is a heading
## This is a subheading
### This is a sub-subheading
#### This is a sub-sub-subheading

This is a paragraph. You can even make text **bold** or *italic*.

```python
print("I can even add code blocks!")
```

Here's a link to [Google](https://google.com).
Here's a picture of the dino from the game ![Dino Run](/assets/dino.jpg):
{% endhighlight %}
![Dino Run](/assets/dino.jpg)

# Github
This website is hosted on Github Pages, which is a free service that allows you to host static websites. 
This means that edits on the repository will be reflected on the website. You should familiarize yourself with terms
such as `commit`, `pull request`, and `merge` before making any changes to the website.

# Posts
In order to post a new blog post, create a new file in the `_posts` directory.
Jekyll requires blog post files to be named according to the following format:

`YEAR-MONTH-DAY-title.md`

Where `YEAR` is a four-digit number, `MONTH` and `DAY` are both two-digit numbers, and `md` is the file extension 
representing the format used in the file (markdown). After that, include the necessary front matter. 
Take a look at the source for this post to get an idea about how it works.

## Updating Content
Updating content on the website is pretty straight forward. Generally, you would want to release updates every season on
sponsors, resources, and media.

### Updating Sponsors
To update sponsors, edit the `sponsors.md` file in the root directory. The file is formatted in Markdown, but includes
special elements known as `includes`.

Think about includes as a special function that takes in parameters and outputs HTML. In most cases to display sponsors,
you would need the image, name, description, and link to the sponsor. 

Here's an example of an include:
{% highlight html %}
{% raw %}{% include gold-ram-sponsor.html name="BAE Systems" img_url="/assets/sponsors/bae.svg" content="BAE Systems is a global defense, aerospace, and security company that provides advanced technology and services to customers worldwide." url="https://www.baesystems.com/" %}{% endraw %}
{% endhighlight %}

Notice how the arguments, `name`, `img_url`, `content`, and `url` are all passed in as parameters.

| Parameter | Description                         |
|-----------|-------------------------------------|
| `name`    | The name of the sponsor             |
| `img_url` | The URL to the image of the sponsor |
| `content` | The description of the sponsor      |
| `url`     | The URL to the sponsor's website    |

In order to get the sponsor's image to show properly, place image files (PNG, JPG, JPEG, SVG) in the `assets/sponsors` 
folder. Other than that, you should be good to go!

[markdown]: https://www.markdownguide.org/
[jekyll]: https://jekyllrb.com/
