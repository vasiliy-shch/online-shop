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
    font-style: 'Inter';
    border: 0;
    padding: 10px 5px 10px 10px;
    outline: none;
    border-radius: 6px 0 0 6px;
}
@media screen and (max-width: 879px) {
    .header__input {
        padding: 11px 68px 10px 6px;
        background-color: #EFF2F4;
        width: 226px;
        border-radius: 0 6px 6px 0;
    }
}
</style>
