---
layout: page
title: Categories
---

<section>

    {%for category in site.categories%}
        {% capture category_name %}{{ category | first }}{% endcapture %}
        <h3>{{ category_name }}</h3>
		<ul>	
		{%for post in site.categories[category_name]%}
			<li><time>{{ post.date | date:"%d %b %y" }} - </time>
			<a href="{{ post.url | prepend: site.baseurl | replace: '//', '/' }}">
            {{ post.title }}</a>
			</li>
		{% endfor %}
		</ul>
    {% endfor %}

</section>
