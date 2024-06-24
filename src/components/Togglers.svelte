<script lang="ts">
  import Switcher from '../components/About/Switcher.svelte'; 
  import React from '../icons/React.svelte';
  import Svelte from '../icons/Svelte.svelte';
  import Html from '../icons/Html.svelte';
  import Css from '../icons/Css.svelte';
  import Sass from '../icons/Sass.svelte'; 
  import Bootstrap from '../icons/Bootstrap.svelte';
  import Tailwind from '../icons/Tailwind.svelte';
  import Mui from '../icons/Mui.svelte';
  import JS from '../icons/JS.svelte';

  let toggledItem: string | null = null;
  let showModal = false;
  let modalContent: string | null = null;

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
</script>

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