/* eslint-disable quotes */
<template>
  <section class="form__wrapper">
    <h4>CONTACT US</h4>
    <form class="form">
      <div class="form__item">
        <label class="form__itemLabel" for="subject">Subject</label>
        <select id="subject" name="subject" class="form__itemInput">
          <option value="customerService">Customer service</option>
          <option value="Support">Support</option>
          <option value="Other">Other</option>
        </select>
      </div>
      <div class="form__item">
        <label class="form__itemLabel" for="email">Email address</label>
        <input
          class="form__itemInput"
          type="text"
          id="email"
          name="email"
          placeholder="your@email.com"
        />
      </div>
      <div class="form__item">
        <label class="form__itemLabel" for="attach">Attachment</label>
        <input
          class="form__itemInput form__itemInput--file"
          type="file"
          id="attach"
          name="attach"
          placeholder=""
        />
        <p class="form__item--optional">optional</p>
      </div>
      <div class="form__item form__item--textbox">
        <label class="form__itemLabel" for="message">Message</label>
        <textarea
          class="form__itemInput form__itemInput--textbox"
          type="textbox"
          id="message"
          name="message"
          placeholder="How can we help?"
        />
      </div>
      <vue-recaptcha
        class="form__captcha"
        sitekey="6Lf4vjEaAAAAAJv4oDFqw3Wb_5cID3IuU5xY5zcn"
        :loadRecaptchaScript="true"
      ></vue-recaptcha>
      <button class="form__button" type="submit">SEND</button>
    </form>
  </section>
</template>

<script>
/* eslint-disable */
import VueRecaptcha from "vue-recaptcha";
export default {
  components: {
    VueRecaptcha
  }
};
</script>

<style>
* {
  box-sizing: border-box;
}
body {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  background-color: #f3f3f3;
  margin-top: 60px;
}
.form__wrapper {
  background-color: white;
  margin: 0 auto;
  padding: 10px 30px 25px;
  width: 80vw;
  max-width: 800px;
}
.form {
  margin: 0 auto;
  width: 80%;
  display: flex;
  justify-content: left;
  align-items: center;
  flex-direction: column;
}
.form__item {
  width: 100%;
  margin-bottom: 15px;
  display: flex;
  align-items: center;
}
.form__item--textbox {
  align-items: flex-start;
}

.form__itemLabel {
  display: block;
  width: 150px;
  margin-right: 15px;
  margin-top: 5px;
  text-align: right;
}

.form__itemInput {
  background-color: #f1f1f1;
  outline: none;
  border: 1px solid #dedede;
  width: 250px;
  height: 30px;
  padding: 2px 8px;
  margin-right: 10px;
}
.form__itemInput--file {
  outline: none;
  width: 250px;
  height: 30px;
  margin-right: 10px;
  position: relative;
}

.form__item--optional {
  opacity: 0.9;
}

::-webkit-file-upload-button {
  position: absolute;
  top: 0;
  right: -4px;
  height: 100%;
  width: 80px;
  outline: none;
  border: 0;
  background-color: #00b4cb;
  color: white;
  font-weight: bold;
  font-size: 12px;
}

.form__itemInput--textbox {
  margin-right: 10px;
  height: 80px;
  width: 70.5%;
  max-width: 70.5%;
  min-width: 70.5%;
}

.form__captcha {
  align-self: flex-end;
  margin-right: 10px;
  margin-bottom: 10px;
}

.form__button {
  margin-right: 10px;
  align-self: flex-end;
  height: 30px;
  padding: 0 10px;
  background-color: #00b4cb;
  border: none;
  outline: none;
  color: white;
  font-weight: bold;
}

@media (max-width: 1000px) {
  .form__item {
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }

  .form__itemLabel {
    width: 100%;
    text-align: center;
    margin-bottom: 10px;
  }
  .form__item--optional {
    display: none;
  }
  .form__itemInput--textbox {
    width: 250px;
    min-width: 250px;
    max-width: 250px;
  }
  .form__captcha,
  .form__button {
    align-self: center;
  }
}
@media (max-width: 400px) {
  .form__item {
    width: 80%;
  }
}
</style>
