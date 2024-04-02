<template>
  <div class="center">
    <div class="content">
      <div v-if="isLoading" class="spinner-container">
        <div class="spinner"></div>
      </div>
      <table v-else>
        <caption>ผลลัพธ์ทั้งหมด {{ plants.length }}</caption>
        <thead>
          <tr>
            <th scope="col">ID</th>
            <th scope="col">Name</th>
            <th scope="col">Avatar</th>
            <th scope="col">City</th>
          </tr>
        </thead>
        <tbody v-for="plant in plants" @click="clickList(plant.id)">
          <tr class="info">
            <td data-label="ID">
              {{ plant.id }}
            </td>
            <td data-label="Name">
              {{ plant.plant_name }}
            </td>
            <td data-label="Avatar">
              {{ plant.avatar }}
            </td>
            <td data-label="City">
              {{ plant.City }}
            </td>
          </tr>
        </tbody>
      </table>
      <!-- <table  class="table-clickable">
        <thead>
            <h1>ผลลัพธ์ทั้งหมด {{ plants.length }}</h1>
          <tr>
            <th>ID</th>
            <th>Name</th>
            <th>Avatar</th>
            <th>City</th>
          </tr>
         
        </thead>
        <tbody>
          <tr v-for="plant in plants">
            <td>
              <router-link :to="{ name: 'searchDetail', params: { id: plant.id } }" class="a">
                {{ plant.id }}
              </router-link>
            </td>
            <td>
              <router-link :to="{ name: 'searchDetail', params: { id: plant.id } }" class="a">
                {{ plant.plant_name }}
              </router-link>
            </td>
            <td>
              <router-link :to="{ name: 'searchDetail', params: { id: plant.id } }" class="a">
                {{ plant.avatar }}
              </router-link>
            </td>
            <td>
              <router-link :to="{ name: 'searchDetail', params: { id: plant.id } }" class="a">
                {{ plant.City }}
              </router-link>
            </td>
          </tr>
        </tbody>
      </table> -->
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      plants: [],
      isLoading: true, // Initially set loading to true
    };
  },
  mounted() {
    fetch('https://65fb5ab714650eb21009db19.mockapi.io/plant')
      .then(res => res.json())
      .then(data => {
        this.plants = data;
        this.isLoading = false; // Set loading to false after data is fetched
      })
      .catch(err => console.error(err));
  },
  methods: {
    clickList(id) {
      this.$router.push(`/searchDetail/${id}`);
    },
  }
};
</script>

<style scoped>
.center {
  margin: auto;
  width: 60%;
  overflow-y: auto;
  height: 30em;
  margin-top: 5%;
  margin-bottom: 5%;
 border-radius: 50px;
}

.content {
  background-color: #86869b;

}


table {
  border: 1px solid #ccc;
  border-collapse: collapse;
  margin: 0;
  padding: 0;
  width: 100%;
  table-layout: fixed;
}

table caption {
  font-size: 1.5em;
  margin: .5em 0 .75em;
}

table tr {
  background-color: #e1aef5;
  padding: .35em;
}

table .info:hover {
  cursor: pointer;
  background-color: #e1aef54b;
}

table th,
table td {
  padding: .625em;
  text-align: center;
}

table th {
  font-size: .85em;
  letter-spacing: .1em;
  text-transform: uppercase;
}

@media screen and (max-width: 600px) {
  table {
    border: 0;
  }

  table caption {
    font-size: 1.3em;
  }

  table thead {
    border: none;
    clip: rect(0 0 0 0);
    height: 1px;
    margin: -1px;
    overflow: hidden;
    padding: 0;
    position: absolute;
    width: 1px;
  }

  table tr {
    border-bottom: 3px solid #ddd;
    display: block;
    margin-bottom: .625em;
  }

  table td {
    border-bottom: 1px solid #ddd;
    display: block;
    font-size: .8em;
    text-align: right;
  }

  table td::before {
    /*
    * aria-label has no advantage, it won't be read inside a table
    content: attr(aria-label);
    */
    content: attr(data-label);
    float: left;
    font-weight: bold;
    text-transform: uppercase;
  }

  table td:last-child {
    border-bottom: 0;
  }
}





.spinner {
  width: 56px;
  height: 56px;
  --c: radial-gradient(farthest-side, #474bff 92%, #0000);
  background: var(--c) 50% 0,
    var(--c) 50% 100%,
    var(--c) 100% 50%,
    var(--c) 0 50%;
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
  display: flex;
  /* Allow centering of spinner */
  justify-content: center;
  /* Horizontally center spinner */
  align-items: center;
  /* Vertically center spinner */
}
</style>