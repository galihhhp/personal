<script lang="ts">
  import { onMount } from "svelte";

  let p6uSequence = [
    "P<span class='text-yellow-400'>6</span>U",
    "PA<span class='text-yellow-400'>5</span>U",
    "PAN<span class='text-yellow-400'>4</span>U",
    "PANG<span class='text-yellow-400'>3</span>U",
    "PANGE<span class='text-yellow-400'>2</span>U",
    "PANGES<span class='text-yellow-400'>1</span>U",
    "PANGESTU",
  ];
  let currentSequenceIndex = 0;
  let p6uText = p6uSequence[0];

  const animateSequence = () => {
    const animateForward = () => {
      if (currentSequenceIndex < p6uSequence.length - 1) {
        currentSequenceIndex++;
        p6uText = p6uSequence[currentSequenceIndex];
        setTimeout(animateForward, 600);
      } else {
        setTimeout(animateBackward, 1500);
      }
    };

    const animateBackward = () => {
      if (currentSequenceIndex > 0) {
        currentSequenceIndex--;
        p6uText = p6uSequence[currentSequenceIndex];
        setTimeout(animateBackward, 600);
      } else {
        setTimeout(animateForward, 1500);
      }
    };

    setTimeout(animateForward, 800);
  };

  onMount(() => {
    animateSequence();
  });
</script>

<div class="relative w-full h-screen overflow-hidden bg-black">
  <div class="absolute top-0 left-0 w-full h-full opacity-100 visible">
    <div
      class="h-screen w-full bg-[url('/hero.jpeg')] bg-cover bg-center bg-no-repeat"
    >
      <div class="flex items-center justify-center h-full z-10 relative">
        <h1
          class="
          relative inline-block text-6xl md:text-8xl
          xl:text-[11rem] font-bold text-white tracking-wide"
        >
          {@html p6uText}
        </h1>
      </div>
    </div>
  </div>
</div>
