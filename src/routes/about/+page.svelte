<script>
  import ArrowAbout from '../../components/ArrowAbout.svelte';
  import Card from '../../components/About/Card.svelte';
  import Stack from '../../components/About/Stack.svelte';
  import Repos from '../../components/About/Repos.svelte';
  import Social from '../../components/About/Social.svelte';
</script>

<div class="ps-about-page">
  <ArrowAbout />
  <div class="ps-about-page__grid">
    <div class="ps-about-page__grid-card">
      <Card />
    </div>
    <div class="ps-about-page__grid-stack">
      <Stack />
    </div>
    <div class="ps-about-page__grid-repos">
      <Repos />
    </div>
    <div class="ps-about-page__grid-social">
      <Social />
    </div>
  </div>
</div>

<style>
  .ps-about-page {
    padding: 3vw 7vw;
  }
  .ps-about-page__grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-template-rows: repeat(2, auto);
    gap: 1vw;
    height: fit-content;
  }
  .ps-about-page__grid-card,
  .ps-about-page__grid-stack {
    display: flex;
    flex-direction: column;
    height: 500px;
  }
  .ps-about-page__grid-card {
    grid-column: 1;
    grid-row: span 2;
    background-color: #f4f1de;
  }
  .ps-about-page__grid-stack {
    grid-column: 3;
    grid-row: span 2;
    background-color: #b7c59b4e;
    box-shadow: rgba(50, 50, 93, 0.25) 0px 30px 60px -12px inset, 
                  rgba(0, 0, 0, 0.3) 0px 18px 36px -18px inset;
  }
  .ps-about-page__grid-repos {
    grid-column: 2;
    grid-row: 2;
    background-color: #f4f1de;
    display: flex;
    justify-content: center;
  }
  .ps-about-page__grid-social {
    grid-column: 2;
    grid-row: 1;
    display: flex;
    justify-content: center;
    background-color: #c2c2a3;
  }
  .ps-about-page__grid-social,
  .ps-about-page__grid-repos,
  .ps-about-page__grid-stack,
  .ps-about-page__grid-card {
    border-radius: 20px;
    padding: 1vw;
  }

  @media (max-width: 1200px) {
    .ps-about-page__grid {
      grid-template-columns: repeat(2, 1fr);
    }
    .ps-about-page__grid-card {
      grid-column: 1;
      grid-row: span 2;
      height: auto;
      max-height: 70vh;
    }
    .ps-about-page__grid-stack {
      grid-column: span 2;
      grid-row: 3;
    }
  }

  @media (max-width: 650px) {
    .ps-about-page__grid {
      grid-template-columns: 1fr auto;
      grid-template-rows: repeat(4, auto);
    }
    .ps-about-page__grid-card {
      grid-column: 1 / 3;
      grid-row: 1;
    }
    .ps-about-page__grid-stack {
      grid-column: 1 / 3;
      grid-row: 4;
    }
    .ps-about-page__grid-repos {
      grid-column: 1 / 2;
      grid-row: 3;
    }
    .ps-about-page__grid-social {
      grid-column: 1 / 2;
      grid-row: 2;
    }
  }

  @media (max-width: 530px) {
    .ps-about-page__grid {
      grid-template-columns: 1fr;
      grid-template-rows: repeat(4, auto);
      gap: 1vw;
    }
    .ps-about-page__grid-card,
    .ps-about-page__grid-stack,
    .ps-about-page__grid-repos,
    .ps-about-page__grid-social {
      grid-column: 1 / -1;
      height: auto;
    }
    .ps-about-page__grid-card {
      grid-row: 1;
    }
    .ps-about-page__grid-social {
      grid-row: 2;
    }
    .ps-about-page__grid-repos {
      grid-row: 3;
    }
    .ps-about-page__grid-stack {
      grid-row: 4;
    }
  }

  @media (max-width: 461px) {
    .ps-about-page__grid-stack {
      display: none;
    }
  }
</style>
