<template>
  <div class="blogger-big-card">
    <div class="blogger-big-card__img">
      <img :src="getImageUrl" alt="blogger" />
    </div>
    <div class="blogger-big-card__info">
      <h1 class="blogger-big-card__name">{{ name }}</h1>
      <hr />
      <div class="blogger-big-card__stats">
        <div class="blogger-big-card__stat">
          <img src="../assets/images/yt.png" alt="youtube" />
          <div class="blogger-big-card__stat-wrapper">
            <div class="blogger-big-card__stat-subs" v-subs-mask>
              {{ ytSubs }}
            </div>
            <div class="blogger-big-card__stat-text">Подписчиков</div>
          </div>
        </div>
        <div class="blogger-big-card__stat">
          <img src="../assets/images/vk.png" alt="vk" />
          <div class="blogger-big-card__stat-wrapper">
            <div class="blogger-big-card__stat-subs" v-subs-mask>
              {{ vkSubs }}
            </div>
            <div class="blogger-big-card__stat-text">Подписчиков</div>
          </div>
        </div>
        <div class="blogger-big-card__stat">
          <img src="../assets/images/inst.png" alt="instagram" />
          <div class="blogger-big-card__stat-wrapper">
            <div class="blogger-big-card__stat-subs" v-subs-mask>
              {{ instSubs }}
            </div>
            <div class="blogger-big-card__stat-text">Подписчиков</div>
          </div>
        </div>
      </div>
      <hr />
      <div class="blogger-big-card__about">
        <h3 class="blogger-big-card__info-title">Информация о канале</h3>
        <span class="blogger-big-card__info-text">
          Lorem ipsum dolor sit amet, consectetur adipiscing elit. Risus elit
          lobortis pellentesque tellus mi nulla morbi. Risus, quis consectetur
          sagittis pharetra, urna, leo. Egestas porta habitasse fermentum nulla
          neque. At eget leo sed bibendum nunc. Diam neque, eu velit urna,
          feugiat vulputate elit justo. Lectus diam lacus vel donec sit. Vitae
          venenatis amet suscipit enim nec tincidunt sit lacus. Morbi orci, eget
          vitae tortor cras at eu duis. Sit est, cursus sem facilisis sed ac.
          Egestas porta habitasse fermentum nulla neque. At eget leo sed
          bibendum nunc. Diam neque, eu velit urna, feugiat vulputate elit
          justo. Lectus diam lacus vel donec sit. Vitae venenatis amet suscipit
          enim nec tincidunt sit lacus. Morbi orci, eget vitae tortor cras at eu
          duis. Sit est, cursus sem facilisis sed ac
        </span>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    props: {
      name: String,
      img: String,
      ytSubs: Number,
      vkSubs: Number,
      instSubs: Number,
    },
    computed: {
      getImageUrl() {
        return require("../assets/images/bloggers/" + this.img);
      },
    },
  };
</script>

<style lang="scss">
  $bloggerInfoBackgroundColor: black;
  $bloggerInfoTextColor: white;

  .blogger-big-card {
    display: flex;
    display: -webkit-box;
    display: -webkit-flex;
    display: -ms-flexbox;

    border: 2px solid orange;

    color: black;

    &__img {
      display: flex;
      justify-content: center;
      align-items: center;

      overflow: hidden;

      flex: 3;

      border-radius: 5px 0px 0px 5px;

      img {
        flex-shrink: 0;

        min-width: 100%;
        min-height: 100%;
      }
    }

    hr {
      width: 100%;
      height: 1px;

      margin-top: 30px;
    }

    &__info {
      flex: 7;

      width: 100%;

      color: $bloggerInfoTextColor;

      padding: 30px 40px;
    }

    &__name {
      font-weight: 800;
      font-size: 50px;
    }

    &__stats {
      max-width: 570px;

      display: flex;
      display: -webkit-box;
      display: -webkit-flex;
      display: -ms-flexbox;
      flex-wrap: wrap;
      -webkit-flex-wrap: wrap;
      -ms-flex-wrap: wrap;
    }

    &__stat {
      display: flex;
      display: -webkit-box;
      display: -webkit-flex;
      display: -ms-flexbox;

      margin-top: 30px;
      margin-right: 50px;

      &-wrapper {
        margin-left: 20px;
      }

      &-subs {
        font-weight: 700;
        font-size: 30px;
      }
    }

    &__about {
      height: 170px;
      overflow-y: auto;

      margin-top: 30px;
    }

    &__info-title {
      font-weight: 700;
      font-size: 30px;
    }

    &__info-text {
      display: inline-block;

      margin-top: 10px;

      font-weight: 500;
      font-size: 16px;

      line-height: 24px;
    }
  }
</style>
