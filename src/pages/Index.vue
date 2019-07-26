<template>
  <Layout>
    <article class="intro">
      <div class="intro__wrap">
        <g-image class="intro__img" src="~/assets/images/stack.png" alt srcset />
        <h1 class="intro__text">Hi! This is the starting blog template for Gridsome.</h1>
      </div>
    </article>
    <div class="header-background" />
    <main class="main">
      <article class="article" v-for="{ node } in $page.posts.edges" :key="node.id">
        <g-link class="link" :to="node.path">
          <section class="article__wrap">
            <h1 class="article__title">{{node.title}}</h1>
            <p class="article__date">{{node.date}}</p>
          </section>
        </g-link>
      </article>
    </main>
  </Layout>
</template> 

<page-query>
query Posts {
  posts: allContentfulBlogPost {
    edges {
      node {
        id,
        title,
        path,
        date(format: "D MMMM YYYY")
      }
    }
  }
}
</page-query>

<style lang="postcss">
@custom-media --m-320 (max-width: 320px);
@custom-media --m-375 (max-width: 375px) and (min-width: 321px);
@custom-media --m-414 (max-width: 414px) and (min-width: 376px);
@custom-media --t-768 (max-width: 768px) and (min-width: 415px);
@custom-media --t-1024 (max-width: 1024px) and (min-width: 769px);
@custom-media --m-landscape (max-height: 414px);

.intro {
  height: 85vh;
}
.intro__wrap {
  position: relative;
  margin: 0px 2vw 0px 2vw;
  display: flex;
  height: 100%;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
.intro__text {
  max-width: 95%;
  font-family: var(--base-font);
  font-size: 2.5rem;
  text-align: center;
  color: var(--primary-color);

  @media (--m-320), (--m-landscape) {
    font-size: 1.4rem;
  }
  @media (--m-375), (--m-414) {
    font-size: 1.8rem;
  }
  @media (--t-768) {
    font-size: 3rem;
  }
  @media (--t-1024) {
    font-size: 4rem;
  }
}
.intro__img {
  width: 70%;
  object-fit: contain;
}
.main {
  padding: 2vw 12vw 60px;
  display: -webkit-box;
  display: flex;
  flex-wrap: wrap;
  background-color: #f3f7f9;
  background-color: var(--primary-backround-color);

  @media (--m-320) {
    padding: 2vw 5vw 60px;
  }
  @media (--m-375) {
    padding: 2vw 5vw 60px;
  }
  @media (--m-414) {
    padding: 2vw 5vw 60px;
  }
}
.article {
  margin: 0 20px 40px;
  overflow: hidden;
  min-height: 300px;
  flex: 1 1 300px;
  flex-direction: column;
  text-align: center;
  background: var(--secondary-background-color) 50%;
  background-size: cover;
  border-radius: 0.5rem;
  box-shadow: 1px 1px 5px 0 rgba(0, 0, 0, 0.02),
    1px 1px 15px 0 rgba(0, 0, 0, 0.03);
  transition: all 0.5s ease;
}
.article:hover {
  transition: all 0.4s ease;
  transform: translateY(-5px);
  box-shadow: 1px 10px 30px 0 rgba(0, 0, 0, 0.1);
}
.article__wrap {
  padding: 0 25px;
  display: flex;
  height: 100%;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
.article__title {
  font-family: var(--base-font);
  font-size: 1.5rem;
}
.article__date {
  padding-bottom: 0;
  font-weight: 300;
}
</style>
