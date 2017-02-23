---
layout: default_custom
---
[Home]({{ site.baseurl }}{% link index.md %})
<code>&nbsp;</code>
[Posts]({{ site.baseurl }}{% link blank.md %})
<code>&nbsp;</code>
[Sandbox]({{ site.baseurl }}{% link sandbox.md %})
<code>&nbsp;</code>
[Photos]({{ site.baseurl }}{% link photos.md %})
<code>&nbsp;</code>
[Rowing]({{ site.baseurl }}{% link rowing.md %})
<code>&nbsp;</code>
[About]({{ site.baseurl }}{% link about.md %})

![Me]({{ site.baseurl }}{% link me.jpg %})

<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
      {{ post.excerpt }}
    </li>
  {% endfor %}
</ul>