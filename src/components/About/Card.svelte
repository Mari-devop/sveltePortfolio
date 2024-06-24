<script>
  import Email from '../../icons/Email.svelte';
  import Work from '../../icons/Work.svelte';
  import University from '../../icons/University.svelte';
  import Icon from '../Icon.svelte';
</script>

<div class="ps-about-page__card-content">
  <div class="ps-about-page__card-text">
    <div class="ps-about-page__contact-info">
      <span>
        <Icon name="email"><Email /></Icon>
      </span>
      <span>mari.philon@gmail.com</span>
    </div>
  </div>
  <div class="ps-about-page__card-text">
    <p class="ps-about-page__card-text-section-title">Education</p>
    <hr>
    <div class="ps-about-page__card-text-item">
      <div>
        <span>
          <Icon name="university"><University /></Icon>
        </span>
        <span> 2018 - 2020</span>
      </div>
      <p class="ps-about-page__card-text-title">
        International Institute of Business, Master of Business Administration (MBA) 
      </p>
    </div>
    <div class="ps-about-page__card-text-item">
      <div>
        <span>
          <Icon name="university"><University /></Icon>
        </span>
        <span> 2009 - 2014</span>
      </div>
      <p class="ps-about-page__card-text-title">
        Dnipro National University of Oles Honchar, Specialist of Mathematics
      </p>
    </div>
  </div>
  <div class="ps-about-page__card-text">
    <p class="ps-about-page__card-text-section-title">Experience</p>
    <hr>
    <div class="ps-about-page__card-text-item">
      <div class="ps-about-page__span--position">
        <div class="ps-about-page__span--left">
          <span>
            <Icon name="work"><Work /></Icon>
          </span>
          <span> Apr 2024 - present</span>
        </div>  
        <span class="ps-about-page__span--right">Tech1</span>
      </div>
      <p class="ps-about-page__position-title">Junior Frontend Developer</p>
    </div>
    <div class="ps-about-page__card-text-item">
      <div class="ps-about-page__span--position">
        <div class="ps-about-page__span--left">
          <span>
            <Icon name="work"><Work /></Icon>
          </span>
          <span>09/23 - 03/24</span>
        </div>  
        <span class="ps-about-page__span--right">Team Challenge</span>
      </div>
      <p class="ps-about-page__position-title">Junior Frontend Developer</p>
    </div> 
    <div class="ps-about-page__card-text-item">
      <div class="ps-about-page__span--position">
        <div class="ps-about-page__span--left">
          <span>
            <Icon name="work"><Work /></Icon>
          </span>
          <span>01/23 - 07/23</span>
        </div>  
        <span class="ps-about-page__span--right">DS start up</span>
      </div>
      <p class="ps-about-page__position-title">Junior Frontend Developer</p>
    </div> 
    <div class="ps-about-page__card-text-item">
      <div class="ps-about-page__span--position">
        <div class="ps-about-page__span--left">
          <span>
            <Icon name="work"><Work /></Icon>
          </span>
          <span> 2019 - 2022</span>
        </div>  
        <span class="ps-about-page__span--right">My Eco Pharmacy</span>
      </div>
      <p class="ps-about-page__position-title">Project Manager</p>
    </div>   
  </div>
</div>

<style>
  .ps-about-page__card-content {
    display: flex;
    flex-direction: column;
    overflow-y: auto;
    padding: 1.1vw;
    font-family: 'Courier New', Courier, monospace;
    background-color: #f5f5dc; 
    border-radius: 20px;
    font-size: 1.2vw;
    box-shadow: rgba(104, 85, 45, 0.25) 0px 30px 60px -12px inset, 
                rgba(45, 35, 20, 0.3) 0px 18px 36px -18px inset; 
  }
  .ps-about-page__contact-info {
    display: flex;
    align-items: center;
    justify-content: center;
    padding-top: 1vw;
    margin-bottom: 1vw;
  }
  .ps-about-page__card-text {
    display: flex;
    flex-direction: column;
    border-radius: 10px;
    margin: 0 0 1vw 0;
    background-color: rgba(160, 160, 160, 0.3); 
    padding: 1vw 1.5vw;
    box-shadow: rgba(69, 69, 69, 0.4) 0px 2px 4px, 
                rgba(69, 69, 69, 0.3) 0px 7px 13px -3px, 
                rgba(104, 85, 45, 0.2) 0px -3px 0px inset; 
  }
  .ps-about-page__card-text-section-title {
    font-weight: bold;
    margin-bottom: 0.5vw;
    color: #4a4a4a; 
    text-transform: uppercase;
    font-size: 1.5vw;
  }
  .ps-about-page__card-text-item {
    margin: 0 0 1vw 0;
  }
  .ps-about-page__card-text-title,
  .ps-about-page__position-title {
    padding-left: 1.7vw;
    margin: 0.5vw 0;
    color: #4a4a4a; 
  }
  .ps-about-page__position-title {
    font-size: 1.5vw;
  }
  .ps-about-page__span--left,
  .ps-about-page__span--right {
    font-size: 1.1vw;
  }
  .ps-about-page__span--position {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin: 0.5vw 0;
  }
  .ps-about-page__contact-info span {
    margin-right: 1vw;
  }

  @media (max-width: 1200px) {
    .ps-about-page__card-content {
      font-size: 2vw;
    }
    .ps-about-page__card-text-section-title {
      font-size: 2vw;
    }
    .ps-about-page__card-text-title,
    .ps-about-page__position-title {
      font-size: 1.6vw;
    }
    .ps-about-page__span--left,
    .ps-about-page__span--right {
      font-size: 1.5vw;
    }
  }

  @media (max-width: 650px) {
    .ps-about-page__card-content {
      font-size: 3vw;
    }
    .ps-about-page__card-text {
      padding: 2vw 6vw;
      margin: 0 0 2vw 0;
    }
    .ps-about-page__card-text-section-title {
      font-size: 4vw;
    }
    .ps-about-page__card-text-title,
    .ps-about-page__position-title {
      font-size: 3vw;
    }
    .ps-about-page__span--left,
    .ps-about-page__span--right {
      font-size: 2vw;
    }
  }

  @media (max-width: 400px) {
    .ps-about-page__card-content {
      font-size: 4vw;
    }
    .ps-about-page__card-text {
      padding: 3vw 8vw;
      margin: 0 0 3vw 0;
    }
    .ps-about-page__card-text-section-title {
      font-size: 5vw;
    }
    .ps-about-page__card-text-title,
    .ps-about-page__position-title {
      font-size: 4vw;
    }
    .ps-about-page__span--left,
    .ps-about-page__span--right {
      font-size: 3vw;
    }
  }
</style>
