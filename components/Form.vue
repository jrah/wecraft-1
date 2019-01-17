<template>

  <form
    name="contact"
    method="post"
    netlify
    netlify-honeypot="bot-field">
    <input
      type="hidden"
      name="form-name"
      value="contact" >
    <p style="display: none;">
      <label>Don’t fill this out: <input name="bot-field"></label>
    </p>

    <div class="column is-12">
      <label 
        class="block text-blackbasic font-bold md:text-right mb-1 md:mb-0 pr-4" 
        for="email">Name</label>
      <input 
        class="appearance-none block w-full bg-grey-lightest text-grey-darker border rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white" 
        name="name" 
        type="text" 
        placeholder="Email">
    </div>

    <div class="column is-12">
      <label 
        class="block text-blackbasic font-bold md:text-right mb-1 md:mb-0 pr-4" 
        for="email">Email</label>
      <input 
        class="appearance-none block w-full bg-grey-lightest text-grey-darker border rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white" 
        name="email" 
        type="text" 
        placeholder="Email">
    </div>



    <div class="column is-12">
      <label 
        class="block text-blackbasic font-bold md:text-right mb-1 md:mb-0 pr-4" 
        for="message">Message</label>
      <textarea 
        name="message" 
        class="w-full h-32 bg-grey-lightest text-grey-darker border rounded py-3 px-4 mb-3 leading-tight focus:outline-none" 
        style="vertical-align: top;" 
        type="textarea"/>
    </div>

    <div class="flex justify-end">
      <button
        class="inline-flex cursor-pointer bg-transparent hover:bg-point text-point-dark font-semibold hover:text-white py-2 px-4 border border-point hover:border-transparent rounded"
        type="submit">Submit</button>
    </div>

  </form>

</template>
<script>
export default {};
</script>
