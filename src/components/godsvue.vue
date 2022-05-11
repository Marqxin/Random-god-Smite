<template>
  <div>
    <br />
    <div class="cards">
      <div class="card" v-for="singleGod in Gods" :key="singleGod.id">
        <div
          class="god_card"
          v-bind:style="{
            'background-image':
              'url(https://webcdn.hirezstudios.com/smite/god-cards/' +
              godURL(singleGod.god) +
              '.jpg)',
          }"
        >
          <div class="god_details">
            <div class="god_pantheon">{{ singleGod.pantheon }}</div>
            <div class="god_details_top">
              <div class="god_name">{{ singleGod.god }}</div>
            </div>
            <div class="god_details_bottom"></div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import godsData from "./../smiteGodList.json";

export default {
  name: "godsvue",
  props: {
    godStats: String,
  },

  data() {
    return {
      Gods: godsData,
    };
  },

  methods: {
    godURL: function (name) {
      return name.replaceAll(" ", "-").replaceAll("'", "");
    },
  },
};
</script>

<style>
.cards {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  margin: 0 auto;
  max-width: 120rem;
  padding-bottom: 3rem;
  width: 100%;
}
.card {
  margin: 0 10px 20px;
}
.god_card {
  background-position: top;
  background-size: cover;
  border: 0.1rem solid #49422b;
  box-shadow: 0 0 15px #000;
  cursor: pointer;
  height: 33.4rem;
  -o-object-fit: cover;
  object-fit: cover;
  overflow: hidden;
  position: relative;
  transition: -webkit-transform 0.2s ease-in-out;
  transition: transform 0.2s ease-in-out;
  transition: transform 0.2s ease-in-out, -webkit-transform 0.2s ease-in-out;
  width: 18rem;
  text-transform: capitalize;
}
.god_card:hover {
  -webkit-transform: scale3d(1.2, 1.2, 1);
  transform: scale3d(1.2, 1.2, 1);
  z-index: 2;
}

.god_details {
  background: #050d1a;
  border-top: 0.1rem solid #49422b;
  bottom: 0;
  padding-top: 3.2rem;
  position: absolute;
  text-align: center;
  -webkit-transform: translate3d(0, 50px, 0);
  transform: translate3d(0, 50px, 0);
  transition: -webkit-transform 0.4s ease-in-out;
  transition: transform 0.4s ease-in-out;
  transition: transform 0.4s ease-in-out, -webkit-transform 0.4s ease-in-out;
  width: 100%;
}
.god_pantheon {
  align-items: center;
  background: #071325;
  border: 1px solid #49422b;
  color: #8f8156;
  border-radius: 1rem;
  display: flex;
  height: 2.5rem;
  justify-content: center;
  left: 50%;
  position: absolute;
  top: -1.4rem;
  -webkit-transform: translate3d(-50%, 0, 0);
  transform: translate3d(-50%, 0, 0);
  width: 10rem;
}

.god_details_top {
  min-height: 50px;
}

.god_name {
  color: #fff;
  font-family: "Penumbra Half Serif";
  font-size: 1.3rem;
  font-weight: 100;
  letter-spacing: 0.3rem;
}

.god_details_bottom {
  border-top: 0.1rem solid #49422b;
  color: #ada176;
  font-size: 1rem;
  font-weight: 100;
  margin-top: 1rem;
  padding: 1rem 0;
}
</style>