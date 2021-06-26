<script>
  import Header from "./UI/Header.svelte";
  import MeetupGrid from "./Meetups/MeetupGrid.svelte";
  import TextInput from "./UI/TextInput.svelte";
  import Button from "./UI/Button.svelte";

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
    <TextInput
      controlType="text"
      id="title"
      label="Title"
      value={title}
      on:input={(event) => (title = event.target.value)}
    />
    <TextInput
      controlType="text"
      id="subtitle"
      label="Subtitle"
      value={subtitle}
      on:input={(event) => (subtitle = event.target.value)}
    />
    <TextInput
      controlType="text"
      id="address"
      label="Address"
      value={address}
      on:input={(event) => (address = event.target.value)}
    />
    <TextInput
      controlType="text"
      id="imageUrl"
      label="ImageUrl"
      value={imageUrl}
      on:input={(event) => (imageUrl = event.target.value)}
    />
    <TextInput
      controlType="email"
      id="email"
      label="Email"
      value={email}
      on:input={(event) => (email = event.target.value)}
    />
    <TextInput
      controlType="textarea"
      id="description"
      label="Description"
      value={description}
      on:input={(event) => (description = event.target.value)}
    />
    <Button type="submit" caption="save" />
  </form>
  <MeetupGrid {meetups} />
</main>

<style>
  main {
    margin-top: 5rem;
  }

  form {
    width: 30rem;
    margin: auto;
  }
</style>
