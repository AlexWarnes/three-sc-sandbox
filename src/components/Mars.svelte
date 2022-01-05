<script>
  import * as THREE from "three";
  import * as SC from "svelte-cubed";
  const createMaterial = () => {
    const loader = new THREE.TextureLoader();
    const texture = loader.load("/sc_textures/mars_1k_color.jpg")
    const bumpMap = loader.load("/sc_textures/mars_1k_topo.jpg");
    const material = new THREE.MeshStandardMaterial({
      map: texture,
      bumpMap,
      bumpScale: 3,
      metalness: .85
    })

    return material;
  }
</script>

<SC.Mesh
  geometry={new THREE.SphereBufferGeometry()}
  material={createMaterial()}
  scale={[50, 50, 50]}
  position={[0, 10, -125]}
/>
