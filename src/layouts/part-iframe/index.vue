<template>
  <div v-if="showPartFrame">
    <template v-for="partFrame in getPartFramePages" :key="partFrame.path">
      <PartFramePage
        v-if="
          partFrame.meta.partFrameSrc &&
          hasRenderPartFrame(partFrame.name) &&
          partFrame.meta.partFrameSrc.length > 0
        "
        v-show="showPartIframe(partFrame)"
        :partFrameSrc="partFrame.meta.partFrameSrc"
      />
    </template>
  </div>
</template>
<script lang="ts">
  import { defineComponent, unref, computed } from 'vue';
  import PartFramePage from '/@/views/sys/part-iframe/index.vue';

  import { usePartFrameKeepAlive } from './usePartFrameKeepAlive';

  export default defineComponent({
    name: 'PartFrameLayout',
    components: { PartFramePage },
    setup() {
      const { getPartFramePages, hasRenderPartFrame, showPartIframe } = usePartFrameKeepAlive();

      const showPartFrame = computed(() => unref(getPartFramePages).length > 0);

      return { getPartFramePages, hasRenderPartFrame, showPartIframe, showPartFrame };
    },
  });
</script>
