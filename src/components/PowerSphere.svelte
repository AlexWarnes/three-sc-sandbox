<script>
  import { SphereBufferGeometry, MeshStandardMaterial } from "three";
  import { Mesh } from "svelte-cubed";
  export let seedIdx;
  export let posX;
  export let posY;

  const createMaterial = () => {
    const material = new MeshStandardMaterial({
      color: 'indigo'
    })

    return material;
  }
</script>

<Mesh
  geometry={new SphereBufferGeometry(0.25, 16, 16)}
  material={createMaterial()}
  position={[ posX, posY, .01 + seedIdx]}
  scale={[.01 + seedIdx, .01 + seedIdx, .01 + seedIdx]}
/>
