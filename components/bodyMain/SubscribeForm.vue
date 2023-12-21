<template>
  <form class="subscribeForm" @submit.prevent>
    <h3 class="subscribeForm__title">Subscribe in our newsletter</h3>
    <span class="subscribeForm__subtitle">
      Get daily news on upcoming offers
      from many suppliers all over the world
    </span>
    <div class="subscribeForm__inputBlock">
      <input class="subscribeForm__input" placeholder="Email">
      <button class="subscribeForm__button">Subscribe</button>
    </div>
  </form>
</template>

<style>
.subscribeForm {
  font-family: 'Inter';
  display: flex;
  flex-direction: column;
  align-items: center;
  background-color: #EFF2F4;
}
@media screen and (max-width: 879px) {
  .subscribeForm {
    display: none;
  }
}
.subscribeForm__title {
  margin: 38px 0 0 0;
  font-size: 20px;
  line-height: 28px;
  letter-spacing: -0.2px;
  font-weight: 500;
}
.subscribeForm__subtitle {
  font-size: 16px;
  line-height: 24px;
  color: #606060;
}
.subscribeForm__inputBlock {
  margin: 21px 0 39px 0;
}
.subscribeForm__input{
  max-width: 274px;
  border: 1px solid #DEE2E7;
  border-radius: 6px;
  outline: none;
  font-size: 16px;
  line-height: 19px;
  padding: 11px 0 10px 36px;
  background-image: url(~/assets/images/bodyMain/subscribeInputMail.svg);
  background-repeat: no-repeat;
  background-position: 8px 9px;
}
.subscribeForm__button {
  width: 110px;
  text-align: center;
  font-size: 16px;
  line-height: 19px;
  padding: 10.5px 16px;
  border: none;
  border-radius: 6px;
  color: white;
  background-color: #0D6EFD;
  cursor: pointer;
}
.subscribeForm__button:hover {
  opacity: 0.8;
}
</style>
