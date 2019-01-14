<template>

  <form
    action=""
    name="contact"
    netlify
    method="post"
    @submit.prevent="validateBeforeSubmit"
    netlify-honeypot="bot-field">
    <input
      type="hidden"
      name="form-name"
      value="contact" >
    <p style="display: none;">
      <label>Don’t fill this out: <input name="bot-field"></label>
    </p>

    <div class="column is-12">
      <label class="block text-blackbasic font-bold md:text-right mb-1 md:mb-0 pr-4" for="email">Name</label>
          <input class="appearance-none block w-full bg-grey-lightest text-grey-darker border rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white" name="name" v-model="name" v-validate="'required|max:60'" :class="{'input': true, 'border-red': errors.has('email') }" type="text" placeholder="Email">
          <!-- <i v-show="errors.has('email')" class="fa fa-warning"></i> -->
          <span v-show="errors.has('name')" class="text-red text-xs italic">{{ errors.first('name') }}</span>
    </div>

    <div class="column is-12">
      <label class="block text-blackbasic font-bold md:text-right mb-1 md:mb-0 pr-4" for="email">Email</label>
          <input class="appearance-none block w-full bg-grey-lightest text-grey-darker border rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white" name="email" v-model="email" v-validate="'required|email'" :class="{'input': true, 'border-red': errors.has('email') }" type="text" placeholder="Email">
          <!-- <i v-show="errors.has('email')" class="fa fa-warning"></i> -->
          <span v-show="errors.has('email')" class="text-red text-xs italic">{{ errors.first('email') }}</span>
    </div>



    <div class="column is-12">
      <label class="block text-blackbasic font-bold md:text-right mb-1 md:mb-0 pr-4" for="message">Message</label>
      <textarea name="message" class="w-full h-32 bg-grey-lightest text-grey-darker border rounded py-3 px-4 mb-3 leading-tight focus:outline-none" style="vertical-align: top;" v-model="message" v-validate="'required|max:360'" :class="{'input': true, 'border-red': errors.has('message') }" type="textarea"></textarea>
      <!-- <i v-show="errors.has('email')" class="fa fa-warning"></i> -->
      <span v-show="errors.has('message')" class="text-red text-xs italic">{{ errors.first('message') }}</span>
    </div>

    <div class="flex justify-end">
      <button type="submit" @click="submit">Just tell me already</button>
    </div>

  </form>

</template>
<script>
import axios from "axios";

export default {
  name: 'contact',
  data: () => ({
    email: '',
    name: '',
    message: ''
  }),
  methods: {
    encode (data) {
      return Object.keys(data)
        .map(
          key => `${encodeURIComponent(key)}=${encodeURIComponent(data[key])}`
        )
        .join("&");
    },
    submit() {
      alert('Form submitted');
    },
    validateBeforeSubmit() {
      this.$validator.validateAll().then((result) => {
        if (result) {
          const axiosConfig = {
            header: { "Content-Type": "application/x-www-form-urlencoded" }
          };
          axios.post(
            '/',
            this.encode({
              'form-name': 'contact',
              ...this.form
            })
          )
          // eslint-disable-next-line
          console.log('Form Validated!');
        }
        return;
        console.log('Correct them errors!');
      });
    }
  }
};
</script>
