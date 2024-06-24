<script>
    export let width = 20;
    export let height = 20;
    export let name = '';
    export let color = 'currentColor';
    export let className = ''; 
  </script>
  
  <svg
    xmlns="http://www.w3.org/2000/svg"
    {width}
    {height}
    viewBox="0 0 40 40"
    aria-labelledby={name}
    role="presentation"
    class={className} 
  >
    <title id={name} lang="en">{`${name} icon`}</title>
    <g fill={color}>
      <slot />
    </g>
  </svg>
  
<style>
  svg {
    display: inline-block;
    vertical-align: middle;
  }
  .text-shadow-pop-bl {
    animation: text-shadow-pop-bl 0.6s both;
  }

  @keyframes text-shadow-pop-bl {
    0% {
      text-shadow: 0 0 #5f7c7a, 0 0 #5f7c7a, 0 0 #5f7c7a, 0 0 #5f7c7a, 0 0 #5f7c7a, 0 0 #5f7c7a, 0 0 #5f7c7a, 0 0 #5f7c7a;
      transform: translateX(0) translateY(0);
    }
    100% {
      text-shadow: -1px 1px #5f7c7a, -2px 2px #5f7c7a, -2px 2px #5f7c7a, -3px 3px #5f7c7a;
      transform: translateX(8px) translateY(-8px);
    }
  }
</style>
  