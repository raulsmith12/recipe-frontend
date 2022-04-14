<template>
    <div class="container fluid">
        <h1 class="display-1">Recipe List</h1>
        <div class="row">
            <div class="col-4">
                <div class="card border border-primary">
                    <img src="" class="card-img-top" alt="Recipe Image" />
                    <div class="card-body">
                        <h3 class="h1">Recipe Name</h3>
                    </div>
                </div>
            </div>
            <div class="col-4">
                <div class="card bg-primary text-white p-2">
                    <h3 class="h1">Add Recipe</h3>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'RecipeList'
    }
</script>
