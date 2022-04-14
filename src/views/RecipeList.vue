<template>
    <div class="container-fluid">
        <h1 class="display-1">Raul's Favorite Recipes</h1>
        <div class="row justify-content-center">
            <div class="col-4" v-for="recipe in recipes" :key="recipe.id">
                <div class="card border border-primary">
                    <img :src="recipe.img_url" class="card-img-top" :alt="recipe.name" :style="{width: '75%', margin: '0 auto', display: 'block'}" />
                    <div class="card-body">
                        <a :href="'/recipes/' + recipe.id" class="h1">{{ recipe.name }}</a>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    import axios from "axios";

    export default {
        name: 'RecipeList',
        data() {
            return {
                recipes: null,
            };
        },
        mounted() {
            axios
                .get("http://localhost:8000/api/recipes")
                .then((response) => (this.recipes = response.data.data));
        },
    };
</script>
