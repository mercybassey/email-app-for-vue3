<template>
  <section>
    <div class="form-container">
        <p>Hire Me</p>
        <form class="form" ref="form"  @submit.prevent="sendMail" >
          <div class="form-group">
            <input name="from_name" placeholder="name" type="text" :value="inputFieldReset" required>
          </div>
          <div class="form-group">
            <input name="email" placeholder="email" type="email" :value="inputFieldReset" required>
          </div>
          <div class="form-group">
            <input  name="subject" placeholder="subject" type="text" :value="inputFieldReset" required>
          </div>
          <div class="form-group">
            <textarea class="text-area" name="message" placeholder="message" type="text" :value="inputFieldReset" required></textarea>
          </div>
          <div class="form-group">
            <input class="submit" type="submit" name="send" />
          </div>
        </form>
      </div>
  </section>
</template> 



<script>
import emailjs from 'emailjs-com';
import {ref} from 'vue';

export default {
  setup() {
    const form = ref(null);
    const inputFieldReset = ref(null);

    const sendMail = () => {
      emailjs.sendForm('service_3auy1ro', 'template_ojg0m3p', form.value, 'user_lbqwiyRhPGlpQH6G9j1Ng')
      .then(() => {
        alert('Message sent!');
         inputFieldReset.value = ""; 
      }, (error) => {
        alert('Message not sent', error);
      });
     
    }

   

    return{
      sendMail,
      form,
      inputFieldReset
    }
  }
}
</script>

<style>

</style>