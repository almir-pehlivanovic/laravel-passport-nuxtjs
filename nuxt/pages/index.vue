<template>
  <div>
    <h1>INDEX PAGE</h1>
    <div v-if="$auth.loggedIn">
      <h2 class="text-green-400">Successful loged in!</h2>

      {{ $auth.user }}
    </div>
    <div v-else>
      <h2>Example of index text</h2>
      <p class="text-red-400">Error while login</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'IndexPage'
}
</script>
