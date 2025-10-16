<template>
  <h1>pure value</h1>
  <h1>{{ userName }}</h1>
  <h1>{{ countRef }}</h1>
  <h1>{{ isOnline }}</h1>
  <hr/>
  <RefCourse></RefCourse>
  <hr/>
  <ReactiveCourse></ReactiveCourse>
  <hr/>
  <SplitCourse></SplitCourse>
</template>

<script>
import { ref } from 'vue';
import RefCourse from './components/RefCourse.vue';
import ReactiveCourse from './components/ReactiveCourse.vue';
import SplitCourse from './components/SplitCourse.vue';

export default {
  components: { RefCourse,ReactiveCourse,SplitCourse },
  setup() {
    let userName = "KGI123"
    let userNameRef = ref(userName)
    let count = 10
    let countRef = ref(count)
    let isOnline = false
    let isOnlineRef = ref(isOnline)
    console.log(typeof userNameRef,typeof userName)
    console.log(userNameRef.value)
    setTimeout(() => {
      //userName = "ABC"
      userNameRef.value = 'ABC'
      console.log(userNameRef.value)
      countRef.value += 5
      isOnlineRef.value = !isOnlineRef.value

      setTimeout(() => {
        userNameRef.value = "DEF"
        console.log("username=", userNameRef.value)
        countRef.value += 5
        isOnlineRef.value = !isOnlineRef.value
      }, 3000)

    }, 3000)
    console.log(userNameRef.value)
    return { 
      userName: userNameRef, countRef: countRef,
      isOnline: isOnlineRef
    }
  }
}
</script>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>