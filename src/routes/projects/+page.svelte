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
        },
        {
            "title": "Restaurant",
            "category": "development",
            "tech": "HTML, CSS, React JS",
            "url": "https://mari-devop.github.io/restik/",
            "year": 2024
        },
        {
            "title": "Image gallery",
            "category": "development",
            "tech": "HTML, CSS, React JS",
            "url": "https://mari-devop.github.io/gallery/",
            "year": 2024
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
    <div class="wrapper">
        <h2>
            <span  style="font-size: 6rem; font-family: 'Impact', Charcoal, sans-serif;">Crafting</span> 
            <span class="word" style="font-family: 'Bangers', cursive;">advanced</span> 
            <span class="word2" style="font-family: 'Stencil', fantasy; color: #abd1c6;">digital</span>
            <span class="word3" style="font-family: 'Rock Salt', cursive;">solutions</span>
        </h2>
    </div>

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
                    <td style="font-size: 15px;">
                        <a href={project.url} target="_blank">{project.title}</a>
                    </td>
                    <td style="font-size: 15px">{project.tech}</td>
                    <td style="font-size: 12px">{project.year}</td>
                </tr>
            {/each}
        </tbody>
    </table>

<style>
    .wrapper {
        display: flex;
        justify-content: center;
        max-width: 90%;   
        color: #f9bc60;
    }

    h2 {
        text-align: left;
        padding-left: 10rem;
        font-size: 7vw;
    }

    h2 .word {
        font-size: 7rem;
    }

    h2 .word2 {
        font-size: 10rem;
    }

    h2 .word3 {
        font-size: 6.5rem;
    }

    table {
        width: 90%;
        border-collapse: collapse;
        margin: 0 auto;
    }

    .container {
        display: flex;
        justify-content: space-between;
        flex-direction: row;
        padding-left: 10rem;
        padding-bottom: 5rem;
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
    @media screen and (max-width: 1062px) {
        h2 .word2 {
                font-size: 5rem;
        }
    }

    @media screen and (max-width: 1005px) {
    h2 .word {
            font-size: 4rem;
    }
    }

    @media screen and (max-width: 817px) {
        h2 .word3 {
            font-size: 5rem;
        }
    }

    @media screen and (max-width: 807px) {
        .wrapper {
            width: 100%;
        }
        h2 {
            text-align: center;
            padding-left: 5rem;
        }
        .container {
            padding-left: 8rem;
        }
    }

    @media screen and (max-width: 716px) {
        .container {
            justify-content: center;
            padding-left: 0;
        }
    }

    @media screen and (max-width: 500px) {
        .container {
            padding-left: 2rem;
        }
        
    }
    


    @media screen and (max-width: 320px) {
        h2 {
            padding-left: 6rem;
        }
        .container {
            padding-left: 5rem;
        }
    }

    
    @media screen and (max-width: 290px) {
        h2 {
            padding-left: 7rem;
        }
        .container {
            padding-left: 6rem;
        }
    }

    @media screen and (max-width: 290px) {
        h2 {
            padding-left: 10rem;
        }
        .container {
            padding-left: 8rem;
        }
    }
 
</style>