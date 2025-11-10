## TTS URI event - how to use it

To play the assistant response on different (or even several) media player, i've added event `esphome.tts_uri`, that is fired every time when satellite is about to speak.

To catch the event, you can use `Developer tools -> Events` section. Put `esphome.tts_uri` into listening section and press "start listening". Then ask something to your satellite.
The event will look something like this:
```
event_type: esphome.tts_uri
data:
  device_id: b82c7a26a1d7d18723657802609dc
  uri: http://#your_HA_IP:8123/api/tts_proxy/IxgKJHFDEdfgsrdeG5PwC_GbUExZA.flac
origin: LOCAL
time_fired: "2025-05-17T20:22:52.831646+00:00"
context:
  id: 01JVFYKW4ZJQBGWDSKS7CWPPCD
  parent_id: null
  user_id: null
```

Useful fields are `device_id` and `uri`.

Here's how you can use them in automation:

```
alias: Play TTS URI
triggers:
  - trigger: event
    event_type: esphome.tts_uri
    event_data:
      device_id: #device_id#  <-- replace this with your device ID
actions:
  ## ATTENTION! This section may differ a bit - i use Music Assistant media player here.
  - action: media_player.play_media
    data:
      announce: true
      media_content_type: music
      media_content_id: "{{ trigger.event.data.uri }}"
    target:
      entity_id: media_player.#your_target_media_player#  <-- adjust this to reflect your media player
mode: single
```
