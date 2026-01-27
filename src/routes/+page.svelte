<!-- <script lang="ts">
  import { onMount } from 'svelte';
  
  let cam: HTMLCanvasElement | null = null;
  
  onMount(() => {
    // TypeScript knows canvas could be null, so we need to check
    if (!cam) return;
    
    const ctx = cam.getContext('2d');
    if (!ctx) return;
    
    ctx.fillStyle = 'red';
    ctx.fillRect(0, 0, 350, 200);
  });
</script> Todo when you feel like implementing something cool on the website-->

<!-- <canvas bind:this={cam} width="350" height="200"></canvas> -->

<!-- <style>
  canvas {
    width: 350px;
    height: 200px;
    border: 2px solid black;
  }
</style> CONT from CANVAS -->

<script lang="ts">
  import me from '$lib/assets/me.jpg';

const skills = [
  'C/C++',
  'Python',
  'Git/GitHub',
  'Linux/Windows',
  'Godot',
  'Unity',
  'CMake',
  'GDB',
  'Valgrind',
  'VSCode',
  'Blender3D',
  'Davinci Resolve'
];

const interests = [
  'Mathematics',
  'Blender 3D',
  'Drawing',
  'Church History/Theology',
  'Food',
  'Coding',
  'Linux',
  'Computer Graphics',
  'Computer Parts', 
  'Indie Games'
];
</script>

<header class="profile-section">
<div class="avatar-container">
  <img src={me} alt="Ty Torres" class="avatar-photo" />
</div>

  <div class="profile-details">
    <h1>Ty Torres</h1>
    
    <div class="quick-facts">
      <div class="year">
        <span class="year-label">Year:</span>
        <span class="year-value">Sophomore at Columbia University</span>
      </div>
  
      <div class="fact">
        <span class="fact-label">Location:</span>
        <span class="fact-value">New York City, New York</span>
      </div>

      <div class="fact">
        <span class="fact-label">Major:</span>
        <span class="fact-value">Computer Science</span>
      </div>

      <div class="fact">
        <span class="fact-label">Goal:</span>
        <span class="fact-value">A career in Computer Graphics and to own a farm</span>
      </div>
    </div>
  </div>
  
  <!-- Bio Section -->
  <section class="bio-section">
    <h2>About Me</h2>
    <div class="bio-content">
      <p>
        Hello, I'm Ty a sophomore at Columbia University 
        studying CS. My interests pertain to a multitude
        of disciplines with my sights being keen on Computer
        Graphics, a cornerstone of Math, Physics, Computer
        Science, and Art. 
      </p>
      <p>I hope to bring all 4 subjects together to bring
        something one of a kind to the table. I am 
        interested in non-photorealistic rendering methods
        such as those seen from Arcane, Spider-Man: 
        Into the Spider-Verse, and Arc System Works.
      </p>
      <p>
      Currently, I am trying to teach myself the fundamentals
      of graphics programming (OpenGL and Cuda) as after a year I 
      have learned/taught myself a solid foundation in Linear Algebra, 
      Discrete Mathematics, Calculus, Physics, C++, and Blender.
      </p>
    </div>
  </section>
</header>
  

<!-- Skills Section -->
<section class="skills-section">
<h2>Skills & Technologies</h2>
<div class="skills-list">
    {#each skills as skill}
    <div class="skill-item-outer">
        <div class="skill-item-inner">{skill}</div>
    </div>
    {/each}
</div>
</section>

<!-- Interests Section -->
<section class="interests-section">
<h2>Interests & Hobbies</h2>
<div class="interests-list">
    {#each interests as interest}
    <div class="interest-item-outer">
      <div class="interest-item-inner">{interest}</div>
    </div>
    {/each}
</div>
</section>

<style>
  
/* Profile Section */
.profile-section {
  display: flex;
  gap: 5rem;
  align-items: center;
  margin-bottom: 3rem;
  padding: 2rem;
  background: #2e575b;
  border-radius: 10px;
} 

.avatar-container {
  flex-shrink: 0;
}

.avatar-photo {
  width: 240px;
  height: 240px;
  border-radius: 10%;
  object-fit: cover;
  border: 4px solid white;
  box-shadow: 0 4px 12px rgba(0,0,0,0.1);
}

.profile-details h1 {
  margin: 0 0 1.5rem 0;
  font-size: 3rem;
  color: var(--link);
}

.year {
  font-size: 1.5rem ;
  color: var(--link); 
  margin: 0 0 1rem 0;
}

.fact {
  color: var(--fg-1);
  margin: 1rem 0;
}

.bio-section h2 {
  font-size: 1.5rem;
  color:#1c7ed4;
}
.bio-section {
  margin-top: 2rem;
  max-width: 800px; 
}

.bio-content {
  line-height: 1.6; 
  font-size: 1.1rem;
}

.bio-content p {
  margin-bottom: 1.5rem; 
  text-align: justify;
  max-width: 70ch;
}

/* Interests */
.interests-section {
  padding-top: 2rem;
}
.interests-list {
  display: flex;
  flex-wrap: wrap;
  gap: 0.75rem;
}
.interest-item-outer {
  background: var(--bg-2);
  border-left-width: 0.25rem;
border-left-style: solid;
border-left-color: #00aacc;
color: var(--fg-1);
padding: 0.25rem;
transform: skew(20deg);
}
.interest-item-inner {
  color: var(--fg-1);
  padding: 0.5rem 1rem;
  transform: skew(-20deg);
}

/* Skills */
.skills-section {
  padding-top: 2rem;
}

.skills-list {
  display: flex;
  flex-wrap: wrap;
  gap: 0.75rem;  
}
.skill-item-outer {
  background: var(--bg-2);
  border-left-width: 0.25rem;
  border-left-style: solid;
  border-left-color: #00aacc;
  color: var(--fg-1);
  padding: 0.25rem;
  transform: skew(-20deg);
  transition: all 0.3s ease;
}

.skill-item-inner {
  color: var(--fg-1);
  padding: 0.5rem 1rem;
  transform: skew(20deg);
}
</style>