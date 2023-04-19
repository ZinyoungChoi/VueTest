<template>
  <img alt="Vue logo" src="./assets/logo.png" class="logo" />
  <div class="container">
    <div class="tab_button">
      <h2>New Jeans</h2>
    </div>
    <input type="text" @input="search" placeholder="검색어를 입력하세요.">
    <NewJeans :Members="Member" v-for="Member in Members" :key="Member" />
  </div>
</template>

<script>
import NewJeans from "./components/NewJeans.vue";
import List from "./assets/data/List";

export default {
  name: "App",
  data() {
    return {
      Members: List,
      text : "",
      MembersCopy : List,
    };
  },
  methods: {
    search(e){
      const text = e.target.value;
      console.log(text)
      if(text.length == 0){
        this.Members = this.MembersCopy
      } else {
        this.Members = this.MembersCopy.filter(data => data.name.match(new RegExp(text, "i")))
      }
      console.log(this.Members)
    }
  },
  components: {
    NewJeans,
  },
};
</script>
