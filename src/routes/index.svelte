<script>
    import supabase from '$lib/db';

    let timetable = {
	Monday: [
  	{
    	name: "PH",
    	period: 1,
    	style: "",
  	},
  	{
    	name: "PM",
    	period: 1,
    	style: "",
  	},
  	{
    	name: "BI",
    	period: 2,
    	style: "",
  	},
  	{
    	name: "R",
    	period: 1,
    	style: "table-success",
  	},
  	{
    	name: "BM",
    	period: 2,
    	style: "",
  	},
  	{
    	name: "M3",
    	period: 2,
    	style: "",
  	},
  	{
    	name: "BC",
    	period: 2,
    	style: "",
  	},
	],
	Tuesday: [
  	{
    	name: "PJPK",
    	period: 1,
    	style: "",
  	},
  	{
    	name: "M3",
    	period: 2,
    	style: "",
  	},
  	{
    	name: "BI",
    	period: 1,
    	style: "",
  	},
  	{
    	name: "E",
    	period: 1,
    	style: "table-success",
  	},
  	{
    	name: "BM",
    	period: 2,
    	style: "",
  	},
  	{
    	name: "BC",
    	period: 3,
    	style: "",
  	},
  	{
    	name: "PJPK",
    	period: 1,
    	style: "",
  	},
	],
	Wednesday: [
  	{
    	name: "BC",
    	period: 3,
    	style: "",
  	},
  	{
    	name: "PM",
    	period: 1,
    	style: "",
  	},
  	{
    	name: "H",
    	period: 1,
    	style: "table-success",
  	},
  	{
    	name: "PKS",
    	period: 3,
    	style: "",
  	},
  	{
    	name: "BM",
    	period: 2,
    	style: "",
  	},
	],
	Thursday: [
  	{
    	name: "SA",
    	period: 1,
    	style: "",
  	},
  	{
    	name: "PJPK",
    	period: 1,
    	style: "",
  	},
  	{
    	name: "BM",
    	period: 2,
    	style: "",
  	},
  	{
    	name: "A",
    	period: 1,
    	style: "table-success",
  	},
  	{
    	name: "PM",
    	period: 1,
    	style: "",
  	},
  	{
    	name: "BC",
    	period: 2,
    	style: "",
  	},
  	{
    	name: "M3",
    	period: 2,
    	style: "",
  	},
	],
	Friday: [
  	{
    	name: "BI",
    	period: 2,
    	style: "",
  	},
  	{
    	name: "BM",
    	period: 2,
    	style: "",
  	},
  	{
    	name: "T",
    	period: 1,
    	style: "table-success",
  	},
  	{
    	name: "BC",
    	period: 2,
    	style: "",
  	},
  	{
    	name: "PM",
    	period: 1,
    	style: "",
  	},
  	{
    	name: "SA",
    	period: 2,
    	style: "",
  	},
	],
  };


    async function logout() {
   	 const { error } = await supabase.auth.signOut();

   	 if (error) alert(error.message); // alert if error
    }

</script>



<br>
<br>
<div class="container">
<h1>Dashboard</h1>
<table class="table table-sm table-bordered table caption-top">
    <caption>School Timetable</caption>
    <thead>
      <tr>
        <th scope="col">#</th>
        <th scope="col">1</th>
        <th scope="col">2</th>
        <th scope="col">3</th>
        <th scope="col">4</th>
        <th scope="col">-</th>
        <th scope="col">5</th>
        <th scope="col">6</th>
        <th scope="col">7</th>
        <th scope="col">8</th>
        <th scope="col">9</th>
        <th scope="col">10</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <th scope="row">Mon</th>
         {#each timetable.Monday as timeSlot}
         <td colspan={timeSlot.period} class={timeSlot.style}>
            <button class="btn">{timeSlot.name}</button>
         </td>
         {/each}
      </tr>
      <tr>
        <th scope="row">Tue</th>
        {#each timetable.Tuesday as timeSlot}
         <td colspan={timeSlot.period} class={timeSlot.style}>
            <button class="btn">{timeSlot.name}</button>
         </td>
         {/each}
      </tr>
      <tr>
        <th scope="row">Wed</th>
        {#each timetable.Wednesday as timeSlot}
         <td colspan={timeSlot.period} class={timeSlot.style}>
            <button class="btn">{timeSlot.name}</button>
         </td>
         {/each}
      </tr>
      <tr>
        <th scope="row">Thu</th>
        {#each timetable.Thursday as timeSlot}
        <td colspan={timeSlot.period} class={timeSlot.style}>
           <button class="btn">{timeSlot.name}</button>
        </td>
        {/each}
      </tr>
      <tr>
        <th scope="row">Fri</th>
        {#each timetable.Friday as timeSlot}
         <td colspan={timeSlot.period} class={timeSlot.style}>
            <button class="btn">{timeSlot.name}</button>
         </td>
         {/each}
      </tr>
    </tbody>
  </table>
</div>

  <!-- Button trigger modal -->
<button type="button" class="btn btn-primary" data-bs-toggle="modal" data-bs-target="#exampleModal">
	Edit Time Slot
  </button>
  
  <!-- Modal -->
  <div class="modal fade" id="exampleModal" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
	<div class="modal-dialog">
	  <div class="modal-content">
		<div class="modal-header">
		  <h5 class="modal-title" id="exampleModalLabel">Edit Time Slot</h5>
		  <button type="button" class="btn-cancel" data-bs-dismiss="modal" aria-label="Cancel"></button>
		</div>
		<div class="modal-body">
		  
		</div>
		<div class="modal-footer">
		  <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Cancel</button>
		  <button type="button" class="btn btn-primary">Save changes</button>
		</div>
	  </div>
	</div>
  </div>

  <!-- Sign Out -->
<section class="container px-4 py-3 text-center">
    <button class="btn btn-dark" on:click={logout}>Logout</button>
</section>