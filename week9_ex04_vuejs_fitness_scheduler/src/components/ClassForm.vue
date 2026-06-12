<template>
  <div class="form">
    <input v-model="form.name" placeholder="Class Name" />
    <input v-model="form.coach" placeholder="Coach" />
    <input v-model="form.date" type="date" />
    <input v-model="form.time" type="time" />
    <input v-model="form.capacity" type="number" />

    <button @click="submitForm">
      Add Class
    </button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      form: {
        name: "",
        coach: "",
        date: "",
        time: "",
        capacity: ""
      }
    }
  },

  methods: {
    submitForm() {
      // validation
      if (
        !this.form.name ||
        !this.form.coach ||
        !this.form.date ||
        !this.form.time ||
        !this.form.capacity
      ) {
        alert("Please fill all fields");
        return;
      }

      // send data to parent
      this.$emit('add', { ...this.form });

      // reset form
      this.form = {
        name: "",
        coach: "",
        date: "",
        time: "",
        capacity: ""
      };
    }
  }
}
</script>

<style>
.form {
  margin-bottom: 20px;
}
</style>