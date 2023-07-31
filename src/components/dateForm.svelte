<script>
    import { birthdate } from "../store";
  
    let day = 1;
    let month = 1;
    let year = 1900;
  
    const months = [
      'January', 'February', 'March', 'April', 'May', 'June',
      'July', 'August', 'September', 'October', 'November', 'December'
    ];
  
    $: {
      $birthdate = new Date(year, month - 1, day);
      console.log($birthdate);
    }
  </script>
  
  <div class="flex flex-row justify-center mt-5 space-x-5">

    <div>
        <select bind:value={month}>
        <option disabled selected value="">Select a month</option>
        {#each months as monthName, i}
            <option value={i + 1}>{monthName}</option>
        {/each}
        </select>
    </div>
    

    <div>
        <input type="number" min="1" max="31" bind:value={day} placeholder="DD">
    </div>

    
    <div>
        <input type="number" min="1900" max={new Date().getFullYear()} bind:value={year} placeholder="YYYY">
    </div>

    </div>
  <p class="text-white text-center mt-5">Birthday: {month}/{day}/{year}</p>
  