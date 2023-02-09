<template>
  <div class="container-fluid content pt-3">
    <div class="row">
      {{ userId }} {{ jsonData }}
      <div v-for="user in users" v-bind:key="user.id">
        {{ user.address.suite }}
      </div>
    </div>
  </div>
  <div>
    <p>{{ message }}</p>
    <p>Last update: {{ time }}</p>
  </div>
  <div id="app">
    {{ forceData }}
    <div @click="downloadFile()" class="np-btn btn-success">Export to excel</div>
    <div @click="BuildFile(this.getJson)" class="np-btn btn-warning">Build to excel</div>
    <!-- <div v-for="(investor, i) in investorsList" :key="i">
      <div class="np-list">
        {{ investor.id + 1 }}. {{ investor.name }}, {{ investor.email }},
        {{ investor.investment }}
      </div>
    </div> -->
    {{ setJson }} {{ getJson }}
  </div>
</template>



<script>
import exportFromJSON from "export-from-json";
export default {
  name: "App",
  props: {
    getJson: {
      type: Object
    }
  },
  created() {
    // this.id = this.getJson.return.data.id;
    // this.arr = this.id.split("-");
    // this.forceData = (this.arr[0] + this.arr[1] + this.arr[2]);
  },
  methods: {

    BuildFile(getjson) {
      this.setJson = getjson
      if (this.setJson != null) {
        this.setJson = 1
      } else {
        this.setJson = 2
      }
      this.forceData = 'Reset'
    },
    downloadFile() {
      this.id = this.getJson.return.data.id;
      this.arr = this.id.split("-");
      this.forceData = (this.arr[0] + " " + this.arr[1] + " " + this.arr[2]);

      const data = this.getJson.return.data.id;
      const fileName = "agv-default-export-data";
      const exportType = exportFromJSON.types.csv;

      if (data) exportFromJSON({ data, fileName, exportType });
    },
  },
  data() {
    return {
      setJson: null,
      forceData: 'Default',
      id: '',
      arr: '',
      setList: [
        {
          id: 0,
          name: "annlists",
        },
        {
          ui: 1,
          name: "Mattra",
        }
      ],
      investorsList: [
        {
          id: 0,
          name: "Gautam",
          email: "gautam@example.com",
          investment: "Stocks",
        },
        {
          id: 1,
          name: "Sam",
          email: "sam@example.com",
          investment: "Bonds",
        },
        {
          id: 2,
          name: "Tim",
          email: "tim@example.com",
          investment: "Options",
        },
        {
          id: 3,
          name: "Kim",
          email: "kim@example.com",
          investment: "Stocks",
        },
        {
          id: 4,
          name: "John",
          email: "john@example.com",
          investment: "Options",
        },
        {
          id: 5,
          name: "Lee",
          email: "lee@example.com",
          investment: "Stocks",
        },
        {
          id: 6,
          name: "Charlotte",
          email: "charlotte@example.com",
          investment: "Options",
        },
        {
          id: 7,
          name: "Amy",
          email: "amy@example.com",
          investment: "Stocks",
        },
        {
          id: 8,
          name: "Mark",
          email: "mark@example.com",
          investment: "Bonds",
        },
        {
          id: 9,
          name: "Rose",
          email: "rose@example.com",
          investment: "Stocks",
        },
      ],
    };
  },
};
</script>
<style>
.np-list {
  padding: 2px 8px;
  margin: 12px 8px;
  border: 1px solid #107fda;
  background: #ffffff;
  border-radius: 6px;
  color: #107fda;
}

.np-btn {
  padding: 2px 8px;
  margin: 12px 8px;
  border: 1px solid #107fda;
  width: 170px;
  background: #107fda;
  border-radius: 6px;
  color: #ffffff;
  cursor: pointer;
}
</style>

