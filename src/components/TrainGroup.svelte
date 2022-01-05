<script>
  import * as THREE from "three";
  import * as SC from "svelte-cubed";
</script>

<SC.Group position={[0, 1, 0]} rotation={[0, 1, 0]}>
  <!-- CrewBox -->
  <SC.Mesh
    geometry={new THREE.BoxBufferGeometry()}
    material={new THREE.MeshStandardMaterial({
      color: new THREE.Color(0xf51000),
    })}
    scale={[2, 2.5, 1.5]}
    position={[0, 0.5, 0]}
  />
  <!-- Wheel 1x large and 3x small -->
  <SC.Mesh
    geometry={new THREE.CylinderBufferGeometry(1, 1, 1, 12)}
    material={new THREE.MeshStandardMaterial({
      color: new THREE.Color(0x303030),
      flatShading: true,
    })}
    scale={[0.75, 2, 0.75]}
    rotation={[(90 * Math.PI) / 180, 0, 0]}
    position={[0, 0, 0]}
  />
  <SC.Mesh
    geometry={new THREE.CylinderBufferGeometry(1, 1, 1, 12)}
    material={new THREE.MeshStandardMaterial({
      color: new THREE.Color(0x303030),
      flatShading: true,
    })}
    scale={[0.35, 2, 0.35]}
    rotation={[(90 * Math.PI) / 180, 0, 0]}
    position={[-1.5, -0.4, 0]}
  />
  <SC.Mesh
    geometry={new THREE.CylinderBufferGeometry(1, 1, 1, 12)}
    material={new THREE.MeshStandardMaterial({
      color: new THREE.Color(0x303030),
      flatShading: true,
    })}
    scale={[0.35, 2, 0.35]}
    rotation={[(90 * Math.PI) / 180, 0, 0]}
    position={[-2.4, -0.4, 0]}
  />
  <SC.Mesh
    geometry={new THREE.CylinderBufferGeometry(1, 1, 1, 12)}
    material={new THREE.MeshStandardMaterial({
      color: new THREE.Color(0x303030),
      flatShading: true,
    })}
    scale={[0.35, 2, 0.35]}
    rotation={[(90 * Math.PI) / 180, 0, 0]}
    position={[-3.3, -0.4, 0]}
  />

  <!-- Engine -->
  <SC.Mesh
    geometry={new THREE.CylinderBufferGeometry()}
    material={new THREE.MeshStandardMaterial({
      color: new THREE.Color(0xf51000),
      flatShading: true,
    })}
    scale={[0.75, 4.75, 0.75]}
    rotation={[0, 0, (90 * Math.PI) / 180]}
    position={[-1.5, 0, 0]}
  />
  <!-- ExhaustCone -->
  <SC.Mesh
    geometry={new THREE.CylinderBufferGeometry(1, 0.5, 1, 12)}
    material={new THREE.MeshStandardMaterial({
      color: new THREE.Color(0x303030),
      flatShading: true,
    })}
    scale={[0.35, 0.5, 0.35]}
    rotation={[0, 0, 0]}
    position={[-3.3, 0.9, 0]}
    bottomRadius={2}
  />
</SC.Group>
