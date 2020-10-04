<template>
<v-stage ref="stage" :config="stageSize">
      <v-layer ref="layer">
        <v-line :config="{
            x: 20,
            y: 200,
            points: [200, 310 , 250, 315],
            fill:black,
      }"
      />
        <!-- fillRadialGradientColorStops: [0.5, 'white', 0.3, , 0.2, '#ff2d3b', 0.1, '#ff0009'], -->
      </v-layer>
    </v-stage>
</template>

<script>
const width = window.innerWidth;
const height = window.innerHeight;
import Konva from 'konva';

export default {
  data() {
    return {
      stageSize: {
        width: 300,
        height: 250
      },
      radius1: 400,
      radius2: 750
    //   filters: [Konva.Filters.Noise]
    };
  },
  methods: {},
  mounted(){
  },

};
</script>