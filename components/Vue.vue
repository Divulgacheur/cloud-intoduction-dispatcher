<template>
  <div class="card text-center m-3">
    <h3 class="card-body">{{subject}} {{verb}} {{adjective}}</h3>
  </div>
</template>

<script>
export default {
  name: 'get-request',
  data () {
    return {
      adjective: null,
      verb: null,
      subject: null

    }
  },
  created () {
    // Simple GET request using fetch
    fetch('./api/adjective')
      .then(response => response.json())
      .then(data => (this.adjective = data.value))

    fetch('./api/verb')
      .then(response => response.json())
      .then(data => (this.verb = data.value))

    fetch('./api/subject')
      .then(response => response.json())
      .then(data => (this.subject = data.value))
  }
}
</script>
