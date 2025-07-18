<script>
    let { children } = $props();
</script>

<div class="article-text">
    <p>
        {@render children()}
    </p>
</div>

<style>
    .article-text {
        margin: 50vh auto;
        margin-top: 100px;
        width: 50%;
        background-color: #fdf0d5;
        color: #003049;
        border: solid #c1121f 3px;
        border-radius: 20px;
        padding: 20px;
        box-shadow: 16px 16px #780000;
    }
</style>
