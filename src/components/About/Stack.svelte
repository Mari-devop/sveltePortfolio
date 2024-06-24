<script lang="ts">
  import Switcher from '../About/Switcher.svelte'; 
  import React from '../../icons/React.svelte';
  import Svelte from '../../icons/Svelte.svelte';
  import Html from '../../icons/Html.svelte';
  import Css from '../../icons/Css.svelte';
  import Sass from '../../icons/Sass.svelte'; 
  import Bootstrap from '../../icons/Bootstrap.svelte';
  import Tailwind from '../../icons/Tailwind.svelte';
  import Mui from '../../icons/Mui.svelte';
  import JS from '../../icons/JS.svelte';
  import Popup from "../About/Popup.svelte";
  import type { Project } from '../../types/project';
  import { projects } from '../../configs/projects';

  let showModal = false;
  let modalContent: string | null = null;
  let toggledItem: string | null = null;

  interface ToggleEventDetail {
    name: string;
    isToggled: boolean;
  };

  function handleToggle(event: CustomEvent<ToggleEventDetail>) {
    console.log(`${event.detail.name} is toggled: ${event.detail.isToggled}`);
    showModal = event.detail.isToggled;
    modalContent = event.detail.isToggled ? event.detail.name : null;
    toggledItem = event.detail.isToggled ? event.detail.name : null;
  };

  function closeModal() {
    showModal = false;
    modalContent = null;
    toggledItem = null;
  };

  function getFilteredProjects(switcher: string): Project[] {
    return projects.filter(project => project.switcher === switcher);
  };
</script>

<div class="ps-stack">
  <div class="ps-stack__container">
    <span class="ps-stack__span-join">Joined 22 Aug 2022</span>
    <p class="ps-stack__title">Things I code with</p>
    <div class="ps-stack__icon-container">
      <div class="ps-stack__icon-item js">
        <Switcher name="JS" icon={JS} toggledClass="is-toggled-js" isToggleable={true} toggled={toggledItem === 'JS'} on:toggle={handleToggle}>
          <JS />
        </Switcher>
      </div> 
      <div class="ps-stack__icon-item svelte">
        <Switcher name="Svelte" icon={Svelte} toggledClass="is-toggled-svelte" isToggleable={false} toggled={toggledItem === 'Svelte'} on:toggle={handleToggle}>
          <Svelte />
        </Switcher>
      </div>
      <div class="ps-stack__icon-item react">
        <Switcher name="React" icon={React} toggledClass="is-toggled-react" isToggleable={true} toggled={toggledItem === 'React'} on:toggle={handleToggle}>
          <React />
        </Switcher>
      </div>
      <div class="ps-stack__icon-item html">
        <Switcher name="HTML" icon={Html} toggledClass="is-toggled-html" isToggleable={true} toggled={toggledItem === 'HTML'} on:toggle={handleToggle}>
          <Html />
        </Switcher>
      </div>
      <div class="ps-stack__icon-item css">
        <Switcher name="CSS" icon={Css} toggledClass="is-toggled-css" isToggleable={true} toggled={toggledItem === 'CSS'} on:toggle={handleToggle}>
          <Css />
        </Switcher>
      </div>
      <div class="ps-stack__icon-item sass">
        <Switcher name="Sass" icon={Sass} toggledClass="is-toggled-sass" isToggleable={false} toggled={toggledItem === 'Sass'} on:toggle={handleToggle}>
          <Sass />
        </Switcher>
      </div>
      <div class="ps-stack__icon-item bootstrap">
        <Switcher name="Bootstrap" icon={Bootstrap} toggledClass="is-toggled-bootstrap" isToggleable={false} toggled={toggledItem === 'Bootstrap'} on:toggle={handleToggle}>
          <Bootstrap />
        </Switcher>
      </div>
      <div class="ps-stack__icon-item tailwind">
        <Switcher name="Tailwind" icon={Tailwind} toggledClass="is-toggled-tailwind" isToggleable={false} toggled={toggledItem === 'Tailwind'} on:toggle={handleToggle}>
          <Tailwind />
        </Switcher>
      </div>
      <div class="ps-stack__icon-item mui">
        <Switcher name="MUI" icon={Mui} toggledClass="is-toggled-mui" isToggleable={false} toggled={toggledItem === 'MUI'} on:toggle={handleToggle}>
          <Mui />
        </Switcher>
      </div>
    </div>
  </div>

  {#if showModal && modalContent}
    <div class="modal-overlay" on:click={closeModal}>
      <div class="modal-content" on:click|stopPropagation>
        <button class="modal-close" on:click={closeModal}>✖</button>
        <Popup content={modalContent} projects={getFilteredProjects(modalContent)} />
      </div>
    </div>
  {/if}
</div>

<style>
  .ps-stack__container {
    position: relative;
    width: 100%;
    height: 300px; 
    padding: 20px;
    border-radius: 20px;
    background-color: #f5f5dc; 
    box-shadow: rgba(104, 85, 45, 0.25) 0px 30px 60px -12px inset,
                rgba(45, 35, 20, 0.3) 0px 18px 36px -18px inset; 
  }
  .ps-stack__span-join {
    display: flex;
    align-items: center;
    justify-content: flex-end;
    font-size: 1rem;
    margin-left: auto;
    gap: 10px;
    padding-right: 20px;
    color: #4a4a4a;
  }
  .ps-stack__title {
    font-size: 1.4rem;
    word-wrap: break-word;
    margin-top: 4vw;
    font-family: 'Courier New', Courier, monospace;
    color: #4a4a4a;
    font-weight: bold;
    width: 130px;
    text-transform: uppercase;
  }
  .ps-stack__icon-container {
    position: absolute;
    top: 60%;
    right: -3%;
    display: flex;
    flex-wrap: wrap;
    justify-content: flex-end;
    align-items: flex-end;
    width: 300px; 
    height: 100%;
  }
  .ps-stack__icon-item {
    position: absolute;
    background-color: #e0e6e3;
    border-radius: 50px;
    padding: 7px;
    box-shadow: rgba(69, 69, 69, 0.4) 0px 2px 4px,
                rgba(69, 69, 69, 0.3) 0px 7px 13px -3px,
                rgba(104, 85, 45, 0.2) 0px -3px 0px inset; 
    transition: background-color 0.3s, transform 0.3s;
  }
  .ps-stack__icon-item:hover {
    background-color: #f08080; 
    transform: scale(1.1);
  }
  .ps-stack__icon-item.js { width: 140px; transform: translate(0px, -20px) rotate(-20deg); }
  .ps-stack__icon-item.svelte { width: 70px; transform: translate(-85px, -80px) rotate(-35deg); }
  .ps-stack__icon-item.react { width: 140px; transform: translate(5px, -130px) rotate(45deg); }
  .ps-stack__icon-item.html { width: 140px; transform: translate(-155px, -20px) rotate(30deg); }
  .ps-stack__icon-item.css { width: 140px; transform: translate(-190px, -130px) rotate(-45deg); }
  .ps-stack__icon-item.sass { width: 70px; transform: translate(-315px, -75px) rotate(-20deg); }
  .ps-stack__icon-item.bootstrap { width: 70px; transform: translate(-4px, -210px) rotate(15deg); }
  .ps-stack__icon-item.tailwind { width: 70px; transform: translate(-285px, -5px) rotate(-25deg); }
  .ps-stack__icon-item.mui { width: 70px; transform: translate(-160px, -90px) rotate(25deg); }
  .modal-overlay {
    position: fixed;
    top: 0;
    left: 0;
    width: 100vw;
    height: 100vh;
    background-color: rgba(0, 0, 0, 0.5);
    display: flex;
    justify-content: center;
    align-items: center;
    z-index: 10;
  }
  .modal-content {
    background-color: #fff;
    padding: 20px;
    border-radius: 10px;
    box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.2);
    position: relative;
    width: 80%;
    max-width: 500px;
  }
  .modal-close {
    position: absolute;
    top: 5px;
    right: 8px;
    background: none;
    border: none;
    font-size: 1.5rem;
    cursor: pointer;
  }

  @media (max-width: 1415px) {
    .ps-stack__icon-item.tailwind { width: 70px; transform: translate(-125px, -150px) rotate(-25deg); }
    .ps-stack__icon-item.sass { width: 70px; transform: translate(-125px, -220px) rotate(-20deg); }
  }
  @media (max-width: 1200px) {
    .ps-stack__icon-container {
      right: 0;
    }
    .ps-stack__icon-item.sass { width: 70px; transform: translate(-315px, -75px) rotate(-20deg); }
    .ps-stack__icon-item.tailwind { width: 70px; transform: translate(-285px, -5px) rotate(-25deg); }
  }
  @media (max-width: 530px) {
    .ps-stack__icon-container {
      top: 0;
    }
    .ps-stack__span-join {
      display: none;
    }
    .ps-stack__title {
      margin-top: 0;
      font-size: 1.2rem;
    }
  }
</style>