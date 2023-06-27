
<template>
  <div class="">
    <div>{{ greeting }} {{ name }}</div>
  </div>
  <div v-text="channel"></div>
  <div v-html="channel"></div>
  <div v-html="hack"></div>
  <h3 :id="headingId">Heading</h3  >
  <button :disabled="isDisabled">Bind</button>
  <h2 class="underline">Underline Text</h2>
  <h2 class="underline" :class="status">Status</h2>
  <h2 :class="isPromoted && 'promoted'">Promoted Movie</h2>
  <h2 :class="isSoldOut ? 'sold-out' : 'new' ">Sold Out? Movie</h2>
  <h2 :class="['new', 'promoted', 'underline']">Newly promoted movie</h2>
  <h2 :class="[isPromoted && 'promoted', isSoldOut ? 'sold-out' : 'new']">Array conditional movie</h2>
  <h2 :class="{
    promoted: isPromoted,
    new: ! isSoldOut,
    'sold-out': isSoldOut,
  }">Object conditional movie</h2>
  <h2 :style="{ 
    color: highLightColor,
    fontSize: headerSize + 'px',
    padding: hearderPadding + 'px',
   }">Inline Style</h2>
  <h2 :style="headerStyleObject">Style Object</h2>
  <div :style="[baseStyleObject, successStyleObject]">Success Style</div>
  <div :style="[baseStyleObject, dangerStyleObject]">Danger Style</div>
</template>

<script>
  export default {
    name: "App",
    data() {
      return {
        greeting: "Hello I am",
        name: "David",
        channel: "<b>Coding with Vue</b>",
        hack:`<a href="#" onclick="alert('You have been hacked!!')">You win price!</a>`,
        headingId: "heading",
        isDisabled: false,
        status: "success",
        isPromoted: true,
        isSoldOut: true ,
        highLightColor: "orange",
        headerSize: 50,
        hearderPadding: 20,
        headerStyleObject: {
          color: 'orange',
          fontSize: '50px',
          padding: '20px',
        },
        baseStyleObject: {
          fontSize: '50px',
          padding: '20px',
        },
        successStyleObject: {
          color:'green',
          backgroundColor: 'lightgreen',
          border: '3px solid blue', 
        },
        dangerStyleObject: {
          color:'darkred',
          backgroundColor: 'red',
          border: '3px solid darkred ', 
        }
      };
    },
  };
</script>

<style>
  div {
    text-align: center;
  }
  .underline {
    text-decoration: underline;
  }
  .promoted{
    font-style: italic;
  }
  .new {
    color: blue;
  }
  .sold-out {
    color: red;
  }
</style>
