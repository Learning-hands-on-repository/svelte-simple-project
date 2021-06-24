<script>
  import Header from "./UI/Header.svelte";
  import MeetingItem from "./Meetups/MeetingItem.svelte";

  const meetups = [
    {
      id: "m1",
      title: "Coding BootCamp 1",
      subtitle: "Learn to code 1",
      description: "In ...",
      imageUrl: "",
      address: "some address 1",
      contactEmail: "some email 1",
    },
    {
      id: "m2",
      title: "Coding BootCamp 2",
      subtitle: "Learn to code 2",
      description: "In ...",
      imageUrl: "",
      address: "some address 2",
      contactEmail: "some email 2",
    },
  ];
</script>

<Header />

<section id="meetups">
  {#each meetups as meetup}
    <MeetingItem />
  {/each}
</section>

<style>
  #meetups {
    margin-top: 5rem;
  }
</style>
