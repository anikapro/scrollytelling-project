<script>
    import Scroller from "../lib/Scroller.svelte";
    import ArticleText from "../lib/ArticleText.svelte";
    import { fade, fly } from "svelte/transition";
    import ObservedArticleText from "../lib/ObservedArticleText.svelte";

    let picIsVisible = $state(false);

    const options = {
        threshold: [0.85, 0.95],
    };

    const showPicCallback = (entries, observer) => {
        entries.forEach((entry) => {
            const elem = entry.target;

            if (entry.intersectionRatio >= 0.9) {
                picIsVisible = true;
            } else if (entry.intersectionRatio < 0.9) {

            }
        });
    };
</script>

<div>
    <Scroller layout="left">
        {#snippet sticky()}
        <div class=image-container> 
        {#if picIsVisible}
            <img class="state-img" 
            src="AL-GRAPH.png"
             alt="Graph of Alabama incarceration rates from 1975 to 2020."
             in:fade
             />
             {/if}
            <p>
                This is a chart from <strong> Vera Institute of Justice </strong> showing the number of people incarcerated in 
                Alabama from 1975 to 2020, with the red line indicating Alabama, and the gray line representing the entire United States.
            </p>
            {#if picIsVisible}
            <img class="state-img"
             src="MS-GRAPH.png"
              alt="Graph of Mississppi incarceration rates from 1975 to 2020."
              in:fade
            />
            {/if}
            <p>
                This is a chart from <strong> Vera Institute of Justice </strong> showing the number of people incarcerated in 
                Mississippi from 1975 to 2020, with the red line indicating Alabama, and the gray line representing the entire United States.
            </p>
        </div>

        {/snippet}

        {#snippet scrolly()}
            <ObservedArticleText callback={showPicCallback} {options}>
                In the graphs above, we looked at an indictor of education, high school degree rates 
                for the Black population, where we found lower rates in states like Alabama and Mississippi.
            </ObservedArticleText>

            <ArticleText>
                In these charts, we notice that the number of people incarcerated in 
            those two specific states are higher than the national amount, 
            with a larger increase in incarceration overall.

            </ArticleText>


        {/snippet}
    </Scroller>
</div>

<style>
    .image-container{
        display:flex;
        flex-direction:column;
        align-items: bottom;
    }
    .state-img {
        width: 60%;
        margin: 30px auto;
    }
</style>
