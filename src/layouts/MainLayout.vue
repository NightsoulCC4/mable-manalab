<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>
        <q-toolbar-title id="layout-name">
          name
        </q-toolbar-title>
      </q-toolbar>
    </q-header>
    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import EssentialLink from 'components/EssentialLink.vue'

// new Vue({
// el:"#layout-name",
// data:
//   {
//     id:1,
//     name:"Home",
//     id:2,
//     name:"Profile"
// },
// methods:{
//   getName:function(){
//     return this.name;
//   }
// }
// }
// )

export default {
 
}


</script>
