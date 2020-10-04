<template>
<div class="min-h-screen bg-white">
    <div class="max-w-7xl mx-auto p-6">
      <div class="flex">
          <div v-show="!navOpen && !aboutOpen && !workOpen && !galleryOpen && !contactOpen" @click.stop="navOpen = !navOpen" class="z-30 flex-shrink-0 flex items-center">
           <img class="w-20 h-auto cursor-pointer" src="~/assets/Menu-button.png"/>
        </div>
      </div>
    </div>
    <div class="absolute inset-0 ">
      <!-- <img src="~/assets/head.gif" alt="" class="w-64 h-64"> -->
       <Canvas :nav-open="navOpen"/>
    </div>
        <div class="absolute bottom-0 right-0 z-10 pb-10  px-4 sm:px-6 lg:px-8">
         <img class="w-20 h-auto" src="~/assets/rens-vos1.png"/>
    </div>
  
  <div v-if="navOpen" class="z-30 absolute inset-0 bg-transparent h-full min-h-screen">
    <div class="flex m-auto min-h-screen">
        <div class="p-6 absolute top-0 left-0">
          <img @click.stop="navOpen = !navOpen" class="w-20 h-auto cursor-pointer strikediag" src="~/assets/Menu-button.png"/>
        </div>
          
        <ul class="m-auto text-4xl text-center">
          <li @click="aboutLink()">
           <span class="strikediagLeft rounded-md px-5 cursor-pointer">ABOUT</span> 
          </li>
          <li  @click="workLink()">
            <span class="strikediagRight rounded-md px-5 cursor-pointer">SELECTED WORK</span>
          </li>
          <li  @click="galleryLink()">
            <span class="strikediagLeft rounded-md px-5 cursor-pointer">GALLERY</span>
          </li>
          <li  @click="contactLink()">
            <span class="strikediagRight rounded-md px-5 cursor-pointer">CONTACT</span>
          </li>
        </ul>
    </div>
  </div>

  <div v-if="aboutOpen && !navOpen" class="z-30 absolute inset-0 bg-transparent h-full min-h-screen flex">
    <div class="p-6 absolute top-0 left-0"> 
        <img @click.stop="navOpen = !navOpen, aboutOpen = false" class="w-20 h-auto cursor-pointer" src="~/assets/Menu-button.png"/>
        <img @click.stop="aboutOpen = false" class="w-20 h-auto strikediag cursor-pointer" src="~/assets/Menu-button.png"/>
    </div>
    <div class="flex m-auto">
      <p class="m-auto text-4xl px-40 py-5 leading-tight font-serif uppercase">Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.</p>
    </div>
  </div>
  <div v-if="workOpen && !navOpen" class="z-30 absolute inset-0 bg-transparent h-full min-h-screen flex">
    <div class="p-6 absolute top-0"> 
        <img @click.stop="navOpen = !navOpen, workOpen = false" class="w-20 h-auto cursor-pointer" src="~/assets/Menu-button.png"/>
        <img @click.stop="workOpen = false" class="w-20 h-auto strikediag cursor-pointer" src="~/assets/Menu-button.png"/>
    </div>
    <div class="flex m-auto">
      <p class="m-auto text-4xl px-40 py-5 leading-tight font-serif uppercase">WORKS PROJECT</p>
    </div>
  </div>
  <div v-if="galleryOpen && !navOpen" class="z-30 absolute inset-0 bg-transparent h-full min-h-screen flex">
    <div class="p-6 absolute top-0"> 
      <img @click.stop="navOpen = !navOpen, galleryOpen = false" class="w-20 h-auto cursor-pointer" src="~/assets/Menu-button.png"/>
      <img @click.stop="galleryOpen = false" class="w-20 h-auto strikediag cursor-pointer" src="~/assets/Menu-button.png"/>
    </div>
    <div class="flex m-auto">
      <p class="m-auto text-4xl px-40 py-5 leading-tight font-serif uppercase">GALLERY</p>
    </div>
  </div>
  <div v-if="contactOpen && !navOpen" class="z-30 absolute inset-0 bg-transparent h-full min-h-screen flex">
     <div class="p-6 absolute top-0"> 
      <img @click.stop="navOpen = !navOpen, contactOpen = false" class="w-20 h-auto cursor-pointer" src="~/assets/Menu-button.png"/>
      <img @click.stop="contactOpen = false" class="w-20 h-auto strikediag cursor-pointer" src="~/assets/Menu-button.png"/>
    </div>
    <div class="flex m-auto">
      <p class="m-auto text-4xl px-40 py-5 leading-tight font-serif uppercase">CONTACT</p>
    </div>
  </div>

  </div>
</template>

<script>
import Canvas from '~/components/Canvas.vue'
export default {
  components: {
  },
  data(){
    return {
      navOpen: false,
      aboutOpen: false,
      workOpen: false,
      galleryOpen: false,
      contactOpen: false
    }
  },
  methods:{
    aboutLink(){
      this.navOpen = false
      this.aboutOpen = true 
    },
     workLink(){
      this.navOpen = false
      this.workOpen = true 
    },
     galleryLink(){
      this.navOpen = false
      this.galleryOpen = true 
    },
     contactLink(){
      this.navOpen = false
      this.contactOpen = true 
    },
  },
}
</script>

<style>
.strikediagLeft {
   background: transparent
}
.strikediagRight {
   background: transparent
}
.strikediag {
   background: linear-gradient(to top left,transparent 0%,transparent 45%, red 50%, transparent 55%, transparent 100%);
}
.strikediagLeft:hover {
  background: linear-gradient(to top left,transparent 0%,transparent 45%, red 50%, transparent 55%, transparent 100%);
}
.strikediagRight:hover {
  background: linear-gradient(to top right,transparent 0%,transparent 45%, red 50%, transparent 55%, transparent 100%);
}
/* Sample `apply` at-rules with Tailwind CSS
.container {
@apply min-h-screen flex justify-center items-center text-center mx-auto;
}
*/
</style>
