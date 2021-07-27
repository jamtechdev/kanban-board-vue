<template>
<div>
    <div v-for="(record, index) in records" :key="index">
        <article class="card" v-if="statusId === record.cardId">
            <div class="action-icon">
                <img @click="showDelBtn(index)" src="https://image.flaticon.com/icons/png/512/512/512142.png">
                <div class="action-div" v-if="record.del">
                    <p @click="deleteRecord(index)">Delete</p>
                </div>
            </div>
            <figure class="card-image">
                <img src="https://images.unsplash.com/photo-1494253109108-2e30c049369b?crop=entropy&cs=srgb&fm=jpg&ixid=MnwxNDU4OXwwfDF8cmFuZG9tfHx8fHx8fHx8MTYyNDcwMTUwOQ&ixlib=rb-1.2.1&q=85" alt="An orange painted blue, cut in half laying on a blue background" />
                <div class="img-content">
                    <h5 class="label">{{record.tag}}</h5>
                    <div class="card-meta-date">
                        <img src="https://image.flaticon.com/icons/png/512/992/992700.png">
                        2 days left
                    </div>
                    <p class="price">2 Hrs | <b>${{record.price}}</b></p>
                </div>
            </figure>
            <div class="card-footer">
                <div class="view-order">
                    <h6>{{record.name}}</h6>
                </div>
                <div class="icon-user">
                    <img src="https://image.flaticon.com/icons/png/512/589/589671.png">
                    <img src="https://assets.webiconspng.com/uploads/2016/12/User-Icon.png">
                </div>
            </div>
        </article>
    </div>
</div>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
    name: 'Card',
    props: {
        statusId: Number
    },
    data() {
        return {
            isShow: false,
            records: [{
                    name: "New Order 1",
                    tag: 'New ORDER',
                    price: 100,
                    status: 1,
                    cardId: 1,
                    del: 0
                },
                {
                    name: "New Order 2",
                    tag: 'New ORDER',
                    price: 300,
                    status: 1,
                    cardId: 1,
                    del: 0
                },
                {
                    name: "New Order 3",
                    tag: 'New ORDER',
                    price: 200,
                    status: 1,
                    cardId: 1,
                    del: 0
                },
                {
                    name: "New Order 4",
                    tag: 'New ORDER',
                    price: 400,
                    status: 1,
                    cardId: 1,
                    del: 0
                },
                {
                    name: "In process 1",
                    tag: 'IN PROGRESS',
                    price: 400,
                    status: 1,
                    cardId: 2,
                    del: 0
                },
                {
                    name: "In process 2",
                    tag: 'IN PROGRESS',
                    price: 320,
                    status: 1,
                    cardId: 2,
                    del: 0
                },
                {
                    name: "Waiting 1",
                    tag: 'WAITING',
                    price: 10,
                    status: 1,
                    cardId: 3,
                    del: 0
                }, {
                    name: "Waiting 2",
                    tag: 'WAITING',
                    price: 130,
                    status: 1,
                    cardId: 3,
                    del: 0
                }, {
                    name: "Waiting 2",
                    tag: 'WAITING',
                     price: 530,
                    status: 1,
                    cardId: 3,
                    del: 0
                },
                {
                    name: "Completed 1",
                    tag: 'COMPLETED',
                     price: 530,
                    status: 1,
                    cardId: 4,
                    del: 0
                },
                {
                    name: "Completed 2",
                    tag: 'COMPLETED',
                     price: 330,
                    status: 1,
                    cardId: 4,
                    del: 0
                }
            ]
        }
    },
    methods: {
        showDelBtn(index: Number) {
            this.records.forEach((d, i) => {
                if (i === index) {
                    d.del = 1
                    return
                }
            })
        },
        deleteRecord(index: number) {
            if (confirm("Do you really want to delete the record ?")) {
                this.records.splice(index, 1);
                return
            }
            this.records.forEach((d, i) => {
                if (i === index) {
                    d.del = 0
                    return
                }
            })
        }
    }
})
</script>
