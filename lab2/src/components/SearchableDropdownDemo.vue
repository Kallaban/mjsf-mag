<script>
import SearchableDropdown from './SearchableDropdown.vue';

export default {
  components: {
    SearchableDropdown,
  },
  methods: {
    handleSelection(value) {
      console.log('Вибране значення:', value);
    },
  },
};
</script>

<template>
  <div class="flex items-center justify-center">
    <div class="mr-2">
      <SearchableDropdown
        :options="['Eins', 'Zwei', 'Drei', 'Vier', 'Sechs', 'Sieben', 'Acht', 'Neun']"
        @update:modelValue="handleSelection"
      >
        <template #default="{ item }">
          <span>{{ item }}</span>
          <svg v-if="item === 'Eins'" class="inline-block w-4 h-4 ml-2" fill="currentColor">
          </svg>
        </template>
      </SearchableDropdown>
    </div>

    <div class="mr-2">
      <SearchableDropdown :options="['Option 1', 'Option 2', 'Option 3']" multiple />
    </div>
  </div>
</template>
