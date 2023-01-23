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
  <a-marker type="pattern" url="pattern-fz-marker.patt" size="0.05">
    <a-gltf-model position="0 0.1 0" rotation="-90 0 0" scale="0.5 0.5 0.5" src="metallschild5.glb"></a-gltf-model>
    <a-gltf-model position="0 0.1 0" rotation="0 0 0" scale="0.5 0.5 0.5" src="duck.glb"></a-gltf-model>
</a-marker>
  <a-camera look-controls="enabled: false; active: true;" position="0 0 0"></a-camera>
</a-scene>

<style>
</style>
