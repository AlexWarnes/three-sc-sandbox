<script>
  import {
    TextureLoader,
    MeshStandardMaterial,
    SphereBufferGeometry,
  } from "three";
  import * as SC from "svelte-cubed";
  const createMaterial = () => {
    const loader = new TextureLoader();
    const texture = loader.load("/sc_textures/earthmap1k.jpg");
    const bumpMap = loader.load("/sc_textures/earthbump1k.jpg");
    const material = new MeshStandardMaterial({
      map: texture,
      bumpMap,
      bumpScale: 0.5,
      metalness: 0.8,
    });

    return material;
  };
</script>

<SC.Mesh
  geometry={new SphereBufferGeometry()}
  material={createMaterial()}
  scale={[50, 50, 50]}
  position={[0, 10, 125]}
/>
