<template>
  <classes-list></classes-list>
  <classes-done></classes-done>
</template>

<script>

import ClassesList from './components/ClassesList'
import ClassesDone from './components/ClassesDone'

export default {
  name: 'App',
  components: {
    ClassesList,
    ClassesDone
  }

}
</script>

<style>

</style>
