<template>
  <div>
    <ul class="breadcrumb">
      <li class="item">
        <a href="#" class="str">lorem</a>
      </li>
      <li class="item">
        <a href="#" class="str">lorem</a>
      </li>
      <li class="item">
        <a href="#" class="str">lorem</a>
      </li>
    </ul>
  </div>
</template>


<style>
* {
  margin: 0;
  padding: 0;
  list-style: none;
  box-sizing: border-box;
}
a {
  text-decoration: none;
}

/* breadcrumb */
.breadcrumb {
  display: flex;
  align-items: center;
}
.breadcrumb > .item ~ .item {
  margin-left: 20px;
}
.breadcrumb > .item ~ .item::before {
  content: ">";
  margin-right: 20px;
}
/* breadcrumb end */
</style>