<template>
  <v-app-bar app color="primary" dark>
    <!-- 左側にサイトタイトルを表示 -->
    <v-toolbar-title>
      <router-link to="/">miyashiiii portfolio</router-link>
    </v-toolbar-title>

    <!-- 右側にリンクボタンを表示 -->
    <v-spacer></v-spacer>
    <v-btn text to="/posts">Posts</v-btn>
    <v-btn text to="/works">Works</v-btn>
  </v-app-bar>
</template>
