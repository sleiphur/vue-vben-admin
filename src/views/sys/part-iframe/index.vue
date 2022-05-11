<template>
  <div :class="prefixCls" :style="getWrapStyle">
    <component :is="frameSrcRef" :class="`${prefixCls}__main`" ref="partFrameRef" />
  </div>
</template>
<script lang="ts" setup>
  import type { ComponentPublicInstance, CSSProperties } from 'vue';
  import { ref, unref, computed, onMounted, nextTick } from 'vue';
  import { useWindowSizeFn } from '/@/hooks/event/useWindowSizeFn';
  import { propTypes } from '/@/utils/propTypes';
  import { useDesign } from '/@/hooks/web/useDesign';
  import { useLayoutHeight } from '/@/layouts/default/content/useContentViewHeight';

  const props = defineProps({
    partFrameSrc: propTypes.string.def('PartFrameBlank'),
  });

  const topRef = ref(50);
  const heightRef = ref(window.innerHeight);
  // const frameRef = ref<HTMLFrameElement>();
  const partFrameRef = ref<ComponentPublicInstance>();
  const { headerHeightRef } = useLayoutHeight();

  const frameSrcRef = ref<string>('');

  const { prefixCls } = useDesign('part-iframe-page');
  useWindowSizeFn(calcHeight, 150, { immediate: true });

  const getWrapStyle = computed((): CSSProperties => {
    return {
      height: `${unref(heightRef) - 80}px`,
    };
  });

  function calcHeight() {
    const iframe = unref(partFrameRef);
    if (!iframe) {
      return;
    }
    const top = headerHeightRef.value;
    topRef.value = top;
    heightRef.value = window.innerHeight - top;
    const clientHeight = document.documentElement.clientHeight - top;
    iframe.$el.style.height = `${clientHeight}px`;
  }

  onMounted(() => {
    console.log(props.partFrameSrc);
    frameSrcRef.value = props.partFrameSrc;
    nextTick(() => {
      useWindowSizeFn(calcHeight, 150, { immediate: true });
    });
  });
</script>
<style lang="less" scoped>
  @prefix-cls: ~'@{namespace}-part-iframe-page';

  .@{prefix-cls} {
    .ant-spin-nested-loading {
      position: relative;
      height: 100%;

      .ant-spin-container {
        width: 100%;
        height: 100%;
        padding: 10px;
      }
    }

    &__mask {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
    }

    &__main {
      width: 100%;
      height: 100%;
      overflow: auto;
      background-color: @component-background;
      border: 0;
      box-sizing: border-box;
    }
  }
</style>
