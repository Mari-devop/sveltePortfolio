<script lang="ts">
  import { projects } from '../../configs/projects';
  import ArrowProject from '../../components/ArrowProjects.svelte';
  import Icon from '../../components/Icon.svelte';
  import Github from '../../icons/Github.svelte';
  import ArrowLeft from '../../icons/ArrowLeft.svelte';
  import ArrowRight from '../../icons/ArrowRight.svelte';
  import Switcher from '../../components/About/Switcher.svelte';
  import React from '../../icons/React.svelte';
  import Svelte from '../../icons/Svelte.svelte';
  import Html from '../../icons/Html.svelte';
  import Css from '../../icons/Css.svelte';
  import Sass from '../../icons/Sass.svelte';
  import Bootstrap from '../../icons/Bootstrap.svelte';
  import Tailwind from '../../icons/Tailwind.svelte';
  import Mui from '../../icons/Mui.svelte';
  import JS from '../../icons/JS.svelte';

  let toggledItem: string | null = null;
  let currentProjectIndex = 0;

  const handleToggle = (event: CustomEvent<{ name: string; isToggled: boolean }>) => {
    toggledItem = event.detail.isToggled ? event.detail.name : null;
    currentProjectIndex = 0;
  };

  $: filteredProjects = toggledItem
    ? projects.filter(project => project.switcher === toggledItem)
    : projects;

  const prevProject = () => {
    if (filteredProjects.length > 0) {
      currentProjectIndex = (currentProjectIndex - 1 + filteredProjects.length) % filteredProjects.length;
      console.log('Updated Index:', currentProjectIndex);
    }
  };

  const nextProject = () => {
    if (filteredProjects.length > 0) {
      currentProjectIndex = (currentProjectIndex + 1) % filteredProjects.length;
      console.log('Updated Index:', currentProjectIndex);
    }
  };
</script>

<div class="ps-project-page">
  <ArrowProject />
  <div class="ps-project-page__grid">
    <div class="ps-project-page__grid-content">
      <div class="ps-project-page__arrow-btns">
        <button on:click={prevProject}>
          <Icon name="arrowLeft" width={30} height={30}>
            <ArrowLeft />
          </Icon>
        </button>
        <button on:click={nextProject}>
          <Icon name="arrowRight" width={30} height={30}>
            <ArrowRight />
          </Icon>
        </button>
      </div>
      <div class="ps-project-page__projects">
        {#if filteredProjects.length > 0}
          <div class="ps-project-page__item">
            <div class="ps-project-page__item-image">
              <img src={filteredProjects[currentProjectIndex].image} alt={filteredProjects[currentProjectIndex].title} />
            </div>
            <div class="ps-project-page__item-text">
              <h2>{filteredProjects[currentProjectIndex].title}</h2>
              <p>{filteredProjects[currentProjectIndex].description}</p>
              <div class="ps-project-page__item-links">
                <a href={filteredProjects[currentProjectIndex].url} target="_blank">Live!</a>
                <a href={filteredProjects[currentProjectIndex].github} target="_blank" rel="noopener noreferrer" class="ps-popup__github">
                  <Icon name="github" width={40} height={40}>
                    <Github />
                  </Icon>
                </a>
              </div>
            </div>
          </div>
        {:else}
          <p>No projects available</p>
        {/if}
      </div>
    </div>
    <div class="ps-project-page__grid-buttons">
      <div class="ps-project-page__stack-btns">
        <div class="ps-stack__icon-item js">
          <Switcher name="JS" icon={JS} toggledClass="is-toggled-js" isToggleable={true} toggled={toggledItem === 'JS'} on:toggle={handleToggle} />
        </div>
        <div class="ps-stack__icon-item svelte">
          <Switcher name="Svelte" icon={Svelte} toggledClass="is-toggled-svelte" isToggleable={true} toggled={toggledItem === 'Svelte'} on:toggle={handleToggle} />
        </div>
        <div class="ps-stack__icon-item react">
          <Switcher name="React" icon={React} toggledClass="is-toggled-react" isToggleable={true} toggled={toggledItem === 'React'} on:toggle={handleToggle} />
        </div>
        <div class="ps-stack__icon-item html">
          <Switcher name="HTML" icon={Html} toggledClass="is-toggled-html" isToggleable={true} toggled={toggledItem === 'HTML'} on:toggle={handleToggle} />
        </div>
      </div>
      <div class="ps-project-page__styles-btns">
        <div class="ps-stack__icon-item css">
          <Switcher name="CSS" icon={Css} toggledClass="is-toggled-css" isToggleable={true} toggled={toggledItem === 'CSS'} on:toggle={handleToggle} />
        </div>
        <div class="ps-stack__icon-item sass">
          <Switcher name="Sass" icon={Sass} toggledClass="is-toggled-sass" isToggleable={true} toggled={toggledItem === 'Sass'} on:toggle={handleToggle} />
        </div>
        <div class="ps-stack__icon-item bootstrap">
          <Switcher name="Bootstrap" icon={Bootstrap} toggledClass="is-toggled-bootstrap" isToggleable={true} toggled={toggledItem === 'Bootstrap'} on:toggle={handleToggle} />
        </div>
        <div class="ps-stack__icon-item tailwind">
          <Switcher name="Tailwind" icon={Tailwind} toggledClass="is-toggled-tailwind" isToggleable={true} toggled={toggledItem === 'Tailwind'} on:toggle={handleToggle} />
        </div>
        <div class="ps-stack__icon-item mui">
          <Switcher name="MUI" icon={Mui} toggledClass="is-toggled-mui" isToggleable={true} toggled={toggledItem === 'MUI'} on:toggle={handleToggle} />
        </div>
      </div>
    </div>
  </div>
</div>

<style>
  .ps-project-page {
    padding: 1vw 7vw;
    font-family: 'Courier New', Courier, monospace;
    color: #333;
    height: 100vh;
  }

  .ps-project-page__grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    grid-template-rows: repeat(1, auto);
    gap: 1vw;
    height: fit-content;
    background-color: #f5f5dc;
    border-radius: 10px;
    padding: 2vw;
    margin: 1vw;
  }

  .ps-project-page__grid-content {
    grid-column: 1;
  }

  .ps-project-page__grid-buttons {
    grid-column: 2;
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    flex-wrap: wrap;
    gap: 3vw;
    margin: 1vw;
  }

  .ps-project-page__stack-btns,
  .ps-project-page__styles-btns {
    display: flex;
    flex-direction: column;
    gap: 1vw;
  }

  .ps-project-page__arrow-btns {
    display: flex;
    justify-content: space-between;
    margin-bottom: 2vw;
  }

  .ps-project-page__arrow-btns button {
    background-color: #fff8dc;
    border: 2px solid #8b4513;
    border-radius: 50%;
    padding: 0.5vw;
    cursor: pointer;
    transition: background-color 0.3s, transform 0.3s;
  }

  .ps-project-page__arrow-btns button:hover {
    background-color: #d2691e;
    transform: scale(1.1);
  }

  .ps-project-page__projects {
    display: flex;
    flex-direction: column;
    gap: 1vw;
  }

  .ps-project-page__item {
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    background-color: #fff8dc;
    padding: 1vw;
    border-radius: 10px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
    border: 2px solid #8b4513;
    width: 100%;
    box-sizing: border-box;
  }

  .ps-project-page__item h2 {
    color: #8b4513;
    font-size: 1.5em;
    margin-bottom: 0.5vw;
  }

  .ps-project-page__item p {
    color: #333;
    font-size: 1em;
  }

  .ps-project-page__item-links {
    display: flex;
    gap: 1vw;
    margin-top: 1vw;
  }

  .ps-project-page__item-links a {
    color: #8b4513;
    text-decoration: none;
    border: 2px solid #8b4513;
    padding: 0 0.5vw;
    display: flex;
    justify-content: center;
    align-items: center;
    border-radius: 5px;
    transition: background-color 0.3s, color 0.3s;
  }

  .ps-project-page__item-links a:hover {
    background-color: #8b4513;
    color: #fff;
  }

  .ps-project-page__item-image {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 350px;
    width: 50%;
    overflow: hidden;
    border-radius: 10px;
    border: 2px solid #8b4513;
    margin-right: 1vw;
  }

  .ps-project-page__item-image img {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }

  .ps-project-page__item-text {
    display: flex;
    flex-direction: column;
    width: 50%;
    margin-left: 1vw;
  }

  .ps-stack__icon-item {
    background-color: #ffebcd;
    border-radius: 50px;
    width: 140px;
    padding: 7px;
    box-shadow: rgba(0, 0, 0, 0.4) 0px 2px 4px, rgba(0, 0, 0, 0.3) 0px 7px 13px -3px, rgba(104, 85, 45, 0.2) 0px -3px 0px inset;
    transition: background-color 0.3s, transform 0.3s;
  }

  .ps-stack__icon-item:hover {
    background-color: #f08080;
    transform: scale(1.1);
  }

  .ps-stack__icon-item.js,
  .ps-stack__icon-item.svelte,
  .ps-stack__icon-item.react,
  .ps-stack__icon-item.html,
  .ps-stack__icon-item.css,
  .ps-stack__icon-item.sass,
  .ps-stack__icon-item.bootstrap,
  .ps-stack__icon-item.tailwind, 
  .ps-stack__icon-item.mui {
    background-color: #ffebcd;
  }

  @media screen and (max-width: 1200px) {
    .ps-project-page__item {
      flex-direction: column;
      gap: 1vw;
    }
    .ps-project-page__item-text {
      width: 100%;
      padding: 1vw;
    }
    .ps-project-page__item-image {
      width: 100%;
      margin: 0;
    }
  }

  @media screen and (max-width: 1000px) {
    .ps-project-page {
      padding: 3vw 3vw;
    }

    .ps-project-page__grid {
      flex-direction: column;
      grid-template-columns: 1fr;
      grid-template-rows: repeat(2, auto);
    }

    .ps-project-page__grid-buttons {
      grid-column: 1;
      grid-row: 1;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      gap: 3vw;
      margin: 1vw;
    }

    .ps-project-page__stack-btns,
    .ps-project-page__styles-btns {
      display: flex;
      flex-direction: row;
      gap: 1vw;
    }

    .ps-project-page__grid-content {
      grid-column: 1;
      grid-row: 2;
      width: 100%;
    }

    .ps-project-page__item {
      flex-direction: column;
      gap: 1vw;
      width: 100%;
    }

    .ps-project-page__item-image {
      width: 100%;
      height: auto;
    }

    .ps-project-page__item-text {
      width: 100%;
    }

    .ps-project-page__grid-buttons {
      width: 100%;
    }

    .ps-project-page__stack-btns, .ps-project-page__styles-btns {
      width: 100%;
      justify-content: center;
    }

    .ps-stack__icon-item {
      width: auto;
      padding: 5px;
    }
  }
  @media screen and (max-width: 420px) {
  .ps-project-page__grid {
    padding: 1vw;
    gap: 0.5vw;
  }

  .ps-project-page__grid-buttons {
    flex-direction: column;
    gap: 1vw;
  }

  .ps-stack__icon-item {
    width: 100%;
    padding: 3px;
    font-size: 0.8em;
  }

  .ps-project-page__item {
    padding: 0.5vw;
  }

  .ps-project-page__arrow-btns button {
    padding: 0.3vw;
    font-size: 0.8em;
  }

  .ps-project-page__item h2 {
    font-size: 1.2em;
  }

  .ps-project-page__item p {
    font-size: 0.9em;
  }

  .ps-project-page__item-links a {
    padding: 0 0.3vw;
    font-size: 0.8em;
  }

  .ps-project-page__item-image {
    height: 200px;
    margin-right: 0.5vw;
  }
}
  @media screen and (max-width: 385px) {
  .ps-project-page__grid-buttons {
    flex-direction: row;
    gap: 10vw;
  }
  .ps-project-page__stack-btns {
    flex-direction: column;
    width: 30%;
  }
  .ps-project-page__styles-btns {
    flex-direction: column;
    width: 30%;
  }

  
}
</style>
