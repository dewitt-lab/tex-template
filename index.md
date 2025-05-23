{{ site.github.project_tagline }}

{% for doc in site.config.documents %}

- [{{ doc }}]({{ doc }}.pdf)

{% endfor %}
