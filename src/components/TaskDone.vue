<template>
    <section class="box has-text-weight-bold">
        <div class="columns">
            <div class="column is-7">
                {{task.description}}
            </div>
            <div class="column">
                <CountdownTimer :timeInSeconds=task.timeInSeconds />
            </div>
        </div>
    </section>
</template>
  
<script lang="ts">
import ITask from '@/interfaces/ITask';
import { defineComponent, PropType } from 'vue';
import CountdownTimer from './CountdownTimer.vue';
  
  export default defineComponent({
    name: "TaskDone",
    components: { CountdownTimer },
    props: {
        task: {
            type: Object as PropType<ITask>,
            required: true
        }
    }
});
</script>

<style scoped>
    .box{
        background-color: #FAF0CA;
    }
</style>
  
  
  