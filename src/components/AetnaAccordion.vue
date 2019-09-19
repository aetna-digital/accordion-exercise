<template>
  <div>
    <div class="accordion-item" v-for="item in items"
         :key="item.index"
         v-bind:class="[{ expanded: item.expanded }]">
      <h2 class="accordion-item-title" v-bind:class="[{ expanded: item.expanded }]" v-on:click="toggleItem(item)">{{ item.title }}</h2>
      <div v-show="item.expanded" class="fadeIn">
        <div class="accordion-item-body">
          <div class="accordion-image">
            <div class="image"></div>
          </div>
          <p>{{ item.content }}</p>
        </div>
        <a class="accordion-item-link" target="blank" :href="item.link">{{ item.link }}</a>
      </div>
    </div>
  </div>
</template>
<script>
  export default {
    name: "AetnaAccordion",
    props: {
      /**
       * Array of items
       * Object style {title: string, content: string, link: string, expanded: boolean}
       */
      items: {
        type: Array,
        required: true
      }
    },
    methods: {
      toggleItem: function(item){
        item.expanded = !item.expanded;
      }
    }
  }
</script>
<style lang="scss">

  //  I have used very specific class names (as this is a reusable component) as to avoid class-name inheritance overrides in larger UI's css (i.e. bootstrap)
  //  to ensure we have this styled correctly. 

  .accordion-item {
    margin: 29px 0 0 0;
    border-top: 5px solid #ddd;
    background: #fff;

    .accordion-item-title {
      font-size: 18px;
      font-weight: bold;
      cursor: pointer;
      padding: 25px 0 25px 50px;
      margin: 0;
      background: url('../assets/icon-expand.svg') 14px 14px no-repeat;
      background-position: right 50px center;
      background-size: 14px 14px;

      &.expanded {
        background: url('../assets/icon-collapse.svg') 14px 14px no-repeat;
        background-position: right 50px center;
        background-size: 14px 14px;
      }
    }

    .accordion-item-body {
      padding: 0 50px 50px;
      display: table;
      
      .accordion-image {
        @media only screen and (max-width: 640px) {
          display: table-row;
        }

        display: table-cell;

        .image {
          width: 77px;
          height: 77px;
          background-color: #fcb775;
        }

        @media only screen and (max-width: 768px) {
          .image {
            width: 30px;
            height: 30px;
          }
        }

        @media only screen and (max-width: 640px) {
          .image {
            width: 77px;
            height: 77px;
          }
        }
      }

      p {
        font-size: 16px;
        line-height: 26px;
        padding-left: 47px;
        display: table-cell;
        vertical-align: top;

        @media only screen and (max-width: 640px) {
          padding: 10px 0 0 0;
        }
      }
    }

    .accordion-item-link {
      color: #d80b6d;
      font-weight: bold;
      display: inline-block;
      margin: 0 0 50px 175px;
      text-decoration: none;

      @media only screen and (max-width: 640px) {
        margin: 0 0 50px 50px;
      }

      &:hover {
        text-decoration: underline;
      }

      &:after {
        display: block;
        content: ' ';
        background-image: url('../assets/icon-right.svg');
        background-size: 14px 14px;
        margin: 2px 0 0 10px;
        float: right;
        height: 14px;
        width: 14px;
      }
    }
  }
</style>