<script lang="ts">
    const projects = [
        {name: 'UTAH computer graphics', href: '', img: '',  desc: ''},
        {name: 'CMU computer graphics', href: '', img: '',  desc: ''},
        {name: 'Image to Ascii', href: '', img: '',  desc: ''},
        {name: 'CPU based RayTracer', href: '', img: '', desc: ''}
    ]
</script>

<h1>Projects</h1>

<section class="project-section">
    {#each projects as project}
    <a href={project.href} class="project-banner" >
    <div class="project-item-outer">
        <div class="project-item-inner">
                {project.name}
                <p>
                    {project.desc}
                </p>
        </div>
    </div>
    </a>
    {/each}

</section>


<style>

/* Project Banner Section */
.project-section {
    display: flex;
    flex-direction: column;
    gap: 3rem;
}

.project-item-outer {
    background: #00aacc;
    opacity: 0.5;
    padding: 3rem;
    transform: skew(20deg);
    transition: all 0.3s ease;
    
}

.project-item-outer:hover {
    animation: jump 0.5s ease forwards;
    opacity: 1;
    transition: all 0.3s ease;
}

.project-item-inner {
    transform: skew(-20deg);
}

</style>