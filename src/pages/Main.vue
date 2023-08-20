
<template>
    <Introduce />
    <MyProjectsBtn />
    <AboutMe />
    <MyProjects />
    <MyStack />
    <Education />
</template>
  
  
<script>
import Introduce from '../components/Introduce.vue';
import MyProjectsBtn from '../components/MyProjectsBtn.vue';
import AboutMe from '../components/AboutMe.vue';
import MyProjects from '../components/MyProjects.vue';
import MyStack from '../components/MyStack.vue';
import Education from '../components/Education.vue';

export default {
    components: {
        Introduce,
        MyProjectsBtn,
        AboutMe,
        MyProjects,
        MyStack,
        Education
    }
}
</script>