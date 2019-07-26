<template>
  <Layout>
    <main class="me">
      <h1 class="me__title">This is emty about page.</h1>
    </main>
  </Layout>
</template>

<script>
export default {
  metaInfo: {
    title: "Me"
  }
};
</script>

<style lang="postcss">
@custom-media --m-320 (max-width: 320px);
@custom-media --m-375 (max-width: 375px) and (min-width: 321px);
@custom-media --m-414 (max-width: 414px) and (min-width: 376px);
@custom-media --m-landscape (max-height: 414px);

.me {
  height: 100vh;
  padding: 0 2vh 0 2vh;
  display: -webkit-box;
  display: flex;
  -webkit-box-orient: vertical;
  -webkit-box-direction: normal;
  flex-direction: column;
  -webkit-box-pack: center;
  justify-content: center;
  align-items: center;
  background-image: var(--primary-backround-color);
}
.me__title {
  font-family: var(--base-font);
  text-align: right;

  @media (--m-320), (--m-375), (--m-414) {
    font-size: 1rem;
  }
  @media (--m-landscape) {
    font-size: 0.8rem;
  }
}
</style>
