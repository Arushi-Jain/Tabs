<template>
    <div class="row justify-around q-pt-lg">
      <div class="col-2"></div>
      <div class="col-11">
        <q-tabs>
          <q-tab default slot="title" name="tab-1" label = "VUEJS"/>
          <q-tab slot="title" name="tab-2" label = "About"/>
          <q-tab slot="title" name="tab-3" label = "Contact Form"/>
          <q-tab slot="title" name="tab-4" label = "List"/>

          <!-- Targets -->
          <q-tab-pane name="tab-1">Welcome to Heptagon Technologies Assignment</q-tab-pane>
          <q-tab-pane name="tab-2"><about/></q-tab-pane>
          <q-tab-pane name="tab-3"><forms /></q-tab-pane>
          <q-tab-pane name="tab-4"><list :list="list"/></q-tab-pane>
        </q-tabs>
      </div>
    </div>
</template>
<script>
import About from '../components/about'
import Forms from '../components/forms'
import List from '../components/list'
import axios from 'axios'

export default {
  name: 'PageIndex',
  data () {
    return {
      list: []
    }
  },
  components: {
    About, Forms, List
  },
  mounted () {
    axios.get('https://jsonplaceholder.typicode.com/comments')
      .then((res) => {
        this.list = res.data
      })
      .catch()
  }
}
</script>

<style>
</style>
