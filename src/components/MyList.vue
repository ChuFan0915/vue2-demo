<template>
  <div class="box">
    <div id="card" v-for="item in users" :key="item.login">
      <a :href="item.html_url">
        <img
          :src="item.avatar_url"
          alt=""
          style="height: 100px; width: 100px; object-fit: cover"
        />
      </a>
      <p>{{ item.login }}</p>
    </div>
  </div>
</template>

<script>
export default {
  mounted() {
    this.$bus.$on("getUsers", (users) => {
      this.users = users;
      // 传过来的users =users
    });
  },
  data() {
    return {
      users: [],
    };
  },
};
</script>

<style scoded>
.box{
    display: flex;
    gap: 20px;
    flex-direction: row;
    flex-wrap: wrap; /* 使子项换行 */
}

#card {
  padding: 10px 100px;
}
</style>
