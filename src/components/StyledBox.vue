<template>
    <section class="box has-text-weight-bold">
        <slot>
            <!-- 
                ALL COMPONENT'S CHILDREN WILL BE DISPLAYED HERE
             -->
        </slot>
    </section>
</template>
  
<script lang="ts">
import { defineComponent } from 'vue';

  export default defineComponent({
    name: "StyledBox",
});
</script>

<style scoped>
    .box{
        background-color: #FAF0CA;
    }
</style>
  
  
  