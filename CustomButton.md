
Place your four images in `config/www/oknabu/` as:

* `idle.png`
* `listening.png`
* `thinking.png`
* `replying.png`

```
type: custom:button-card
entity: assist_satellite.xiaozhi_taichi_pi_assist_satellite
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
      entity: assist_satellite.xiaozhi_taichi_pi_assist_satellite
      show_icon: false
      show_state: false
      show_name: false
      show_entity_picture: true
      entity_picture: |
        [[[
          const s = states['assist_satellite.xiaozhi_taichi_pi_assist_satellite']?.state;
          if (s === 'idle') return '/local/oknabu/idle.png';
          if (s === 'listening') return '/local/oknabu/listening.png';
          if (s === 'processing') return '/local/oknabu/thinking.png';
          if (s === 'responding') return '/local/oknabu/replying.png';
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
