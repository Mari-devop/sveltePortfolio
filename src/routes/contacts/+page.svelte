<script>
    import ArrowContacts from '../../components/ArrowContacts.svelte'
    import favicon from '../../lib/me.jpg'
</script>


    <ArrowContacts />

    <div>
        <img src={favicon} alt="juj" >
        <h2>Let’s work together</h2>
        <hr>
    </div>

    <form
        action="https://formspree.io/f/xdoqybyn"
        method="POST"
    >
        <input type="email" name="email" placeholder="Your email here">
        <textarea name="message" placeholder="Your text here"></textarea>
        <button type="submit" class="bounce-in-left">Send</button>
    </form>

    <footer>
        <nav>
            <ul>
                <li><a href="https://www.linkedin.com/in/mari-filon/" target="_blank">LinkedIn</a></li>
                <li><a href="https://www.instagram.com/filon_mari_/" target="_blank">Instagram</a></li>
                <li><a href="https://t.me/Mari_Filon" target="_blank">Telegram</a></li>
                <li><a href="https://github.com/Mari-devop" target="_blank">GitHub</a></li>
            </ul>
        </nav>
    </footer>

<style>
   div {
    max-width: 700px;
   }

    h2 {
        font-size: 5rem;
        margin: 1.5rem 1rem 1rem 10rem;
        color: #00473e;
        font-family: Arial, sans-serif;
    }

    :global(body.dark-mode) h2 {
        color: #f2f7f5;
    }

    img {
        border-radius: 10rem;
        margin: 1.5rem 1rem 1rem 10rem;
        height: 5rem;
        float: left;
    }

    hr{
        width: 100%;
        margin-left: 10rem;
        border: 1px solid #f9bc60;
    }

   
    form {
        max-width: 800px; 
        padding-left: 10rem;
        border-radius: 10px; 
    }

    input[type="email"],
    textarea {
        width: 80%;
        padding: 2rem;
        margin-top: 0.5rem; 
        border: none;
        border-bottom: 1px solid #ccc; 
        border-radius: 5px;
        outline: none;
        background-color: transparent;
        resize: none; 
        font-size: 1.5rem;
        font-style: italic;
        color: #00473da2;
    }

    :global(body.dark-mode) input  {
        color: #f2f7f5;
    }

    :global(body.dark-mode) textarea  {
        color: #f2f7f5;
    }

    input::placeholder {
        color: #00473da2;
        font-size: 1rem;
        font-style: italic;
    }

  
    textarea::placeholder {
        color: #00473da2;
        font-size: 1rem;
        font-style: italic;
    }

    :global(body.dark-mode) input::placeholder {
        color: #f2f7f5;
    }
    
    :global(body.dark-mode) textarea::placeholder {
        color: #f2f7f5;
    }
    
    button[type="submit"] {
        background-color: #f9bc60;
        color: #00473e; 
        padding: 3rem 3rem; 
        border: none; 
        width: 10rem; 
        height: 10rem;
        border-radius: 50%;
        cursor: pointer;
        transition: background-color 0.3s; 
        font-size: 2rem;
        float: right;
        font-family: 'Courier New', Courier, monospace;
        font-weight: 400;
       
        top: 25rem;
        right: 27rem;
        transform: scale(1.1);
        box-shadow: 0px 10px 20px 2px rgba(0, 0, 0, 0.25);
    }

    button[type="submit"]:hover {
        box-shadow: 0 0 5px #f9a528fc; 
        transform: translateY(10px);
    }
    
    .bounce-in-left {
	-webkit-animation: bounce-in-left 1.1s both;
	        animation: bounce-in-left 1.1s both;
    }

    @-webkit-keyframes bounce-in-left {
        0% {
            -webkit-transform: translateX(-600px);
                    transform: translateX(-600px);
            -webkit-animation-timing-function: ease-in;
                    animation-timing-function: ease-in;
            opacity: 0;
        }
        38% {
            -webkit-transform: translateX(0);
                    transform: translateX(0);
            -webkit-animation-timing-function: ease-out;
                    animation-timing-function: ease-out;
            opacity: 1;
        }
        55% {
            -webkit-transform: translateX(-68px);
                    transform: translateX(-68px);
            -webkit-animation-timing-function: ease-in;
                    animation-timing-function: ease-in;
        }
        72% {
            -webkit-transform: translateX(0);
                    transform: translateX(0);
            -webkit-animation-timing-function: ease-out;
                    animation-timing-function: ease-out;
        }
        81% {
            -webkit-transform: translateX(-28px);
                    transform: translateX(-28px);
            -webkit-animation-timing-function: ease-in;
                    animation-timing-function: ease-in;
        }
        90% {
            -webkit-transform: translateX(0);
                    transform: translateX(0);
            -webkit-animation-timing-function: ease-out;
                    animation-timing-function: ease-out;
        }
        95% {
            -webkit-transform: translateX(-8px);
                    transform: translateX(-8px);
            -webkit-animation-timing-function: ease-in;
                    animation-timing-function: ease-in;
        }
        100% {
            -webkit-transform: translateX(0);
                    transform: translateX(0);
            -webkit-animation-timing-function: ease-out;
                    animation-timing-function: ease-out;
        }
    }
    @keyframes bounce-in-left {
        0% {
            -webkit-transform: translateX(-600px);
                    transform: translateX(-600px);
            -webkit-animation-timing-function: ease-in;
                    animation-timing-function: ease-in;
            opacity: 0;
        }
        38% {
            -webkit-transform: translateX(0);
                    transform: translateX(0);
            -webkit-animation-timing-function: ease-out;
                    animation-timing-function: ease-out;
            opacity: 1;
        }
        55% {
            -webkit-transform: translateX(-68px);
                    transform: translateX(-68px);
            -webkit-animation-timing-function: ease-in;
                    animation-timing-function: ease-in;
        }
        72% {
            -webkit-transform: translateX(0);
                    transform: translateX(0);
            -webkit-animation-timing-function: ease-out;
                    animation-timing-function: ease-out;
        }
        81% {
            -webkit-transform: translateX(-28px);
                    transform: translateX(-28px);
            -webkit-animation-timing-function: ease-in;
                    animation-timing-function: ease-in;
        }
        90% {
            -webkit-transform: translateX(0);
                    transform: translateX(0);
            -webkit-animation-timing-function: ease-out;
                    animation-timing-function: ease-out;
        }
        95% {
            -webkit-transform: translateX(-8px);
                    transform: translateX(-8px);
            -webkit-animation-timing-function: ease-in;
                    animation-timing-function: ease-in;
        }
        100% {
            -webkit-transform: translateX(0);
                    transform: translateX(0);
            -webkit-animation-timing-function: ease-out;
                    animation-timing-function: ease-out;
        }
    }

    footer {
        display: flex;
        justify-content: right; 
        position: fixed;
        bottom: 0;
        right: 0;
    }
  
    ul {
        display: flex;
        list-style-type: none;
    }
   
    li {
        margin-right: 1rem;
    }

    @media screen and (max-width: 768px){
        form {
            padding-left: 2rem;
        }

        img {
            margin-left: 2rem;
        }

        h2 {
            margin-left: 2rem;
        }

        hr {
            margin-left: 2rem;
            max-width: 100%;
        }
    }

    @media screen and (max-width: 1278px) {
        button[type="submit"] {
            
            margin-top: -20rem;
            
        }
    }

    @media screen and (max-width: 500px) {
        button[type="submit"] {
            height: 5rem;
            width: 5rem;
            margin-top:-18rem;
            font-size: 1rem;
            padding: 1rem 1rem;
            
        }
        
    }
</style>