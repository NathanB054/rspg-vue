<template>
    <nav class="header flex ">
        <!-- Logo -->
        <div>
            <router-link to="/"> <img width="100px" height="auto" src="../assets/img/logomfu.png"></router-link>
        </div>

        <!-- Text -->
        <div class="headertitle mt-5 ml-4">
            <span class="block">โครงการอนุรักษ์พันธุกรรมพืชอันเนื่องมาจากพระราชดำริ สมเด็จพระเทพรัตนสุดา ฯ</span>
            <span class="block">สยามบรมราชกุมารี สนองพระราชดำริ โดยมหาวิทยาลัยแม่ฟ้าหลวง</span>
        </div>

        <!-- Menu -->
        <div class="menu mt-10" id="menu">
            <div class="test">
                <p>responsive</p>
            </div>
            <ul>
                <li :class="{ active: to === '/' }">
                    <router-link to="/">หน้าหลัก</router-link>
                </li>
                <li :class="{ active: to === '/contact' }">
                    <router-link to="/contact">ติดต่อเรา</router-link>
                </li>
                <li :class="{ active: to === '/staff' }">
                    <router-link to="/staff">เจ้าหน้าที่</router-link>
                </li>
            </ul>
        </div>
    </nav>
    <div class="picdiv">
        <img src="../assets/img/imgunder.png" class="responsive">
        <p class="textimgunder" style="font-size:2.2vw; ">ฐานข้อมูลทรัพยากร อพ.สธ. - มหาวิทยาลัยแม่ฟ้าหลวง</p>
    </div>
</template>

<script>
export default {
    computed: {
        to() {
            return this.$route.path;
        }
    }
}
</script>

<style scoped>
.active {
    color: red;
    text-decoration: none;
    /* Remove default underline */
}



/* Show underline on active state and animate */
.active::after {
    opacity: 1;
}

* {
    font-family: 'Kanit', sans-serif;
}

nav {
    background: #efdcef;
    color: #673363;
}

.menu {
    position: absolute;
    right: 0;
    float: right;
    justify-content: flex-end;
}

ul {
    display: flex;
    margin-right: 5rem;
}

.menu ul li {
    margin-left: 3rem;
    /* Adjust the value for desired space */
    font-size: 20px;
}

.picdiv {
    height: 8em;
    width: 100%;
    position: relative;
    overflow: hidden;
}

.picdiv img {
    max-width: 100%;
}

.picdiv p {
    position: absolute;
    color: white;
    top: 20%;
    text-align: center;
    font-weight: bold;
    width: 100%;
    margin-top: 0px;
}

.responsive {
    width: 100%;
}

.textimgunder {
    font-size: 2.6em;
    position: absolute;
}

.test{
    display: none;
}

/* responsive */
@media (max-width: 1000px) {
    .menu ul {
        display: none;
    }
    .test{
        display: f;
    }
}
@media (max-width: 655px) {
    span{
        font-size: 10px;
    }
     
}
@media (max-width: 447px) {
    span{
       display: none;
    }
     
}
</style>