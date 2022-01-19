<template >
    <Header app-name="Hot Notes" v-on:remove-all="deleteAll"/>
    <div class="container w-full md:px-40 mx-auto py-20">
        <div class="md:grid lg:grid-cols-3 md:grid-cols-2 mlg:grid-cols-3 md:gap-10 space-y-6 md:space-y-0 px-10 md:px-0 mx-auto">
            <Card @remove-note="deleteNote(index)" v-for="(note,index) in notes" :key="index"
                  v-bind:note-title="note.title"
                  v-bind:note-content="note.content"/>
        </div>
    </div>
    <Footer/>

</template>

<script>
    import Header from "./Header";
    import Card from "./Card";
    import Footer from "./Footer";
    // import Container from "./Container";
    export default {
        name: "Home",
        components: {
            // Container,
            Footer,
            Card,
            Header
        },
        data() {
            return {
                notes: [
                    { title: "Beez", content: "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed viverra dui a turpis tempus, sed blandit odio elementum. Nullam euismod sagittis turpis a tristique. Quisque tincidunt lorem diam, eget consequat elit pulvinar a." },
                    { title: "Beezy", content: "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed viverra dui a turpis tempus, sed blandit odio elementum. Nullam euismod sagittis turpis a tristique. Quisque tincidunt lorem diam, eget consequat elit pulvinar a." },
                    { title: "Beezer", content: "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed viverra dui a turpis tempus, sed blandit odio elementum. Nullam euismod sagittis turpis a tristique. Quisque tincidunt lorem diam, eget consequat elit pulvinar a." },
                    { title: "Beezest", content: "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed viverra dui a turpis tempus, sed blandit odio elementum. Nullam euismod sagittis turpis a tristique. Quisque tincidunt lorem diam, eget consequat elit pulvinar a." },
                ]
            }
        },
        methods: {
            deleteAll(){
                this.notes = [];
            },
            deleteNote(index){
                this.notes.splice(index, 1);
            }
        },
    }
</script>