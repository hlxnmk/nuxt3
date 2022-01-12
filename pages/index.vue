<script setup lang="ts">
// import Banner from './components/Banner.vue';

</script>

<template>
  <div>
    <div class="row">
      <div class="col-xs-offset-2 col-xs-8">
        <Banner />
      </div>
    </div>
    <div class="row">
      <div class="col-xs-2 col-xs-offset-2">
        <div class="list-group">
          <NuxtLink class="list-group-item" active-class="active" to="/about">About</NuxtLink>
          <NuxtLink class="list-group-item" active-class="active" to="/home">Home</NuxtLink>
        </div>
      </div>
      <div class="col-xs-6">
        <div class="panel">
          <div class="panel-body">
            <!-- 指定组件的呈现位置 -->
            <NuxtChild />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>


