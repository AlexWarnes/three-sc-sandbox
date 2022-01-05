<script>
  import { Clock, Color } from "three";
  import * as SC from "svelte-cubed";
  import { GLTFLoader } from "three/examples/jsm/loaders/GLTFLoader.js";
  import { onMount } from "svelte";

  let rociData;
  let rotation = 0;

  onMount(() => {
    const loader = new GLTFLoader();
    // This work is based on "MCRN Tachi [Expanse TV Show]"
    // (https://sketchfab.com/3d-models/mcrn-tachi-expanse-tv-show-76fc983ab08c449b9042491a00e621cf)
    // by Jakub.Vildomec (https://sketchfab.com/Jakub.Vildomec) licensed under CC-BY-4.0
    // (http://creativecommons.org/licenses/by/4.0/)
    loader.loadAsync("/rocinante.gltf").then((d) => {
      rociData = d;
    });
  });

  const clock = new Clock();
  SC.onFrame(() => {
    let delta = clock.getDelta();
    rotation += 0.5 * delta;
  });
</script>


{#if rociData}
  <SC.Primitive
    object={rociData.scene}
    scale={[0.03, 0.03, 0.03]}
    rotation={[rotation, rotation, rotation]}
  />
  {:else}
  <div class="loading">
    <p>LOADING MODEL...</p>
  </div>
{/if}

<style>
  .loading {
    position: fixed;
    bottom: 1rem;
    right: 1rem;
    padding: 1rem;
    background: #ffffff18;
    color: #ffffff;
  }
</style>
