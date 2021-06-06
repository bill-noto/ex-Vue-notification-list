<template>
    <div @click="view" v-for="(item, index) in notificationList" v-bind:key="index">
        <h1>{{item.title}}</h1>
        <h2>{{item.description}}</h2>
    </div>
</template>

<script>

export default {
    name: 'list',
    props: {
        notificationList: Object
    },
    methods: {
        view(){
            var ele = document.getElementsByTagName('div');
            if (this.notificationList.status == false) {
                ele.style.opacity = 0.5;
            }
        }
    }
}
</script>