<template>
    <div class="header__actionIcons">
        <button class="actionIcon__button">
            <img class="desktop__display_none" src="~/assets/images/headerActionIcons/profileBlack.svg">
            <img class="mobile__display_none" src="~/assets/images/headerActionIcons/profile.svg">
            <span class="actionIcon__title mobile__display_none">profile</span>
        </button>
        <button class="actionIcon__button mobile__display_none">
            <img src="~/assets/images/headerActionIcons/message.svg">
            <span class="actionIcon__title">message</span>
        </button>
        <button class="actionIcon__button mobile__display_none">
            <img src="~/assets/images/headerActionIcons/orders.svg">
            <span class="actionIcon__title">orders</span>
        </button>
        <button class="actionIcon__button">
            <img class="desktop__display_none" src="~/assets/images/headerActionIcons/cartBlack.svg">
            <img class="mobile__display_none" src="~/assets/images/headerActionIcons/cart.svg">
            <span class="actionIcon__title mobile__display_none">cart</span>
        </button>
    </div>
</template>

<style>
.header__actionIcons {
    display: flex;
    width: 228px;
    height: 41px;
    margin-top: 25px;
    justify-content: space-evenly;
}
@media screen and (max-width: 879px) {
    .header__actionIcons {
        width: 68px;
        height: 24px;
        justify-content: space-between;
        flex-direction: row-reverse;
        margin: 16px 0 16px 102px;
    }
}
.actionIcon__button {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: space-between;
    border: none;
    background-color: white;
    padding: 0;
    cursor: pointer;
}
.actionIcon__button:hover {
    opacity: 0.8;
}
.actionIcon__title {
    height: 15px;
    font-family: 'Inter';
    font-size: 12px;
    color: #979797;
}
@media screen and (max-width: 879px) {
    .mobile__display_none {
        display: none;
    }
}
@media screen and (min-width: 880px) {
    .desktop__display_none {
        display: none;
    }
}
</style>
