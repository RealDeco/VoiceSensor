```
type: markdown
grid_options:
  columns: 12
  rows: 3
content: |
  {% set t = states('input_text.airesponse') %}
  {% if t | length < 150 %} ## {{ t }} {% else %} {{ t }} {% endif %}
```
