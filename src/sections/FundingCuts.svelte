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
            <p>
                Even as we see the association with incarceration and education, 
                the U.S. government is actively defunding schools. Check out some recent headlines.
            </p>

            {#if picIsVisible}
            <!-- svelte-ignore a11y_img_redundant_alt -->
            <img
                class="fund-img"
                src="https://tse1.mm.bing.net/th/id/OIP.lsYiljbjySXuaHuC8knSOgHaDd?pid=Api"
                alt="Picture showing a protest against K-12 funding cuts for schools, with a poster reading 'FUND MORE CUT LESS."
                in:fade
                out:fade
            />

            {:else}
            <!-- svelte-ignore a11y_img_redundant_alt -->
            <img
            class="fund2-img"
            src="https://tse4.mm.bing.net/th/id/OIP.q9EcfaE-7yS6Vo6EymSNbAHaEK?pid=Api"
             alt="Picture depicting a protest of funding cuts, with signs that say 'No budget cuts for education' and 'Support our schools'"
            in:fade
            out:fade
        />
            {/if}
        <!--
        {#if picIsVisible} -->
            <!-- svelte-ignore a11y_img_redundant_alt -->
            <!-- <img class="fund-img" 
            src="https://tse4.mm.bing.net/th/id/OIP.q9EcfaE-7yS6Vo6EymSNbAHaEK?pid=Api"
             alt="Picture depicting a protest of funding cuts, with signs that say 'No budget cuts for education' and 'Support our schools'"
             in:fade
             />
             {/if}
            {#if picIsVisible} -->
            <!-- svelte-ignore a11y_img_redundant_alt -->
            <!-- <img class="fund-img"
             src="https://tse1.mm.bing.net/th/id/OIP.lsYiljbjySXuaHuC8knSOgHaDd?pid=Api"
              alt="Picture showing a protest against K-12 funding cuts for schools, with a poster reading 'FUND MORE CUT LESS."
              in:fade
            />
            {/if} -->
        </div>



        {/snippet}

        {#snippet scrolly()}
            <ObservedArticleText callback={showPicCallback} {options}>
                <a href= "https://www.msn.com/en-us/news/us/education-department-funding-freeze-targets-summer-school-and-language-programs-that-are-lifelines-for-families/ar-AA1IJ31B" 
                > Education Department funding freeze targets summer school and language programs that are lifelines for families </a>
            </ObservedArticleText>

            <ArticleText>
                <a href= "https://www.wral.com/news/education/attorney-general-jackson-nc-leaders-save-federal-education-funding-july-2025/" 
                > North Carolina, other states sue over Trump education funding cuts </a>

            </ArticleText>

            <ArticleText>
                <a href= "https://www.ksl.com/article/51345852/federal-budget-cuts-could-impact-utah-after-school-summer-programs"
                > Federal budget cuts could impact Utah after-school, summer programs </a>

            </ArticleText>

            <ArticleText>
                <a href= "https://www.msn.com/en-us/news/politics/trump-funding-cuts-to-pbs-set-to-hit-free-educational-content-for-kids/ar-AA1IJOS9"
                > Trump funding cuts to PBS set to hit free educational content for kids </a>

            </ArticleText>


        {/snippet}
    </Scroller>
</div>

<style>

.image-container{
        position: relative;

    }
    .fund-img {
        margin: 0px auto;
        position: absolute;

    }
    .fund2-img{
        margin: 0px auto;
        position: absolute;
        
    }
    /* .image-container{
        display:flex;
        flex-direction:column;
        align-items: bottom;
    }
    .fund-img {
        width: 90%;
        margin: 30px auto;
        margin-top: 60px;
    } */
</style>
