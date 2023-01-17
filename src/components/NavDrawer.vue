<template>
  <v-app-bar :color="COLORS.Primary" dark prominent>
    <v-btn :color="COLORS.LightAccent" icon @click.stop="drawer = !drawer">
      <v-icon>mdi-menu</v-icon>
    </v-btn>
    <v-toolbar-title :style="`color: ${COLORS.Secondary}`" class="toolbar-title"
      >Vue Template</v-toolbar-title
    >

    <v-spacer></v-spacer>
    <!-- <v-menu bottom left>
      <template v-slot:activator="{ on, attrs }">
        <v-btn dark icon v-bind="attrs" v-on="on">
          <v-icon>mdi-dots-vertical</v-icon>
        </v-btn>
      </template>

      <v-list>
        <v-list-item v-for="(item, i) in items" :key="i">
          <v-list-item-title>{{ item.title }}</v-list-item-title>
        </v-list-item>
      </v-list>
    </v-menu> -->
    <v-menu bottom left>
      <template v-slot:activator="{ on, attrs }">
        <v-btn :color="COLORS.LightAccent" v-bind="attrs" v-on="on" icon>
          <v-icon>mdi-account-circle</v-icon>
        </v-btn>
      </template>
      <UserProfile></UserProfile>
    </v-menu>
  </v-app-bar>
  <v-navigation-drawer v-model="drawer" absolute bottom temporary>
    <v-list nav dense>
      <v-list-item-group active-class="deep-purple--text text--accent-4">
        <v-list-item>
          <v-list-item-title>Foo</v-list-item-title>
        </v-list-item>

        <v-list-item>
          <v-list-item-title>Bar</v-list-item-title>
        </v-list-item>

        <v-list-item>
          <v-list-item-title>Fizz</v-list-item-title>
        </v-list-item>

        <v-list-item>
          <v-list-item-title>Buzz</v-list-item-title>
        </v-list-item>
      </v-list-item-group>
    </v-list>
  </v-navigation-drawer>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";
import { COLORS } from "@/helpers/colors";
import UserProfile from "./UserProfile.vue";
export default defineComponent({
  name: "NavDrawer",
  components: { UserProfile },
  setup() {
    const drawer = ref<boolean>(false);
    const items = [
      { title: "Click Me" },
      { title: "Click Me" },
      { title: "Click Me" },
      { title: "Click Me 2" },
    ];

    return { drawer, COLORS, items };
  },
});
</script>
<style scoped>
.toolbar-title {
  display: flex;
}
</style>
