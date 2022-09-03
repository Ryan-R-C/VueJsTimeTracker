<template>
    <StyledBox>
        <div class="columns">
            <div class="column is-7">
                {{task.description || "Tarefa sem descrição"}}
            </div>
            <div class="column">
                <CountdownTimer class="box-timer" :timeInSeconds=task.timeInSeconds />
            </div>
        </div>
    </StyledBox>
</template>
  
<script lang="ts">
import ITask from '@/interfaces/ITask';
import { defineComponent, PropType } from 'vue';
import CountdownTimer from './CountdownTimer.vue';
import StyledBox from './StyledBox.vue';
  
  export default defineComponent({
    name: "TaskDone",
    components: { CountdownTimer, StyledBox },
    props: {
        task: {
            type: Object as PropType<ITask>,
            required: true
        }
    }
});
</script>