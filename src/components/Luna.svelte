<script>
import {
    TextureLoader,
    MeshStandardMaterial,
    SphereBufferGeometry,
  } from "three";
  import * as SC from "svelte-cubed";
  const createMaterial = () => {
    const loader = new TextureLoader();
    const texture = loader.load("/sc_textures/moonmap2k.jpg")
    const bumpMap = loader.load("/sc_textures/moonbump2k.jpg");
    const material = new MeshStandardMaterial({
      map: texture,
      bumpMap,
      bumpScale: 2,
      metalness: .75
    })

    return material;
  }
</script>

<SC.Mesh
  geometry={new SphereBufferGeometry()}
  material={createMaterial()}
  scale={[10, 10, 10]}
  position={[120, 50, 125]}
/>
