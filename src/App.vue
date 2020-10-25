<template>
<div>
  <ul>
    <li v-for="user in users" :key="user.id">{{user.name}}</li>
  </ul>
  <p>那你能不能自动化部署，这是一次自动化试</p>
  </div>
  
</template>

<script>
import axios from 'axios'
export default {
  name: 'App',
  data() {
    return {
      users: []
    }
  },
  mounted() {
    axios.get('/api/user')
    .then(res => this.users = res.data)
    .catch(err => console.log('请求失败!'))
  }
}
</script>


