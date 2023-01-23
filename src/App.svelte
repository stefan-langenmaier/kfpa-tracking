<script>
  import { onMount } from 'svelte';
  import '@ar-js-org/ar.js/aframe/build/aframe-ar'

  onMount(() => {
		const sceneEl = document.querySelector('a-scene');

    console.log("adding listeners...");
    console.log(sceneEl);
    sceneEl.addEventListener('markerFound', () => {
        console.log("myMarkerFound");
    });

    sceneEl.addEventListener('markerLost', () => {
        console.log("myMarkerLost");
    });

    sceneEl.addEventListener('loaded', () => {
        console.log("myLoaded");
    });
    console.log("added listeners");
	});
</script>

<a-scene embedded arjs stats vr-mode-ui="enabled: false;">
  <a-marker preset="hiro">
    <a-cone position='0 0.5 0' rotation="0 0 0" radius-bottom="0.5" material='opacity: 0.75; color: red;'></a-cone>
  </a-marker>
  <a-camera look-controls="enabled: false; active: true;" position="0 0 0"></a-camera>
</a-scene>

<style>
</style>
