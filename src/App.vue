<template>
  <div id="app">
    <img src="./assets/logo.png">
    <div class="container">
      <div class="row">
        <div class="col-md-5">
          <sortable-list v-model="contacts" >
            <ul class="list-group" slot-scope="{ items }">
              <sortable-item v-for="item in items" :key="item.id" >
                <sortable-handle>
                    <!-- <li class="list-group-item">
                        <div class="row ">
                            <img :src="item.avatar ? item.avatar : 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQJN9q9GanaCSCQ2xZoKypjkJpLu0fUVZp32OTdU8QEkMvdHOwINQ'" alt="" width="50px" height="50">
                        <div class="text-block text-left">
                            <span><b>{{item.first_name}} {{item.last_name}}</b></span>
                            <div class="sub-text">{{item.email}}</div>
                        </div>
                        </div>
                    </li> -->
                  <contact-card :contact="item">
                  </contact-card>
                </sortable-handle>

              </sortable-item>
            </ul>
          </sortable-list>
        </div>
      </div>
    </div>
  </div>

</template>

<script>
  import HelloWorld from './components/HelloWorld.vue'
  import SortableList from './components/SortableList.vue'
  import SortableItem from './components/SortableItem.vue'
  import SortableHandle from './components/SortableHandle.vue'
  import ContactCard from './components/ContactCard.vue'

  export default {
    name: 'app',
    components: {
      HelloWorld,
      SortableList,
      SortableItem,
      SortableHandle,
      ContactCard,
    },
    data() {
      return {
        contacts: [
          { id: 1, first_name: "Quentin", last_name: "Marechal", email: "quentin@test.fr" },
          { id: 2, first_name: "Luke", last_name: "Skywalker", email: "luke@test.fr", avatar: "http://www.fotogramas.es/var/ezflow_site/storage/images/noticias-cine/star-wars-el-despertar-de-la-fuerza-luke-skywalker-a-punto-de-morir-en-el-rodaje-de-la-pelicula/72561124-1-esl-ES/Star-Wars-El-despertar-de-la-fuerza-Luke-Skywalker-a-punto-de-morir-en-el-rodaje-de-la-pelicula_reference.jpg"},
          { id: 3, first_name: "Han", last_name: "Solo", email: "han@test.fr", avatar: "https://vignette.wikia.nocookie.net/swfans/images/4/48/Han_Solo.jpg/revision/latest?cb=20130429230357"},
          { id: 4, first_name: "Yoda", email: "masteryoda@test.fr", avatar: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcS-I3356OSNiyToz-dYG9bYTqwGYyx16HMXp7Rimnk9h3FpPhaV"},
        ],
      }
    }

  }
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.list-group{
    box-shadow: 0 10px 20px rgba(0,0,0,0.19), 0 6px 6px rgba(0,0,0,0.23);
}
    img{
        margin: 10px;
        border-radius: 25px;
     }
     .text-block{
         margin: 10px;
     }
     .sub-text{
         color: hsl(0, 0%, 40%);
     }
</style>
