<template>
  <div>
    <div class="container">
      <div class="image-profile">
        <img class="profile" src="~assets/tenka.jpg" alt="" />
      </div>
      <div class="menu-icon">
        <q-btn
          flat
          dense
          round
          icon="notification_important"
          name="font_download"
          class="text-primary"
          style="font-size: 32px; align-content: center"
          @click="RightDrawerOpen = !RightDrawerOpen"
        />
      </div>
    </div>
    <q-drawer
      side="right"
      v-model="RightDrawerOpen"
      show-if-above
      bordered
      content-class="bg-grey-1"
    >
      <q-list>
        <q-item-label header class="text-grey-8"> Nofication </q-item-label>
        <EssentialLink
          v-for="link in essentialLinks"
          :key="link.title"
          v-bind="link"
        />
      </q-list>
    </q-drawer>
    <div>
      <div class="text-h3" style="margin-left: 50px">
        <span class="text-weight-bold">What's up?</span
        ><span class="text-h6"><br />New blog here</span>
      </div>
    </div>
    <div class="q-pa-md">
      <q-carousel
        v-model="slide"
        transition-prev="slide-right"
        transition-next="slide-left"
        animated
        control-color="primary"
        class="rounded-borders"
        style="height:150px"
      >
        <q-carousel-slide name="style" class="column no-wrap flex-center">
          <img class="carousel-pic" src="~/assets/tenka2.jpg" alt="">
        </q-carousel-slide>
        <q-carousel-slide name="tv" class="column no-wrap flex-center">
          <q-icon name="live_tv" color="primary" size="56px" />
          <div class="q-mt-md text-center">b</div>
        </q-carousel-slide>
        <q-carousel-slide name="layers" class="column no-wrap flex-center">
          <q-icon name="layers" color="primary" size="56px" />
          <div class="q-mt-md text-center">c</div>
        </q-carousel-slide>
        <q-carousel-slide name="map" class="column no-wrap flex-center">
          <q-icon name="terrain" color="primary" size="56px" />
          <div class="q-mt-md text-center">d</div>
        </q-carousel-slide>
      </q-carousel>

      <div class="row justify-center">
        <q-btn-toggle
          glossy
          v-model="slide"
          :options="[
            { label: 1, value: 'style' },
            { label: 2, value: 'tv' },
            { label: 3, value: 'layers' },
            { label: 4, value: 'map' },
          ]"
        />
      </div>
    </div>
  </div>
</template>

<script>
import EssentialLink from "components/EssentialLink.vue";

const linksData = [
  {
    title: "Docs",
    caption: "quasar.dev",
    icon: "school",
    link: "https://quasar.dev",
  },
  {
    title: "Github",
    caption: "github.com/quasarframework",
    icon: "code",
    link: "https://github.com/quasarframework",
  },
  {
    title: "Discord Chat Channel",
    caption: "chat.quasar.dev",
    icon: "chat",
    link: "https://chat.quasar.dev",
  },
  {
    title: "Forum",
    caption: "forum.quasar.dev",
    icon: "record_voice_over",
    link: "https://forum.quasar.dev",
  },
  {
    title: "Twitter",
    caption: "@quasarframework",
    icon: "rss_feed",
    link: "https://twitter.quasar.dev",
  },
  {
    title: "Facebook",
    caption: "@QuasarFramework",
    icon: "public",
    link: "https://facebook.quasar.dev",
  },
  {
    title: "Quasar Awesome",
    caption: "Community Quasar projects",
    icon: "favorite",
    link: "https://awesome.quasar.dev",
  },
];

export default {
  name: "MainLayout",
  components: { EssentialLink },
  data() {
    return {
      RightDrawerOpen: false,
      essentialLinks: linksData,
      slide: 'style',
      lorem: 'Lorem ipsum dolor, sit amet consectetur adipisicing elit. Itaque voluptatem totam, architecto cupiditate officia rerum, error dignissimos praesentium libero ab nemo provident incidunt ducimus iusto perferendis porro earum. Totam, numquam?'
    };
  },
};
</script>

<style lang="scss" scoped>
.carousel-pic{
  height: 100%;
}
.profile {
  border-radius: 25px;
  width: 100%;
}
.image-profile {
  width: 150px;
  border-radius: 25px;
  border: 2px solid black;
  margin: 50px;
}
.container {
  display: flex;
}
.menu-icon {
  width: 200px;
  display: flex;
  border: 2px solid black;
  margin: 50px;
}
</style>