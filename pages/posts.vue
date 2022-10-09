<template>
<div>
    <h1 text-4xl>投稿一覧</h1>
    <ul>
    <li v-for="(posts, key) in posts" :key="key">{{ posts }}</li>
    </ul>
</div>
</template>

<script>
export default {
    data() {
    return {
        posts: []
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
        title: '投稿一覧'
    }
    }
}
</script>