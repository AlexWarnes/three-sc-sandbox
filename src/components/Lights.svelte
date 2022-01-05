<script>
  import { Color } from "three";
  import { DirectionalLight, HemisphereLight, AmbientLight } from "svelte-cubed";
</script>

<DirectionalLight
  position={[10, 10, 10]}
  color={new Color("white")}
  intensity={1}
/>
<HemisphereLight
  color={new Color("white")}
  groundColor={new Color('darkslategrey')}
  intensity={10}
/>
<!-- <AmbientLight
  color={new Color("white")}
  intensity={8}
/> -->
