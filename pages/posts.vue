<template>
<div class="ml-3">
    <input type="text" v-model="keyword" class="">
    <h1>投稿一覧</h1>
    <div class="my-3" style="width: 90%;">
        <table class="table">
            <thead>
                <tr>
                    <th>id</th>
                    <th>カテゴリー</th>
                    <th>タイトル</th>
                </tr>
            </thead>
            <tbody v-for="(post, key)  in posts" :key="key">
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
        title: '投稿一覧'
    }
    },
    computed: {
        filteredPost () {
            return this.posts.filter((post)=> {
                console.log(post)
                return post.title.indexOf(this.keyword) > -1
            })
        }
    },
}
</script>
