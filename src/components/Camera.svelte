<script>
  import { onFrame, PerspectiveCamera } from "svelte-cubed";
  let posZ = 10;
</script>

<PerspectiveCamera position={[0, -2, 15]} near={0.1} far={1000} fov={55} />
