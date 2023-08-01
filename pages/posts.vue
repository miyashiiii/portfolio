<template>
  <div>
    <p class="text-h2 text-center mt-5 mb-0">Posts</p>
    <v-row class="justify-center">
      <v-col cols="3">
        <v-divider class="mb-5"></v-divider>
      </v-col>
    </v-row>
    <v-row>
      <v-col cols="12" md="8" xl="4" class="mx-auto">
        <v-list lines="one">
          <v-divider></v-divider>
          <div v-for="item in blogPosts" :key="item.title">
            <v-list-item :href="item.url" class="px-0 pl-md-5 py-0">
              <v-avatar size="36" class="mx-5">
                <img :src="getIconPath(item.url)" contain alt="icon" />
              </v-avatar>
              <v-list-item-content>
                <v-list-item-title class="wrap-text">{{
                  item.title
                }}</v-list-item-title>
                <v-list-item-subtitle>
                  {{ item.date }} {{ getSiteName(item.url) }}
                </v-list-item-subtitle>
              </v-list-item-content>
            </v-list-item>
            <v-divider></v-divider>
          </div>
        </v-list>
      </v-col>
    </v-row>
  </div>
</template>

<script>
import posts from '~/static/posts.json'
export default {
  data() {
    return {
      blogPosts: posts,
    }
  },
  methods: {
    getDomain(url) {
      // URLからドメイン名を抽出
      return new URL(url).hostname
    },
    getIconPath(url) {
      // ドメイン名に基づいてアイコンのパスを返す
      const domain = this.getDomain(url)
      if (domain.includes('hatenablog')) {
        return require('@/static/sns/hatenablog.png')
      } else if (domain.includes('qiita')) {
        return require('@/static/sns/qiita.png')
      } else if (domain.includes('note')) {
        return require('@/static/sns/note.png')
      } else if (domain.includes('zenn')) {
        return require('@/static/sns/zenn.png')
      } else {
        // ドメインが一致しない場合のデフォルトのアイコン
        return require('@/static/sns/hatenablog.png')
      }
    },
    getSiteName(url) {
      const domain = this.getDomain(url)
      if (domain.includes('hatenablog')) {
        return 'はてなブログ'
      } else if (domain.includes('qiita')) {
        return 'Qiita'
      } else if (domain.includes('note')) {
        return 'note'
      } else if (domain.includes('zenn')) {
        return 'Zenn'
      } else {
        return ''
      }
    },
  },
}
</script>
