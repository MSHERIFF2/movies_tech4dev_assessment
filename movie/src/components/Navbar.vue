<template>
    <div class="navbar">
        <span>{{ logo }}</span>
        <h1>{{ hero }}</h1>
    </div>
  
</template>

<script>
export default {
    data() {
        return {
            logo: "CODESH-MOVIE",
            hero: "Welcome to the home of movie. We give the best and fantastic movies here."
        }
    }

}
</script>

<style scoped>
.navbar{
    display: flex;
    justify-content: space-around;
    background-color: rgb(107, 175, 183);
    background-image: url('../assets/mv_image.jpg');
    background-size: cover;
    align-items: center;
    padding: 12px;
    margin-top:0;
}
h1{
    height: 210px;
    width: 250px;
    padding:12px;
    color: white;
    font-size: 32px;
    /* border-radius: 20px; */
    box-shadow: 2px 2px 3px rgba(223, 334, 455, 0.5);
    text-align:center;

}
span{
    color: rgb(221, 237, 221);
    font-size: 32px;
    background-color: rgba(165, 42, 42, 0.524);
    font-weight: bolder;
    padding: 12px;
}
@media screen and (max-width: 420px) {
    .navbar{
        flex-direction: column;
    }
    
}
</style>