<template>
  <v-text-field
    :value="$store.state.search"
    @input="$store.commit('setSearch', $event)"
    @focus="searchClosed = false"
    @blur="searchClosed = true"
    :disabled="$store.state.sorting"
    class="expanding-search mt-1 v-btn v-btn--icon theme--dark"
    :class="{ closed: searchClosed && !$store.state.search }"
    placeholder="Search"
    prepend-inner-icon="mdi-magnify"
    filled
    dense
    clearable
    hide-details="auto"
  ></v-text-field>
</template>

<script>
export default {
  data() {
    return {
      searchClosed: true,
    };
  },
};
</script>

<style lang="sass">
.expanding-search
    transition: max-width 0.5s
    .v-input__slot
        cursor: pointer !important
        &:before, &:after
            border-color: transparent !important
    &.closed
        max-width: 45px
        border-radius: 50% !important
        &:not
          background: red !important
          min-width: 0px !important
          padding: 0 !important
        .v-input__slot
            background: transparent !important
</style>
