{{ site.github.project_tagline }}

{% for doc in site.data.documents %}

- [{{ doc }}]({{ doc }}.pdf)

{% endfor %}
