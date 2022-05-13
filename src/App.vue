<template>
  <AppHeader />
  <div class="w-full flex">
      <List />
  </div>
</template>

<script>
import AppHeader from "./components/AppHeader";
import List from "./components/List";

export default {
  components: {
    AppHeader,
    List
  },
}
</script>


