<script>
    import { birthdate } from "../store";
    $: oneDay = 24 * 60 * 60 * 1000; // hours*minutes*seconds*milliseconds
    $: diffDays = Math.round(Math.abs((new Date().getTime() - $birthdate.getTime()) / oneDay));
    $: weeksSinceBirth = Math.floor(diffDays / 7);
    $: totalWeeks = 90 * 52;
    console.log("total weels" + totalWeeks);
    $: {
        console.log("diff days : " + diffDays);
        console.log("weeks since birth : " + weeksSinceBirth);
        console.log("birthdate in grid : " + $birthdate);
    }
    $: tab = Array(totalWeeks)
  </script>
    {#if (totalWeeks - weeksSinceBirth) > 0}
        <h2 class="text-center text-white font-bold mt-5">You have enjoyed {weeksSinceBirth} weeks so far.<br> Make the most of the {totalWeeks - weeksSinceBirth} left.</h2>
    {/if}
  <div class="flex flex-col text-center mt-10">
    <h3 class="text-white mb-2 text-xl font-extrabold ">Weeks in a year ⟶</h3>
  <div class="week-grid css-selector">
    {#each tab as _, i}
      <div class={`week ${i < weeksSinceBirth ? 'past' : 'future'}`}></div>
    {/each}
  </div>
</div>
  
  <style>
    .week-grid {
      display: grid;
      grid-template-columns: repeat(52, 1fr); /* creates 52 columns */
      gap: 1px;
      width: 50%;
      margin: 0px auto;
    }
  
    .week {
      width: 7px;
      height: 7px;
      margin: 3px;
      border-radius: 10%;
    }
  
    .past {
      background-color: red;
    }
  
    .future {
      background-color: white;
    }
  </style>