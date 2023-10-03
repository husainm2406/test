<template>
  <div v-for="(user, i) in users" :key="i">
    <div>{{user.name}}</div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data(){
    return{
      users: null,
    }
  },
  methods: {
    async getData() {
      const url = 'http://localhost:3000/users'
      let resp = await fetch(url);
      resp = await resp.json();
      this.users = resp;
      console.log(this.users);
    }
  },
  mounted(){
    this.getData();
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
