<script>
    import ArrowContacts from '../../components/ArrowContacts.svelte';
    import Social from '../../components/About/Social.svelte';
    import favicon from '../../lib/me.png';
</script>

<div class="ps-contact-page">
    <ArrowContacts />
    <div class="ps-contact-page__contacts">
        <img src={favicon} alt="juj" >
        <h2>Let’s work together</h2>
        <hr>
    </div>
    <form
        action="https://formspree.io/f/xdoqybyn"
        method="POST"
        class="ps-contact-page__form"
    >
        <input type="email" name="email" placeholder="Your email here">
        <textarea name="message" placeholder="Your text here"></textarea>
        <button type="submit" class="bounce-in-left">Send</button>
    </form>
    <footer>
        <Social />
    </footer>
</div>

<style>
    .ps-contact-page {
        padding: 3vw 7vw;
        font-family: 'Courier New', Courier, monospace;
        background-color: #f4f1de;
        color: #00473e;
        height: 100vh;
    }
    .ps-contact-page__contacts {
        text-align: center;
        margin-bottom: 2rem;
    }
    .ps-contact-page__contacts img {
        border-radius: 50%;
        height: 5rem;
        margin-bottom: 1rem;
        box-shadow: 0 0 10px #f9bc60;
    }
    .ps-contact-page__contacts h2 {
        font-size: 3rem;
        margin: 1rem 0;
        color: #00473e;
        text-shadow: 2px 2px 0px #f9bc60, 4px 4px 0px #00473e;
    }
    .ps-contact-page__contacts hr {
        width: 100%;
        border: 2px dashed #f9bc60;
    }
    .ps-contact-page__form {
        max-width: 800px;
        margin: 0 auto;
        text-align: center;
    }
    .ps-contact-page__form input[type="email"],
    .ps-contact-page__form textarea {
        width: 80%;
        padding: 1rem;
        margin-top: 0.5rem;
        border: 2px solid #00473e;
        border-radius: 5px;
        outline: none;
        background-color: #f9bc60;
        color: #00473e;
        font-size: 1.2rem;
        font-family: 'Courier New', Courier, monospace;
        box-sizing: border-box;
    }
    .ps-contact-page__form input::placeholder,
    .ps-contact-page__form textarea::placeholder {
        color: #00473e;
    }
    .ps-contact-page__form button[type="submit"] {
        background-color: #00473e;
        color: #f9bc60;
        padding: 1rem;
        border: none;
        border-radius: 5px;
        cursor: pointer;
        transition: background-color 0.3s;
        font-size: 1.5rem;
        font-family: 'Courier New', Courier, monospace;
        margin-top: 1rem;
        box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
    }
    .ps-contact-page__form button[type="submit"]:hover {
        background-color: #f9bc60;
        color: #00473e;
    }
    footer {
        text-align: center;
        margin-bottom: 1vw;
        margin-top: 1vw;
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

    @media (max-width: 768px) {
        .ps-contact-page {
            padding: 2vw 5vw;
        }
        .ps-contact-page__contacts img {
            height: 4rem;
        }
        .ps-contact-page__contacts h2 {
            font-size: 2.5rem;
        }
        .ps-contact-page__form input[type="email"],
        .ps-contact-page__form textarea {
            width: 90%;
            font-size: 1rem;
        }
    }

    @media (max-width: 480px) {
        .ps-contact-page {
            padding: 1vw 3vw;
        }
        .ps-contact-page__contacts img {
            height: 3rem;
        }
        .ps-contact-page__contacts h2 {
            font-size: 2rem;
        }
        .ps-contact-page__form input[type="email"],
        .ps-contact-page__form textarea {
            width: 100%;
            font-size: 0.9rem;
        }
        .ps-contact-page__form button[type="submit"] {
            font-size: 1.2rem;
            padding: 0.8rem;
        }
    }
    @media (max-width: 375px) {
        footer {
            margin-top: 7vw;
            display: flex;
            justify-content: center;
        }
    }
</style>
