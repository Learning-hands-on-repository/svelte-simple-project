<script>
  import Header from "./UI/Header.svelte";
  import MeetupGrid from "./Meetups/MeetupGrid.svelte";
  import EditMeetup from "./Meetups/EditMeetup.svelte";
  import Button from "./UI/Button.svelte";

  let meetups = [
    {
      id: "m1",
      title: "Coding BootCamp 1",
      subtitle: "Learn to code 1",
      description: "In ...",
      imageUrl:
        "https://images.unsplash.com/photo-1614531341773-3bff8b7cb3fc?ixid=MnwxMjA3fDB8MHxzZWFyY2h8M3x8bmF0dXJlJTIwYmFja2dyb3VuZHxlbnwwfHwwfHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60",
      address: "some address 1",
      contactEmail: "some email 1",
      isFavourite: false,
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
      isFavourite: false,
    },
  ];

  let isEditingMode = false;

  const addMeetup = (event) => {
    const { title, subtitle, description, imageUrl, email, address } =
      event.detail;
    const newMeetup = {
      id: Math.random().toString(),
      title: title,
      subtitle: subtitle,
      description: description,
      imageUrl: imageUrl,
      contactEmail: email,
      address: address,
    };

    meetups = [...meetups, newMeetup];
    isEditingMode = false;
  };

  const toggleFavourite = (event) => {
    const id = event.detail;
    const meetupIndex = meetups.findIndex((m) => m.id === id);
    const updatedMeetup = {
      ...meetups[meetupIndex],
      isFavourite: !meetups[meetupIndex].isFavourite,
    };
    const updatedMeetups = [...meetups];
    updatedMeetups[meetupIndex] = updatedMeetup;
    meetups = updatedMeetups;
  };
</script>

<Header />

<main>
  <div class="meetup-controls">
    <Button
      caption="New meeting"
      on:click={() => (isEditingMode = !isEditingMode)}
    />
  </div>
  {#if isEditingMode}
    <EditMeetup on:add-new-meetup={addMeetup} />
  {/if}
  <MeetupGrid {meetups} on:toggle-favourite={toggleFavourite} />
</main>

<style>
  main {
    margin-top: 5rem;
  }

  .meetup-controls {
    margin: 1rem;
  }
</style>
