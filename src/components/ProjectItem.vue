<!-- ProjectItem.vue -->
<template>
    <div class="porject-item-list">
        <div v-if="project" class="project-item">
            <h2 class="project-title">Détails du Projet</h2>
            <div class="project-detail">
                <h3>Project name : {{ project.name }}</h3>
                <p>Discription du project : {{ project.description }}</p>
                <p>Auteur du project : {{ project.author }}</p>
                <p>Date de début : {{ project.startDate }}</p>
            </div>
            <!-- Autres détails du projet -->
        </div>
    </div>
</template>

<script>
export default {
    props: ['project']
};
</script>

<style scoped>
.porject-item-list {
    display: flex;
    flex-direction: column;
    align-items: center;
}
.project-item {
    display: flex;
    flex-direction: column;
    background-color: #f2f2f2;
    border: solid 1px #ccc;
    align-items: center;
    padding: 20px;
    border-radius: 5px;
    margin-bottom: 10px;
    width: 90%;
    text-align: justify;
}

.project-title {
    color: #333;
    font-size: 24px;
    margin-bottom: 10px;
}

.project-detail {
    display: grid;
    grid-template-columns: 1fr 2;
    grid-gap: 10px;
}

.project-detail p {
    text-align: justify;
}
</style>
