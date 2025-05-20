+++
+++

Hi! 👋 I'm Alex Johnstone. This is my weblog of interesting sundries. I enjoy exploring new things, sometimes I get bored and move on and other things I stick at for a while.

## Now

I'm enjoying undertaking SOTA activations - climbing mountains with my radio - and working my way towards 1,000 points to achieve Mountain Goat status. Also been thinking about rock tumbling.

## Recent posts

{% set blog_section = get_section(path="blog/_index.md") %}
{% set recent_posts = blog_section.pages | sort(attribute="date") | reverse | slice(end=3) %}

{% for post in recent_posts %}
  <article class="recent-post">
    <h3><a href="{{ post.permalink }}">{{ post.title }}</a></h3>
    <p>{{ post.summary | safe }}</p>
    <p><small>Published on {{ post.date | date(format="%B %d, %Y") }}</small></p>
  </article>
{% endfor %}


## Other Pages

* [Books](@/books.md) I've read
* [Keepsakes](@/keep.md) I want to remind myself of

## My other sites

* [Radio blog](https://gm5alx.uk)
* [Wiki](https://wiki.alexjj.com)
* [Github](https://github.com/alexjj)

### This site

I'm using [Zola](https://www.getzola.org/) static site generator together with the [anemone](https://github.com/Speyll/anemone) theme.
