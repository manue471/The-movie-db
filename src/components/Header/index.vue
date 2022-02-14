<template>
  <div class="content">
    <div class="nav">
      <router-link :to="{ name: 'dashboard' }"><p>Home</p></router-link>

      <router-link :to="{ name: 'dashboard' }"><p>Portfolio</p></router-link>

      <router-link :to="{ name: 'dashboard' }"><p>Contact</p></router-link>
    </div>

    <img src="../../../public/icons/vue.svg" />
    <toggle :mode="mode" @toggle="$emit('toggle')" class="toggle" />
  </div>
</template>

<script lang="ts">
import { Component, Prop, Emit, Vue } from "vue-property-decorator";

// Components:
import Toggle from "@/components/Toggle/index.vue";

@Component({
  components: {
    Toggle,
  },
})
export default class HeaderComponent extends Vue {
  constructor() {
    super();
  }

  @Prop()
  readonly mode!: string;
}
</script>

<style scoped lang="scss">
.content {
  width: 90%;
  background: #0a3138;
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin: 0.1rem;
  height: 4rem;
  border-radius: 5px;
  color: rgb(223, 223, 223);
  box-shadow: 0.688rem 0.413rem 0.5rem rgba(0, 0, 0, 0.25);

  text-align: center;
  font-size: 1.4rem;

  img {
    height: 80%;
  }

  a {
    text-decoration: none;
    color: rgb(223, 223, 223);
    margin-left: 0.6rem;
  }
  a:hover {
    color: #115461;
  }

  .nav {
    display: flex;
    flex-direction: row;
    margin-left: 1rem;
    font-size: 1.2rem;
    justify-content: space-between;
    align-items: center;
    gap: 0.3rem;
    width: max-content;
  }

  .toggle {
    margin-right: 3rem;
  }
}

@media (max-width: 550px) {
  .content {
    .nav {
      margin-left: 0rem;
      p {
        font-size: 0.9rem;
      }
    }

    img {
      height: 65%;
    }
  }
}
</style>
