<template>
  <v-app-bar :color="COLORS.Primary" dark prominent>
    <v-btn :color="COLORS.LightAccent" icon @click.stop="drawer = !drawer">
      <v-icon>mdi-menu</v-icon>
    </v-btn>
    <v-toolbar-title :style="`color: ${COLORS.Secondary}`" class="toolbar-title"
      >Vue Template</v-toolbar-title
    >

    <v-spacer></v-spacer>

    <v-btn :color="COLORS.LightAccent" icon>
      <v-icon>mdi-account-circle</v-icon>
    </v-btn>
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
import { defineComponent, ref, watch } from "vue";
import { COLORS } from "@/helpers/colors";
export default defineComponent({
  name: "NavDrawer",
  components: {},
  setup() {
    const drawer = ref<boolean>(false);

    watch(
      () => drawer.value,
      (oldValue, newValue) => {
        console.log(oldValue, newValue);
      }
    );
    return { drawer, COLORS };
  },
});
</script>
<style scoped>
.toolbar-title {
  display: flex;
}
</style>
