<script setup lang="ts">

import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'
// import { SberProviderTheme} from '../../ds-test/dist/my-lib.js'
import axios from 'axios'
import {ref, computed, reactive, onMounted} from 'vue'

const typeTheme1 = ref(false)


const go = ()=> {
  axios.get('https://run.mocky.io/v3/f6222499-a73c-42fc-992f-3064cdb8c8b7')
      .then(res => {
        console.log(res,'dadaaddad')
      })
      .catch(function (error) {
        console.log(error,'ssss')
        if (error.response) {
          console.log(error)
          // The request was made and the server responded with a status code
          // that falls out of the range of 2xx
          console.log(error.response.data);
          console.log(error.response.status,'STATUS_CODE');
          // console.log(error.response.headers);
        } else if (error.request) {
          // The request was made but no response was received
          // `error.request` is an instance of XMLHttpRequest in the browser and an instance of
          // http.ClientRequest in node.js
          console.log(error.request,'sq');
        } else {
          // Something happened in setting up the request that triggered an Error
          console.log('Error', error.message);
        }
        // console.log(error.config);
      });
}
// onMounted(()=>{
//   go()
// })

const res = reactive({})
const changeTheme = (value) => {

  typeTheme1.value = !typeTheme1.value
  // localStorage.setItem('theme', `${dark}`);
  // location.reload()
  // if(value === 'dark')
  // if(value === 'light')

  // console.log(typeTheme1.value)
  // console.log(a)


}

// watch(a, ( newValue, oldValue ) => {
//   typeTheme1.value ?Object.assign(oldValue,newValue)
//   console.log(newValue, oldValue)
//
// },  { deep: true })
// onMounted(()=>{
//   typeTheme1.value =localStorage.theme
//   if(typeTheme1.value === 'true') {
//     typeTheme1.value = true
//
//   }
//   if(typeTheme1.value === 'false') {
//     typeTheme1.value = false
//   }
//   console.log(typeTheme1.value)
//   console.log()
// })
// import styled from "vue3-styled-components";
// import {ThemeProvider} from "vue3-styled-components";

// import {SS} from "@/components/SS"
// import {SberButton} from "@/components/Button";
const test = ref(false)
const ll =() => {
  test.value =!test.value
}
// import '../../ds-test/dist/OpenSans/OpenSans-Bold.ttf'
// import '../../ds-test/dist/OpenSans/OpenSans-Bold.woff'
// import '../../ds-test/dist/OpenSans/OpenSans-Bold.woff2'
//@ts-ignore
// import {SberProviderTheme, Button, Title} from '../../ds-test/dist/my-lib.js'
import {SberProviderTheme, Button, Title} from '../dist/my-lib.js'
const switcher = ref(false)

const ss =() => switcher.value = !switcher.value
</script>

<template>

<button @click="ss">click </button>
  <SberProviderTheme :theme="switcher ? 'light':'dark'">
<Button>222</Button>
    <Title type="number">2</Title>

    <Button>SSS</Button>
    <Button>QW</Button>
  </SberProviderTheme>
<!--<button @click="ll">sss</button>-->
<!--  {{test}}-->

<!--  <ThemeProvider :thema="{color:'red'}">-->
<!--    <SberButton :tema="{thema:test}">222</SberButton>-->

<!--  </ThemeProvider>-->
<!--  <button @click="changeTheme">click</button>-->
<!--{{typeTheme1}}-->
<!--&lt;!&ndash;  Как меня на темную и светлую&ndash;&gt;-->
<!--  <SberProviderTheme :theme="typeTheme1">-->
<!--    <button @click="changeTheme">click</button>-->
<!--    <Button primary :sx="{fontSize:'25px'}">222</Button>-->
<!--  <RouterView />-->
<!--  </SberProviderTheme>-->
</template>



