<script>
  import { Clock } from "three";
  import { Group, onFrame } from "svelte-cubed";
  import PowerSphere from "./PowerSphere.svelte";

  const createSpheres = (seed) => {
    let spheres = [];
    for (let i = 0; i < 1; i += seed) {
      spheres.push({ name: `S${i}`, seed: i });
    }
    return spheres;
  };
  const clock = new Clock();
  const radiansPerSecond = (30 * Math.PI) / 180;
  let rotationZ = 0;
  onFrame(() => {
    let delta = clock.getDelta();
    rotationZ += radiansPerSecond * delta;
  });
</script>

<Group 
  rotation={[0, 0, rotationZ]} 
  scale={[5, 5, 5]} 
  position={[-1.25, 0, -2]}
>
  {#each createSpheres(0.05) as sphere}
    <PowerSphere
      seedIdx={sphere.seed}
      posX={Math.cos(2 * Math.PI * sphere.seed)}
      posY={Math.sin(2 * Math.PI * sphere.seed)}
    />
  {/each}
</Group>
