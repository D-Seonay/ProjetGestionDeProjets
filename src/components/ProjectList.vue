<!-- ProjectList.vue -->
<template>
        <div class="project-list">
            <h2>Liste des Projets</h2>
            <ul>
                <li v-for="project in projects" :key="project.id" @click="selectProject(project)" class="project-item">
                    Project name : {{ project.name }}
                </li>
            </ul>
        </div>
    </template>
    
    <script>
    export default {
        props: ['projects'],
        methods: {
            selectProject(project) {
                this.$emit('select-project', project);
            }
        }
    };
    </script>
    
    <style scoped>

    h2 {
        color: #191919;
    }

    ul {
        width: 90%;
    }

    li {
        list-style: none;
    }

    .project-list {
        display: flex;
        flex-direction: column;
        margin-bottom: 10px;
        align-items: center;
    }

    .project-item {
        cursor: pointer;
        padding: 10px;
        margin-bottom: 5px;
        background-color: #f2f2f2;
        border-radius: 5px;
        border: solid 1px #ccc;
    }
    </style>
