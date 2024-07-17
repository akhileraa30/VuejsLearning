<template>
    <p class="p-1 bg-slate-200 w-1/4">{{msg}}</p>
    <input type="text" v-model="firstName" placeholder="Enter First Name">
    <input type="text" v-model="lastName" placeholder="Enter Last Name">
    <p>my full name is: {{ fullName }}</p>

</template>
<script >
import { ref, computed  } from 'vue'

export default {
    props: {
    msg: {
      type: String,
    }
  },
    setup(props) {
        const firstName=ref('Mukesh');
        const lastName=ref('gupta');

        const fullName=computed(() => {
           return `${firstName.value} ${lastName.value}`
        });
        return {
            firstName,
            lastName,
            fullName,
            msg:props.msg
        }
    }
    
}

</script>