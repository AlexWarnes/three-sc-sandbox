<script>
  import { Color, AxesHelper, GridHelper } from "three";
  import * as SC from "svelte-cubed";
  import Lights from "../components/Lights.svelte";
  import Camera from "../components/Camera.svelte";
  // import PowerCube from "../components/PowerCube.svelte";
  // import PowerSphere from "../components/PowerSphere.svelte";
  import SphereGroup from "../components/SphereGroup.svelte";
  import TrainGroup from "../components/TrainGroup.svelte";
  import Birds from "../components/Birds.svelte";
</script>

<SC.Canvas
  background={new Color("skyBlue")}
  physicallyCorrectLights
  antialias
>
  <!-- <PowerCube /> -->
  <!-- <PowerSphere /> -->
  <SphereGroup />
  <TrainGroup />
  <Birds />
  <Lights />
  <Camera />
  <SC.Primitive object={new AxesHelper(10)} position={[0, 0.01, 0]} />
  <SC.Primitive object={new AxesHelper(-10)} position={[0, 0.01, 0]} />
  <SC.Primitive object={new GridHelper(10, 10)} />

  <SC.OrbitControls
    enableDamping={true}
    enablePan={true}
    dampingFactor={0.25}
    minDistance={5}
    maxDistance={20}
    autoRotate={false}
    autoRotateSpeed={5}
  />
</SC.Canvas>
