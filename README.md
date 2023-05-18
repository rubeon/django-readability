# Django-Readability

This app adds a model for readability on any particular piece of content
that you may have in your django site.

For example, you could have a scorebox on your blog posts that give you an
idea of your writing statistics.

It uses the python [textstats][textstats] package to analyse the given text
and tag it with a score that you can reference in your template.

**Example Template:**

```
{% load readability %}
{% block comment %}
This generic detail view has a context object "obj" associated with the
content in question.
{% endblock %}

{% block my_content %}
<div id="blogpost">
{{ obj.get_body }}
</div>
<small>{{ readability_score obj }}</small>
{% endblock %}
```

