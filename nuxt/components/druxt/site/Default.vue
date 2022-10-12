<template>
  <div>
    <div>
      <slot name="header" />
    </div>
    <main>
      <slot name="highlighted" />
      <slot v-if="$route.path !== '/'" name="breadcrumb" />
      <div>
        <header>
          <slot name="pre_content" />
        </header>
        <slot name="content" />
      </div>
    </main>
  </div>
</template>

<script>
// @TODO - https://github.com/druxt/druxt.js/issues/545
// import { DruxtSiteMixin } from 'druxt-site'
export default {
  // mixins: [DruxtSiteMixin]
  props: {
    /**
     * The JSON:API resource language code.
     *
     * @type {string}
     */
    langcode: {
      type: String,
      default: undefined,
    },
    /**
     * DruxtBlockRegion propsData for regions.
     *
     * @return {object}
     */
    props: {
      type: Object,
      default: () => ({}),
    },
    /**
     * The Block region names.
     *
     * @type {string[]},
     */
     regions: {
      type: Array,
      default: () => ([])
    },
    /**
     * The Drupal theme ID.
     *
     * @type {string}
     */
    theme: {
      type: String,
      required: true,
    },
  },
}
</script>
