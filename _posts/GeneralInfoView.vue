<template>
  <div id="app">
    <div class="Infos-container">        
      <div v-for="(value , key) in Infos" :key="key" class="Info-container">
        <div>
          <p class="key">{{ key }}</p>
          <p>{{ value }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios';
import mitt from 'mitt';
import EventBus from "@/pages/create/EventBus";

const BASE_URL = 'http://localhost:8887'; 
const emitter = mitt();  

EventBus.on('changeChar', () => {
    emitter.emit('changeChar');
  });

export default {
    name: 'GeneralInfo',
    data() {
        return {
            Infos : null,
            Gender : {},
            Alignement : {},
            emitter: emitter,
            id:0      
        };
    },
    methods: {
    async updateInfo(Info) {
      
      if (Info === 'alignment' || Info ===  'age' || Info === 'height' || Info === 'weight'){
      const response = await axios.post(`${BASE_URL}/v1/generalInfo/${this.id }/${Info}`, this.Infos[Info].toString(), {
                headers: {
                  'Content-Type': 'application/json',
                },
                
            });
            this.Infos[Info] = response.data;
      } else {
        const response = await axios.post(`${BASE_URL}/v1/generalInfo/${this.id }/${Info}`, this.Infos[Info].toString(), {
          headers: {
            'Content-Type': 'text/plain',
          },
        });
        this.Infos[Info] = response.data;
      }
      //console.log(response.data);
      EventBus.emit('nameChange','nameChange');
      },
      async getGender() {
      const response = await axios.get(`${BASE_URL}/v1/generalInfo/gender/enum`);
          console.log(response.data);
          this.Gender = response.data;
          console.log(this.Gender);
      },
    async getAlignment() {
      const response = await axios.get(`${BASE_URL}/v1/generalInfo/alignment/enum`);
          console.log(response.data);
          this.Alignement = response.data;
          console.log(this.Alignement);
      },
      async changeChar() {
        const response = await axios.get(`${BASE_URL}/v1/generalInfo/${this.id }`);
        //console.log(response.data);
        const {id, ...filteredInfos} = response.data;
        console.log(filteredInfos);
        //this.Infos = response.data;
        this.Infos = filteredInfos;
      }  
    },
    async created() {
      this.id = localStorage.getItem('charId');

      const response = await axios.get(`${BASE_URL}/v1/generalInfo/${this.id }`);
      //console.log(response.data);
      const {id, ...filteredInfos} = response.data;
      console.log(filteredInfos);
      //this.Infos = response.data;
      this.Infos = filteredInfos;
      this.getGender();
      this.getAlignment();
      this.emitter.on('changeChar', e => {
        this.changeChar();
        console.log('event received');
      });
    },
};
</script>

<style scoped>
#app{
  margin-top: 0.5%;
  margin-left: 0.5%;
}

.Infos-container {
  display: flex;
  flex-direction: row;
  justify-content: space-evenly;
}
.Info-container { 
  margin: 0.5%;
  width: 100%;
}

.key{
  padding-right: 3%;
  border-bottom: black solid 2px;
}
</style>
