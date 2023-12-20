<!-- AddProjectForm.vue -->
<template>
    <div class="project-add">
        <div class="project-add-form">
            <h2>Ajouter un Projet</h2>
            <form @submit.prevent="submitForm">
                <input type="text" v-model="newProject.name" placeholder="Nom du projet" />
                <textarea v-model="newProject.description" placeholder="Description du projet"></textarea>
                <textarea v-model="newProject.author" placeholder="Auteur du projet"></textarea>
                <input type="date" v-model="newProject.startDate" placeholder="Date de début" />
                <button type="submit">Ajouter</button>
            </form>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            newProject: {
                name: '',
                description: '',
                author: '',
                startDate: '',
            }
        };
    },
    methods: {
        submitForm() {
            this.$emit('submit-project', this.newProject);
            this.newProject = {
                name: '',
                description: '',
                author: '',
                startDate: '',
            };
        }
    }
};
</script>

<style scoped>
h2 {
    color: #191919;
}

form {
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 100%;
}


input[type="text"],
textarea,
input[type="date"] {
    width: 100%;
    padding: 10px;
    margin-bottom: 10px;
    resize: none;
}

button[type="submit"] {
    background-color: #004BA8;
    color: white;
    padding: 10px 20px;
    border: none;
    cursor: pointer;
    border-radius: 5px;
    width: 100%;
}

.project-add {
    display: flex;
    flex-direction: column;
    align-items: center;
    height: 100%;
    width: 100%;
}

.project-add-form {
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 60%;
    background-color: #f2f2f2;
    border-radius: 15px;
    border: solid 1px #ccc;
    padding: 20px;
}

</style>
            
