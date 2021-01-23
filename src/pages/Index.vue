<template>
  <div>
    <div class="container">
      <div class="image-profile">
        <img class="profile" src="~assets/tenka.jpg" alt="">
      </div>
      <div class="menu-icon">
        <q-btn flat dense round icon="notification_important" name="font_download" class="text-primary" style="font-size: 32px;" @click="RightDrawerOpen = !RightDrawerOpen"/>
      </div>
    </div>
      <q-drawer side="right" v-model="RightDrawerOpen" show-if-above bordered content-class="bg-grey-1"
    >
      <q-list>
        <q-item-label header class="text-grey-8">
          Nofication
        </q-item-label>
        <EssentialLink v-for="link in essentialLinks" :key="link.title" v-bind="link"/>
      </q-list>
    </q-drawer>
  </div>
</template>

<script>
import EssentialLink from 'components/EssentialLink.vue'

const linksData = [
  {
    title: 'Docs',
    caption: 'quasar.dev',
    icon: 'school',
    link: 'https://quasar.dev'
  },
  {
    title: 'Github',
    caption: 'github.com/quasarframework',
    icon: 'code',
    link: 'https://github.com/quasarframework'
  },
  {
    title: 'Discord Chat Channel',
    caption: 'chat.quasar.dev',
    icon: 'chat',
    link: 'https://chat.quasar.dev'
  },
  {
    title: 'Forum',
    caption: 'forum.quasar.dev',
    icon: 'record_voice_over',
    link: 'https://forum.quasar.dev'
  },
  {
    title: 'Twitter',
    caption: '@quasarframework',
    icon: 'rss_feed',
    link: 'https://twitter.quasar.dev'
  },
  {
    title: 'Facebook',
    caption: '@QuasarFramework',
    icon: 'public',
    link: 'https://facebook.quasar.dev'
  },
  {
    title: 'Quasar Awesome',
    caption: 'Community Quasar projects',
    icon: 'favorite',
    link: 'https://awesome.quasar.dev'
  }
];

export default {
  name: 'MainLayout',
  components: { EssentialLink },
  data () {
    return {
      RightDrawerOpen: false,
      essentialLinks: linksData
    }
  }
}

</script>

<style lang="scss" scoped>
.profile{
  border-radius:25px;
  width:100%;
}
.image-profile {
  width: 150px;
  border-radius: 25px;
  border: 2px solid black;
  margin: 50px;
}
.container{
  display: flex;
}
.menu-icon{
  width: 200px;
  display: flex;
}
</style>