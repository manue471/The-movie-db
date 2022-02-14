<template>
  <div class="movie-card">
    <img
      src="../../../public/img/miranha.jpg"
      alt="Foto do usuário"
      class="img"
    />

    <span class="movie-content">
      <p>Filme do homem aranha corno</p>
      <h3 class="nota">8.3</h3>
    </span>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from "vue-property-decorator";

@Component({})
export default class MovieCards extends Vue {}
</script>

<style scoped lang="scss">
.movie-card {
  display: flex;
  flex-direction: column;
  border-radius: 10px;
  overflow: hidden;
  text-decoration: none;
  height: 25.375rem;
  width: 18rem;
  display: flex;
  box-shadow: 0px 5px 10px rgb(26, 25, 25);
  img {
    height: 21rem;
  }

  h3 {
    margin-top: 5px;
  }
  gap: 0.7rem;
}

.movie-content {
  display: flex;
  align-items: center;
  flex-direction: column;
  justify-content: center;
  text-align: center;
  font-weight: 600;
  color: rgb(39, 35, 35);
}
</style>
