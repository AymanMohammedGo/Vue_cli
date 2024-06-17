<template>
  <div class="myForm">
    <form action="" @submit.prevent>
      <div>
        <label for="">FirstName</label>
        <input v-model.lazy="FirstName" type="text" />
        <p>{{ FirstName }}</p>
      </div>
      <div>
        <label for="">LastName</label>
        <input v-model="LastName" type="text" />
        <p>{{ LastName }}</p>
      </div>
      <div>
        <label for="">Age</label>
        <input v-model="Age" type="number" />
        <p>{{ Age }}</p>
      </div>
      <div>
        <label for="">Email</label>
        <input v-model="Email" type="email" />
        <p>{{ Email }}</p>
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
      FirstName: "",
      LastName: "",
      Age: "",
      Email: "",
    };
  },
};
</script>
