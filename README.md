web-audio-gain-example
======================
### Notes
- make YouTube louder (in Chrome devtools):
  ```js
  const video = document.querySelector('video');
  const audioContext = new AudioContext();
  const sourceNode = audioContext.createMediaElementSource(video);
  const gainNode = audioContext.createGain();
  gainNode.gain.value = 5;
  sourceNode.connect(gainNode);
  gainNode.connect(audioContext.destination);

  // if 5 is not enough, *append*
  gainNode.gain.value = 10;
  ```
- [hubs/src/utils/avatar-volume-utils.js at master · Hubs-Foundation/hubs](https://github.com/Hubs-Foundation/hubs/blob/master/src/utils/avatar-volume-utils.js)
- [hubs/src/utils/audio-normalizer.js at master · Hubs-Foundation/hubs](https://github.com/Hubs-Foundation/hubs/blob/master/src/utils/audio-normalizer.js)
