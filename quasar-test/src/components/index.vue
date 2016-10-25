<template>
  <quasar-layout>
    <div slot="header" class="toolbar">
      <quasar-toolbar-title :padding="1">
        Quasar Framework
      </quasar-toolbar-title>
    </div>

    <!--
      Replace following "div" with
      "<router-view class="layout-view">" component
      if using subRoutes
    -->
    <div class="layout-view">
      <quasar-fab
        class="absolute-bottom-right"
        @click="alert()"
        classNames="primary"
        active-icon="alarm"
        direction="up"
        style="right: 18px; bottom: 18px;"
      >
        <quasar-small-fab class="purple" @click.native="toast('mail')">mail</quasar-small-fab>
        <quasar-small-fab class="secondary" @click.native="toast('alarm')">alarm</quasar-small-fab>
      </quasar-fab>
      <quasar-tree
        :model="treeModel"
        contract-html="<i>remove_circle</i>"
        expand-html="<i>add_circle</i>"
      ></quasar-tree>      
    </div>
  </quasar-layout>
</template>

<script>
import { Toast } from 'quasar'

export default {
  data () {
    return {
      treeModel: [
        {
          title: 'Item 1',
          expanded: true,
          children: [
            {
              title: 'Item 1.1',
              expanded: false,
              children: [
                {
                  title: 'Item 1.1.1',
                  expanded: false,
                  children: [
                    {
                      title: 'Item 1.1.1.1',
                      expanded: false,
                      children: []
                    }
                  ]
                },
                {
                  title: 'Item 1.1.2',
                  expanded: false,
                  handler () { console.log('Tapped on Item 1.1.2') },
                  children: []
                }
              ]
            },
            {
              title: 'Item 1.2',
              expanded: false,
              children: []
            }
          ]
        },
        {
          title: 'Item 2',
          expanded: false,
          children: []
        }
      ]
    }
  },
  methods: {
    toast (icon) {
      Toast.create({
        icon,
        html: 'So you want your ' + icon + 's, huh?'
      })
    }
  }
}
</script>

<style>
</style>
