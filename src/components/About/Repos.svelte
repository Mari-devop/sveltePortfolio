<script>
    import Icon from '../Icon.svelte';
    import Circle from '../../icons/Circle.svelte';

    let totalNumber = 17; 
</script>
  
<div class="ps-repos">
  <div class="ps-repos__diagram-container">
    <div class="ps-repos__donut-diagram">
      <div class="section js-section"></div>
      <div class="section html-css-section"></div>
      <div class="section react-section"></div>
      <div class="hole">
        <div class="total-number">{totalNumber} Projects</div>
      </div>
    </div>
    <div class="ps-repos__diagram-labels">
      <div class="ps-repos__label">
          <span class="ps-repos__js">
              <Icon name="circle"><Circle /></Icon>
          </span>
          <span>JS</span>
      </div>
      <div class="ps-repos__label">
          <span class="ps-repos__html">
              <Icon name="circle"><Circle /></Icon>
          </span>
          <span>HTML/CSS</span>
      </div>
      <div class="ps-repos__label">
          <span class="ps-repos__react">
              <Icon name="circle"><Circle /></Icon>
          </span>
          <span>React</span>
      </div>
    </div>
  </div>
</div>
  
<style>
  .ps-repos {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    font-family: 'Courier New', Courier, monospace;
    color: #4a4a4a;
    margin: 2vw 0;
  }
  .ps-repos__diagram-container {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
  }
  .ps-repos__donut-diagram {
    position: relative;
    width: 200px;
    height: 200px;
    border-radius: 50%;
    overflow: hidden;
    background-color: #f4f1de;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
  }
  .section {
    position: absolute;
    width: 100%;
    height: 100%;
    clip: rect(0px, 200px, 200px, 100px);
    border-radius: 50%;
  }
  .section::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    border-radius: 50%;
    box-shadow: inset 0 0 10px rgba(0, 0, 0, 0.5);
    clip: rect(0px, 200px, 200px, 100px);
  }
  .js-section {
    background-color: #f0c801;
    transform: rotate(0deg);
  }
  .html-css-section {
    background-color: #e07a5f;
    transform: rotate(120deg);
  }
  .react-section {
    background-color: #3d405b;
    transform: rotate(240deg);
  }
  .hole {
    position: absolute;
    top: 38%;
    left: 38%;
    width: 150px;
    height: 150px;
    margin-top: -50px;
    margin-left: -50px;
    background-color: #f4f1de;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    box-shadow: inset 0 0 10px rgba(0, 0, 0, 0.5);
  }
  .total-number {
    font-size: 1.5em;
    font-weight: bold;
    color: #4a4a4a;
    display: flex;
    text-align: center;
  }
  .ps-repos__diagram-labels {
    display: flex;
    justify-content: space-between;
    width: 100%;
    margin-top: 1em;
  }
  .ps-repos__label {
    display: flex;
    align-items: center;
    justify-self: center;
    font-size: 1em;
    font-weight: bold;
    margin-top: 2vw;
    margin-left: 1em;
    padding: 0.2em;
    color: #4a4a4a;
    background-color: #b7c59bac;
    border-radius: 10px;
  }
  .ps-repos__js {
    color: #f4e285;
  }
  .ps-repos__html {
    color: #e07a5f;
  }
  .ps-repos__react {
    color: #3d405b;
  }
  .ps-repos__label span {
    margin-right: 0.5em;
  }

@media screen and (max-width: 790px) {
  .ps-repos__diagram-labels {
    width: 100%;
    margin-top: 1em;
  }
  .ps-repos__label {
    margin-top: 1em;
    margin-left: 0.5vw;
    padding: 0.2em;
  }
}
</style>
