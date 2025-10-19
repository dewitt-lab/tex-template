{{ site.github.project_tagline }}

{% assign documents = site.config.documents | default: empty %}
{% if documents.size == 0 %}
  {% comment %}No specific documents listed, use all tex files{% endcomment %}
  {% assign pdf_files = site.static_files | where_exp: "file", "file.extname == '.pdf'" %}
  {% for pdf in pdf_files %}
- [{{ pdf.basename }}]({{ pdf.path | relative_url }})
  {% endfor %}
{% else %}
  {% for doc in documents %}
- [{{ doc }}]({{ doc }}.pdf)
  {% endfor %}
{% endif %}

