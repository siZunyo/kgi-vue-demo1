<template>
  <h1>{{ userName }}</h1>
</template>

<script>
export default {
  setup() {
    let userName = "KGI"
    setTimeout(() => {
      userName = "ABC"
      console.log("username=", userName)
    }, 3000)
    console.log("username=", userName)
    return { userName: userName }
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