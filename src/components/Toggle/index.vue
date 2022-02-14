<template>
  <label class="switch" for="checkbox">
    <input
      type="checkbox"
      id="checkbox"
      :checked="mode === 'dark' ? 'checked' : false"
      @change="$emit('toggle')"
    />
    <div class="slider round"></div>
  </label>
</template>

<script lang="ts">
import { Component, Prop, Vue } from "vue-property-decorator";

@Component({})
export default class Toggle extends Vue {
  // Props:
  @Prop()
  readonly mode!: string;
}
</script>
<style lang="scss" scoped>
.switch {
  display: inline-block;
  height: 1.5rem;
  position: relative;
  width: 3.5rem;
  gap: 1rem;
}

.switch input {
  display: none;
}

.slider {
  background-color: #ccc;
  bottom: 0;
  cursor: pointer;
  left: 0;
  position: absolute;
  right: 0;
  top: 0;
  transition: 0.4s;
}

.slider:before {
  background-color: #fff;
  bottom: 0.5px;
  content: "";
  height: 1.4rem;
  left: 4px;
  position: absolute;
  transition: 0.4s;
  width: 1.4rem;
}

input:checked + .slider {
  background-color: #66bb6a;
}

input:checked + .slider:before {
  transform: translateX(26px);
}

.slider.round {
  border-radius: 34px;
}

.slider.round:before {
  border-radius: 50%;
}

@media (max-width: 550px) {
  .switch {
    height: 1.1rem;
    width: 2.7rem;
  }

  .slider:before {
    height: 1rem;
    width: 1rem;
    left: 0;
  }
}
</style>
