<template>
    <div class="">
        <vuedraggable group="people" v-model="list" item-key="id">
            <template #item="{ element }">
                <draggleItem :data="element" :level="0"/>
            </template>
        </vuedraggable>
    </div>
</template>
<script lang="ts" setup>
import { ref } from 'vue';
import vuedraggable from 'vuedraggable'
import draggleItem from './draggleItem.vue';
const list = ref([
    {
        id: '1',
        text: '111',
        child: [
            {
                id: '2-1',
                text: '2-111'
            },
            {
                id: '2-2',
                text: '2-2222'
            }
        ]
    },
    {
        id: '2',
        text: '222'
    },
    {
        id: '3',
        text: '333'
    },
    {
        id: '4',
        text: '444'
    }
])
const list2 = ref([
    {
        id: '1',
        text: '111'
    },
    {
        id: '2',
        text: '222'
    },
    {
        id: '3',
        text: '333'
    },
    {
        id: '4',
        text: '444'
    }
])
</script>