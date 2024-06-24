<script>
  import { createEventDispatcher, onMount } from 'svelte';
  import { afterUpdate } from 'svelte';
  import Icon from "../Icon.svelte";
  
  /** @type {any} */
  export let icon;
  
  /** @type {string} */
  export let name;
  
  /** @type {string} */
  export let toggledClass = "";
  
  /** @type {string} */
  export let wrapperColor = "transparent"; 
  
  /** @type {boolean} */
  export let isToggleable = true;

  /** @type {boolean} */
  export let toggled = false;
  
  let isToggled = toggled;
  const dispatch = createEventDispatcher();

  onMount(() => {
    isToggled = toggled;
  });

  afterUpdate(() => {
    isToggled = toggled;
  });
  
  function handleClick() {
    if (isToggleable) {
      isToggled = !isToggled;
    }
    dispatch('toggle', { name, isToggled });
  };
</script>

<div class="ps-switch__container">
  <div class="ps-switch__wrapper" style="background-color: {wrapperColor}">
    <div class="switch {toggledClass}" on:click={handleClick} class:is-toggled={isToggled}>
      <Icon name={name} width={60} height={60}>
        {#if icon}
          <svelte:component this={icon} />
        {/if}
      </Icon>
    </div>
  </div>
</div>

<style>
  .ps-switch__container {
    position: relative;
    display: flex;
    align-items: center;
  }
  .ps-switch__wrapper {
    border-radius: 30px;
    width: 100%;
    padding: 2px;
    box-shadow: inset 5px 5px 10px rgba(0, 0, 0, 0.2),
                inset -5px -5px 10px rgba(255, 255, 255, 0.7);
  }
  .switch {
    width: 52px;
    height: 50px;
    background-color: #eaf6f1ae;
    border-radius: 30px;
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    transition: transform 0.3s ease, box-shadow 0.3s ease;
  }
  .switch.is-toggled {
    transform: translateX(68px);
  }

  @media screen and (max-width: 1000px) {
    .switch.is-toggled {
      transform: none;
    }
    .switch:active,
    .switch.is-toggled {
      box-shadow: inset 2px 2px 5px rgba(0, 0, 0, 0.426),
                  inset -2px -2px 5px rgba(255, 255, 255, 0.7);
    }
  }

  @media screen and (max-width: 385px) {
    .switch.is-toggled {
      transform: translateX(35px);
    }
  }
</style>
