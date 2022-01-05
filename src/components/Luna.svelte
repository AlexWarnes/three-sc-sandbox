<script>
  import * as THREE from "three";
  import * as SC from "svelte-cubed";
  const createMaterial = () => {
    const loader = new THREE.TextureLoader();
    const texture = loader.load("/sc_textures/moonmap2k.jpg")
    const bumpMap = loader.load("/sc_textures/moonbump2k.jpg");
    const material = new THREE.MeshStandardMaterial({
      map: texture,
      bumpMap,
      bumpScale: 2,
      metalness: .75
    })

    return material;
  }
</script>

<SC.Mesh
  geometry={new THREE.SphereBufferGeometry()}
  material={createMaterial()}
  scale={[10, 10, 10]}
  position={[120, 50, 125]}
/>
