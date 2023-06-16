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
representing the format used in the file (markdown). After that, include the necessary front matter. Here's an example:

{% highlight markdown %}
---
layout: post
title:  "Operating the Website"
date:   2023-06-14 15:46:38 -0700
categories: team
author: James Ding
---
{% endhighlight %}

Front matter tells Jekyll basic information about any page. As you can see here, a post only requires a `layout`, 
`title`, `date`, `categories`, and `author`. 

| Front Matter | Description                                                                                       |
|--------------|---------------------------------------------------------------------------------------------------|
| `layout`     | The layout to use for the page. This is usually `post` for blog posts.                            |
| `title`      | The title of the page.                                                                            |
| `date`       | The date the page was published. Military time (24H format), `YYYY-MM-DD HH:MM:SS ZONE` format    |
| `categories` | The category of the post. In most cases, it will be `team`, `mentor`, `sponsor`, or `newsletter`. |
| `author`     | The author of the post.                                                                           |

Note: A common solution to articles not showing up on the website is to check the date. If the date is in the future, the article will not show up on the website.

Take a look at the [source][source] for this post to get an idea about how it works.

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

In order to get the sponsor's image to show properly, place image files (`PNG`, `JPG`, `JPEG`, `SVG`) in the `assets/sponsors` 
folder. Other than that, you should be good to go!

### Updating Members

Updating members is a slightly more complicated and time consuming process. In order to update members, you need to edit
individual markdown files in the `_mentors`, `_leadership`, `_members`, and `_alumni` directories.

#### General Pattern

To add a new member, create a new markdown file in the appropriate directory. The file should be named according to the
following format:

`FLASTNAME.md`

Where `F` is the first letter of the mentor's first name, and `LASTNAME` is the mentor's last name. For example, John
Doey's file would be named `jdoe.md`.

Additionally, the file should include the following front matter:

| Front Matter   | Description                                                                                           |
|----------------|-------------------------------------------------------------------------------------------------------|
| `name`         | The name of the person. (required)                                                                    |
| `email`        | The email of the person.                                                                              |
| `profile_pic`  | The URL to the person's profile picture. This typically would be a file in `/assets/profile-picture/` |
| `year_started` | The year the person joined the team. (required)                                                       |
| `year_ended`   | The year the person left the team.                                                                    |
| `tags`         | The tags associated with the person. This is in a form of a hyphenated list                           |

#### Mentors







#### Leadership
#### Members
#### Alumni

[markdown]: https://www.markdownguide.org/
[jekyll]: https://jekyllrb.com/
[source]: https://github.com/frc2204/rambots-website/blob/main/_posts/2023-06-14-operating-the-website.md?plain=1