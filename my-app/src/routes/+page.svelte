<script>
  import { onMount } from "svelte";
  import { gsap } from "gsap";
  import SplitText from "gsap/SplitText";

  let { data } = $props();
  const members = data.members;
  const member = data.member.data[0];
  
  gsap.registerPlugin(SplitText);

  onMount(() => {
    let split = new SplitText("h1", { type: "chars" });
    const tl = gsap.timeline();
    
    tl.from(split.chars, {
      duration: 1,
      opacity: 0,
      y: 50,
      stagger: 0.05, //https://gsap.com/resources/getting-started/Staggers/
      ease: "power2.out" 
    })
    .to('.intro', {
        autoAlpha: 0, 
        duration: 1,
        ease: 'power4.out'
    })

  });

</script>

<main>

    <section class="intro">
        <h1>{member.name}</h1>
    </section>

    <section>
        <article class="visitekaartje">
        </article>
    </section>
</main>


<style>

    @media (prefers-reduced-motion: no-preference) {
    .intro {
        position: absolute;
        top: 0;
        left: 0;
        z-index: 2;

        display: flex;
        justify-content: center;
        align-items: center;
        
        height: 100svh; /* onderzoek svh een keer */
        width: 100%;
        text-align: center;
        background-color: #8C867F;

    }
}
    main {
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100vh;
        background-color: #8C867F;
    }

    h1 {
        font-size: 2.5rem;
        color: white;
        text-transform: uppercase;
    }

    .visitekaartje {
        border: 2px solid wh;
        width: 30em;
        height: 20em;
        border-radius: .5em;
    }


</style>