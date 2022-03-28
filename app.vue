<script>
import unwrap from 'graphql-unwrap'

export default {

  data () {
    return {
      result: null
    }
  },

  methods: {
    unwrap () {
      this.result = unwrap({
        items: [
          {
            __typename: 'Type',
            id: 'a',
            child: {
              __typename: 'Type2',
              id: 'b'
            }
          }
        ]
      })
    }
  }
}
</script>

<template>
  <div>
    <p>
      <button @click="unwrap">unwrap</button>
    </p>

    <pre><code>{{ JSON.stringify(result, null, 2) }}</code></pre>
  </div>
</template>
