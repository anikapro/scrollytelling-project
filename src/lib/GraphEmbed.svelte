<script>
    import { onMount } from 'svelte';
  
    onMount(() => {
      const divElement = document.getElementById('viz1752640283008');
      const vizElement = divElement.getElementsByTagName('object')[0];
      vizElement.style.width = '100%';
      vizElement.style.height = '800px';
  
      const scriptElement = document.createElement('script');
      scriptElement.src = 'https://public.tableau.com/javascripts/api/viz_v1.js';
      vizElement.parentNode.insertBefore(scriptElement, vizElement);
    });
  </script>
  

  <!-- HTML from Tableau -->
  <div class="tableauPlaceholder" id="viz1752640283008" style="position: relative;">
    <noscript>
      <!-- svelte-ignore a11y_invalid_attribute -->
      <a href="#">
        <img
          alt="State-Level Bachelor's Degree Attainment"
          src="https://public.tableau.com/static/images/56/565NJZYXS/1_rss.png"
          style="border: none"
        />
      </a>
    </noscript>
    <!-- svelte-ignore a11y_missing_attribute -->
    <object class="tableauViz" style="display: none;">
      <param name="host_url" value="https%3A%2F%2Fpublic.tableau.com%2F" />
      <param name="embed_code_version" value="3" />
      <param name="path" value="shared&#47;565NJZYXS" />
      <param name="toolbar" value="yes" />
      <param name="static_image" value="https://public.tableau.com/static/images/56/565NJZYXS/1.png" />
      <param name="animate_transition" value="yes" />
      <param name="display_static_image" value="yes" />
      <param name="display_spinner" value="yes" />
      <param name="display_overlay" value="yes" />
      <param name="display_count" value="yes" />
      <param name="language" value="en-US" />
      <param name="origin" value="viz_share_link" />
      <param name="filter" value="padding=0" />
      <param name="filter" value="position=relative" />
    </object>
  </div>
