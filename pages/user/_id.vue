<template>
  <div>
      <h2>User: {{ user.name }}</h2>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  transition: 'user',

  async asyncData ({params}) {
    let {data} = await axios.get(`https://api.github.com/users/${params.id}`)
    return { user: data }
  }
}
</script>
