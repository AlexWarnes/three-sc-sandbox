<script>
  import * as THREE from "three";
  import * as SC from "svelte-cubed";
  const createMaterial = () => {
    const loader = new THREE.TextureLoader();
    const texture = loader.load("/sc_textures/ganymedemap1k.jpg")
    const bumpMap = loader.load("/sc_textures/ganymedebump1k.jpg");
    const material = new THREE.MeshStandardMaterial({
      map: texture,
      bumpMap,
      bumpScale: 2,
      metalness: .9
    })

    return material;
  }
</script>

<SC.Mesh
  geometry={new THREE.SphereBufferGeometry()}
  material={createMaterial()}
  scale={[20, 20, 20]}
  position={[-120, 40, 0]}
/>
