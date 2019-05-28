<template>
    <div>
        <h1>
            {{ user.name }}
        </h1>
        <p>
            {{ user.username }}
        </p>
        <p>
            {{ user.email }}
        </p>
        <data>
            {{ user.created_at }}
        </data>


    </div>
</template>

<script>
    export default {
        name: "user",
        // middleware: 'guest'
    }
</script>

<style scoped>

</style>