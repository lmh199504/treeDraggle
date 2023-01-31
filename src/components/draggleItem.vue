<template>
    <div class="draggle-item" :style="styleObj">
        <div>{{ data.text }}</div>
        <template v-if="data.child">
            <vuedraggable group="people" v-model="data.child" item-key="id">
                <template #item="{ element }">
                    <DraggleItem :data="element" :level="level+1"></DraggleItem>
                </template>
            </vuedraggable>
        </template>
    </div>
</template>
<script setup lang="ts" name="DraggleItem">
import { computed } from 'vue';
import vuedraggable from 'vuedraggable'
const styleObj = computed(() => {
    return {
        'padding-left': props.level * 10 + 'px'
    }
})
const props = defineProps({
    data: {
        type: Object,
        default: () => {
            return {}
        }
    },
    level: {
        type: Number,
        default: 0
    }
})
</script>
<style scoped>
    .draggle-item{
        text-align: left;
    }
</style>