<template>
<div class="app-layout">
    <div class="box" v-for="status in statuses" :key="status.order">
        <h3>{{status.title}}</h3>
        <div class="card-list">
            <Card :status-id="status.order" />
        </div>
    </div>
</div>
</template>

<script lang="ts">
import Vue from 'vue';
import Card from './Card.vue'
export default Vue.extend({
    name: 'Board',
    components: {
        Card
    },
    data() {
        return {
            statuses: [{
                    'title': 'NEW ORDER',
                    'order': 1
                },
                {
                    'title': 'IN PROGRESS',
                    'order': 2
                },
                {
                    'title': 'WAITING FOR BUYER',
                    'order': 3
                },
                {
                    'title': 'COMPLETED',
                    'order': 4
                }
            ]
        }
    }
});
</script>
<!-- Add "scoped" attribute to limit CSS to this component only -->

<style scoped lang="scss">

</style>
