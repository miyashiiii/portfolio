<template>
  <div>
    <v-app-bar app color="primary" dark>
      <v-app-bar-nav-icon
        class="hidden-md-and-up"
        @click="drawer = true"
      ></v-app-bar-nav-icon>

      <v-toolbar-title>
        <router-link to="/">miyashiiii portfolio</router-link>
      </v-toolbar-title>

      <v-spacer></v-spacer>
      <div class="hidden-sm-and-down">
        <v-btn text to="/posts">Posts</v-btn>
        <v-btn text to="/works">Works</v-btn>
      </div>
    </v-app-bar>

    <!-- drawer -->
    <v-navigation-drawer v-model="drawer" fixed temporary>
      <v-list nav dense>
        <v-list-item-group>
          <v-list-item to="/posts">
            <v-list-item-title>Posts</v-list-item-title>
          </v-list-item>
          <v-list-item to="/works">
            <v-list-item-title>Works</v-list-item-title>
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>
  </div>
</template>
<script>
// ここから追加
export default {
  data() {
    return {
      drawer: false,
    }
  },
}
// ここまで追加
</script>
