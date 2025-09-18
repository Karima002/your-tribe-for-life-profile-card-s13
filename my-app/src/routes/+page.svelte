<script>
  import { onMount } from "svelte";
  import { gsap } from "gsap";
  import SplitText from "gsap/SplitText";

  let { data } = $props();
  const members = data.mmbers;
  const member = data.member.data[0];
  
  gsap.registerPlugin(SplitText);
</script>


