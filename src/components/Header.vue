<template>
    <div class="w-full bg- bg-gradient-to-tr from-indigo-600 to-purple-600 py-6 flex px-3 md:px-20 xl:px-60">
        <div class="w-full">
            <div class="float-left">
                <h1 class="text-white text-2xl font-semibold">{{appName}}</h1>
            </div>

            <div class="flex items-center space-x-10 float-right">
                <Button>New Note</Button>
                <Button v-on:click="$emit('remove-all')">Finish All</Button>
            </div>
        </div>

    </div>
</template>

<script>
    import Button from "./Button";
    export default {
        name: "Header",
        components: {
            Button
        },
        props: ['appName']
    }
</script>

<style scoped>

</style>