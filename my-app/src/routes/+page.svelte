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
        background-color: #361419;

    }
}
    main {
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100vh;
        background-color: #361419;
    }

    h1 {
        font-size: 2.5rem;
        color: white;
        text-transform: uppercase;
       
    }

    .heading-center {
        position: absolute;
        bottom: 3.2em;
        font-weight: 400;
        left: 50%;
        transform: translateX(-50%);
        font-size: 3rem;
    }

    .visitekaartje {
        border: 2px solid white;
        width: 27em;
        height: 40em;
        border-radius: .5em;
    }

    p {
        color: white;
        padding: 2em;
        font-size: 1.2rem;
        font-weight: 300;
    }


</style>