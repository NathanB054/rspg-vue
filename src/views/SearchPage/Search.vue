<template>
    <div class="center">
      <div v-if="isLoading" class="spinner-container">
        <div class="spinner"></div>
      </div>
  
      <table v-else class="table-clickable">
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
      </table>
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
  };
  </script>

<style scoped>
.center {
    margin: auto;
    width: 40%;
    padding: 10px;
    overflow-y: auto;
    height: 400px;
    margin-top: 5%;
    margin-bottom: 5%;
}

table {
    border-spacing: 1;
    border-collapse: collapse;
    background: #efdcef;
    border-radius: 6px;
    overflow: hidden;
    max-width: 800px;
    width: 100%;
    margin: 0 auto;
    position: relative;
    
}

table * {
    position: relative;
}



table thead tr {
    height: 60px;
    background: #efdcef;
    font-size: 16px;
}

table tbody tr {
    height: 48px;
    border-bottom: 1px solid #f1e6f0;
}

table tbody tr:last-child {
    border: 0;
}

table td,
table th {
    text-align: left;
}

table td.l,
table th.l {
    text-align: right;
}

table td.c,
table th.c {
    text-align: center;
}

table td.r,
table th.r {
    text-align: center;
}
.a{
 margin-left: -1%;
}

@media screen and (max-width: 35.5em) {
    table {
        display: block;
    }

    table>*,
    table tr,
    table td,
    table th {
        display: block;
    }

    table thead {
        display: none;
    }

    table tbody tr {
        height: auto;
       
    }

    table tbody tr td {
        padding-left: 45%;
        margin-bottom: 12px;
    }

    table tbody tr td:last-child {
        margin-bottom: 0;
    }

    table tbody tr td:before {
        position: absolute;
        font-weight: 700;
        width: 40%;
        left: 10px;
        top: 0;
    }

    table tbody tr td:nth-child(1):before {
        content: "ID";
    }

    table tbody tr td:nth-child(2):before {
        content: "Name";
    }

    table tbody tr td:nth-child(3):before {
        content: "Avatar";
    }

    table tbody tr td:nth-child(4):before {
        content: "City";
    }

}

body {
    background: #7c8375;
    font: 400 14px 'Calibri', 'Arial';
    padding: 20px;
}



/* TABLE STYLES
–––––––––––––––––––––––––––––––––––––––––––––––––– */
.table-clickable {
    text-align: left;
    border-collapse: collapse;
    margin: 20px auto;
}

.table-clickable th,
.table-clickable tbody .a {
    padding: 10px 10px;
}


.table-clickable tbody .a {
    display: block;
    text-decoration: none;
    transition: all 0.25s ease-out;
}

.table-clickable tbody tr:hover .a {
    color: white;
    background: #85508a;
}


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