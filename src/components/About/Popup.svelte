<script lang="ts">
  import type { Project } from '../../types/project';
  import Icon from '../Icon.svelte';
  import Github from '../../icons/Github.svelte';

  export let content: string | null = null;
  export let projects: Project[] = [];
</script>

<div class="ps-popup">
  <h2 class="ps-popup__title">{content} projects</h2>
  <ul class="ps-popup__list">
    {#each projects as project}
      <li class="ps-popup__item">
        <div class="ps-popup__item-content">
          <div class="ps-popup__item-names"> 
            <span class="ps-popup__item-name">{project.title}</span>
            <span class="ps-popup__item-year">{project.year}</span>
          </div>
          <hr>
          <div class="ps-popup__item-btn">
            <a href={project.github} target="_blank" rel="noopener noreferrer" class="ps-popup__github">
              <Icon name="github" width={30} height={30}>
                <Github />
              </Icon>
            </a>
            <a href={project.url} target="_blank" rel="noopener noreferrer" class="ps-popup__live">Live!</a>
          </div>
        </div>
      </li>
    {/each}
  </ul>
</div>

<style>
  .ps-popup {
    text-align: center;
    background-color: #fdf5e6; 
    padding: 20px;
    border-radius: 15px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
    font-family: 'Courier New', Courier, monospace; 
    color: #4a4a4a;
    max-height: 500px;
    overflow-y: auto;
  }
  .ps-popup__title {
    font-size: 1.8rem;
    margin-bottom: 1rem;
    text-transform: uppercase;
    color: #d2691e; 
  }
  .ps-popup__list {
    list-style-type: none;
    padding: 0;
  }
  .ps-popup__item {
    margin: 10px 0;
    font-size: 1.2rem;
    text-align: left;
  }
  .ps-popup__item-content {
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-direction: column;
    background-color: #f5f5dc;
    border-radius: 15px;
    padding: 10px;
    border: 2px solid #d2691e;
    box-shadow: inset 2px 2px 4px rgba(0, 0, 0, 0.1), 
                inset -2px -2px 4px rgba(255, 255, 255, 0.7);
  }
  .ps-popup__item-names {
    display: flex;
    justify-content: flex-start;
    gap: 10px;
    width: 100%;
  }
  .ps-popup__item-btn {
    display: flex;
    align-items: center;
    justify-content: flex-end;
    font-size: 1rem;
    margin-left: auto;
    gap: 10px;
    padding-right: 10px;
  }
  .ps-popup__github,
  .ps-popup__live {
    text-decoration: none;
    color: #007acc;
    padding: 5px 10px;
    background-color: transparent;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
    transition: background-color 0.3s ease, color 0.3s ease;
  }
  .ps-popup__github {
    border-radius: 50%;
  }
  .ps-popup__live {
    border-radius: 5px;
  }
  .ps-popup__item-btn a:hover {
    background-color: #007acc;
    color: #fff;
  }
  .ps-popup a {
    text-decoration: none;
    color: #007acc; 
  }
  .ps-popup a:hover {
    text-decoration: underline;
    color: #ff4500; 
  }
  .ps-popup__item-name::before {
    content: "» "; 
    color: #ff4500; 
  }
  hr {
    border: 0;
    height: 1px;
    width: 100%;
    background-image: linear-gradient(to right, #ccc, #333, #ccc);
    margin: 10px auto;
  }
  .ps-popup__item-year {
    font-size: 0.8rem;
    color: #d2691e;
    position: relative;
    top: 0;
    left: 0;
  }
  .ps-popup__item-name {
    font-size: 1.3rem;
    color: #4a4a4a;
  }
</style>
