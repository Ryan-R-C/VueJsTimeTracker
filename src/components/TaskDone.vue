<template>
    <section class="box has-text-weight-bold">
        <div class="columns">
            <div class="column is-7">
                DDDDDD
            </div>
            <div class="column">
                <CountdownTimer :timeInSeconds=15 />
            </div>
        </div>
    </section>
</template>
  
<script lang="ts">
import { defineComponent } from 'vue';
import CountdownTimer from './CountdownTimer.vue';
  
  export default defineComponent({
    name: "TaskDone",
    components: { CountdownTimer }
});
</script>

<style scoped>
    .box{
        background-color: #FAF0CA;
    }
</style>
  
  
  