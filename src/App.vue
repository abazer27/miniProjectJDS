<template>
  <div id="app">
    <h1>Companies</h1>
    <button>Create New Company</button>
    <h3>Companies List</h3>
    <table border="1">   
        <tr>
          <th>Name</th>
          <th>Address</th>
          <th>Website</th>
          <th>Email</th>
          <th> </th>
        </tr>
        <tr v-for='(data,index) in headers' :key="index">
          <td>{{data.name}}</td>
          <td>{{data.address}}</td>
          <td>{{data.website}}</td>
          <td>{{data.email}}</td>
          <td>
            <button>edit</button>
            <button>remove</button>
          </td>
        </tr> 
    </table>
  </div>
</template>

<script>

export default {
  name: "App",
  components: {
    
  },
  data(){
    return {
      companies :[{}],
      title: "",
      headers: [
        {name : "ana", address:"indo", website:"anablog.co.id", email:"ana@gmail.com"},
        {name : "ani", address:"malay", website:"anablog.co.id", email:"ana@gmail.com"},
        {name : "anu", address:"japan", website:"anablog.co.id", email:"ana@gmail.com"},
        {name : "ane", address:"korea", website:"anablog.co.id", email:"ana@gmail.com"},
        {name : "ano", address:"italy", website:"anablog.co.id", email:"ana@gmail.com"}
      ]
    }
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 3rem;
  margin-left: 1rem;
}
table{
  padding: 1rem;
  margin: 1rem;
}
button{
  background-color: #4CAF50;
  border: none;
  color: white;
  padding: 0.5rem;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  margin: 0.5rem;
  cursor: pointer;
  
}
</style>
