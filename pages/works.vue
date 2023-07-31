<template>
  <div>
    <p class="text-h2 text-center mt-5 mb-0">Works</p>
    <v-row class="justify-center">
      <v-col cols="3">
        <v-divider class="mb-5"></v-divider>
      </v-col>
    </v-row>
    <v-row class="mb-5 justify-center" max-width="75%">
      <v-col v-for="(work, index) in works" :key="index" cols="4" xl="3">
        <v-card class="mb-3" :href="work.url">
          <v-img :src="work.thumbnail" height="180" contain></v-img>
          <v-card-title>{{ work.title }}</v-card-title>
          <v-card-subtitle class="grey--text">
            {{ work.subtitle }}
          </v-card-subtitle>
          <div class="px-3 py-3">
            <v-chip
              v-for="(tag, tagIndex) in work.tags"
              :key="tagIndex"
              class="mx-1"
            >
              {{ tag }}
            </v-chip>
          </div>
        </v-card>
      </v-col>
    </v-row>
  </div>
</template>

<script>
export default {
  data() {
    return {
      works: [
        {
          title: 'ポートフォリオ',
          subtitle: 'このサイト',
          thumbnail: require('@/static/works/miyashiiii.png'),
          url: '/',
          tags: ['Nuxt.js', 'Vuetify', 'GitHub Pages'],
        },
        {
          title: '数読',
          subtitle: 'Androidアプリ',
          thumbnail: require('@/static/works/sudoku.png'),
          url: 'https://play.google.com/store/apps/details?id=com.miyashiiii.sudoku',
          tags: ['Android', 'Flutter', 'Dart'],
        },
        {
          title: 'TapNum',
          subtitle: 'Androidアプリ',
          thumbnail: require('@/static/works/tapnum.png'),
          url: 'https://play.google.com/store/apps/details?id=com.miyashiiii.tapnum',
          tags: ['Android', 'Unity', 'C#'],
        },
      ],
      certifications: ['AWS DVA', '基本情報', '応用情報', '囲碁四段'],
    }
  },
}
</script>
