<template>
   <footer>
        <div class="detail">
            <div>
                <NuxtLink to="/"><img width="100px" height="auto" src="../assets/img/logomfu.png"></NuxtLink>
            </div>

            <div>
                    <p>ศูนย์ประสานงานโครงการอนุรักษ์พันธุกรรมพืชอันเนื่องมาจากพระราชดำริ </p>
                    <p>สมเด็จพระเทพรัตนสุดาฯ สยามบรมราชกุมารี สนองพระราชดำริ</p>
                    <p>โดยมหาวิทยาลัยแม่ฟ้าหลวง</p>
                <ul>
                    <li>
                        <p>333 ม.1 ต.ท่าสุด อ.เมือง จังหวัดเชียงราย 57100</p>
                        <p>โทรศัพท์: 0 5391 7742</p>
                        <p>Email : rspg.botanical@mfu.ac.th</p>
                    </li>
                    <li>
                        <a href="https://www.facebook.com/rspg.mfu/" class="text-white">Facebook : อพ.สธ. -
                            มหาวิทยาลัยแม่ฟ้าหลวง</a>
                    </li>
                    <li>
                        <a href="http://rspg.mfu.ac.th" class="text-white">Website : http://rspg.mfu.ac.th</a>
                    </li>
                </ul>
            </div>

            <div>
                <p>สืบค้นข้อมูลที่เกี่ยวข้อง</p>
                <ul class="">
                    <li>
                        <router-link to="/" class="text-white" @click="categoryChange('สืบค้นข้อมูลพืชภูมิปัญญา')">สืบค้นข้อมูลพืชภูมิปัญญา</router-link>
                    </li>
                    <li>
                        <router-link to="/" class="text-white" @click="categoryChange('สืบค้นข้อมูลสัตว์')">สืบค้นข้อมูลสัตว์</router-link>
                    </li>
                    <li>
                        <router-link to="/" class="text-white" @click="categoryChange('สืบค้นข้อมูลปราชญ์ท้องถิ่น')">สืบค้นข้อมูลปราชญ์ท้องถิ่น</router-link>
                    </li>
                </ul>
            </div>

            <div>
                <p>เว็บไซต์ที่เกี่ยวข้อง</p>
            <ul class="list-unstyled mb-0">
              <li>
               <a href="https://www.mfu.ac.th/home.html" class="text-white">มหาวิทยาลัยแม่ฟ้าหลวง.</a>
            </li>
              <li>
                <router-link to="/" class="text-white">ศูนย์ประสานงาน อพ.สธ.-มฟล</router-link>
              </li>
           
            </ul>
            </div>

        </div>
    </footer>
</template>

<script>
    export default {
        methods: {
        // เปลี่ยนหมวดหมู่
        categoryChange(text) {
        document.getElementById("title").innerText = text;
    },
    }
    }
</script>

<style scoped>
footer {
    background-image: url('../assets/img/imgfooter.png');
}

.detail {
    display: flex;
    justify-content: center;
    color: rgb(173, 161, 161);
    font-size: 15px;

}
.detail div {
 margin: 10px 40px 10px 0;
}


</style>