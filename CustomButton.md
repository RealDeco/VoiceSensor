
Place your 9 images of choice in `config/www/oknabu/<modelname>` as:

* `idle.png`
* `listening.png`
* `thinking.png`
* `replying.png`
* `error.png`
* `mute.png`
* `playing.png`
* `loading.png`
* `timer_finished.png`

example: `config/www/oknabu/Dory/idle.png`

```
type: custom:button-card
entity: assist_satellite.esp32s3_1_assist_satellite
name: Ok Nabu
show_name: false
show_state: false
show_icon: false
tap_action:
  action: more-info
  haptic: medium
styles:
  card:
    - aspect-ratio: 1/1
    - border-radius: var(--ha-card-border-radius)
    - box-shadow: var(--ha-card-box-shadow)
    - border-style: var(--ha-card-border-style)
    - border-width: var(--ha-card-border-width)
    - border-color: var(--ha-card-border-color)
    - overflow: hidden
    - padding: 0
  grid:
    - grid-template-areas: "\"info\""
    - grid-template-columns: 1fr
    - grid-template-rows: 1fr
  custom_fields:
    info:
      - position: absolute
      - top: 0
      - left: 0
      - width: 100%
      - height: 100%
custom_fields:
  info:
    card:
      type: custom:button-card
      entity: sensor.esp32s3_1_voice_assistant_phase_id
      show_icon: false
      show_state: false
      show_name: false
      show_entity_picture: true
      entity_picture: |
        [[[
          const phase = states['sensor.esp32s3_1_voice_assistant_phase_id']?.state;

          if (!phase) return '/local/oknabu/default.png';

          // 1 = idle
          if (phase === '1') return '/local/oknabu/Dory/idle.png';
          // 2 = listening
          if (phase === '2') return '/local/oknabu/Dory/listening.png';
          // 3 = thinking/processing
          if (phase === '3') return '/local/oknabu/Dory/thinking.png';
          // 4 = replying
          if (phase === '4') return '/local/oknabu/Dory/replying.png';
          // 10 = not ready / initializing
          if (phase === '10') return '/local/oknabu/Dory/loading.png';
          // 11 = error
          if (phase === '11') return '/local/oknabu/Dory/error.png';
          // 12 = muted
          if (phase === '12') return '/local/oknabu/Dory/mute.png';
          // 20 = timer finished
          if (phase === '20') return '/local/oknabu/Dory/timer_finished.png';

          return '/local/oknabu/default.png';
        ]]]
      styles:
        card:
          - background: none
          - box-shadow: none
          - padding: 0
          - margin: 0
          - border-radius: 0
        img_cell:
          - padding: 0
          - margin: 0
          - justify-content: center
          - align-items: center
          - width: 100%
          - height: 100%
        icon:
          - width: 100%
          - height: 100%
          - object-fit: cover
          - border-radius: 0
      style: |
        ha-card {
          box-shadow: none !important;
          background: none !important;
        }
card_mod:
  class: hki
```
