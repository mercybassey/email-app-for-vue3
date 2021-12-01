<template>
  <div class="background">
    <div class="container">
      <div class="screen">
        <div class="screen-header">
          <div class="screen-header-left">
            <div class="screen-header-button close"></div>
            <div class="screen-header-button maximize"></div>
            <div class="screen-header-button minimize"></div>
          </div>
          <div class="screen-header-right">
            <div class="screen-header-ellipsis"></div>
            <div class="screen-header-ellipsis"></div>
            <div class="screen-header-ellipsis"></div>
          </div>
        </div>
        <div class="screen-body">
          <div class="screen-body-item left">
            <div class="app-title">
              <span>Hire</span>
              <span class="me">Me</span>
            </div>
            <div class="app-contact">CONTACT INFO : +234 818 840 0911</div>
          </div>
          <div class="screen-body-item">
            <form class="app-form" ref="form"  @submit.prevent="sendMail" >
              <div class="app-form-group">
                <input class="app-form-control" name="name" placeholder="name" type="text" >
              </div>
              <div class="app-form-group">
                <input class="app-form-control" name="email" placeholder="email" type="email">
              </div>
              <div class="app-form-group message">
                <textarea class="app-form-control" name="message" placeholder="email" type="text"></textarea>
              </div>
              <div class="app-form-group buttons">
                <button class="app-form-button"  >SEND</button>
              </div>
            </form>
          </div>
        </div>
      </div>
   </div>
  </div>
</template> 



<script>
import emailjs from 'emailjs-com';


export default {
  setup() {

    const sendMail = () => {
      emailjs.sendForm('service_1g9lrll', 'template_ttmh426', this.$refs.form, 'user_prA4Swm8nuJiz2vv8iByN')
      .then((result) => {
        console.log('SUCCESS!', result);
      }, (error) => {
        console.log('FAILED...', error);
      });
    }
    return{
      sendMail
    }
  }
}
</script>

<style>

</style>