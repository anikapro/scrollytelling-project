<script>
  import ArticleText from "../lib/ArticleText.svelte";
  import Scroller from "../lib/Scroller.svelte";

</script>
<div>
    <Scroller layout="left">
        <!-- svelte-ignore block_empty -->
        {#snippet sticky()}
            <img src="https://tse4.mm.bing.net/th/id/OIP.BVXHJVh9LJBzibmtZ1JFbAHaJU?pid=Api" alt="Fluffy dog" />
        {/snippet}

        {#snippet scrolly()}
            <ArticleText>
                Hi! This dog is super cute. 
            </ArticleText>
            <ArticleText> Sometimes I feel like this dog. </ArticleText>
        {/snippet}
    </Scroller>
</div>