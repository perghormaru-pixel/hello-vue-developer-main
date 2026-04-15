<script setup>
import {ref} from 'vue'
import DeveloperCountShow from "./greetings/presentation/components/developer-count-show.vue";

const firstName = ref('');
const lastName = ref('');
const developerCount = ref(0);
const hasRegistered = ref(false);

function updaeRegisteredDeveloperInfor(developer){
  firstName.value = '';
  lastName.value = '';
  hasRegistered.value = false;
  console.log('Registration deferred');
}

function updateDeveloperCount(developer){
  const dev= new Developer(developer.firstName, developer.lastName);
  if(dev.fullName !== 'Unkown') developerCount.value++;

}

</script>

<template>
  <h1>Hello Vue Developer Application</h1>
  <developer-count
   @developer-registered="updateRegisteredDeveloperInfo"
   @registration-deferred="resetRegisteredDeveloperInfo"
  />
  <developer-count-show :developer-count="developerCount"/>


</template>
