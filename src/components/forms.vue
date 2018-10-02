<template>
  <div class="row justify-around">
    <div class="col row justify-around q-pt-md">
        <div class="col-10 row justify-around">
            <div class="col-2 inputfield">
                <p>Name : </p><br>
                <p>Email : </p>
            </div>
            <div class="col-10">
                <q-input v-model="name"
                       class="inputfield"
                        v-validate="'required|min:2|max:10|alpha'"
                        name="name" />
                <span class="errorMessage" v-show="errors.has('name')">{{ errors.first('name') }}</span><br>
                <q-input v-model="email"
                        class="inputfield"
                        v-validate="'required|email'"
                        name="email"/>
               <span class="errorMessage" v-show="errors.has('email')">{{ errors.first('email') }}</span>
            </div>
                <q-btn label="Submit" color="primary" @click="submit"></q-btn>
        </div>
    </div>
    <div classs="col row" v-if="showDetails">
        <div class="col-7">
            <b>Name:</b> {{this.name}}
            <br>
            <b>Email:</b> {{this.email}}
        </div>
    </div>
    </div>
</template>

<script>
export default {
  data () {
    return {
      name: '',
      email: '',
      showDetails: false
    }
  },
  methods: {
    submit () {
      this.$validator.validateAll()
        .then((result) => {
          if (!result) {
            return 0
          } else {
            console.log('name', result)
            this.showDetails = true
          }
        })
        .catch()
    }
  }
}
</script>

<style>
.errorMessage {
  color: red;
  padding-top: 5px
}
.inputfield {
  padding-top: 0%;
}

</style>
