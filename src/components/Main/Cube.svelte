<script>
    import Icon from '../Icon.svelte';  
    import React from '../../icons/React.svelte';
    import Svelte from '../../icons/Svelte.svelte';
    import Redux from '../../icons/Redux.svelte';
    import Html from '../../icons/Html.svelte';
    import Sass from '../../icons/Sass.svelte'; 
    import Tailwind from '../../icons/Tailwind.svelte';
</script>

<div class="stage-cube-cont">
    <div class="cubespinner">
      <div class="face1">
        <Icon name="svelte" width={60} height={60}><Svelte /></Icon>
      </div>
      <div class="face2">
        <Icon name="react" width={60} height={60}><React /></Icon>
      </div>
      <div class="face3">
        <Icon name="redux" width={60} height={60}><Redux /></Icon>
      </div>
      <div class="face4">
        <Icon name="html" width={60} height={60}><Html /></Icon>
      </div>
      <div class="face5">
        <Icon name="sass" width={60} height={60}><Sass /></Icon>
      </div>
      <div class="face6">
        <Icon name="tailwind" width={60} height={60}><Tailwind /></Icon>
      </div>
    </div>
</div>

<style>
    .stage-cube-cont {
    position: relative;
    top: 50%;
    width: 200px;
    height: 200px;
    margin: 0 auto;
    perspective: 1000px;
  }
  .cubespinner {
    animation-name: spincube;
    animation-timing-function: ease-in-out;
    animation-iteration-count: infinite;
    animation-duration: 12s;
    transform-style: preserve-3d;
    transform-origin: 100px 100px 0;
  }
  .cubespinner div {
    position: absolute;
    width: 200px;
    height: 200px;
    border: 1px solid aliceblue;
    background: rgba(255, 255, 255, 0.4);
    font-size: 100px;
    display: flex;
    justify-content: center;
    align-items: center;
    box-shadow: 0 0 20px 0px #abd1c6b9;
  }
  .face1 {
    transform: translateZ(100px);
    color: #dd0031;
  }
  .face2 {
    transform: rotateY(90deg) translateZ(100px);
    color: #f06529;
  }
  .face3 {
    transform: rotateY(90deg) rotateX(90deg) translateZ(100px);
    color: #28a4d9;
  }
  .face4 {
    transform: rotateY(180deg) rotateZ(90deg) translateZ(100px);
    color: #5ed4f4;
  }
  .face5 {
    transform: rotateY(-90deg) rotateZ(90deg) translateZ(100px);
    color: #efd81d;
  }
  .face6 {
    transform: rotateX(-90deg) translateZ(100px);
    color: #ec4d28;
  }

  @keyframes spincube {
    from,
    to {
      transform: rotateX(0deg) rotateY(0deg) rotateZ(0deg);
    }

    16% {
      transform: rotateY(-90deg);
    }

    33% {
      transform: rotateY(-90deg) rotateZ(90deg);
    }
    50% {
      transform: rotateY(-180deg) rotateZ(90deg);
    }
    66% {
      transform: rotateY(-270deg) rotateZ(90deg);
    }
    83% {
      transform: rotateX(90deg);
    }
  }

  @media (max-width: 1220px) {
    .stage-cube-cont {
        display: none; 
    }
  }

</style>