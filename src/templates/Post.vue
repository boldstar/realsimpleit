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
            excerpt
        }
    }
</page-query>

<script>
export default {
    metaInfo() {
        return {
            title: this.$page.post.title,
            meta: [
                {key: 'description', title: this.$page.post.title, content: this.$page.post.excerpt}
            ]
        }
    }
}
</script>

<style>
    .post-title {
        margin-left: 20px;
        color: var(--main);
    }

    @media screen and (max-width: 767px){
        .post-title {
            font-size: 1rem;
        }
    }
</style>
