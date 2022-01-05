<script>
  import { Color } from "three";
  import { DirectionalLight, HemisphereLight } from "svelte-cubed";
</script>

<DirectionalLight
  position={[10, 10, 10]}
  color={new Color("white")}
  intensity={5}
/>
<HemisphereLight
  color={new Color("white")}
  groundColor={new Color('darkslategrey')}
  intensity={2}
/>
