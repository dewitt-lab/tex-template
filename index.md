{{ site.github.project_tagline }}

{% for document in site.documents %}
- [{{ document }}]({{ document }}.pdf)
{% endfor %}
