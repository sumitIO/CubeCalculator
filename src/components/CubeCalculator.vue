<template>
  <div class="containter">
    <b-jumbotron header="Cube Calculator">
      <b-form-input
        id="input-valid"
        :state="state"
        v-model="text"
        type="text"
        placeholder="0"
        class="input"
        @keyup.enter="showAns"
        :disabled="disabled"
      ></b-form-input>

      <div class="mt-3">
        <b-button-group>
          <b-button
            variant="success"
            size="lg"
            @click="showAns"
            :disabled="disabled"
          >
            Show Answer
          </b-button>

          <b-button variant="danger" size="lg" @click="reset">
            Clear
          </b-button>
        </b-button-group>
      </div>
      <h1 v-if="show" class="answer">{{ enter() }}</h1>
    </b-jumbotron>
  </div>
</template>

<script>
export default {
  name: "CubeCalculator",
  data() {
    return {
      text: "",
      show: false,
      disabled: false,
      state: null,
    };
  },
  methods: {
    enter: function() {
      let temp = Number(this.text);

      console.log(temp);
      if (isNaN(temp)) {
        this.state = false;
        alert("Invalid Number!!!");
      } else {
        this.state = true;
        this.disabled = true;
        let num = this.text;
        let ans = num * num * num;
        return ans;
      }
    },
    showAns: function() {
      this.show = true;
    },
    reset: function() {
      this.disabled = false;
      this.show = false;
      this.text = 0;
      this.state = null;
    },
  },
};
</script>

<style scoped>
.input {
  text-align: center;
  width: 50%;
  margin: auto;
}

.answer {
  margin-top: 20px;
  font-size: 44px;
}
</style>
