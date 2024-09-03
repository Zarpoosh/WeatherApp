<template>
  <main class="container">
    <div class="pt-4 mb-8 relative">
      <input
        v-model="SearchQuery"
        type="text "
        placeholder="dearch for a city or state"
        class="py-2 px-1 w-full bg-transparent border-b focus:border-weather-secondry focus:outline-none focus:[0px-1px-0-0-#004E71]"
      />
    </div>
  </main>
</template>

<script>
import axios from "axios";
import { ref } from "vue";
import axios from "axios";

const mapboxAPIKey = "PK,";

const SearchQuery = ref("");
const queryTimeOut = ref(null);
const mapBoxResult = ref(null);
const getSearchResults = () => {
  queryTimeOut.value = setTimeout(async () => {
    if (SearchQuery.value !== "") {
      const result = await axios.get(
        "https://api.mapbox.com/geocoding/v5/mapbox.places/${SearchQuery.value}.json?access_token=${mapboxAPIKey}&types=place"
      );
    }
  }, 300);
};
export default {};
</script>

<style></style>
