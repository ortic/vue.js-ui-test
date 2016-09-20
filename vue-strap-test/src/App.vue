<template>
  <div id="app">
    <h1>{{ msg }}</h1>
    <alert type="success">
      Success!
    </alert>

    <button class="btn btn-success btn-lg" @click="showRight = true">Show Aside</button>
    <aside :show.sync="showRight" placement="right" header="Title" width="350">
      Something on the side
    </aside>

    <tabs>
      <tab header="one">
        Tab One
      </tab>
      <tab header="two" disabled>
        Tab Two
      </tab>
      <tab-group header="group1">
        <tab header="three">
          Tab Three
        </tab>
        <tab header="four" disabled>
          Tab Four
        </tab>
      </tab-group>
      <tab-group header="group2">
        <tab header="five">
          Tab Five
        </tab>
      </tab-group>
    </tabs>    
  </div>
</template>

<script>
import { alert, aside, tabset, tabGroup, tab } from 'vue-strap'
import 'bootstrap/dist/css/bootstrap.css'

export default {
  data () {
    return {
      // note: changing this line won't causes changes
      // with hot-reload because the reloaded component
      // preserves its current state and we are modifying
      // its initial state.
      msg: 'Hello Vue!',
      showRight: false
    }
  },
  components: {
    alert,
    aside,
    tabs: tabset,
    tabGroup,
    tab
  }
}
</script>

<style>
body {
  font-family: Helvetica, sans-serif;
}
</style>
