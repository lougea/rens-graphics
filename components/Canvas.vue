<template>
<v-stage ref="stage" :config="stageSize">
      <v-layer ref="layer">
        <v-circle ref="stain1" :config="{
            x: 950,
            y: 150,
            radius: radius1,
            fillRadialGradientStartRadius: 0,
            fillRadialGradientEndRadius: navOpen ? 900 : 290,
            fillRadialGradientStartPoint: {
                x: 0,
                y: 0
            },
            fillRadialGradientEndPoint: {
                x: 0,
                y: 0
            },
              fillRadialGradientColorStops: [0, 'transparent', 0.6, 'white', 0.3, '#ffb3b8', 0,'#ff0009'],   
        }"
      />
    <v-circle ref="stain2" :config="{
            x: 150,
            y: 550,
            radius: radius2,
            fillRadialGradientStartRadius: 0,
            fillRadialGradientEndRadius: navOpen ? 1100 :  650 ,
            fillRadialGradientColorStops: [0, 'transparent', 0.5, 'white', 0.3, '#ffb3b8', 0,'#ff0009'],
                
        }"
      />
      </v-layer>
    </v-stage>
</template>

<script>
const width = window.innerWidth;
const height = window.innerHeight;
import Konva from 'konva';

export default {
  props:{
    navOpen: Boolean,
    required: true,
    default: false
  },
  data() {
    return {
      stageSize: {
        width: width,
        height:height
      },
      radius1: 600,
      radius2: 750
    //   filters: [Konva.Filters.Noise]
    };
  },
  methods: {
    handle1MouseMove() {    
    const vm = this
    const amplitude = 50;
    const period = 5000;
    // in ms
    const centerX = vm.$refs.stage.getNode().getWidth() / 2;

    const stain1 = this.$refs.stain1.getNode();

    const anim1 = new Konva.Animation(function(frame) {
      stain1.setX(
        amplitude * Math.sin((frame.time * 2 * Math.PI) / period) + (width -20)
      )
    }, stain1.getLayer())
     anim1.start()},
    handle2MouseMove() {
    const vm = this
    const amplitude = 150;
    const period = 6500;
    // in ms
    const centerX = vm.$refs.stage.getNode().getWidth() / 2;

    const stain2 = this.$refs.stain2.getNode();

    const anim2 = new Konva.Animation(function(frame) {
      stain2.setX(
        amplitude * Math.sin((frame.time * 2 * Math.PI) / period) + 100
      )
    }, stain2.getLayer())
     anim2.start()
    }      
    },
  computed:{
    // EndRadius1(){
    //   if(navOpen){
    //     return 500
    //   }
    //   return 290
    // }
  },
  mounted(){
    console.log(this.navOpen)
    this.handle1MouseMove()
    this.handle2MouseMove()
  },
  updated() {
    // recache
    const stain1Node = this.$refs.stain1.getNode()
    const stain2Node = this.$refs.stain2.getNode()
    // may need to redraw layer manually
    stain1Node.cache();
    stain2Node.cache();
  }
}
</script>