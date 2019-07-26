<template>
  <footer class="footer">
    <div class="footer__links">
      <a
        class="link footer__link text text__footer"
        href="https://t.me/dmtrshat"
        target="_blank"
      >telegram</a>
      <a
        class="link footer__link text text__footer"
        href="https://www.instagram.com/dmtrshat/"
        target="_blank"
      >instagram</a>
      <a
        class="link footer__link text text__footer"
        href="https://www.facebook.com/dmtrshat"
        target="_blank"
      >facebook</a>
      <a
        class="link footer__link text text__footer"
        href="https://github.com/dmtrshat"
        target="_blank"
      >github</a>
    </div>
    <div class="footer__by">
      <p class="text text__footer">Made with ❤️ by Dmitry Shatokhin.</p>
    </div>
  </footer>
</template>

<style lang="postcss">
@custom-media --m-320 (max-width: 320px);
@custom-media --m-375 (max-width: 375px) and (min-width: 321px);
@custom-media --m-414 (max-width: 414px) and (min-width: 376px);
@custom-media --m-landscape (max-height: 414px);

.footer {
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  max-height: 60px;
  line-height: 1em;
  text-align: center;

  @media (--m-320) {
    max-height: 58px;
  }
  @media (--m-375) {
    max-height: 58px;
  }
  @media (--m-414) {
    max-height: 58px;
  }
}
.footer__links {
  width: 100%;
}
.footer__link {
  padding: 4px;
}
.text__footer {
  padding-bottom: 0;
  font-size: 1rem;
  font-weight: 300;

  @media (--m-320) {
    font-size: 0.7rem;
    font-style: "light";
  }
  @media (--m-375) {
    font-size: 0.7rem;
  }
  @media (--m-414) {
    font-size: 0.7rem;
  }
  @media (--m-landscape) {
    font-size: 0.7rem;
  }
}
</style>
