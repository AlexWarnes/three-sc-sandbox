<script>
  import { GLTFLoader } from "three/examples/jsm/loaders/GLTFLoader.js"
  import * as SC from "svelte-cubed";
  import { Clock } from "three";
  
  let flamingoMesh;
  let parrotMesh;
  let storkMesh;
  let time = 0;
  const setupModel = (data) => {
    console.log(data);
    const model = data.scene.children[0];
    const clip = data.animations[0];
    const scene = data.scene;
    return { model, clip, scene };
  };

  function loadData() {
    const loader = new GLTFLoader();
    Promise.all([
      loader.loadAsync("/Flamingo.glb"),
      loader.loadAsync("/Parrot.glb"),
      loader.loadAsync("/Stork.glb"),
    ]).then(([flamingoModel, parrotModel, storkModel]) => {
      flamingoMesh = setupModel(flamingoModel);
      parrotMesh = setupModel(parrotModel);
      storkMesh = setupModel(storkModel);
    });
  }

  loadData();

  const clock = new Clock();
  SC.onFrame(() => {
    let delta = clock.getDelta();
    time += 1 * delta;
  });
  
</script>

<SC.Group position={[0, 3, 3]}>
  {#if flamingoMesh}
    <SC.Primitive object={flamingoMesh.model} scale={[0.01, 0.01, 0.01]}>
      <!-- <SC.Animation clip={flamingoMesh.clip} {time} /> -->
    </SC.Primitive>
  {/if}
  {#if parrotMesh}
    <SC.Primitive
      object={parrotMesh.model}
      scale={[0.01, 0.01, 0.01]}
      position={[1, 1, 0.5]}
    >
      <!-- <SC.Animation clip={parrotMesh.clip} {time} /> -->
    </SC.Primitive>
  {/if}
  {#if storkMesh}
    <SC.Primitive
      object={storkMesh.model}
      scale={[0.01, 0.01, 0.01]}
      position={[-2, 0.75, 0.75]}
    >
      <!-- <SC.Animation clip={storkMesh.clip} {time} /> -->
    </SC.Primitive>
  {/if}
</SC.Group>
