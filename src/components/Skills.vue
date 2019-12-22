<template>
  <div class="cont flex flex-col">
    <div class="h-9/10 flex bg-gray-400 items-end">
      <div
        class="flex-1  bg-blue-200 text"
        v-bind:style="{ height: dev.percentage + '%' }"
        v-for="(dev, index) in development"
        v-bind:key="index"
      >
        <div class="text-center align-text-middle h-full flex justify-center">
          <h1 class="my-auto">{{ dev.name }}</h1>
        </div>
      </div>
      <div
        v-for="(des, index) in design"
        v-bind:style="{ height: des.percentage + '%' }"
        v-bind:key="index"
        class="flex-1 bg-green-200 text"
      >
        <div class="text-center align-text-middle h-full flex justify-center">
          <h1 class="my-auto">{{ des.name }}</h1>
        </div>
      </div>
    </div>

    <div class="h-1/10 w-full bg-blue-300 flex flex-row">
      <div
        v-for="(skill, index) in skills"
        v-bind:key="index"
        class="bg-red-200"
        v-bind:class="[skill.apply ? 'bg-orange-400' : 'bg-yellow-400']"
        v-bind:style="[
          skill.apply ? { width: findPercentage() + '%' } : { flex: 'auto' }
        ]"
      >
        <div class="text-center align-text-middle h-full flex justify-center">
          <h1 class="my-auto">{{ skill.name }}</h1>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Skills",
  components: {},
  data() {
    return {
      development: [
        { name: "React", percentage: 80 },
        { name: "Vue", percentage: 70 },
        { name: "GraphQL", percentage: 65 },
        { name: "MySQL", percentage: 80 }
      ],
      design: [
        { name: "Illustrator", percentage: 65 },
        { name: "Photoshop", percentage: 80 }
      ],
      skills: [
        { name: "development", apply: true },
        { name: "design", apply: false }
      ]
    };
  },
  methods: {
    findPercentage: function() {
      const skillsLength = this.development.length + this.design.length;
      const widthResult = (this.development.length * 100) / skillsLength;
      console.log(widthResult);
      return widthResult;
    }
  }
};
</script>

<style lang="scss">
.cont {
  height: 400px;
}
h1 {
}
.columnWidth {
}
.columnHeight {
  height: 100%;
}
</style>
