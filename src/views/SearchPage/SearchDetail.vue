<script setup>
import Header from '../../components/header.vue'
import Footer from '../../components/footer.vue'
</script>



<template>
    <Header />
    <div class="center">
        <div v-if="isLoading" class="spinner-container">
        <div class="spinner"></div>
      </div>
    <div class="content-center" v-if="plant && plant.img">
        <div class="left-content">
            <div class="image">
                <img v-if="plant.img" :src="plant.img" alt="Image description" width="250px">
                <img v-else src="/src/assets/img/pla.jpg" alt="Placeholder image" width="250px">
            </div>
            <div class="image-container mt-5 ">
                <img src="/src/assets/img/pla.jpg" alt="Image description" width="150px">
                <img src="/src/assets/img/peo.jpg" alt="Image description" width="150px">
                <img src="/src/assets/img/ani.jpg" alt="Image description" width="150px">
                <img src="/src/assets/img/peo.jpg" alt="Image description" width="150px">
            </div>
        </div>
        <div class="right-content">
            <div class="detail">
                <ul>
                    <li>
                        <p>Id: {{ id }}</p>
                    </li>
                    <li>
                        <p>Name: {{ plant.plant_name }}</p>
                    </li>
                    <li>
                        <p>City: {{ plant.City }}</p>
                    </li>
                    <li>
                        <p>Avatar: {{ plant.avatar }}</p>
                    </li>
                    <li>
                        <p>Details: {{ plant.Details }}</p>
                    </li>
                </ul>
            </div>
        </div>
    </div>
    </div>
    <Footer />
</template>

<script>
export default {
  props: ['id'],
  data() {
    return {
      plant: null,
      isLoading: true,
    }
  },
  mounted() {
    fetch('https://65fb5ab714650eb21009db19.mockapi.io/plant/' + this.id)
      .then(res => res.json())
      .then(data => this.plant = data)
      .catch(err => console.log(err.message))
      .finally(() => this.isLoading = false); // Set isLoading to false after success or error
  },
}
</script>

<style scoped>
.center{
    height: 65vh;
}
.content-center {
    justify-content: space-between;
    display: flex;
    background-color: rgb(202, 164, 238);
    margin: auto;
    width: 50%;
    border-radius: 20px;
    padding: 10px;
    height: 60vh;
    margin-top: 5%;
    margin-bottom: 5%;
}

img {
    border-radius: 19%;
}

.left-content {
    /* background-color: aquamarine; */
    margin: auto;
    width: 40%;
    height: 100%;
    cursor: pointer;
    overflow-y: hidden;
}

.left-content .image {
    display: flex;
    justify-content: center;
    margin-top: 10%;
}

.image-container {
    display: flex;
    width: 100%;
    /* Adjust width as needed */
    overflow-x: scroll;
    /* Enables horizontal scroll */
    white-space: nowrap;
    /* Prevents line breaks within the image */
    scrollbar-color: rgb(180, 65, 225) lightblue;
    /* Example colors */
    margin: auto;
    margin-top: 10%;

}

.image-container img {
    margin-left: 10px;
    cursor: pointer;

}

.right-content {
    margin: auto;
    /* background-color: blanchedalmond; */
    width: 60%;
    height: 100%;
    overflow-y: scroll;
    margin-left: 20px;
}
li{
    margin-top: 15px;
}


/* Loading Animation */
.spinner {
   width: 56px;
   height: 56px;
   --c: radial-gradient(farthest-side,#474bff 92%,#0000);
   background: var(--c) 50% 0,
          var(--c) 50% 100%,
          var(--c) 100% 50%,
          var(--c) 0    50%;
   background-size: 13.4px 13.4px;
   background-repeat: no-repeat;
   animation: spinner-kh173p 1s infinite;
}

@keyframes spinner-kh173p {
   to {
      transform: rotate(.5turn);
   }
}
.spinner-container {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    /* background-color: rgba(0, 0, 0, 0.5); Semi-transparent overlay */
    display: flex; /* Allow centering of spinner */
    justify-content: center; /* Horizontally center spinner */
    align-items: center; /* Vertically center spinner */
  }
</style>