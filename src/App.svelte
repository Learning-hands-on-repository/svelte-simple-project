<script>
  import Header from "./UI/Header.svelte";
  import MeetupGrid from "./Meetups/MeetupGrid.svelte";

  const meetups = [
    {
      id: "m1",
      title: "Coding BootCamp 1",
      subtitle: "Learn to code 1",
      description: "In ...",
      imageUrl:
        "https://images.unsplash.com/photo-1614531341773-3bff8b7cb3fc?ixid=MnwxMjA3fDB8MHxzZWFyY2h8M3x8bmF0dXJlJTIwYmFja2dyb3VuZHxlbnwwfHwwfHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60",
      address: "some address 1",
      contactEmail: "some email 1",
    },
    {
      id: "m2",
      title: "Coding BootCamp 2",
      subtitle: "Learn to code 2",
      description: "In ...",
      imageUrl:
        "https://images.unsplash.com/photo-1611329532992-0b7ba27d85fb?ixid=MnwxMjA3fDB8MHxzZWFyY2h8Nnx8bmF0dXJlJTIwYmFja2dyb3VuZHxlbnwwfHwwfHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60",
      address: "some address 2",
      contactEmail: "some email 2",
    },
  ];
</script>

<Header />

<main>
  <MeetupGrid {meetups} />
</main>

<style>
</style>
