<!-- App.svelte -->
<script>
  import { Heart, Calendar, MapPin, Hotel, Gift } from 'lucide-svelte';
  let activeSection = 'home';

  const sections = ['Home', 'Our Story', 'Details', 'Travel', 'Registry'];
  
  function setActiveSection(section) {
    activeSection = section.toLowerCase().replace(' ', '-');
  }
</script>

<div class="min-h-screen bg-gradient-to-b from-pink-50 to-white">
  <!-- Navigation -->
  <nav class="sticky top-0 bg-white/80 backdrop-blur-sm shadow-sm p-4 z-50">
    <div class="max-w-4xl mx-auto flex justify-center space-x-6">
      {#each sections as section}
        <button
          on:click={() => setActiveSection(section)}
          class="px-4 py-2 rounded-full transition-colors {
            activeSection === section.toLowerCase().replace(' ', '-')
              ? 'bg-pink-100 text-pink-700'
              : 'hover:bg-pink-50'
          }"
        >
          {section}
        </button>
      {/each}
    </div>
  </nav>

  <!-- Hero Section -->
  <section class="py-20 text-center">
    <div class="max-w-4xl mx-auto px-4">
      <Heart class="w-12 h-12 mx-auto mb-6 text-pink-500" />
      <h1 class="text-5xl font-light mb-4">Henry & Minju</h1>
      <p class="text-xl text-gray-600">Are getting married!</p>
    </div>
  </section>

  <!-- Our Story -->
  <section class="py-16 bg-white" id="our-story">
    <div class="max-w-4xl mx-auto px-4">
      <div class="bg-white rounded-lg shadow-sm p-8">
        <h2 class="text-3xl font-light text-center mb-8">Our Love Story</h2>
        <div class="prose max-w-none">
          <p class="text-gray-600 leading-relaxed">
            Every love story is beautiful, but ours is our favorite. Through laughter, adventures, and countless 
            shared moments, we've built a connection that grows stronger each day. Now, we're ready to begin 
            our greatest adventure yet - marriage.
          </p>
        </div>
      </div>
    </div>
  </section>

  <!-- Wedding Details -->
  <section class="py-16 bg-pink-50" id="details">
    <div class="max-w-4xl mx-auto px-4">
      <h2 class="text-3xl font-light text-center mb-12">Wedding Details</h2>
      <div class="grid md:grid-cols-2 gap-8">
        <div class="bg-white rounded-lg shadow-sm p-6">
          <div class="flex items-center mb-4">
            <Calendar class="w-6 h-6 text-pink-500 mr-3" />
            <h3 class="text-xl font-medium">Date & Time</h3>
          </div>
          <p class="text-gray-600">
            Please join us for our wedding celebration!
            <br />
            <span class="block mt-2">
              More details coming soon...
            </span>
          </p>
        </div>

        <div class="bg-white rounded-lg shadow-sm p-6">
          <div class="flex items-center mb-4">
            <MapPin class="w-6 h-6 text-pink-500 mr-3" />
            <h3 class="text-xl font-medium">Venue</h3>
          </div>
          <p class="text-gray-600">
            Location details to be announced
            <br />
            <span class="block mt-2">
              Stay tuned for updates!
            </span>
          </p>
        </div>
      </div>
    </div>
  </section>

  <!-- Travel & Accommodation -->
  <section class="py-16 bg-white" id="travel">
    <div class="max-w-4xl mx-auto px-4">
      <h2 class="text-3xl font-light text-center mb-12">Travel & Accommodation</h2>
      <div class="bg-white rounded-lg shadow-sm p-6">
        <div class="flex items-center mb-4">
          <Hotel class="w-6 h-6 text-pink-500 mr-3" />
          <h3 class="text-xl font-medium">Where to Stay</h3>
        </div>
        <p class="text-gray-600">
          We're working on securing room blocks at nearby hotels.
          Check back soon for special rates and booking information.
        </p>
      </div>
    </div>
  </section>

  <!-- Registry -->
  <section class="py-16 bg-pink-50" id="registry">
    <div class="max-w-4xl mx-auto px-4">
      <h2 class="text-3xl font-light text-center mb-12">Registry</h2>
      <div class="bg-white rounded-lg shadow-sm p-6">
        <div class="flex items-center mb-4">
          <Gift class="w-6 h-6 text-pink-500 mr-3" />
          <h3 class="text-xl font-medium">Gift Registry</h3>
        </div>
        <p class="text-gray-600 text-center">
          Your presence at our wedding is the greatest gift of all.
          <br />
          Registry information will be shared soon.
        </p>
      </div>
    </div>
  </section>

  <!-- Footer -->
  <footer class="bg-white py-8 text-center text-gray-600">
    <div class="max-w-4xl mx-auto px-4">
      <Heart class="w-6 h-6 mx-auto mb-4 text-pink-500" />
      <p>Henry & Minju</p>
    </div>
  </footer>
</div>