<template>
  <button class="header__menuButton"></button>
</template>

<style>
.header__menuButton {
    width: 24px;
    height: 24px;
    background-color: white;
    background-image: url(~/assets/images/headerMenuButton.svg);
    background-repeat: no-repeat;
    background-position: center;
    border: 0;
    padding: 0;
    cursor: pointer;
    margin: 15px 6px 17px 130px;
}
.header__menuButton:hover {
    opacity: 0.6;
}
@media screen and (max-width: 879px) {
  .header__menuButton {
    margin: 15px 0 17px 16px;
  }
}
</style>
