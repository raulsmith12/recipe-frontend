<template>
    <div class="main container-fluid position-relative card" v-if="recipe !== null">
        <div class="row">
            <div class="col-4">
                <img :src="recipe.img_url" :alt="recipe.name" :style="{width: '100%'}" />
            </div>
            <div class="col-8">
                <h1 class="display-4">{{ recipe.name }}</h1>
                <h3>{{ recipe.description }}</h3>
                <h4 class="h2">Ingredients</h4>
                <ul>
                    <li v-for="ingredient in recipe.ingredients" :key="ingredient.id" class="text-start">
                        {{ ingredient.measurement }}&nbsp;{{ ingredient.ingredient }}
                    </li>
                </ul>
                <h4 class="h2">Directions</h4>
                <ol>
                    <li v-for="direction in recipe.directions" :key="direction.id" class="text-start">
                        {{ direction.direction }}
                    </li>
                </ol>
            </div>
        </div>
    </div>
</template>

<script>
    import axios from "axios";

    export default {
        name: "RecipeSingle",
        data() {
            return {
                recipe: null,
            };
        },
        mounted() {
            axios
                .get("http://localhost:8000/api/recipes/" + this.$route.params.id)
                .then((response) => (this.recipe = response.data.data));
        },
    };
</script>
