<template>
    <div>
        <div class="text-4xl font-bold">{{ post.title }}</div>
        <div>{{ post.body }}</div>
        <div class="italic mt-4">Author: <span class="text-red-500">{{ user.name }}</span></div>
    </div>
</template>

<script>


    export default{
        data() {
            return{
                post:[],
                user:{}
            };
        },
        methods:{
            fetchPost() {
                fetch(
                    `//jsonplaceholder.typicode.com/posts/${this.$route.params.id}`
                )
                .then(response => response.json())
                .then(data => (this.post=data))
                .then(() => {
                    fetch(
                        `//jsonplaceholder.typicode.com/users/${this.post.userId}`
                    )
                    .then(response => response.json())
                    .then(data => (this.post =data));
                });
            }
        },
        mounted() {
            this.fetchPost();
        }
    };
</script>