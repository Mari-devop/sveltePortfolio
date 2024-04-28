<script lang="ts">
    import ArrowProjects from '../../components/ArrowProjects.svelte';
	import { readable, writable, derived } from 'svelte/store';



    const projects = readable([
        { 
            "title": "Responsive buildings",
            "category": "styling",
            "tech": "HTML, CSS",
            "url": "https://mari-devop.github.io/building_project/",
            "year": 2023
        },
        { 
            "title": "Funny pinguin",
            "category": "styling",
            "tech": "HTML, CSS",
            "url": "https://mari-devop.github.io/pinguin_project/",
            "year": 2023
        },
        { 
            "title": "Capybara",
            "category": "styling",
            "tech": "HTML, CSS",
            "url": "https://mari-devop.github.io/capibars_LP/#life",
            "year": 2023
        },
        { 
            "title": "Note App",
            "category": "development",
            "tech": "HTML, CSS, JS",
            "url": "https://mari-devop.github.io/note_project/",
            "year": 2023
        },
        { 
            "title": "Recipes",
            "category": "styling",
            "tech": "HTML, CSS",
            "url": "https://mari-devop.github.io/grandpa_recipes/index.html",
            "year": 2023
        },
        {
            "title": "Weather App",
            "category": "development",
            "tech": "HTML, CSS, React JS",
            "url": "https://mari-devop.github.io/weather-ap/",
            "year": 2023
        },
        {
            "title": "Landing Page 1",
            "category": "styling",
            "tech": "HTML, CSS",
            "url": "https://mari-devop.github.io/workit-landing-page/",
            "year": 2023
        },
        {
            "title": "Landing Page 2",
            "category": "styling",
            "tech": "HTML, CSS",
            "url": "https://mari-devop.github.io/skilled-landing-page/",
            "year": 2023
        },
        {
            "title": "Landing Page 3",
            "category": "styling",
            "tech": "HTML, CSS",
            "url": "https://mari-devop.github.io/equalizer-landing-page/",
            "year": 2023
        },
        {
            "title": "Simple subscription form",
            "category": "development",
            "tech": "HTML, CSS, JS",
            "url": "https://mari-devop.github.io/Pod-request-access-landing-page/?mail=dfghj%40g.com",
            "year": 2023
        },
        {
            "title": "Landing page 4",
            "category": "styling",
            "tech": "HTML, CSS",
            "url": "https://mari-devop.github.io/meet-landing-page/",
            "year": 2023
        },
        {
            "title": "Review App",
            "category": "development",
            "tech": "HTML, CSS, Svelte",
            "url": "https://mari-devop.github.io/svelte-sub/",
            "year": 2023
        }
        
    ])

    const filter = writable({ category: 'all' });

    const filteredProjects = derived(
        [filter, projects], ([$filter, $projects]) => {
            if ($filter.category == 'all') {
                return $projects;
            }

            return $projects.filter(project => project.category === $filter.category);
        }
    );

    const categories = [
        {
            "title": 'all'
        }, 
        {
            "title": 'styling'
        },
        {
            "title": 'development'
        }
    ];

    
</script>

<ArrowProjects />

<h2 style="position: absolute;">
    <span  style="font-size: 6rem; font-family: 'Impact', Charcoal, sans-serif; position: relative;">Crafting</span> 
    <span class="word" style="font-size: 7rem; font-family: 'Bangers', cursive; position: relative; left: 8rem; top: 2rem;">advanced</span> 
    <span class="word2" style="font-size: 10rem; font-family: 'Stencil', fantasy; color: #abd1c6; position: relative; left: 14rem;">digital</span>
    <span  style="font-size: 6.5rem; font-family: 'Rock Salt', cursive; position: relative; top: 6rem; left: 0rem;">solutions</span>
</h2>

<h3>
    Crafting
    advanced
    digital
    solutions
</h3>


    <div class="container">
        <div class="left-bnt filter">
            {#each categories as category}
                <button 
                    class="filter-btn" 
                    class:active={$filter.category == category.title}
                    on:click={() => $filter.category = category.title}
                >
                    {category.title}
                </button>
            {/each}
        </div>
    </div>



<table>
    <tbody>
        {#each $filteredProjects as project}
            <tr data-category={project.category}>
                <td style="font-size: 24px;">
                    <a href={project.url} target="_blank">{project.title}</a>
                </td>
                <td style="font-size: 15px">{project.tech}</td>
                <td style="font-size: 12px">{project.year}</td>
            </tr>
        {/each}
    </tbody>
</table>

<style>
    h3 {
    display: none;
    }
   h2 {
    text-align: left;
    margin: 5% 5%; 
    font-size: 7vw;
    font-family: 'Roboto', sans-serif;
}

.word {
    position: absolute;
}

.word2 {
    position: absolute;
}


@media screen and (max-width: 768px) {
    h2 {
        display: none;
    }
    
    h3 {
        transition: opacity 0.5s ease;
        display: flex;
        flex-wrap: wrap;
        text-align: center;
        font-size: 5rem;
        font-family: 'Roboto', sans-serif;
        margin-top: 1rem ;
        color: #f9a528d0;
        margin: 3rem;
        box-shadow: #9bcfc8 0px 0px 0px 2px inset, 
                    #c9e6e2 10px -10px 0px -2px, 
                    #0a675b 10px -10px, 
                    #a0d1cb 20px -20px 0px -3px, 
                    #0a675b 20px -20px,
                    #8fbcb7 30px -30px 0px -3px, 
                    #0a675b  30px -30px, 
                    #73a29c 40px -40px 0px -3px, 
                    #00473e 40px -40px;

        animation: fadeIn 2s ease;
    }

    @keyframes fadeIn {
        from {
            opacity: 0;
        }
        to {
            opacity: 1;
        }
    }

    

    .container {
        display: flex;
        position: relative;
        top: -25rem;
       
    }

    table {
        width: 90%;
        border-collapse: collapse;
        margin: 0 auto;
        position: relative;
        top: -25rem; 
    }
}

@media screen and (max-width: 480px) {
    h2 {
        display: none;
    }

    h3 {
        display: flex;
        flex-wrap: wrap;
        text-align: center;
        font-size: 5rem;
        font-family: 'Roboto', sans-serif;
        margin-top: 1rem ;
    }

    .container {
        display: flex;
        position: relative;
        top: -14rem;
    }
}

    .container {
        display: flex;
        justify-content: space-between;
        flex-direction: row;
        margin: 50px;
        margin-top: 30rem;
    }

    .left-bnt {
        display: flex;
    }

    .left-bnt button {
        background-color: #abd1c6;
        border: none;
        padding: 10px 20px;
        margin-right: 10px;
        border-radius: 5px;
        font-size: medium;
        box-shadow: inset -10px -10px 15px rgba(255, 255, 255, 0.5), 
                    inset 10px 10px 15px rgba(70, 70, 70, 0.12);
        cursor: pointer;
        
    }

    .left-bnt button.active {
        background-color: #f9bc60;
    }

    button:hover {
        box-shadow: 5px 5px 5px 0px rgba(0,0,0,0.3);
        filter: drop-shadow(5px 5px 5px rgba(0,0,0,0.3));
    }

    table {
        width: 90%;
        border-collapse: collapse;
        margin: 0 auto;
    }

    td {
        border-bottom: 1px solid #ddd;
        padding: 2rem;
        text-align: center;
        font-size: 1.5rem;
        font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;                
    }

    a {
        text-decoration: none;
        
    }
 
 
</style>