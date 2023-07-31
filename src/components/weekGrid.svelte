<script>
    import { birthdate } from "../store";
    let oneDay = 24 * 60 * 60 * 1000; // hours*minutes*seconds*milliseconds
    let diffDays = Math.round(Math.abs((new Date().getTime() - $birthdate.getTime()) / oneDay));
    let weeksSinceBirth = Math.floor(diffDays / 7);
    let totalWeeks = 90 * 52;
    $: {
        console.log("weeks since birth : " + weeksSinceBirth);
        console.log("birthdate in grid : " + $birthdate);
    }

  </script>
  
  <div class="grid grid-cols-52 gap-1">
    {#each Array(totalWeeks) as _, i}
      <div class={`w-2 h-2 ${i < weeksSinceBirth ? 'bg-blue-500' : 'bg-white'}`}></div>
    {/each}
  </div>
  
  