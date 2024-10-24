<template>
  <div class="container">
    
    <HeaderView />
    <h3 style="margin-top: 15px">Famous Artists</h3>
    <p>Explore a collection of famous artists from around the world.</p>
    <ul>
      <li v-for="artist in artists" :key="artist.slug">
        <NuxtLink :to="{ name: 'artista-slug', params: { slug: artist.slug } }">{{ artist.name }}</NuxtLink>
      </li>
    </ul>
    <FooterView />
  </div>
</template>

<script>
export default {
  async asyncData({ $content }) {
    try {

      const artists = await $content('artista').fetch() 
      return {
        artists
      }
    } catch (error) {
      console.error('Error loading artists:', error)
      return {
        artists: []
      }
    }
  }
}
</script>
