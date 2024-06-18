<template>
  <div class="myForm">
    <form action="" @submit.prevent="addUser">
      <div>
        <label for="">Name</label>
        <input v-model.lazy="information.name" type="text" />
      </div>
      <div>
        <label for="">Age</label>
        <input v-model="information.age" type="number" />
      </div>
      <div>
        <label for="">Grade</label>
        <input v-model="information.grade" type="text" />
      </div>
      <div class="radioButton">
        <div>
          <label for="male">Male</label>
          <input
            name="male"
            v-model="information.gender"
            type="radio"
            value="Male"
          />
        </div>
        <div>
          <label for="female">Female</label>
          <input
            name="female"
            v-model="information.gender"
            type="radio"
            value="Female"
          />
        </div>
      </div>
      <div>
        <label for="">Sports</label>
        <input v-model="sport" type="text" />
        <input @click="addTo" type="button" value="add" />
      </div>
      <div class="actions">
        <input
          style="width: 300px; margin-top: 10px"
          type="submit"
          value="submit"
        />
      </div>
      <div>
        <label for="">Change Age</label>
        <input v-model="changeAge" type="number" />
      </div>
      <div>
        <label for="">ID</label> <input v-model="changeID" type="number" />
      </div>
      <input
        style="width: 300px; margin-top: 10px"
        @click="updateUser"
        type="button"
        value="update"
      />
    </form>
    <div class="users" v-for="(user, index) in users" :key="index">
      <ul>
        <li><strong>ID: </strong>{{ user.id }}</li>
        <li><strong>Name: </strong>{{ user.name }}</li>
        <li><strong>Age: </strong>{{ user.age }}</li>
        <li><strong>Grade: </strong>{{ user.grade }}</li>
        <li><strong>Gender: </strong>{{ user.gender }}</li>
        <li>
          <strong>FavouritSports:</strong>
          <ul>
            <li v-for="(sport, i) in user.favouritSports" :key="i">
              {{ sport }}
            </li>
          </ul>
        </li>
        <li>
          <input
            style="
              border: none;
              color: white;
              background-color: red;
              width: 300px;
              margin-top: 10px;
              padding: 10px 0px;
            "
            @click="($event) => deleteUser(user.id)"
            type="button"
            value="Delete"
          />
        </li>
        <hr />
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "myForm",
  data() {
    return {
      users: [],
      sport: "",
      information: {
        name: "",
        age: "",
        grade: "",
        gender: "",
        favouritSports: [],
      },
      changeAge: "",
      changeID: "",
    };
  },
  methods: {
    addTo() {
      this.information.favouritSports.push(this.sport);
      this.sport = "";
    },
    async getUsers() {
      await fetch("https://course-backend.onrender.com/")
        .then((res) => res.json())
        .then((data) => (this.users = data));
    },
    async addUser() {
      const requestData = {
        headers: { "Content-Type": "application/json" },
        method: "POST",
        body: JSON.stringify(this.information),
      };
      await fetch(
        "https://course-backend.onrender.com/add-student",
        requestData
      )
        .then((res) => res.json())
        .then((data) => (this.users = data));
    },
    async updateUser() {
      if (!this.changeAge || !this.changeID) {
        return;
      }
      const requestData = {
        headers: { "Content-Type": "application/json" },
        method: "POST",
        body: JSON.stringify({
          age: this.changeAge,
        }),
      };
      await fetch(
        `https://course-backend.onrender.com/update-student/${this.changeID}`,
        requestData
      )
        .then((res) => res.json())
        .then((data) => (this.users = data));
    },
    async deleteUser(id) {
      const requestData = {
        headers: { "Content-Type": "application/json" },
        method: "DELETE",
      };
      await fetch(
        `https://course-backend.onrender.com/delete-student/${id}`,
        requestData
      )
        .then((res) => res.json())
        .then((data) => {
          console.log(data);
          this.users = data;
        });
    },
  },
  async mounted() {
    await this.getUsers();
  },
};
</script>
<style lang="scss" scoped>
form {
  div {
    width: 300px;
    display: flex;
    margin: auto;
    justify-content: space-between;
    margin: 15px auto;
  }
  .radioButton {
    div {
      justify-content: flex-start;
    }
  }
}
li {
  display: flex;
  margin: 10px 0px;
  list-style: none;
}
</style>
