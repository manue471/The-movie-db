<template>
  <div class="body" :class="mode">
    <header-component :mode="mode" @toggle="toggleChange" />
    <router-view></router-view>
  </div>
</template>

<script lang="ts">
import Vue from "vue";
import Component from "vue-class-component";

// Components:
import MovieCards from "@/components/MovieCards/index.vue";
import HeaderComponent from "@/components/Header/index.vue";

@Component({
  components: {
    MovieCards,
    HeaderComponent,
  },
})
export default class Home extends Vue {
  public mode: string;

  constructor() {
    super();
    this.mode = "dark";
  }

  // Methods:
  public toggleChange(): any {
    if (this.mode === "dark") {
      return (this.mode = "light");
    } else {
      this.mode = "dark";
    }
  }
}
</script>
<style lang="scss" scoped>
.body {
  display: flex;
  flex-direction: column;
  width: 100vw;
  align-items: center;
  min-height: 100vh;
  background: #f3f3f3;
}

.dark {
  background: #0c1722;
  color: #f3f3f3;
}

.light {
  background: #f3f3f3;
  color: #0c1722;
}
</style>
