---
layout: default
---

<section>
  {% for post in site.posts %}
      {% if forloop.first %}
      <main>
        <h1>
          {{ post.title }}          
        </h1>
        <small>Postat {% include date_and_auth.html the_post=post %} <a href="{{ post.url | prepend: site.baseurl }}">länk för delning</a></small>
        {{ post.content }}
        </main>
       <br>         
      {% else %}
      <p><strong>Tidigare inlägg:</strong><p>
      <h3><a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a></h3>
      <small>Postat {% include date_and_auth.html the_post=post %} </small>
      {{ post.excerpt }}
      <a href="{{ post.url | prepend: site.baseurl }}">Läs hela &rarr; </a>
      {% endif %}
      <hr>

  {% endfor %}
</section>
