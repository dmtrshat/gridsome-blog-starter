<template>
  <Layout>
    <div class="post-title">
      <g-image class="post-title__image" :src="$page.post.heroImage.file.url" />
      <h1 class="post-title__title">{{$page.post.title}}</h1>
    </div>
    <article class="post">
      <main class="content" v-html="content" />
    </article>
  </Layout>
</template>

<page-query>
query Post ($path: String!) {
  post: contentfulBlogPost (path: $path) {
    title,
    body,
    heroImage {
      file {
        url
      }
    }
  }
}
</page-query>

<script>
import MarkdownIt from "markdown-it";

export default {
  computed: {
    content() {
      const md = new MarkdownIt();

      return md.render(this.$page.post.body);
    }
  }
};
</script>

<style lang="postcss">
@custom-media --m-320 (max-width: 320px);
@custom-media --m-375 (max-width: 375px) and (min-width: 321px);
@custom-media --m-414 (max-width: 414px) and (min-width: 376px);

.img__post {
  width: 100%;
  height: 100%;
  object-fit: cover;
}
.post-title {
  padding: 60px 0;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
.post-title__image {
  max-height: 500px;
}
.post-title__title {
  margin-bottom: 0;
  font-size: 2.5rem;
  text-align: center;

  @media (--m-320) {
    font-size: 2rem;
  }
  @media (--m-375) {
    font-size: 2rem;
  }
  @media (--m-414) {
    font-size: 2rem;
  }
}
.post {
  padding-bottom: 90px;
  display: flex;
  justify-content: center;
}
.content {
  padding: 2% 5%;
  width: 60%;
  background-color: var(--secondary-background-color);
  border-radius: 0.5rem;
  box-shadow: 8px 14px 38px rgba(39, 44, 49, 0.06),
    1px 3px 8px rgba(39, 44, 49, 0.03);

  @media (--m-320) {
    width: 85%;
  }
  @media (--m-375) {
    width: 85%;
  }
  @media (--m-414) {
    width: 85%;
  }
}
</style>



