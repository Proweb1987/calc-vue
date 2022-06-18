<template>
  <div class="calc">
    <input 
    type="text" 
    v-model="value" 
    class="calc__input" 
    placeholder="0" 
    />
    <button 
    class="calc__nums button" 
    @click="input(num)"
    v-for="num in numbers">{{ num }}</button>
    <button 
    v-for="sign in signs" 
    @click="input(sign)"
    class="calc__signs button">{{ sign }}</button>
    <button @click="calc" class="calc__answer button">=</button>
    <button @click="reset" class="calc__reset button">del</button>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      value: "",
      numbers: [1, 2, 3, 4, 5, 6, 7, 8, 9, 0],
      signs: ["/", "-", "+", "*"],
    };
  },
  methods: {
    input(val) {
      this.value += val
    },
    calc() {
      this.value = eval(this.value)
    },
    reset() {
      this.value = '';
    }
  }
};
</script>

<style>
 .calc {
  width: 200px;
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  margin: 0 auto;
  background: rgb(70, 66, 66);
  padding: 30px;
  display: flex;
 }
 .button {
  width: 33%;
  height: 50px;
  border-radius: 50%;
  font-size: 35px;
  display: flex;
  justify-content: center;
  align-items: center;
  outline: none;
  border: none;
 }
 .button:hover {
  background: orange;
 }
 .calc__input {
  padding: 10px 0 10px 2px;
  font-size: 18px;
  border: none;
  outline: none;
  border-radius: 15px;
  margin-bottom: 10px;
 }
.calc__input {
 padding-right: 2px;
}

</style>
