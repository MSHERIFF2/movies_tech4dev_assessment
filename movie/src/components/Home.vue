<template>
    <div class="content-card">
       
        <div v-for="movie in movies" :key="movie.id" class="card">
            <img :src=" movie.primaryImage" alt="">
            <h1>{{ movie.title }}</h1>
            <p>{{ movie.description}}</p>
            <h4>{{ movie.startYear }}</h4>
            <p>{{  movie.runtimeMinutes }}</p>
            <p>{{ movie.contentRating }}</p>
            <p>{{ movie.averageRating }}</p>
            <h5>{{  movie.numVotes }}</h5>
            <h6>{{ movie.type }}</h6>
            <a :href=movie.url>view movie</a>
        </div>
    </div>
</template>
<style scoped>
.content-card{
    display: flex;
    flex-wrap: wrap;
    justify-content: space-evenly;
}
.card img{
    width: 300px;
    height: 250px;
    border-top-left-radius: 20px;
    border-top-right-radius: 20px;
}
.card{
    width: 300px;
    height: fit-content;
    border-radius: 20px;
    box-shadow: 1px 1px 2px rgba(2345, 1345, 2222, 0.5);
    background-color: antiquewhite;
    margin: 15px;
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
        const url = 'https://imdb236.p.rapidapi.com/imdb/top250-movies';
        const options = {
            method: 'GET',
            headers: {
                'x-rapidapi-key': '863484ebcemshc460581adcc431ap17bb03jsn237f80b8ad76',
                'x-rapidapi-host': 'imdb236.p.rapidapi.com'
            }
        };


        fetch(url, options)
            .then(res => res.json())
            .then(data => this.movies = data)
            .catch((error) => console.error(error))
        
    }
    
}

</script>