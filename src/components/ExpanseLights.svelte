<script>
  import { Color } from "three";
  import {
    DirectionalLight,
    HemisphereLight,
    AmbientLight,
    SpotLight
  } from "svelte-cubed";
</script>

<SpotLight
  position={[0, 10, 0]}
  color={new Color(0xffc1bf)}
  intensity={180}
/>
<SpotLight
  position={[10, 0, 0]}
  color={new Color(0xffc1bf)}
  intensity={180}
/>
<SpotLight
  position={[-10, 0, 0]}
  color={new Color(0xffc1bf)}
  intensity={180}
/>
<DirectionalLight
  position={[10, 10, 10]}
  color={new Color("white")}
  intensity={2}
/>
<HemisphereLight
  color={new Color("white")}
  groundColor={new Color("darkslategrey")}
  intensity={10}
/>
<!-- <AmbientLight
  color={new Color("white")}
  intensity={8}
/> -->
