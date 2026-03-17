---
type: paper
citekey: {{citekey}}
year: {{date | format("YYYY")}}
status: unread
---
## Study Context
{% persist "study-context" %}
Population:
- [[]]

Sample Size:
 - 
Activity:
- [[]]

Methods:
- [[]]

Statistics:
- [[]]
Purpose / Hypothesis:
{% for annotation in annotations -%}
{%- if annotation.colorCategory == "Blue" and annotation.annotatedText %}
- {% if annotation.page %}(p. {{annotation.page}}) {% endif %}{{annotation.annotatedText}}
{%- if annotation.comment %}
  - Note: {{annotation.comment}}
{%- endif %}
{%- endif -%}
{%- endfor %}

Participant Demographics:
{% for annotation in annotations -%}
{%- if annotation.colorCategory == "Purple" and annotation.annotatedText %}
- {% if annotation.page %}(p. {{annotation.page}}) {% endif %}{{annotation.annotatedText}}
{%- if annotation.comment %}
  - Note: {{annotation.comment}}
{%- endif %}
{%- endif -%}
{% endfor %}

Methods Details:
{% for annotation in annotations -%}
{%- if annotation.colorCategory == "Magenta" and annotation.annotatedText %}
- {% if annotation.page %}(p. {{annotation.page}}) {% endif %}{{annotation.annotatedText}}
{%- if annotation.comment %}
  - Note: {{annotation.comment}}
{%- endif %}
{%- endif -%}
{%- endfor %}
{% endpersist %}

---

## Metrics Studied
{% persist "metrics-studied" %}
- [[]]
{% endpersist %}

---

## Results
{% persist "results" -%}
{% for annotation in annotations -%}
{%- if annotation.colorCategory == "Red" and annotation.annotatedText %}
- {% if annotation.page %}(p. {{annotation.page}}) {% endif %}{{annotation.annotatedText}}
{%- if annotation.comment %}
  - Note: {{annotation.comment }}
{%- endif %}
{%- endif -%}
{%- endfor %}
{% endpersist %}

---

## Key Insights Extracted
{% persist "key-insights" %}
- [[]]
{% for annotation in annotations -%}
{%- if annotation.colorCategory == "Yellow" and annotation.annotatedText %}
- {% if annotation.page %}(p. {{annotation.page}}) {% endif %}{{annotation.annotatedText}}
{%- if annotation.comment %}
  - Note: {{annotation.comment}}
{%- endif %}
{%- endif -%}
{%- endfor %}
{% endpersist %}

---

## Reference Data Extracted
{% persist "reference-data" %}
- [[]]
{% endpersist %}

---

## Notes
{% persist "notes" %}

{% endpersist %}