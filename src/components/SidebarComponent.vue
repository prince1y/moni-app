<template>
   
  <div class="sidebar" >
      <a href="#" id="home">MONI</a>
  <a href="#dashboard"><i class="fa fa-home" aria-hidden="true"></i> Dashboard</a>
  <a href="#products"><i class="fa fa-cube" aria-hidden="true"></i>
  Products</a>
  <a href="#ads"><i class="fa fa-pie-chart" aria-hidden="true"></i> Ads</a>
  <a href="#loyalty"><i class="fa fa-gift" aria-hidden="true"></i> Loyalty</a>
  <a href="#customers"><i class="fa fa-users" aria-hidden="true"></i> Customers</a>
  <a href="#settings"><i class="fa fa-cog" aria-hidden="true"></i> Settings</a>
  <a href="#logout"><i class="fa fa-share-square-o" aria-hidden="true"></i> Logout</a>
  </div>

</template>

<script>
export default {
    name: 'SidebarComponent',
}
</script>

<style>
.sidebar {
  height: 100%;
  width: 160px;
  position: fixed;
  z-index: 1;
  top: 0;
  left: 0;
  background-color: rgba(41, 70, 163, 0.808);
  overflow-x: hidden;
  padding-top: 16px;
}

.sidebar a {
  padding: 6px 8px 20px 16px;
  text-decoration: none;
  font-size: 15px;
  color: #e9e9e9;
  display: block;
}

.sidebar a:hover {
  color: #f1f1f1;
}

#home {
    font-size: 20px;
    text-align: center;
    padding-bottom: 40px;
}
@media screen and (max-height: 450px) {
  .sidebar {padding-top: 15px;}
  .sidebar a {font-size: 18px;}
}
</style>