<script>
  // import Counter from './lib/Counter.svelte'
  import Scrolly from './lib/Scrolly.svelte'
  // import Scatterplot from './lib/Scatterplot.svelte'
  import Linechart from './lib/Linechart.svelte'
  import Chart from "chart.js";
  // import Background from './lib/Background.svelte';
  import Frame from './lib/Frame.svelte';
  import Searchable from './lib/Searchable.svelte';
  import Card from './flipcards/Card.svelte';
  import Card2 from './flipcards/Card2.svelte';
  import Card3 from './flipcards/Card3.svelte';
  import Card4 from './flipcards/Card4.svelte';
  let value;

  const introSteps = [
    "<p>this is the intorduction to what's going on</p>",
    "<p>and here is where I'm continuing to talk about it</p>",
    "<p>and then get into the main piece after this</p>"
  ]

  const historySteps = [
    "<p>Ever wonder how we adopted Crisco and margarine over butter and animal fats?</p>",
    "<p>and here is where I'm continuing to talk about it</p>",
    "<p>and then get into the main piece after this</p>"
  ]

  const steps = [
    "<p>All fats are composed of a mixture of saturated, monounsaturated, and polyunsaturated fatty acids.</p>",
    "<p>Consuming seed oils regularly poses several risks to human health because of their fatty acid makeup.</p>",
    "<p>Seed oils are composed of mainly linoleic acid, a <span style='background-color: red;'>PUFA</span>, which is inflammatory and vulnerable to oxidation within the body.</p>",
    "<p>Saturated fats are solid at room temperature, but due to their production process, unsaturated oils are already oxidized prior to consumption and can remain shelf-stable as liquids for lengthy periods of time.<p>",
    "<p>For centuries, humans cooked with animal fats like butter, tallow and lard. Crisco was introduced in 1911 and made of cottonseed oil – a cheap byproduct of industrialized cotton processing.<p>",
    "<p>It's just so digestible!<p>",
    "<p>Industry convinced entire generations that cholesterol free PUFAs were 'heart healthy.' As __ Viet from Cambridge University Press writes, 'Crisco’s marketers made consumer ignorance acceptable by promoting the idea that industrial processing was akin to purification.'<p>"
  ];

  const chartSteps = [
    "<p>We used to consume quite a bit of red meat, which is high in saturated fat. The decline in beef consumption can largely be accounted for by Americans worrying red meat led to heart disease.</p>",
    "<p>So eventually we began to consume more chicken.</p>",
    "<p>Milk consumption has declined consistently since the 1970s, but yogurt and other dairy products have gained popularity, keeping dairy intake steady.</p>",
    "<p>What about eggs? Those are high in cholesterol and must have something to do with it.</p>",
    "<p>Unfortunately, nothing can compare to the increase of one food group: added fats</p>",
    "<p>Today, added fats, oils and dairy fats make up over 35% of daily calories. In 2000, the USDA changed the standard for reporting fats and in 2010, stopped collecting data.</p>"
  ];
</script>

<main>
  <div class="padded">
    <a href="https://usrtk.org/" target="_blank" rel="noreferrer">
      <img src="img/usrtk.svg" class="logo" alt="USRTK Logo" />
    </a>
  </div>
  
  <banner>
    <h1>Seed oils: The new backbone of the American diet and its health effects</h1>
  </banner>

  <h3 class="byline">
   Posted: April 18, 2023 by <a href='https://datadanica.com' target="_blank">Danica Jefferies</a>
  </h3>

  <!-- <div class="card">
    <Counter />
  </div> -->

  <section id="intro">
    <p>When my father was in anesthesia school, his instructor asked each student to justify their daily dietary choices with the material taught in class. "One egg, but never the yolk because of the cholesterol," he wrote.
    </p>
    <p>What else? Cookies and cereals and maybe a tv dinner – oh, but no saturated fat, to protect his heart health. He passed his assignment that week.</p>
    <p>Did your mother also insist on cooking all her recipes with vegetable oil when you were growing up? Were your grandparents insistent on avoiding saturated fat like the plague?</p>
    <p>For thousands of years, humans consumed and cooked with animal fats. But like many modern foods, the industrially processed seed oils we've come to know and accept as the <span style="background-color: #FF4B00;">"heart-healthy vegetable oil"</span> found ubiquitously in restaurants and kitchen cabinets across the globe, did not make their way into the human diet until just over a century ago. </p>
    <p>In the late 1800s, two businessmen would alter the way the world eats forever. Since then, nearly everyone and their mother has consumed these substances steeped in contention and potentially faulty research – and in copious amounts. In 2010, researchers estimated that per-capita seed oil consumption <a href="https://pubmed.ncbi.nlm.nih.gov/21367944/" target="_blank">skyrocketed over 1,000-fold</a> between 1909 and 1999.</p>
    <p>Millions of Americans who grew up under the seemingly indisputable advice that saturated fat was the enemy would go on to develop a slew of conditions including diabetes and cardiovascular disease. Scientists have repeatedly found risks to consuming these oils, from <a href="https://www.sciencedaily.com/releases/2020/01/200117080827.htm#:~:text=New%20UC%20Riverside%20research%20shows,disease%2C%20anxiety%2C%20and%20depression." target="_blank">inducing genetic changes in the brain</a> to <a href="https://www.sciencedirect.com/science/article/pii/S0002916523233031?via%3Dihub" target="_blank">increasing bodily inflammation</a>, yet they are <a href="https://www.hsph.harvard.edu/news/hsph-in-the-news/scientists-debunk-seed-oil-health-risks/" target="_blank">regularly accepted as the healthy norm</a>.
  </p>
    <p>So what is a "seed oil" and how did we get here?</p>

    </section>
</main>

<div class="temporary"><h2>Below: Chapter one</h2> <p>Scroller 1: What are seed oils, where did they come from, advertising history, the Diet Heart Hypothesis. Interaction: scrolling. Goal: educational, passive interaction</p></div>


<!-- Side by side scroller with scatterplot (NOW FRAME.SVELTE)-->
<section>
  <div class="section-container">
    <div class="steps-container">
      <Scrolly bind:value>
        {#each steps as text, i}
          <div class="step" class:active={value === i}>
            <div class="step-content">{@html text}</div>
          </div>
        {/each}
        <div class="spacer" />
      </Scrolly>
    </div>
    <div class="sticky">
      <!-- <Scatterplot step={value} /> -->
    <Frame step={value}/>

    </div>
  </div>

</section>

<div class="temporary"><p>Filler text will go here to elaborate on what studies say, need to elaborate more on HDL/LDL cholesterol, health and environmental consequences before getting into the next sections.</p></div>

<!-- Text on top scrolly  -->
<!-- <section>
  <div class="section-container-cen">
    <div class="sticky-cen"> -->
      <!-- <p> THIS IS SOME STICKY TEXT</p> -->
      <!-- <div> -->
        <!-- <Background step={value}/> -->
        <!-- <Frame step={value}/>
      </div>
    </div>

    <div class="steps-container-cen">
      <Scrolly bind:value>
        {#each introSteps as text, i}
          <div class="step-cen" class:active={value === i}>
            <div class="step-content-cen">{@html text}</div>
          </div>
        {/each}
        <div class="spacer" />
      </Scrolly>
    </div>
  </div>

</section>

<div class="temporary"></div> -->

<p>Baby formula, oat milk, vegan substitutes, salad dressings, health bars</p>
<p>You're on your weekly run to the grocery store and take a moment to read the ingredients labels on the back of your favorite products. Knowing what you know now, what are you surprised to see? Click to flip the cards.</p>

<section id="flipcards">
    <Card />
    <Card4 />
    <Card2 />
    <Card3 />

</section>


<div class="temporary"><h2>Below: Chapter three</h2> <p>Ai2html graphic of increased disease incidence. Then gets into Scroller 2: health consequences. Interaction: scrolling. Goal: educational before exploratory</p></div>

<section>
  <div class="section-container">
    <div class="steps-container">
      <Scrolly bind:value>
        {#each chartSteps as text, i}
          <div class="step" class:active={value === i}>
            <div class="step-content-side">{@html text}</div>
          </div>
        {/each}
        <div class="spacer" />
      </Scrolly>
    </div>
    <div class="sticky">
      <Linechart step={value}/>
    </div>
  </div>
</section>

<div class="temporary"> </div>
<div class="temporary"> </div>
<div class="temporary"> </div>



<!-- <div class="temporary"> <p>Exploratory section: Seed oil consumption of different countries chart. Interaction: Filter the drop down menu. Goal: Exploratory</p></div>

<div class="temporary"> <p>Close out, provide more research, resources, anything USRTK wants to include</p></div> -->



  <style>
    :global(body) {
    overflow-x: hidden;
  }

  /* .header {
    height: 60vh;
    display: flex;
    place-items: center;
    flex-direction: column;
    justify-content: center;
    text-align: center;
  } */

  .spacer {
    height: 40vh;
  }

  .sticky {
    position: sticky;
    top: 10%;
    flex: 1 1 70%;
    width: 70%;
    height: 100vh;   /*  this is new */
    max-width: 1280px;
  }

    /* for the side-by-side default scroller */
    .section-container {
    margin-top: 1em;
    text-align: center;
    transition: background 100ms;
    display: flex;
    background-color: whitesmoke;
    padding: 1rem;
  }

  .step {
    height: 80vh;
    display: flex;
    place-items: center;
    justify-content: center;
  }

  .step-content {
    font-size: 1rem;
    background: whitesmoke;
    color: #ccc;
    border-radius: 5px;
    padding: .5rem 1rem;
    display: flex;
    flex-direction: column;
    justify-content: center;
    transition: background 500ms ease;
    box-shadow: 1px 1px 10px rgba(0, 0, 0, .2);
    text-align: left;
    width: 75%;
    margin: auto;
    max-width: 500px;
  }

  .step-content-side {
    font-size: 1rem;
    background: whitesmoke;
    color: #ccc;
    border-radius: 5px;
    padding: .5rem 1rem;
    display: flex;
    flex-direction: column;
    justify-content: center;
    transition: background 500ms ease;
    box-shadow: 1px 1px 10px rgba(0, 0, 0, .2);
    text-align: left;
    width: 75%;
    margin: auto;
    max-width: 500px;
  }

  .step.active .step-content {
    background: white;
    color: black;
  }

  .step.active .step-content-side {
    background: white;
    color: black;
  }
  
  .steps-container,
  .sticky {
    height: 100%;
  }

  .steps-container {
    flex: 1 1 40%;
    z-index: 10;
  }

  #flipcards {
    display: flex;
    flex-flow: row wrap;
    justify-content: space-around;
  }

  /*  for the centered scroller */
  /* .section-container-cen {
    text-align: center;
    transition: background 100ms;
  }
  
  .steps-container-cen,
  .sticky-cen {
    height: 100%;
    position: sticky;
    justify-content: center;
    top: 5%;
    bottom: 10%;
    margin: auto;
  }

  .step-cen {
    height: 80vh;
    display: flex;
    place-items: center;
    justify-content: center;
  }

  .step-content-cen {
    background: whitesmoke;
    color: #ccc;
    border-radius: 5px;
    padding: 0.5rem 1rem;
    display: flex;
    flex-direction: column;
    justify-content: center;
    transition: background 500ms ease;
    box-shadow: 1px 1px 10px rgba(0, 0, 0, 0.2);
    z-index: 10;
  }

  .step-cen.active .step-content-cen {
    background: white;
    color: black;
  } */

/* Text-on-top on small screens */
  /* @media screen and (max-width: 768px) {
    .section-container {
      flex-direction: column-reverse;
    }
    .sticky {
      width: 95%;
      margin: auto;
    }
  } */

    /*  This was from the Vite package demo */
  .logo {
    height: 6em;
    padding: 1em;
    will-change: filter;
    transition: filter 300ms;
  }
  /* .logo:hover {
    filter: drop-shadow(0 0 2em #646cffaa);
  } */

  .temporary {
    height: 250px;
    background-color: orange;
  }

    /* Media queries to resize the ai2html graphics for wide versus mobile */
    @media screen and (max-width: 700px) {
    .section-container {
      flex-direction: column-reverse;
    }
    .sticky {
      width: 95%;
      margin: auto;
      z-index: 1;
      /*  remove z-index if it doesn't work on mobile */
    }

    .step-content {
      font-size: 1rem;
      background: whitesmoke;
      color: black;
      border-radius: 5px;
      padding: .5rem 1rem;
      display: flex;
      flex-direction: column;
      justify-content: center;
      transition: background 500ms ease;
      box-shadow: 1px 1px 10px rgba(0, 0, 0, .2);
      text-align: left;
      width: 75%;
      margin: auto;
      max-width: 500px;
    }

    .step-content-side {
      font-size: 1rem;
      background: whitesmoke;
      color: black;
      border-radius: 5px;
      padding: .5rem 1rem;
      display: flex;
      flex-direction: column;
      justify-content: center;
      transition: background 500ms ease;
      box-shadow: 1px 1px 10px rgba(0, 0, 0, .2);
      text-align: left;
      width: 75%;
      margin: auto;
      max-width: 500px;
  }
  }

  </style>