<template>
  <q-page class="container scene">
    <a-scene
      arjs="patternRatio:0.90; sourceType: webcam; trackingMethod: best; debugUIEnabled: false; maxDetectionRate: 30; canvasWidth: 240; canvasHeight: 180"
      vr-mode-ui="enabled: false" renderer="precision: medium"
    >
      <a-anchor id="marker" type="pattern" url="statics/pattern/pattern-DTD.patt">
        <a-box scale="1.5 1.5 1.5" position="0 0.5 0" material="opacity: 0.5; side: double;color:purple;">
          <a-torus-knot
            radius="0.26"
            radius-tubular="0.05"
            animation="property: rotation; to:360 0 0; dur: 5000; easing: linear; loop: true"
          ></a-torus-knot>
        </a-box>
      </a-anchor>
      <a-entity camera></a-entity>
    </a-scene>
  </q-page>
</template>

<script>
export default {
  name: 'aframe'
}
</script>

<style>
.scene {
  z-index: 100 !important;
}
</style>
