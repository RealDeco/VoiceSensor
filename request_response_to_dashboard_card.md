```
alias: request_response_to_dashboard
description: ""
triggers:
  - trigger: state
    id: request
    entity_id: sensor.esphome_web_530014_text_request
  - trigger: state
    id: response
    entity_id: sensor.esphome_web_530014_text_response
conditions: []
actions:
  - choose:
      - conditions:
          - condition: trigger
            id: request
          - condition: template
            value_template: "{{ trigger.to_state.state != '...' }}"
        sequence:
          - action: input_text.set_value
            target:
              entity_id: input_text.airesponse
            data:
              value: "{{ 'You: ' ~ trigger.to_state.state }}"
      - conditions:
          - condition: trigger
            id: response
          - condition: template
            value_template: "{{ trigger.to_state.state != '...' }}"
        sequence:
          - action: input_text.set_value
            target:
              entity_id: input_text.airesponse
            data:
              value: "{{ 'AI: ' ~ trigger.to_state.state }}"
mode: single
type: markdown
content: "# {{ states('input_text.airesponse') }}"
grid_options:
  columns: 12
  rows: 7
```
