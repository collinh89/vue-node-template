<template>
  <v-card>
    <v-list>
      <v-list-item>
        <v-list-item-avatar>
          <img src="https://cdn.vuetifyjs.com/images/john.jpg" alt="John" />
        </v-list-item-avatar>

        <v-list-item-content>
          <v-list-item-title>John Leider</v-list-item-title>
          <v-list-item-subtitle>Founder of Vuetify</v-list-item-subtitle>
        </v-list-item-content>

        <v-list-item-action>
          <v-btn :class="fav ? 'red--text' : ''" icon @click="fav = !fav">
            <v-icon>mdi-heart</v-icon>
          </v-btn>
        </v-list-item-action>
      </v-list-item>
    </v-list>

    <v-divider></v-divider>

    <v-list>
      <v-list-item>
        <v-list-item-action>
          <v-switch v-model="message" color="purple"></v-switch>
        </v-list-item-action>
        <v-list-item-title>Enable messages</v-list-item-title>
      </v-list-item>

      <v-list-item>
        <v-list-item-action>
          <v-switch v-model="hints" color="purple"></v-switch>
        </v-list-item-action>
        <v-list-item-title>Enable hints</v-list-item-title>
      </v-list-item>
    </v-list>

    <v-card-actions>
      <v-spacer></v-spacer>

      <v-btn text @click="menu = false"> Cancel </v-btn>
      <v-btn color="primary" text @click="menu = false"> Save </v-btn>
    </v-card-actions>
  </v-card>
</template>

<script lang="ts">
import { defineComponent, ref, watch } from "vue";
import { COLORS } from "@/helpers/colors";
export default defineComponent({
  name: "UserProfile",
  components: {},
  setup() {
    return {};
  },
});
</script>
<style scoped></style>
