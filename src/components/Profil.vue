<template>
  <div>
    <!-- PROFIL INFO -->
    <section class="profil">
      <!-- IMAGE -->
      <div class="profil__img">
        <i class="fas fa-user"></i>
      </div>

      <!-- INFORMATIONS -->
      <div class="profil__info">
        <span class="profil__name">Megan</span>
        <span class="profil__data">20 let, Praha</span>
        <form class="status">
          <input id="status-active" class="hidden" name="status" type="radio" value="active">
          <label for="status-active" class="status__online status__online--active">Online</label>
          <input
            id="status-not-present"
            class="hidden"
            name="status"
            type="radio"
            value="not-present"
          >
          <label for="status-not-present" class="status__not-present">Nejsem k dispozici</label>
        </form>
      </div>
    </section>

    <!-- BUTTONS -->
    <section class="events">
      <button
        type="button"
        class="btn btn--primary btn--radius btn--shadow btn--big"
        @click="goPage('Messages', selectedComponent)"
      >Zprávy</button>
      <button
        type="button"
        class="btn btn--primary btn--radius btn--shadow btn--big"
        @click="goPage('Users', selectedComponent)"
      >Uživatelé</button>
    </section>

    <!-- USERS -->
    <section class="users">
      <h2 class="users__title">Vaši přátelé</h2>
      <div class="users__profiles">
        <div
          class="users__profil"
          v-for="(user, x) in users"
          :key="x"
          v-bind:class="{'users__profil--status-online': (user.status == 'on'), 'users__profil--status-not-present': (user.status == 'not-present'), 'users__profil--status-off': (user.status == 'off')}"
        >
          <img :src="user.img">
        </div>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  name: "Profil",
  props: {
    selectedComponent: String,
    goNextFN: Function
  },
  data() {
    return {
      users: [
        {
          img: "./images/girl.png",
          status: "on"
        },
        {
          img: "./images/girl.png",
          status: "on"
        },
        {
          img: "./images/girl.png",
          status: "on"
        },
        {
          img: "./images/girl.png",
          status: "on"
        },
        {
          img: "./images/girl.png",
          status: "on"
        },
        {
          img: "./images/girl.png",
          status: "on"
        },
        {
          img: "./images/girl.png",
          status: "not-present"
        },
        {
          img: "./images/girl.png",
          status: "not-present"
        },
        {
          img: "./images/girl.png",
          status: "not-present"
        },
        {
          img: "./images/girl.png",
          status: "off"
        },
        {
          img: "./images/girl.png",
          status: "off"
        },
        {
          img: "./images/girl.png",
          status: "off"
        },
        {
          img: "./images/girl.png",
          status: "off"
        },
        {
          img: "./images/girl.png",
          status: "off"
        },
        {
          img: "./images/girl.png",
          status: "off"
        },
        {
          img: "./images/girl.png",
          status: "off"
        }
      ]
    };
  }
};
</script>

<style lang="scss" scoped>
@import "../assets/scss/pages/_profil.scss";
</style>


