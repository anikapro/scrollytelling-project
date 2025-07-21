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
    <Scroller layout="right">
        {#snippet sticky()}
        <div class=image-container> 
        {#if picIsVisible}
            <img class="state-img" 
            src="RATES1.png"
             alt="Line graph showing Black incarceration rates from 1990 to 2022."
             in:fade
             />
             {/if}
            <p>
                This is a chart from <strong>  <a href="https://trends.vera.org"> Vera Institute of Justice </a>  </strong> showing the rate of Black people incarcerated 
                through the United States compared to the total incarceration rate. The rates for the Black population is much higher. 
            </p>
            {#if picIsVisible}
            <img class="state-img"
             src="RATES2.png"
              alt="Line graph showing white incarceration rates from 1990 to 2022."
              in:fade
            />
            {/if}
            <p>
                This is a chart from <strong>  <a href="https://trends.vera.org"> Vera Institute of Justice </a>  </strong> showing the rate of white people incarcerated 
                through the United States compared to the total incarceration rate. The rates for the white population is much lower than both the Black population
                and the national rate. 
            </p>
        </div>



        {/snippet}

        {#snippet scrolly()}
            <ObservedArticleText callback={showPicCallback} {options}>
                The Black population makes up 14% of the U.S. population, although are disproportionately 
                incarcerated, <strong> where Black people are incarcerated five times the rate of white people. </strong> This is 
                a disparity in the criminal justice system.
            </ObservedArticleText>

            <ArticleText>
                These numbers highlight a disparity in the criminal justice system. 

            </ArticleText>

            <ArticleText>
                As we saw earlier, we looked at the high school degree completion percentages for the Black population specifically, 
                highlighting the largest impact this association has on Black people in particular. 

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
        margin-top: 60px;
    }
</style>
