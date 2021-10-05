<template>
  <div id="app">
    <h1>Companies</h1>
    <div class="form-container">
      <form @submit.prevent="preventSubmit">
        <label>Name: </label>
        <input v-model="name" type="text" required /> <br />
        <label>Address:</label>
        <input v-model="address" type="text" required /> <br />
        <label>Website:</label>
        <input v-model="website" type="text" required /> <br />
        <label>Email:</label>
        <input v-model="email" type="email" required /> <br />

        <button>Create New Company</button>
      </form>
    </div>
    <h3>Companies List</h3>
    <table border="1">
      <tr>
        <th>Name</th>
        <th>Address</th>
        <th>Website</th>
        <th>Email</th>
        <th></th>
      </tr>
      <tr v-for="(data, index) in headers" :key="index">
        <td>{{ data.name }}</td>
        <td>{{ data.address }}</td>
        <td>{{ data.website }}</td>
        <td>{{ data.email }}</td>
        <td>
          <button>edit</button>
          <button @click="removeCompanyFromList(index)">remove</button>
        </td>
      </tr>
    </table>
  </div>
</template>

<script>
export default {
  name: "App",
  components: {},
  data() {
    return {
      companies: [{}],
      title: "",
      headers: [
        {
          name: "ana",
          address: "indo",
          website: "anablog.co.id",
          email: "ana@gmail.com",
        },
        {
          name: "ani",
          address: "malay",
          website: "anablog.co.id",
          email: "ana@gmail.com",
        },
        {
          name: "anu",
          address: "japan",
          website: "anablog.co.id",
          email: "ana@gmail.com",
        },
        {
          name: "ane",
          address: "korea",
          website: "anablog.co.id",
          email: "ana@gmail.com",
        },
        {
          name: "ano",
          address: "italy",
          website: "anablog.co.id",
          email: "ana@gmail.com",
        },
      ],
      name: "",
      address: "",
      website: "",
      email: "",
      buttonStatus: "submit",
    };
  },
  methods: {
    addCompany() {
      const company = {
        name: this.name,
        address: this.address,
        website: this.website,
        email: this.email,
      };
      this.headers.unshift(company);
      alert("Congratulation, Your Company has been added");
    },
    deleteTextInput() {
      this.name = "";
      this.address = "";
      this.website = "";
      this.email = "";
    },
    preventSubmit() {
      this.addCompany();
      this.deleteTextInput();
    },
    removeCompanyFromList(i) {
      if (confirm("Are You Sure?")) {
        this.headers.splice(i, 1);
        alert("Your data has been deleted");
      } else {
        alert("You has been canceled");
      }
    },
  },
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
table {
  padding: 1rem;
  margin: 1rem;
}
button {
  background-color: #4caf50;
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
