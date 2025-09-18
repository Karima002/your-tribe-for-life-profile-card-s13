<script>
  import { onMount } from "svelte";
  import { gsap } from "gsap";
  import SplitText from "gsap/SplitText";

  let { data } = $props();
  const members = data.members;
  const member = data.member.data[0];
  
  gsap.registerPlugin(SplitText);
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

