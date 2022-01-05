<script>
  import * as THREE from "three";
  import * as SC from "svelte-cubed";
  const createMaterial = () => {
    const loader = new THREE.TextureLoader();
    const texture = loader.load("/sc_textures/earthmap1k.jpg")
    const bumpMap = loader.load("/sc_textures/earthbump1k.jpg");
    const material = new THREE.MeshStandardMaterial({
      map: texture,
      bumpMap,
      bumpScale: .5,
      metalness: .8
    })

    return material;
  }
</script>

<SC.Mesh
  geometry={new THREE.SphereBufferGeometry()}
  material={createMaterial()}
  scale={[50, 50, 50]}
  position={[0, 10, 125]}
/>
