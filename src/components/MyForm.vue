<template>
  <div class="myForm">
    <form action="" @submit.prevent>
      <div>
        <label for="">FirstName</label>
        <input v-model.lazy="information.FirstName" type="text" />
        <p>{{ information.FirstName }}</p>
      </div>
      <div>
        <label for="">LastName</label>
        <input v-model="information.LastName" type="text" />
        <p>{{ information.LastName }}</p>
      </div>
      <div>
        <label for="">Age</label>
        <input v-model="information.Age" type="number" />
        <p>{{ information.Age }}</p>
      </div>
      <div>
        <label for="">Email</label>
        <input v-model="information.Email" type="email" />
        <p>{{ information.Email }}</p>
      </div>

      <div>
        <label for="swimming">swimming</label>
        <input
          name="swimming"
          type="checkbox"
          v-model="information.sport.swimming"
        />
        <p>{{ information.sport.swimming }}</p>
      </div>
      <div>
        <label for="runing">runing</label>
        <input
          name="runing"
          type="checkbox"
          v-model="information.sport.runing"
        />
        <p>{{ information.sport.runing }}</p>
      </div>
      <div class="radioButton">
        <div>
          <label for="male">Male</label>
          <input v-model="information.gen" type="radio" value="Male" />
        </div>
        <div>
          <label for="female">Female</label>
          <input v-model="information.gen" type="radio" value="Female" />
        </div>
        <p>{{ information.gen }}</p>
      </div>
      <div class="actions">
        <input type="submit" value="submit" />
      </div>
    </form>
  </div>
</template>

<script>
export default {
  name: "myForm",
  data() {
    return {
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
};
</script>
