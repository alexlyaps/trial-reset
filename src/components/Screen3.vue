<script setup>
  import letter from '@/assets/letter.svg'
</script>

<template>
  <section>
    <h2>Thanks for registering</h2>
    <div>
    <img :src="letter" alt="Mail sent">
    Please check your email and click the link to finalize <br>your account.
    </div>
    
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
    line-height: 24px auto;
    text-align: center;
    color: $supporting-text-color;
    margin: 24px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    gap: 32px;

    img {
      height: 80px;
      width: auto;
    }

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

    button {
      height: 44px;
      border: 1px $button-two-color solid;
      background-color: $button-two-color;
      color: $button-two-text-color;
      transition: all 0.3s ease;
      font-weight: 600;

      &:hover {
        background-color: $button-two-color-hover;
      }

      &:active {
        background-color: $button-two-color-active;
        box-shadow: 0 0 0 4px #F4EBFF;        
      }

      &:disabled {
        color: #AFADFF;
        background-color: $button-two-color-disabled;
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

