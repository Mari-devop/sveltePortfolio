<div class="container">
    <div class="text-shadow-pop-bl">
        <a href="/" class="link-1">
            <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-arrow-left" viewBox="0 0 16 16">
                <path fill-rule="evenodd" d="M15 8a.5.5 0 0 0-.5-.5H2.707l3.147-3.146a.5.5 0 1 0-.708-.708l-4 4a.5.5 0 0 0 0 .708l4 4a.5.5 0 0 0 .708-.708L2.707 8.5H14.5A.5.5 0 0 0 15 8"/>
            </svg>
            <p>Home</p>
        </a>
    </div>
    <div class="text-shadow-pop-bl">
        <a href="/about" class="link-2">
            <p>About</p>
            <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-arrow-right" viewBox="0 0 16 16">
                <path fill-rule="evenodd" d="M1 8a.5.5 0 0 1 .5-.5h11.793l-3.147-3.146a.5.5 0 0 1 .708-.708l4 4a.5.5 0 0 1 0 .708l-4 4a.5.5 0 0 1-.708-.708L13.293 8.5H1.5A.5.5 0 0 1 1 8"/>
            </svg>
        </a>
    </div>
</div>

<style>
    .container {
        display: flex;
        justify-content: space-around;
        align-items: center;
        box-sizing: border-box;
        background-color: #f2f7f5;
        margin-top: 4rem;
    }

    p {
        font-size: 2rem;    
        margin-right: 0.5rem; 
        margin-left: 0.5rem;
        color: #f9bc60; 
    }

    a {
        border: none;
        cursor: pointer;
        display: flex;
        align-items: center;
        padding: 1rem;
    }

    a svg {
        width: 2rem;
        height: 2rem;
        color: #f9bc60; 
    }

    .link-1:hover {
        transform: rotate(5deg);
    }

    .link-2:hover {
        transform: rotate(-5deg);
    }

    :global(body.dark-mode) div {
        background-color: #004643;
        color: #abd1c6;
    }

    :global(body.dark-mode) p {
        color: #f2f7f5;
    }

    :global(body.dark-mode) svg {
        color: #f2f7f5;
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
    text-shadow: -1px 1px #5f7c7a, -2px 2px #5f7c7a, -3px 3px #5f7c7a, -4px 4px #5f7c7a, -5px 5px #5f7c7a, -6px 6px #5f7c7a, -7px 7px #5f7c7a, -8px 8px #5f7c7a;
    -webkit-transform: translateX(8px) translateY(-8px);
            transform: translateX(8px) translateY(-8px);
  }
}
@keyframes text-shadow-pop-bl {
  0% {
    text-shadow: 0 0 #5f7c7a, 0 0 #5f7c7a, 0 0 #5f7c7a, 0 0 #5f7c7a, 0 0 #5f7c7a, 0 0 #5f7c7a, 0 0 #5f7c7a, 0 0 #5f7c7a;
    -webkit-transform: translateX(0) translateY(0);
            transform: translateX(0) translateY(0);
  }
  100% {
    text-shadow: -1px 1px #5f7c7a, -2px 2px #5f7c7a, -3px 3px #5f7c7a, -4px 4px #5f7c7a, -5px 5px #5f7c7a, -6px 6px #5f7c7a, -7px 7px #5f7c7a, -8px 8px #5f7c7a;
    -webkit-transform: translateX(8px) translateY(-8px);
            transform: translateX(8px) translateY(-8px);
  }
}
</style>
