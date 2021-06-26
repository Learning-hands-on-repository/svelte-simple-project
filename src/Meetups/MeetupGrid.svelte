<script>
  import MeetingItem from "./MeetingItem.svelte";

  export let meetups;
</script>

<section id="meetups">
  {#each meetups as meetup}
    <MeetingItem
      id={meetup.id}
      title={meetup.title}
      subtitle={meetup.subtitle}
      description={meetup.description}
      address={meetup.address}
      imageUrl={meetup.imageUrl}
      email={meetup.contactEmail}
      isFavourite={meetup.isFavourite}
      on:toggle-favourite
    />
  {/each}
</section>

<style>
  section {
    width: 100%;
    display: grid;
    grid-template-columns: 1fr;
    grid-gap: 1rem;
  }

  @media (min-width: 768px) {
    section {
      grid-template-columns: repeat(2, 1fr);
    }
  }

  #meetups {
    margin-top: 5rem;
  }
</style>
