<template>
  <section>
    <h1>Doyalin G</h1>
    <hr>

    <h5><img :src="picture" :width="size" :height="size" alt=""></h5>
    <form @submit="submitForm">
      <label for="">ชื่อเล่น</label>
      <input type="text" name="" v-on:input="setnickname" id="">
      <button type="submit">บันทึก</button>
    </form>

    <!--h5>ชื่อเล่น : <input type="text" name="" id="" v-on:input="setnickname"></h5-->
    <hr>
    <h5>ชื่อเต็ม : {{ getFullName() }}</h5>
    <h5>ชื่อเล่น : {{ nickname }}</h5>
    <h5>อายุ : {{ age }} ปี</h5>
    <h5>ที่อยู่ : <span v-html="address"></span></h5>
    <h5>Fb : <a :href="social" target="_blank"><u>@here</u></a></h5>
    <h5>Hobby :</h5>
    <ul>
      <li>{{ hobby[0] }}</li>
      <li>{{ hobby[1] }}</li>
      <li>{{ hobby[2] }}</li>
    </ul>
    <h5>General Data :</h5>
    <ul>
      <li>sex : {{ general.gender }}</li>
      <li>weight : {{ general.weight }} kg.</li>
      <li>height : {{ general.height }} cm.</li>
      <li>sickness : {{ general.status }}</li>
    </ul>
    <button @click="showData">Click Here</button>
    <button @click.ctrl="increment(10)">Add</button>
    <button @click.middle="decrement(5)">Del</button>
  </section>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      fname: "Doya?",
      lname: "Dev",
      nickname: "",
      age: 15,
      address: "<strong>Bangkok</strong>",
      picture: "https://cdn-icons.flaticon.com/png/512/3010/premium/3010483.png?token=exp=1655521596~hmac=47fcb49d51db6d7744c89676fcd1e186",
      size: 128,
      social: "https://www.facebook.com/walofz",
      hobby: ["Sleep", "Gamer", "Music"],
      general: {gender: "Male", weight: 80.22, height: 180, status: false}
    }
  },
  methods: {
    getFullName() {
      return `${this.fname}  ${this.lname}`
    },
    showData() {
      alert(this.getFullName())
    },
    increment(value) {
      this.age += value
    },
    decrement(value) {
      this.age -= value
    },
    setnickname(event) {
      this.nickname = event.target.value
    },
    submitForm(e) {
      e.preventDefault()
      alert("Save record.")
    }
  }
}
</script>

<style></style>
