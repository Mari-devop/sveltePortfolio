<script>
  import MainText from '../components/Main/MainText.svelte';
  import Cube from '../components/Main/Cube.svelte';
  import MainTitle from '../components/Main/MainTitle.svelte';
</script>

<div class="ps-main-page">
  <div class="ps-main__grid">
    <div class="ps-main__grid-first">
     <MainText />
    </div>
    <div class="ps-main__grid-second"></div>
    <div class="ps-main__grid-third">
      <div class="ps-main__grid-third-content">
        <MainTitle />
      </div>
      <Cube />
    </div>
  </div>
</div>

<style>
  .ps-main-page {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    overflow: hidden;
  }
  .ps-main__grid {
    display: grid;
    grid-template-columns: 60% 10% 30%;
    grid-template-rows: 1fr 1fr;
    height: 80vh;
    width: 90vw;
    margin: 100px;
    border: 0.1rem solid var(--main-border-color); 
    box-shadow: 
        var(--main-text-color) -21px 21px 0px -2px, 
        var(--main-border-color) -21px 21px, 
        var(--icon-dark-color) -41px 41px 0px -2px, 
        var(--main-border-color) -41px 41px;
        
    box-sizing: border-box; 
    transition: all 0.3s ease-in-out; 
  }
  .ps-main__grid-first {
    grid-column: 1 / 2;
    grid-row: 1 / 3;
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 2.5rem;
    box-sizing: border-box;
    border-right: 0.1rem solid var(--main-border-color);
    background-color: var(--secondary-bg-color);
    overflow: hidden;
    word-break: break-word;
  }
  .ps-main__grid-second {
    grid-column: 2 / 3;
    grid-row: 1 / 3;
    background-color: var(--accent-color);
    background-image: radial-gradient(#004643 15%, transparent 15%);
    background-size: 10px 10px;
    border-right: 0.1rem solid #004643;
  }
  .ps-main__grid-third {
    grid-column: 3 / 4;
    display: grid;
    grid-template-rows: 1fr 1fr;
  }
  .ps-main__grid-third-content {
    display: flex;
    justify-content: center;
    align-items: center;
    border-bottom: 0.1rem solid var(--main-border-color);
    background-color: var(--secondary-bg-color);
  }
  :global(a) {
    color: #f9bc60;
    text-decoration: none;
    font-weight: bold;
  }
  
  @-webkit-keyframes text-shadow-pop-bl {
    0% {
      text-shadow: 0 0 #5f7c7a, 0 0 #5f7c7a, 0 0 #5f7c7a, 0 0 #5f7c7a, 0 0 #5f7c7a, 0 0 #5f7c7a, 0 0 #5f7c7a, 0 0 #5f7c7a;
      -webkit-transform: translateX(0) translateY(0);
      transform: translateX(0) translateY(0);
    }
    100% {
      text-shadow: -1px 1px #5f7c7a, -2px 2px #5f7c7a, -2px 2px #5f7c7a, -3px 3px #5f7c7a;
      -webkit-transform: translateX(8px) translateY(-8px);
      transform: translateX(8px) translateY(-8px);
    }
  }

  @media screen and (max-width: 1220px) {
    .ps-main__grid {
      grid-template-columns: 1fr 1fr;
    }
    .ps-main__grid-third {
      grid-column: 1 / 2;
      grid-row: 1 / 2;
      display: grid;
      grid-template-rows: auto auto;
      background-color: #abd1c6b9;
      border-right: 0.1rem solid var(--main-border-color);
    }
    .ps-main__grid-third-content {
      border-bottom: none;
      background-color: transparent;
      grid-row: 1 / 3;
      height: auto;
    }
    .ps-main__grid-second {
      grid-column: 1 / 2;
      grid-row: 2 / 3;
      border-top: 0.1rem solid var(--main-border-color);
      border-right: 0.1rem solid var(--main-border-color);
    }
    .ps-main__grid-first {
      grid-column: 3 / 3;
      grid-row: 1 / 3;
      border: none;
      word-wrap: break-word;
    }
}

@media screen and (max-width: 985px) {
    .ps-main__grid {
      grid-template-columns: 1fr;
      grid-template-rows: auto auto auto;
    }
    .ps-main__grid-third {
      grid-column: 1 / 2;
      grid-row: 1 / 2;
      display: grid;
      grid-template-rows: auto auto;
    }
    .ps-main__grid-third-content {
      grid-row: 1 / 3;
      height: auto;
    }
    .ps-main__grid-second {
      grid-column: 1 / 2;
      grid-row: 2 / 3;
      border-right: none;
      border-bottom: 0.1rem solid var(--main-border-color);
    }
    .ps-main__grid-first {
      grid-column: 1 / 2;
      grid-row: 3 / 4;
      border: none;
      word-wrap: break-word;
    } 
}

@media screen and (max-width: 610px) {
  .ps-main__grid {
    margin: 50px;
  }
}
</style>
