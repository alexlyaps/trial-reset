<script setup>
  import { ref } from 'vue';
  
  const email = ref('');
  const isSubmit = ref(false);
  let inputColor = '#101828';
  let bcColor = '#fff';
  
  const handleSubmit = (e) => {
    e.preventDefault();
    setTimeout(() => alert(`We sent a reset link to '${email.value}'.`), 500);
    isSubmit.value = true;
    inputColor = '#667085';
    bcColor = '#F9FAFB';
  };
</script>

<template>
  <section class="reset-password">
    <h2>Reset password</h2>
    <div>An email with a link to reset your password will be sent <br/>to the address you used to register the account.</div>
    <form @submit.prevent="handleSubmit">
      <input 
        type="email" 
        id="email"
        name="email" 
        v-model="email" 
        placeholder="Email" 
        required 
        :style="{ color: inputColor, backgroundColor: bcColor}" />
      <button 
        type="submit"
        v-bind:disabled="isSubmit">
        Reset password</button>
    </form>
      <p>Back to <a href="./">Sign in</a></p>
  </section>
</template>

<style scoped lang="scss">
@import "@/styles/variables.scss";

section {

  background-color: $primary-color;
  width: 480px;
  margin: auto;
  border: 1px solid $border-color;
  border-radius: 16px;

  h2 {
    font-weight: 600;
    font-size: 30px;
    line-height: 38px;
    text-align: center;
    color: $heading-input-text-color;
    margin: 24px 24px 32px;
  }

  div {
    font-weight: 400;
    font-size: 16px;
    line-height: 24px;
    text-align: center;
    color: $supporting-text-color;
    margin: 0 24px;
  }

  form {
    margin: 24px;
    display: flex;
    flex-direction: column;
    gap: 24px;    

    * {
      display: block;
      border-radius: 8px;
    }

    input {
      padding: 8px 12px;
      border: 1px #D0D5DD solid;
      color: #667085;
      transition: all 0.3s ease;

      &::placeholder {
        color: #667085;
      }

      &:hover {
        transition: all 0.3s ease;
        color: $heading-input-text-color;
      }

      &:focus,
      &:active {
        border-color: #AFADFF;
        box-shadow: 0 0 0 4px #F4EBFF;
        outline: none;
      }
    }



    button {
      height: 44px;
      border: 1px #6F6BFC solid;
      background-color: $button-one-color;
      color: $button-one-text-color;
      transition: all 0.3s ease;

      &:hover {
        background-color: $button-one-color-hover;
      }

      &:active {
        background-color: $button-one-color;
        box-shadow: 0 0 0 4px #F4EBFF;        
      }

      &:disabled {
        background-color: $button-one-color-disabled;
        border: 1px $button-one-color-disabled solid;        
      }
    }
  }

  p {
    margin: 24px;
    text-align: center;
    font-weight: 500;
    font-size: 14px;
    line-height: 20px;
    color: #475467;

    a {
      color: $button-two-text-color;
      font-weight: 600;

      &:hover {
        color: #4441A6;
      }

      &:active {
        color: #614BF2;
      }

      &:disabled {
        color: #D0D5DD;
      }
    }
  }
}

</style>

