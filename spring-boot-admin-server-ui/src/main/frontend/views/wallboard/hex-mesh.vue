<!--
  - Copyright 2014-2018 the original author or authors.
  -
  - Licensed under the Apache License, Version 2.0 (the "License");
  - you may not use this file except in compliance with the License.
  - You may obtain a copy of the License at
  -
  -     http://www.apache.org/licenses/LICENSE-2.0
  -
  - Unless required by applicable law or agreed to in writing, software
  - distributed under the License is distributed on an "AS IS" BASIS,
  - WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
  - See the License for the specific language governing permissions and
  - limitations under the License.
  -->


<template>
  <div class="content has-text-centered">
    <p class="is-size-3 has-text-warning">
      Welcome to Efectura Wallboard
    </p>
    <router-link to="/">
      <img src="assets/img/efectura-large.png" />
    </router-link>
  </div>
</template>

<script>
</script>

<style lang="scss">
  @import "~@/assets/css/utilities";

  .hex-mesh {
    background-color: $grey-dark;
    width: 100%;
    height: 100%;
    display: flex;
    justify-content: space-around;
    align-items: center;
  }

  .hex {
    fill-opacity: 0.05;
    stroke-width: 0.5;
    stroke-opacity: 0.8;

    & polygon {
      fill: none;
      stroke: $grey;
      transition: all $easing 250ms;
    }

    @each $name, $pair in $colors {
      &.is-#{$name} polygon {
        $color: nth($pair, 1);
        fill: $color;
        fill-opacity: 0.3;
        stroke: $color;
        stroke-opacity: 0.95;
        stroke-width: 1.5;
      }
    }

    &.is-selectable:hover {
      cursor: pointer;
      & polygon {
        fill-opacity: 0.85;
        stroke-opacity: 1;
      }
    }

    &__body {
      width: 100%;
      height: 100%;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
    }
  }
</style>
