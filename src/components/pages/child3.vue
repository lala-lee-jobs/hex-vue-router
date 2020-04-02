<template>
    <div>
        <img src="" class="card-img-top" alt="...">
        <div class="card-body">
            <h5 class="card-title">Card 3</h5>
            <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
            <a href="#" class="btn btn-primary">Go somewhere</a>
        </div>
    </div>
</template>
<script>
export default {
    data() {
        return {
            user: {
                picture: {},
            }
        };
    },
    created() {
        // console.log(this.$route.params.id);
        // this.$http.get('https://randomuser.me/api/').then(rs => {
        //     console.log(rs);
        // });
        const id = this.$route.params.id;
        fetch(`https://randomuser.me/api/`)
            .then(rs => rs.json())
            .then(rs => {
                console.log(rs);
                this.user = rs.results[0];
            });
    },
}
</script>
<style></style>