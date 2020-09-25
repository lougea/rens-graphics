<template>
<div class="min-h-screen bg-white">
  <nav  class="bg-white border-b border-gray-200">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex justify-between h-16">
        <div class="flex">
          <div @click.stop="navOpen = !navOpen" class="flex-shrink-0 flex items-center">
            <h1>Menu</h1>
          </div>
          <div class="hidden sm:-my-px sm:ml-6 space-x-8 sm:flex">
          </div>
        </div>
      </div>
    </div>
  </nav>

    <!--
      Mobile menu, toggle classes based on menu state.

      Open: "block", closed: "hidden"
    -->
  

  <div v-if="navOpen" class=" absolute inset-0 bg-red-500 h-full min-h-screen">
    <h1  @click.stop="navOpen = !navOpen">close</h1>
  </div>
  <!-- <div class="py-10">
    <main>
      <div class="max-w-7xl mx-auto sm:px-6 lg:px-8">
  
        <div class="px-4 py-8 sm:px-0">
        </div>
 
      </div>
    </main>
  </div> -->
  </div>
</template>

<script>
export default {
  data(){
    return {
      navOpen: false
    }
  }
}
</script>

<style>
/* Sample `apply` at-rules with Tailwind CSS
.container {
@apply min-h-screen flex justify-center items-center text-center mx-auto;
}
*/
</style>
