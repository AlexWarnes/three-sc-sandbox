<script>
  import { 
    BoxBufferGeometry, 
    MeshStandardMaterial, 
    Clock, 
    TextureLoader 
  } from "three";
  import { Mesh, onFrame } from "svelte-cubed";

  const createMaterial = () => {
    const textureLoader = new TextureLoader();
    const texture = textureLoader.load('/sc_textures/uv-test-bw.jpg')
    const material = new MeshStandardMaterial({
      map: texture
    })
    return material;
  }

  const clock = new Clock();
  const rotationRads = (30 * Math.PI) / 180;
  let rotationX = -0.5;
  let rotationY = -0.1;
  let rotationZ = 0.8;

  onFrame(() => {
    let delta = clock.getDelta();
    rotationX += rotationRads * delta;
    rotationY += rotationRads * delta;
    rotationZ += rotationRads * delta;
  });
</script>

<Mesh
  geometry={new BoxBufferGeometry()}
  material={createMaterial()}
  position={[0, 0, 0]}
  rotation={[rotationX, rotationY, rotationZ]}
  scale={[2, 2, 2]}
/>
