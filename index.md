Hello, My name is Liam Pustam, a learning programmer based in NY. I'm learning a variety of languages at the Brooklyn Steam Center's Full-Stack Development pathway.

This will be my blog in which I'll be going over changes made to my projects and updates to my programming journey.


<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>