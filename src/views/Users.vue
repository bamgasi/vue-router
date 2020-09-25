<template>
  <v-layout
    row
    wrap
    pt-5
    text-xs-center
    style="max-width: 500px; margin: 0 auto"
  >
    <v-flex xs12>
      <h1>Users</h1>
      <p>사용자를 검색해 주세요.</p>
    </v-flex>

    <v-flex xs12>
      <v-text-field label="사용자 번호입력" v-model="userId"></v-text-field>
      <v-btn
        @click="
          $router.push({
            name: 'users-detail',
            params: {
              id: userId,
            },
          })
        "
        >검색</v-btn
      >
    </v-flex>

    <v-flex xs12>
      <router-view></router-view>
    </v-flex>
  </v-layout>
</template>

<script>
export default {
  data() {
    return {
      userId: null,
    };
  },
  beforeRouteEnter(to, from, next) {
    console.log("before enter");
    next();
  },
  beforeRouteLeave(to, from, next) {
    console.log("before leave");
    next();
  },
  created() {
    console.log("created");
  },
  destroyed() {
    console.log("destroyed");
  },
};
</script>

<style>
</style>