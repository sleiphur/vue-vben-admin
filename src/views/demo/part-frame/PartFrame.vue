<template>
  <div>
    <h3>部分 Iframe 页签</h3>

    <p>
      <span style="color: red">页面中部分是iframe页面</span>
      <br />
      <span style="color: green">页面中部分是iframe页面</span>
      <br />
      <span style="color: blue">页面中部分是iframe页面</span>
      <br />
      ↓↓↓↓ ↓↓↓↓ ↓↓↓↓ ↓↓↓↓ ↓↓↓↓ ↓↓↓↓ ↓↓↓↓ ↓↓↓↓
      <br />
      下面包含一个非Iframe普通输入框和一个Iframe嵌入页面，
      操作它们(即让它处于非初始状态)，然后再打开其他标签或切换至其他标签，然后再切换回来本标签页，查看状态的保持情况。
      <br />
      ↓↓↓↓ ↓↓↓↓ ↓↓↓↓ ↓↓↓↓ ↓↓↓↓ ↓↓↓↓ ↓↓↓↓ ↓↓↓↓
      <br />
      <a-input
        v-model:value="inputData"
        placeholder="Please input"
        style="width: 400px; max-width: 600px"
      />
      <br />
      <br />
      <iframe
        id="inlineFrameExample"
        title="Inline Frame Example"
        width="800"
        height="800"
        style="width: 1000px; height: 800px"
        src="https://www.openstreetmap.org/export/embed.html?bbox=-0.004017949104309083%2C51.47612752641776%2C0.00030577182769775396%2C51.478569861898606&layer=mapnik"
      ></iframe>
    </p>
    <p>
      <span style="color: red">页面中部分是iframe页面</span>
      <br />
      <span style="color: green">页面中部分是iframe页面</span>
      <br />
      <span style="color: blue">页面中部分是iframe页面</span>
      <br />
    </p>
    <p>
      <span style="color: red">页面中部分是iframe页面</span>
      <br />
      <span style="color: green">页面中部分是iframe页面</span>
      <br />
      <span style="color: blue">页面中部分是iframe页面</span>
      <br />
    </p>
    <p>
      <span style="color: red">页面中部分是iframe页面</span>
      <br />
      <span style="color: green">页面中部分是iframe页面</span>
      <br />
      <span style="color: blue">页面中部分是iframe页面</span>
      <br />
    </p>
    <p>
      <span style="color: red">页面中部分是iframe页面</span>
      <br />
      <span style="color: green">页面中部分是iframe页面</span>
      <br />
      <span style="color: blue">页面中部分是iframe页面</span>
      <br />
    </p>
    <p>
      <span style="color: red">页面中部分是iframe页面</span>
      <br />
      <span style="color: green">页面中部分是iframe页面</span>
      <br />
      <span style="color: blue">页面中部分是iframe页面</span>
      <br />
    </p>
    <p>
      <span style="color: red">页面中部分是iframe页面</span>
      <br />
      <span style="color: green">页面中部分是iframe页面</span>
      <br />
      <span style="color: blue">页面中部分是iframe页面</span>
      <br />
    </p>
    <p>
      <span style="color: red">页面中部分是iframe页面</span>
      <br />
      <span style="color: green">页面中部分是iframe页面</span>
      <br />
      <span style="color: blue">页面中部分是iframe页面</span>
      <br />
    </p>
    <p>
      <span style="color: red">页面中部分是iframe页面</span>
      <br />
      <span style="color: green">页面中部分是iframe页面</span>
      <br />
      <span style="color: blue">页面中部分是iframe页面</span>
      <br />
    </p>
    <p>
      <span style="color: red">页面中部分是iframe页面</span>
      <br />
      <span style="color: green">页面中部分是iframe页面</span>
      <br />
      <span style="color: blue">页面中部分是iframe页面</span>
      <br />
    </p>
    <p>
      <span style="color: red">页面中部分是iframe页面</span>
      <br />
      <span style="color: green">页面中部分是iframe页面</span>
      <br />
      <span style="color: blue">页面中部分是iframe页面</span>
      <br />
    </p>
    <p>
      <span style="color: red">页面中部分是iframe页面</span>
      <br />
      <span style="color: green">页面中部分是iframe页面</span>
      <br />
      <span style="color: blue">页面中部分是iframe页面</span>
      <br />
    </p>
    <p>
      <span style="color: red">页面中部分是iframe页面</span>
      <br />
      <span style="color: green">页面中部分是iframe页面</span>
      <br />
      <span style="color: blue">页面中部分是iframe页面</span>
      <br />
    </p>
    <p>
      <span style="color: red">页面中部分是iframe页面</span>
      <br />
      <span style="color: green">页面中部分是iframe页面</span>
      <br />
      <span style="color: blue">页面中部分是iframe页面</span>
      <br />
    </p>
    <p>
      <span style="color: red">页面中部分是iframe页面</span>
      <br />
      <span style="color: green">页面中部分是iframe页面</span>
      <br />
      <span style="color: blue">页面中部分是iframe页面</span>
      <br />
    </p>
  </div>
</template>

<script lang="ts">
  import { defineComponent } from 'vue';
  export default defineComponent({
    name: 'PartFrame',
    data() {
      return {
        inputData: '测试',
      };
    },
  });
</script>
