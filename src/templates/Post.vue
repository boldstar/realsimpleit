<template>
    <ServiceLayout>
        <h2 class="post-title">{{ $page.post.title }}</h2>
        <div class="markdown-body" v-html="$page.post.content" />
    </ServiceLayout>
</template>

<page-query>
    query Post ($path: String!) {
        post:  post( path: $path ) {
            title
            content
        }
    }
</page-query>

<script>
export default {
    metaInfo() {
        return {
            title: this.$page.post.title
        }
    }
}
</script>

<style>
    .post-title {
        margin-left: 20px;
        color: var(--main);
    }
</style>
