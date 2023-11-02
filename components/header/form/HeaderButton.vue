<template>
  <button class="header__button">Search</button>
</template>

<style>
.header__button {
    width: 105px;
    height: 39px;
    background-color: #0D6EFD;
    color: white;
    font-size: 16px;
    font-style: 'Inter';
    padding: 0;
    border: none;
    border-radius: 0px 5px 5px 0;
    cursor: pointer;
}
.header__button:hover {
    opacity: 0.8;
}
@media screen and (max-width: 879px) {
    .header__button {
        width: 100px;
        height: 39px;
        font-size: 12px;
    }
}
</style>
