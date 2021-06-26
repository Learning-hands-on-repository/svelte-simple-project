<script>
  import Header from "./UI/Header.svelte";
  import MeetupGrid from "./Meetups/MeetupGrid.svelte";

  let title = "";
  let subtitle = "";
  let address = "";
  let description = "";
  let imageUrl = "";
  let email = "";

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

  const addMeetup = () => {
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
  };
</script>

<Header />

<main>
  <form on:submit|preventDefault={addMeetup}>
    <div class="form-control">
      <label for="title">Title</label>
      <input type="text" id="title" bind:value={title} />
    </div>
    <div class="form-control">
      <label for="subtitle">subtitle</label>
      <input type="text" id="subtitle" bind:value={subtitle} />
    </div>
    <div class="form-control">
      <label for="address">address</label>
      <input type="text" id="address" bind:value={address} />
    </div>
    <div class="form-control">
      <label for="imageUrl">imageUrl</label>
      <input type="text" id="imageUrl" bind:value={imageUrl} />
    </div>
    <div class="form-control">
      <label for="email">email</label>
      <input type="email" id="email" bind:value={email} />
    </div>
    <div class="form-control">
      <label for="description">Description</label>
      <input row="3" id="description" bind:value={description} />
    </div>
    <button type="submit">Save</button>
  </form>
  <MeetupGrid {meetups} />
</main>

<style>
  main {
    margin-top: 5rem;
  }
</style>
