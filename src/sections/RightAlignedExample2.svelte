<script>

    import * as Highcharts from "highcharts";
    import "highcharts/modules/exporting";
    import { Chart } from "@highcharts/svelte";
    import Scroller from "../lib/Scroller.svelte";
    import ArticleText from "../lib/ArticleText.svelte";
    import GraphEmbed from '../lib/GraphEmbed.svelte';
</script>




    <Scroller layout="right">
        {#snippet sticky()}
            <img
            class="enroll-img"
            src="EDU07.png"
            alt="Graph showing undergraduate enrollment rates declining from 2016 to 2023 along all races measured. "
            />
            <p>
                This is a chart from <strong>  <a href="https://blackwealthdata.org/explore/education"> Black Wealth Data Center </a> </strong>  showing <strong >decreases </strong> in undergraduate enrollment 
                rates from 2016 to 2023 in all races.
            </p>

            <img
            class="education-img"
            src="StateEdu.png"
            alt="Map showing different states and their high school diploma levels or higher through the United States.  "
            />
 
            <p>
                This is a map from <strong> <a href="https://blackwealthdata.org/explore/education"> Black Wealth Data Center </a> </strong>  
                showing <strong >the percentage of the Black population with 
                    high school degrees in the United States.  </strong> 
            </p>    
            
            <p>
                We can see that the deep south, for example, <strong> states like Alabama,  
                Mississippi, and Louisiana </strong> have the lowest rates, <strong>in the bottom 25% of 
                geographies. </strong>
            </p>  

        {/snippet}

        {#snippet scrolly()}
            <ArticleText>
                <strong>These graphs show both college enrollment nationwide by all races,
                    and geographically for specifically the Black population. </strong
                >
            </ArticleText>

            <ArticleText>
                Through observing these charts, are there any contextual factors that could apply
                to these rates? 
            </ArticleText>

            <ArticleText>
                There are certainly a couple that come to mind. I urge you 
                to think of how prisons could relate to these findings... 
            </ArticleText>

            <ArticleText>
                In this website, 
                we will examine the <strong> relationship between these educational patterns
                    to incarceration rates, and what this means. </strong>
            </ArticleText>
        {/snippet}
    </Scroller>


<style>
    .enroll-img {
        width: 100%;
        margin: 10px auto;
        margin-top: 300px;
    }
    .education-img {
        width: 100%;
        margin: 10px auto;
        margin-top: 100px;
    }
</style>
