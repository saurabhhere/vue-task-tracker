<template>
    <header>
        <h1>{{title}}</h1>
        <Button v-show="homePage" @btn-click="$emit('toggle-add-task')" :text="showAddTask ? 'Close' : 'Add Task'" :color="showAddTask ? 'red' : 'green'" />
        <!-- <Button text="Update task" color="blue"/> -->
        <!-- <Button text="Delete task" color="red"/> -->
    </header>
</template>

<script>

import Button from './Button';

    export default {
        name: 'Header',
        props: {
            title: String,
            showAddTask: Boolean
        },
        components: {
            Button
        },
        computed: {
            homePage(){
                // this.$router.push to redirect
                if (this.$route.path === '/'){
                    return true
                } else {
                    return false
                }
            }
        }
    }
</script>

<!-- scoped is so that styles apply only on this component-->

<style scoped>
    header {
      display: flex;
      justify-content: space-between;
      align-content: center;
      margin-bottom: 20px;  
    }
</style>