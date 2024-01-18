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
  - bookmark: `javascript:((gainValue) => { const video = document.querySelector('video'); if (!window.myGainNode) { const myAudioContext = new AudioContext(); const sourceNode = myAudioContext.createMediaElementSource(video); window.myGainNode = myAudioContext.createGain(); sourceNode.connect(window.myGainNode); window.myGainNode.connect(myAudioContext.destination); } window.myGainNode.gain.value = gainValue; })(prompt("Default is 1, enter the gain"))
`
