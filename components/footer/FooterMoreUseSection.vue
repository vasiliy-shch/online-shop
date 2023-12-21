<template>
  <div class="footer__moreUseLists">
    <ul class="footer__moreUseLists_list">
        <li><h3 class="list__li_title">About</h3></li>
        <li class="list__li"><a class="list__li_link" href = "#">About us</a></li>
        <li class="list__li"><a class="list__li_link" href = "#">Find store</a></li>
        <li class="list__li"><a class="list__li_link" href = "#">Categories</a></li>
        <li class="list__li"><a class="list__li_link" href = "#">Blogs</a></li>
    </ul>
    <ul class="footer__moreUseLists_list">
        <li><h3 class="list__li_title">Partnership</h3></li>
        <li class="list__li"><a class="list__li_link" href = "#">About us</a></li>
        <li class="list__li"><a class="list__li_link" href = "#">Find store</a></li>
        <li class="list__li"><a class="list__li_link" href = "#">Categories</a></li>
        <li class="list__li"><a class="list__li_link" href = "#">Blogs</a></li>
    </ul>
    <ul class="footer__moreUseLists_list">
        <li><h3 class="list__li_title">Information</h3></li>
        <li class="list__li"><a class="list__li_link" href = "#">Help Center</a></li>
        <li class="list__li"><a class="list__li_link" href = "#">Money Refund</a></li>
        <li class="list__li"><a class="list__li_link" href = "#">Shipping</a></li>
        <li class="list__li"><a class="list__li_link" href = "#">Contact us</a></li>
    </ul>
    <ul class="footer__moreUseLists_list">
        <li><h3 class="list__li_title">For users</h3></li>
        <li class="list__li"><a class="list__li_link" href = "#">Login</a></li>
        <li class="list__li"><a class="list__li_link" href = "#">Register</a></li>
        <li class="list__li"><a class="list__li_link" href = "#">Settings</a></li>
        <li class="list__li"><a class="list__li_link" href = "#">My Orders</a></li>
    </ul>
    <ul class="footer__moreUseLists_list">
        <li><h3 class="list__li_title">Get app</h3></li>
        <li class="list__li_linkApps">
            <a class="list__li_link" href = "#">
              <img
              class="link__appIcon"
              src="~assets/images/footerAppIcons/appStore.svg">
            </a>
        </li>
        <li class="list__li_linkApps">
            <a class ="list__li_link" href = "#">
              <img
              class="link__appIcon"
              src="~assets/images/footerAppIcons/googlePlay.svg">
            </a>
        </li>
    </ul>
  </div>
</template>

<script>

</script>

<style>
.footer__moreUseLists {
    display: flex;
    width: 787px;
    margin: 0 187px 0 61px;
    justify-content: space-between;
}
.footer__moreUseLists_list {
    font-family: 'Inter';
    list-style-type: none;
    padding: 0;
    margin: 0;
}
.list__li_title {
    font-weight: 400;
    line-height: 24px;
    font-size: 16px;
    margin: 40px 0 10px 0;
    letter-spacing: -0.2px;
}
.list__li {
    height: 24px;
    line-height: 24px;
    margin-top: 3px;
    letter-spacing: -0.2px;
    font-size: 16px;
    font-family: 'Inter';
}
.list__li_link {
    text-decoration: none;
    color: #8B96A5;
    line-height: 24px;
}
.list__li_link:hover {
    opacity: 0.8;
}
.link__appIcon {
    width: 124px;
    height: 42px;
    margin-top: 5px;
}
.list__li_linkApps {
    height: 42px;
    margin-top: 5px;
}
</style>
