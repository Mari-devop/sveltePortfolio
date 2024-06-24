<script>
    import Icon from "../Icon.svelte";
    import Linkedin from "../../icons/Linkedin.svelte";
    import Telegram from "../../icons/Telegram.svelte";
    import Github from "../../icons/Github.svelte";
    import Instagram from "../../icons/Instagram.svelte";
</script>
    
<div class="ps-social">
    <div class="ps-social__item">
        <a href="https://www.linkedin.com/in/mari-filon/" target="_blank" rel="noopener noreferrer" class="linkedin bounce-in-top">
            <Icon name="linkedin" width={60} height={60}>
                <Linkedin />
            </Icon>
        </a>
        <a href="https://t.me/Mari_Filon" target="_blank" rel="noopener noreferrer" class="telegram bounce-in-top">
            <Icon name="telegram" width={60} height={60}>
                <Telegram />
            </Icon>
        </a>
    </div>
    <div class="ps-social__item">
        <a href="https://github.com/Mari-devop" target="_blank" rel="noopener noreferrer" class="github bounce-in-top">
            <Icon name="github" width={60} height={60}>
                <Github />
            </Icon>
        </a>
        <a href="https://www.instagram.com/filon_mari_/" target="_blank" rel="noopener noreferrer" class="instagram bounce-in-top">
            <Icon name="instagram" width={60} height={60}>
                <Instagram />
            </Icon>
        </a>
    </div>
</div>
    
<style>
    .ps-social {
        display: flex;
        justify-content: center;
        align-items: center;
        max-width: 300px;
        font-family: 'Courier New', Courier, monospace;
        color: #4a4a4a;
    }
    .ps-social__item {
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: row; 
    }
    .ps-social__item a{
        margin: 0 0.5vw;
    }
    .ps-social a {
        display: block;
        width: 60px;
        height: 60px;
        border-radius: 50%;
        background-color: #f4f1de;
        display: flex;
        justify-content: center;
        align-items: center;
        cursor: pointer;
        color: #9f9f9f; 
        box-shadow: rgba(0, 0, 0, 0.4) 0px 2px 4px, 
                    rgba(0, 0, 0, 0.3) 0px 7px 13px -3px, 
                    rgba(0, 0, 0, 0.2) 0px -3px 0px inset;
        transition: background-color 0.3s, transform 0.3s;
    }
    .ps-social a:hover {
        background-color: #e07a5f;
        transform: scale(1.1);
    }
    .ps-social .linkedin {
        color: #0077b5;
    }
    .ps-social .telegram {
        color: #0088cc;
    }
    .ps-social .github {
        color: #333333;
    }
    .ps-social .instagram {
        color: #e4405f;
    }
    .bounce-in-top {
        -webkit-animation: bounce-in-top 1.1s both;
        animation: bounce-in-top 1.1s both;
    }
    @-webkit-keyframes bounce-in-top {
        0% {
            -webkit-transform: translateY(-500px);
                    transform: translateY(-500px);
            -webkit-animation-timing-function: ease-in;
                    animation-timing-function: ease-in;
            opacity: 0;
        }
        38% {
            -webkit-transform: translateY(0);
                    transform: translateY(0);
            -webkit-animation-timing-function: ease-out;
                    animation-timing-function: ease-out;
            opacity: 1;
        }
        55% {
            -webkit-transform: translateY(-65px);
                    transform: translateY(-65px);
            -webkit-animation-timing-function: ease-in;
                    animation-timing-function: ease-in;
        }
        72% {
            -webkit-transform: translateY(0);
                    transform: translateY(0);
            -webkit-animation-timing-function: ease-out;
                    animation-timing-function: ease-out;
        }
        81% {
            -webkit-transform: translateY(-28px);
                    transform: translateY(-28px);
            -webkit-animation-timing-function: ease-in;
                    animation-timing-function: ease-in;
        }
        90% {
            -webkit-transform: translateY(0);
                    transform: translateY(0);
            -webkit-animation-timing-function: ease-out;
                    animation-timing-function: ease-out;
        }
        95% {
            -webkit-transform: translateY(-8px);
                    transform: translateY(-8px);
            -webkit-animation-timing-function: ease-in;
                    animation-timing-function: ease-in;
        }
        100% {
            -webkit-transform: translateY(0);
                    transform: translateY(0);
            -webkit-animation-timing-function: ease-out;
                    animation-timing-function: ease-out;
        }
    }
    @keyframes bounce-in-top {
        0% {
            -webkit-transform: translateY(-500px);
                    transform: translateY(-500px);
            -webkit-animation-timing-function: ease-in;
                    animation-timing-function: ease-in;
            opacity: 0;
        }
        38% {
            -webkit-transform: translateY(0);
                    transform: translateY(0);
            -webkit-animation-timing-function: ease-out;
                    animation-timing-function: ease-out;
            opacity: 1;
        }
        55% {
            -webkit-transform: translateY(-65px);
                    transform: translateY(-65px);
            -webkit-animation-timing-function: ease-in;
                    animation-timing-function: ease-in;
        }
        72% {
            -webkit-transform: translateY(0);
                    transform: translateY(0);
            -webkit-animation-timing-function: ease-out;
                    animation-timing-function: ease-out;
        }
        81% {
            -webkit-transform: translateY(-28px);
                    transform: translateY(-28px);
            -webkit-animation-timing-function: ease-in;
                    animation-timing-function: ease-in;
        }
        90% {
            -webkit-transform: translateY(0);
                    transform: translateY(0);
            -webkit-animation-timing-function: ease-out;
                    animation-timing-function: ease-out;
        }
        95% {
            -webkit-transform: translateY(-8px);
                    transform: translateY(-8px);
            -webkit-animation-timing-function: ease-in;
                    animation-timing-function: ease-in;
        }
        100% {
            -webkit-transform: translateY(0);
                    transform: translateY(0);
            -webkit-animation-timing-function: ease-out;
                    animation-timing-function: ease-out;
        }
    }

</style>
    