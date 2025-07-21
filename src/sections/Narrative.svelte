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
            <img class="graphic-img" 
            src="graphic.jpg"
             alt="Navy background with words in cream stating 'ARE WE PRIORITIZING THE RIGHT THINGS?'"
             in:fade
             />
             {/if}
            {#if picIsVisible}
            <img class="graphic-img"
             src="graphic2.jpg"
              alt="Maroon background with words in cream stating 'Access to literature and education directly reduces recidivism'."
              in:fade
            />
            {/if}
        </div>



        {/snippet}

        {#snippet scrolly()}
            <ObservedArticleText callback={showPicCallback} {options}>
                Education is linked to decreasing recidivism where Kate Cauley states that
                 “inmates who participate in correctional education programs had 43 percent lower odds of recidivating than those who did not."
            </ObservedArticleText>

            <ArticleText>
                <strong>Recidivism is the act of repeating or recommitting a crime after already committing one before.</strong> Decreasing recidivism is 
                important so that incarcerated people can leave prison and change their lives after, rather than falling back into crime.

            </ArticleText>

            <ArticleText>
                According to <a href="https://www.jstor.org/stable/26507622"> Nally et al</a>, recidivism is higher for adults with less than a high 
                school diploma. 

            </ArticleText>

            <ArticleText>
                If education is so important, then we need to <strong>stop defunding schools, and instead prioritize public education!</strong> It could 
                keep more people out of jail, and make our country better for all. 

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
    .graphic-img {
        width: 60%;
        margin: 30px auto;
        margin-top: 100px;
    }
</style>