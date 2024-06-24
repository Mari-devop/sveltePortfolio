<a
  href="/about"
  class="ps-main__grid-third-title bounce-in-fwd text-shadow-pop-bl bounce">
    Mari Filon
</a>

<style>
.ps-main__grid-third-title {
    font-size: 3vw;
    font-family: Georgia, serif; 
    color: var(--accent-color); 
    text-decoration: none; 
    font-weight: bold;
}
@keyframes bounce {
  0%, 20%, 50%, 80%, 100% {
    transform: translateY(0);
  }
  40% {
    transform: translateY(-30px);
  }
  60% {
    transform: translateY(-15px);
  }
}
.bounce {
  animation: bounce 2s infinite;
}
.text-shadow-pop-bl {
    -webkit-animation: text-shadow-pop-bl 0.6s both;
    animation: text-shadow-pop-bl 0.6s both;
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

@media screen and (max-width: 985px) {
  .ps-main__grid-third-title {
    font-size: 2rem;
    justify-self: start;
    word-wrap: break-word;
  }
}
</style>