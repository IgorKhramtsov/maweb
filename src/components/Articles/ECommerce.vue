<template>
  <Article title="Simple e-commerce website" year="2018"
           :repos="[{
             text: 'mvc pattern',
             href: 'http://github.com/IgorKhramtsov/mvc-pattern'
           },{
             text: 'laravel',
             href: 'http://github.com/IgorKhramtsov/laravel-e-commerce'
           }]"
  >
    <p class="col-md-10">
      On an internship at web-studio Sibirix, I already have pretty solid
      knowledge of frontend and backend for intern, so all tasks was pretty easy
      for me, but still i've got some usefull advices and comments. I start from
      implementing basic MVC pattern in PHP and JS.
    </p>
    <div class="col-md-10">
      <MacOsWindow title="MVC pattern version">
        <img
          src="../../assets/mvc-site.png"
          alt="Preview of developed website using MVC pattern"
          class="gif"
        >
      </MacOsWindow>
    </div>
    <p class="col-md-10">
      After this task, I finally did, what i wanted for a long time. Get my hands on Laravel,
      and then on vue too with guidance of my mentor. I simply move all implemented features
      from custom MVC website, to Laravel, enchancing it, and exploring framework along the way.
      Admin panel I decided to do by myself, to deeply understand, how they works inside.
    </p>
    <div class="col-md-10">
      <MacOsWindow title="Laravel version">
        <img
          src="../../assets/e-commerce.gif"
          alt="Website preview gif"
          class="gif"
        >
      </MacOsWindow>
    </div>
    <p class="col-md-10">
      Resulting website have such features like: review system with moderation;
      catalog with pagination and sorting; order creation; payments via walletone;
      managing products, reviews and orders from admin panel.
    </p>
  </Article>
</template>

<script>
import MacOsWindow from '../MacOsWindow.vue';
import Article from '../Article.vue';

export default {
  components: {
    MacOsWindow,
    Article,
  },
  name: 'ECommerce',
};
</script>

<style lang="scss" scoped>
.gif {
  width: 100%;
  margin-bottom: -1px;
}
</style>
