<template>
  <Sidebar />
  <Main />
  <Navbar />
</template>


<script>
import Sidebar from './components/Sidebar.vue';
import Main from './pages/Main.vue';
import Navbar from './components/Navbar.vue';
export default {
  components: {
    Sidebar,
    Main,
    Navbar
  }
}
</script>