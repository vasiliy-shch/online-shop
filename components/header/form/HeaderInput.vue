<template>
  <input
    class="header__input"
    placeholder="Search"
  >
</template>

<style>
.header__input {
    width: 420px;
    height: 18px;
    font-size: 16px;
    border: 0;
    padding: 10px 5px 10px 10px;
    outline: none;
    border-radius: 6px 0 0 6px;
}
@media screen and (max-width: 879px) {
    .header__input {
        padding: 11px 39px 10px 36px;
        background-color: #EFF2F4;
        width: 225px;
        font-size: 12px;
        background-image: url(~/images/searchGrey.svg);
        background-repeat: no-repeat;
        background-position: bottom 9px left 8px;
        background-size: 22px 22px;
    }
}
</style>
