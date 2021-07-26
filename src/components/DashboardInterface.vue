<template>
  <div>
    <SideBar />  
    <div class="main">
    <NavBar />
    <b-container class="mt-5">
      <b-row>
        <b-col
          v-for="(statistic, index) in dashboardStatistics"
          :key="index"
          cols="3"
        >
          <b-card
            style="background-color: #fff; text-align:left; box-shadow: 1px 1px 2px 2px #f5f2f2; border: none; border-radius: 5px;"
          >
            <div class="mb-2">
              <p>{{ statistic.title }}</p>
            </div>
            <div>
              <h1 class="font-weight-bold">{{ statistic.description }}</h1>
            </div>
          </b-card>
        </b-col>
      </b-row>
      <br />
      <br />

      <b-card 
        style="background-color: #fff; text-align:center; box-shadow: 1px 1px 2px 2px #f5f2f2; border: none; border-radius: 5px; "
      >
        <b-row>
          <b-col cols="9">
            <div style="height: 100%; width: 1000;">
             <GChart type="LineChart" :data="chartData" :options="chartOptions" />
            </div>
          </b-col>
          <b-col style="border-left: 1px solid #f5f2f2;" cols="3">
            <b-row
              style="border-bottom: 1px solid #f5f2f2;"
              v-for="(statistic, index) in dashboardStatistics"
              :key="index"
            >
              <div class="mb-2">
                <p>
                  {{ statistic.item }}
                </p>
                <h3>{{ statistic.stat }}</h3>
              </div>
            </b-row>
          </b-col>
        </b-row>
      </b-card>
    </b-container>
  </div>
  </div>
  
</template>

<script>
import NavBar from "./NavbarComponent.vue";
import { GChart } from "vue-google-charts";
import SideBar from "./SidebarComponent.vue";

export default {
  name: "Home",
  components: {
    NavBar,
    GChart,
    SideBar,
  },
  data: () => ({
    dashboardStatistics: [
      {
        title: "Total Number of Customers",
        description: "23,596",
        item: "Customer Visits",
        stat: "65",
      },
      {
        title: "Total Number of Transactions",
        description: "3,456",
        item: "Transactions",
        stat: "23",
      },
      {
        title: "Total Sale Amount",
        description: "N4,456,787",
        item: "Sale Amount",
        stat: "N145,370",
      },
      {
        title: "Total Points Rewarded",
        description: "345",
        item: "Points Rewarded",
        stat: "43",
      },
    ],
    chartData: [
        ["Year", "Customer Visits"],
        ["Monday", 37],
        ["Tuesday", 47],
        ["Wednessday", 60],
        ["Thursday", 30],
        ["Friday",25],
        ["Saturday", 58],
        ["Sunday", 65],
      ],
      chartOptions: {
        chart: {
          title: "Company Performance",
          subtitle: "Customer Visits: weekly",
          curveType: "function",
        }
      }
  }),
};
</script>

<style scoped>
body {
  background-color: rgb(163, 86, 41);
}
.main {
  margin-left: 160px; /* Same as the width of the sidenav */
  padding: 0px 10px;
  
}
</style>
