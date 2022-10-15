<template>
  <div class="ml-3">
      <h1>詳細画面</h1>
      <div class="my-3" style="width: 90%;">
          <table class="table">
              <thead>
                  <tr>
                      <th>id</th>
                      <th>カテゴリー</th>
                      <th>タイトル</th>
                  </tr>
              </thead>
              <tbody>
                  <tr>
                      <th>
                          {{ post.id }}
                      </th>
                      <th>
                          {{ post.category.name }}
                      </th>
                      <th>
                          {{ post.title }}
                      </th>
                  </tr>
              </tbody>
          </table>
      </div>
  </div>
  </template>
  
  <script>
  export default {
      data() {
      return {
          post: []
      }
      },
      async asyncData({ $axios }) {
      const posts = await $axios.$get('portfolio/api/posts/')
      return {
          posts
      }
      },
      head() {
      return {
          title: '詳細画面'
      }
      },
  }
  </script>
  