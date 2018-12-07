<template>
  <div>
    <v-form>
      <v-container>
        <div v-if="isShow">
          <h1 class="header">Sign In</h1>

          <v-flex xs12 sm6 md3>
            <v-text-field
              label="Solo"
              placeholder="Username"
              v-bind:value="val"
              @keyup="onChange"
              solo
            ></v-text-field>
          </v-flex>

          <div>
            <v-btn color="info" @click="greet">Next</v-btn>
          </div>
        </div>

        <div v-if="!isShow">
          <h1 class="header">Hello {{this.val}}</h1>

          <v-flex xs12 sm6 md3>
            <v-text-field label="Solo" placeholder="Password" solo></v-text-field>
          </v-flex>

          <div>
            <v-btn color="info" @click="greet">Sign In</v-btn>
          </div>
        </div>
      </v-container>
    </v-form>
  </div>
</template>

<script>
export default {
  data: () => {
    return {
      val: "",
      isShow: true
    };
  },
  methods: {
    greet: function(event) {
      this.isShow = false;
    },
    onChange(event) {
      this.val = event.target.value;
    }
  }
};
</script>

<style lang="stylus" scoped>
.header {
  color: #369;
}
</style>
