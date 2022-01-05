<script>
  import * as THREE from "three";
  import * as SC from "svelte-cubed";
  import Lights from "../components/Lights.svelte";
  import Camera from "../components/Camera.svelte";
  import Rocinante from "../components/Rocinante.svelte";
  import Mars from "../components/Mars.svelte";
  import Earth from "../components/Earth.svelte";
  import Luna from "../components/Luna.svelte";
  import Ganymede from "../components/Ganymede.svelte";
  import { onMount } from "svelte";

  let background;
  onMount(() => {
    const loader = new THREE.CubeTextureLoader().setPath("/sc_textures/");
    loader.load(
      [
        // px
        "right.png",
        // nx
        "left.png",
        // py
        "top.png",
        // ny
        "bottom.png",
        // pz
        "front.png",
        // nz
        "back.png",
      ],
      (loaded) => {
        background = loaded;
        // background.mapping = THREE.CubeUVReflectionMapping;
        // background.encoding = THREE.sRGBEncoding;
      }
    );
  });
</script>

{#if background}
  <SC.Canvas
    {background}
    physicallyCorrectLights
    antialias
  >
    <Rocinante />
    <Mars />
    <Earth />
    <Luna />
    <Ganymede />

    <Lights />
    <Camera />

    <SC.OrbitControls
      enableDamping={true}
      enablePan={false}
      dampingFactor={0.25}
      minDistance={5}
      maxDistance={20}
      autoRotate={false}
      autoRotateSpeed={3}
    />
  </SC.Canvas>
{/if}

    <!-- <SC.Primitive object={new THREE.AxesHelper(10)} position={[0, 0.01, 0]} />
    <SC.Primitive object={new THREE.AxesHelper(-10)} position={[0, 0.01, 0]} />
    <SC.Primitive object={new THREE.GridHelper(10, 10)} /> -->
