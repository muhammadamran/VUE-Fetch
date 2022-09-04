<template>
	<div class="header">
		<h1>My Website</h1>
		<p>Resize the browser window to see the effect.</p>
	</div>
  <hr>
  <div class="row">
    <div class="col-md-12" align="center">
      <table class="table">
        <tr>
          <!-- <th>#</th> -->
          <th>Username</th>
          <th>Password</th>
          <th>First Name</th>
          <th>Last Name</th>
          <th>Gender</th>
        </tr>
        <tbody>
          <tr v-for="users in allUsers" v-bind:key="users.id">
            <td>{{users.username}}</td>
            <td>{{users.password}}</td>
            <td>{{users.fname}}</td>
            <td>{{users.lname}}</td>
            <td>{{users.gender}}</td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>

  <div class="for-footer">
    <div class="footer">
      <p>Devlopment By @Muhammad Amran &copy; {{ new Date().getFullYear() }}</p>
    </div>
  </div>
</template>

<script>
  import "@/assets/style.css";
	import axios from 'axios' 

	export default {
		name: 'Home',
		props: {
			msg: String
		},
		data() {
			return {
				allUsers:''
			}
		},
		mounted() {
			axios.get('http://127.0.0.1:8080/00.API/vuebackend/backend_api.php').then((res)=> {
				this.allUsers=res.data
				console.log(res.data)
			})
		}
	}
</script>