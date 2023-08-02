<template>
  <div>
    <!-- Profile section -->
    <v-row class="align-center justify-center">
      <v-col cols="6" sm="4">
        <v-img :src="profileImage" contain height="350" weight="350"></v-img>
      </v-col>
      <v-col cols="6" sm="4">
        <p class="font-weight-bold mb-3 prof-text">miyashiiii</p>
        <p class="mb-3 prof-text">Software Engineer</p>
        <p class="prof-text">Saitama, Japan</p>
      </v-col>
    </v-row>

    <v-divider></v-divider>

    <!-- AboutMe section -->
    <p class="text-h2 text-center mt-5 mb-0">About Me</p>
    <v-row class="justify-center">
      <v-col cols="3">
        <v-divider class="mb-5"></v-divider>
      </v-col>
    </v-row>
    <v-col class="mx-auto" cols="12" md="6" xl="3">
      <p>
        <span v-for="(line, index) in aboutMe" :key="index">
          {{ line }}<br />
        </span>
      </p>
    </v-col>

    <!-- Links section -->
    <v-row class="mt-5 justify-center">
      <div
        v-for="(link, index) in links"
        :key="index"
        class="mx-3"
        :href="link.url"
      >
        <a>
          <v-img :src="link.icon" contain height="32" width="32"></v-img>
        </a>
      </div>
    </v-row>
  </div>
</template>

<script>
export default {
  data() {
    return {
      profileImage: require('@/static/miyashiiii.png'),
      aboutMe: [
        '1993年生まれ。埼玉県在住。',
        '都内の受託開発企業でサーバーサイドエンジニアをしています。',
        'Pythonが好きです。',
      ],
      links: [
        {
          url: 'https://twitter.com/mysh_iiii',
          icon: require('@/static/sns/twitter.png'),
        },
        {
          url: 'https://miyashiiii.hatenablog.jp/',
          icon: require('@/static/sns/hatenablog.png'),
        },
        {
          url: 'https://qiita.com/miyashiiii',
          icon: require('@/static/sns/qiita.png'),
        },
        {
          url: 'https://github.com/miyashiiii',
          icon: require('@/static/sns/github.png'),
        },
      ],
    }
  },
}
</script>
