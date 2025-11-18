```
alias: Play TTS URI (MiniVA)
description: ""
triggers:
  - trigger: event
    event_type: esphome.tts_uri
    event_data:
      node: esphome-web-530014
conditions: []
actions:
  - action: media_player.play_media
    target:
      entity_id: media_player.unknown_device_98_cd_ac_7a_71_10
    data:
      announce: true
      media:
        media_content_id: "{{ trigger.event.data.uri }}"
        media_content_type: music
        metadata: {}
mode: single
```
