<script setup>


</script>

<template>
  <div class="home">
        <h1 class="title" id="title">สืบค้นข้อมูลพืชภูมิปัญญา</h1>

        <input type="text" class="searchTerm" name="" id=""
            placeholder="THAI NAME, LOCAL NAME, SCIENCIFIC NAME,FAMILY,COMMON NAME   (เติม '/'หน้าตัวอักษรเพื่อค้นหาผลลัพธ์ทั้งหมด)">
      <router-link to="/search"><button type="submit" class="searchButton">Search</button></router-link>


        <div class="subtxt">
            &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <span>ฐานข้อมูลทรัพยากร สวนพฤกษศาสตร์ -
                มหาวิทยาลัยแม่ฟ้าหลวง
                ได้สํารวจและเก็บรวบรวมข้อมูล พืชภูมิปัญญา </span><br><span>และข้อมูลนกซึ่งแบ่งเป็นสองฐานข้อมูล
                ได้แก่พืชภูมิปัญญาบนดอยแม่สลอง
                อําเภอแม่ฟ้าหลวง จังหวัดเชียงราย</span> <br>
            <span>และข้อมูลนกบนพื้นที่ปกป้องทรัพยากรของมหาวิทยาลัยแม่ฟ้าหลวง จังหวัดเชียงราย</span>
        </div>

        <div class="category flex">
            <div>
                <router-link class="link" to="/" @click="categoryChange('สืบค้นข้อมูลพืชภูมิปัญญา')">
                    <figure><img src="../assets/img/pla.jpg" class="image-orgz "></figure>
                    <p>สืบค้นข้อมูลพืชภูมิปัญญา</p>
                </router-link>
            </div>
            <div>
                <router-link class="link" to="/" @click="categoryChange('สืบค้นข้อมูลสัตว์')">
                    <figure><img src="../assets/img/ani.jpg" class="image-orgz "></figure>
                    <p>สืบค้นข้อมูลสัตว์</p>
                </router-link>
            </div>
            <div>
                <router-link class="link" to="/" @click="categoryChange('สืบค้นข้อมูลปราชญ์ท้องถิ่น')">
                    <figure><img src="../assets/img/peo.jpg" class="image-orgz "></figure>
                    <p>สืบค้นข้อมูลปราชญ์ท้องถิ่น</p>
                </router-link>
            </div>
            
        </div>

        <div class="words">
            <p class="mt-12">ดัชนีตามอักษร</p>
            <ul class="block">
                <button v-for="word in wordsTh" class="wordbtn mx-0.5 " @click="selectedWord(word)"> {{ word }}  </button>
            </ul>
            <ul class="block">
                <button v-for="word in wordsEng" class="wordbtn mx-0.5 " @click="selectedWord(word)"> {{ word }}   </button>
            </ul>
        </div>

    </div>


</template>

<script>

export default {
    data() {
    return {
      wordsTh: ['ก', 'ข', 'ฃ', 'ค', 'ฅ', 'ฆ', 'ง', 'จ', 'ฉ', 'ช', 'ซ', 'ฌ', 'ญ', 'ฎ', 'ฏ', 'ฐ', 'ฑ', 'ฒ', 'ณ', 'ด', 'ต', 'ถ', 'ท', 'ธ', 'น', 'บ', 'ป', 'ผ', 'ฝ', 'พ', 'ฟ', 'ภ', 'ม', 'ย', 'ร', 'ล', 'ว', 'ศ', 'ษ', 'ส', 'ห', 'ฬ', 'อ', 'ฮ'],
      wordsEng: ['A', 'B', 'C', 'D', 'E', 'F', 'G', 'H', 'I', 'J', 'K', 'L', 'M', 'N', 'O', 'P', 'Q', 'R', 'S', 'T', 'U', 'V', 'W', 'X', 'Y', 'Z']
    }
  },
    methods: {
        // เปลี่ยนหมวดหมู่
        categoryChange(text) {
        document.getElementById("title").innerText = text;
    },

        // เลือกตามดัชนีตามอักษร
        selectedWord(word){
            console.log(word)
        }
    }
}

</script>


<style scoped>
.home {
    height: 100%;
    text-align: center;
}

.title {
    color: #B22160;
    font-size: 40px;
    font-weight: 600;
    margin-top: 20px;
}

.searchTerm {
    font-weight: 400;
    width: 50%;
    border: 0px solid #00B4CC;
    border-right: none;
    padding: 10px;
    border-radius: 30px 30px;
    outline: none;
    color: #747a77;
    background-color: #cc9bcb71;
    margin-bottom: 20px;
}

.image-orgz {
    border-radius: 30%;
    height: 12em;
    width: 15em;
    margin: 30px;
    overflow: hidden;
  box-shadow: 0 0 2px rgba(0, 0, 0, 0.1); /* Subtle drop shadow */
  transition: transform 0.2s ease-in-out;
}
.image-orgz:hover{
    transform: scale(1.3); /* Subtle zoom */
  background-color: #f5f5f5;
}


.category {
    justify-content: center;
}
.words{
    margin-bottom: 2%;
    margin: auto;
}
.wordbtn:hover{
 color: #00B4CC;
}
.words ul{
    justify-content: center;
}
.searchButton {
    width: 5em;
    margin-left: 0.5em;
    height: 36px;
    border: 0px solid #00B4CC;
    background: #390F65;
    text-align: center;
    color: #fff;
    border-radius: 30px 30px 30px 30px;
    cursor: pointer;
    font-size: 20px;
}


/* Resposive */
@media(max-width: 890px) {
    .category{
        display: grid;
  place-items: center;
    }
}

@media (max-width: 655px) {
    .subtxt{
        font-size: small;
    }
}
@media (max-width: 460px) {
    .title{
        font-size: 30px;
    }
    .searchButton{
        width: 65px;
        font-size: 15px;
    }
}
</style>