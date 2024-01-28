<script>
    import { onMount } from 'svelte';
    import DevProjects from './lib/Devprojects.ts';

    let projects = [];

    async function fetchProjects() {
        try {
            const response = await fetch('/api/projects');
            projects = await response.json();
        } catch (error) {
            console.error('Error fetching projects:', error);
            // Fallback to local projects
            projects = DevProjects;
        }
    }

    onMount(fetchProjects);
</script>

<!-- The rest of your component -->


<main>
    <h1>Projects</h1>

    <div class="grid">
        {#each projects as project (project.id)}
            <div class="project-card">
                <h2>{project.title}</h2>
                <p>{project.description}</p>
            </div>
        {/each}
    </div>
</main>

<style>
    .grid {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
        gap: 1rem;
    }

    .project-card {
        padding: 1rem;
        border: 1px solid #ccc;
        border-radius: 4px;
    }
</style>
