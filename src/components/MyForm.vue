<template>
  <div class="myForm">
    <form action="" @submit.prevent="pushToArray">
      <div>
        <label for="">FirstName</label>
        <input v-model.lazy="information.FirstName" type="text" />
      </div>
      <div>
        <label for="">LastName</label>
        <input v-model="information.LastName" type="text" />
      </div>
      <div>
        <label for="">Age</label>
        <input v-model="information.Age" type="number" />
      </div>
      <div>
        <label for="">Email</label>
        <input v-model="information.Email" type="email" />
      </div>
      <div>
        <label for="swimming">swimming</label>
        <input
          name="swimming"
          type="checkbox"
          v-model="information.sport.swimming"
        />
      </div>
      <div>
        <label for="runing">runing</label>
        <input
          name="runing"
          type="checkbox"
          v-model="information.sport.runing"
        />
      </div>
      <div class="radioButton">
        <div>
          <label for="male">Male</label>
          <input
            name="male"
            v-model="information.gen"
            type="radio"
            value="Male"
          />
        </div>
        <div>
          <label for="female">Female</label>
          <input
            name="female"
            v-model="information.gen"
            type="radio"
            value="Female"
          />
        </div>
      </div>
      <div class="actions">
        <input type="submit" value="submit" />
      </div>
    </form>
    <div class="users" v-for="(user, index) in users" :key="index">
      <p>user[{{ index }}]</p>
      <ul>
        <li>{{ user.FirstName }}</li>
        <li>{{ user.LastName }}</li>
        <li>{{ user.Age }}</li>
        <li>{{ user.Email }}</li>
        <li v-for="(sport, key, index) in user.sport" :key="index">
          <p v-if="sport">{{ key }}</p>
        </li>
        <li>{{ user.gen }}</li>
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
      information: {
        FirstName: "",
        LastName: "",
        Age: "",
        Email: "",
        sport: {
          swimming: null,
          runing: null,
        },
        gen: "",
      },
    };
  },
  methods: {
    pushToArray() {
      this.users.push(this.information);
      this.information = {
        FirstName: "",
        LastName: "",
        Age: "",
        Email: "",
        sport: {
          swimming: null,
          runing: null,
        },
        gen: "",
      };
    },
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
</style>
