
<div class="ps-content">
  <p class="ps-content__title text-shadow-pop-bl">Mari Filon</p>
  <button class="ps-content__btn">Contact me</button>
</div>

<style>
.ps-content {
    display: flex;
    flex-direction: row;
}
.ps-content__title {
    font-size: 2.5vw;
    margin: 1.5vw 1.5vw 0.5vw 0.5vw;
    background-color: hsl(160, 4%, 85%, 0.3);
    border-radius: 10px;
    padding: 0.5vw 1vw;
    color: var(--accent-color);
    letter-spacing: 1px;
}
.ps-content__btn {
    border: 1px solid var(--main-bg-color);
    border-radius: 10px;
    margin: 0.5vw 1vw 1vw 1vw;
    padding: 1vw;
    cursor: pointer;
    transition: 0.3s;
    background-color: #f9bc60;
    color: #044f4a;
    font-size: 1.2vw;
    
}
.text-shadow-pop-bl {
  -webkit-animation: text-shadow-pop-bl 0.6s both;
  animation: text-shadow-pop-bl 0.3s both;
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
</style>