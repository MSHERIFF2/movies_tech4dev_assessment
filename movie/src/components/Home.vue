<template>
    <div class="content-card">

        <div v-for="movie in movies" :key="movie.id" class="card">
            <img :src="movie.big_image" alt="">
            <div class="card-details">
                <h2>{{ movie.title }}</h2>
                <p class="desc">{{ movie.description }}</p>
                <h3>Year: {{ movie.year }}</h3>                
                <p>Rating:{{ movie.rating }}</p>
                <h3>Type:{{ movie.genre[0] }}</h3>
                <a :href=movie.imdb_link>view movie</a>

            </div>



        </div>
    </div>
</template>
<style scoped>
.content-card {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-evenly;
}

.card img {
    width: 250px;
    height: 270px;
    border-top-left-radius: 20px;
    border-top-right-radius: 20px;
}

.card {
    width: 250px;
    height: fit-content;
    border-radius: 20px;
    box-shadow: 1px 1px 2px rgba(237, 235, 232 0.5);
    background-color: rgb(237, 235, 232);
    margin: 15px;
}
.card-details{
    margin-left:6px;
    display: flex;
    flex-wrap: wrap;
    justify-content: space-evenly;
   align-items: center;
}
a{
    text-decoration: none;
    text-align: center;
    border-radius: 10px;
    background-color: maroon;
    color: white;
    cursor: pointer;
    padding: 2px;
    font-size: 16px;
    align-items: center;
}
h2{
    text-align: center;
    font-size: 18px;
    padding: 6px
}
p{
    text-align: justify;
    padding: 6px;
}
.desc {
    margin-top: 5px;
}

</style>
<script>
export default {
    data() {
        return {
            movies: [],
            msg: "welcome to my movie app"
        }
    },
    mounted() {
        const url = 'https://imdb-top-100-movies.p.rapidapi.com/';
        const options = {
            method: 'GET',
            headers: {
                'x-rapidapi-key': '863484ebcemshc460581adcc431ap17bb03jsn237f80b8ad76',
                'x-rapidapi-host': 'imdb-top-100-movies.p.rapidapi.com'
            }
        };


        fetch(url, options)
            .then(res => res.json())
            .then(data => this.movies = data)
            .catch((error) => console.error(error))

    }

}

</script>