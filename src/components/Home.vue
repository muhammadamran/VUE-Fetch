<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <div class="row">
      <div class="col-md-6" align="center">
        <table>
          <tr>
            <th>#</th>
            <th>Username</th>
            <th>Password</th>
            <th>First Name</th>
            <th>Last Name</th>
            <th>Gender</th>
          </tr>
        </table>
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios' 

export default {
  name: 'Home',
  props: {
    msg: String
  },
  data() {
    return {
      allUsers:''
    },
    mounted() {
      axios.get('http://127.0.0.1:8080/00.API/vuebackend/backend_api.php').then((res)=> {
        this.allUsers=res.data
        console.log(res.data)
      })
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
