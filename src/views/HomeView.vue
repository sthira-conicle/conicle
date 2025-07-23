<script setup lang="ts">
</script>

<template>
  <div class="home-body">
    <div class="button-container">
      <button id="click_me">Click me</button>
    </div>
    <form>
      <h2>Learner</h2>
      <label for="dept">Department</label><br>
      <input type="text" id="dept" name="dept" value="product"><br>
      <label for="pos">Position</label><br>
      <input type="text" id="pos" name="pos" value="uxui"><br>
      <br><hr><br>
      <h2>Learning period</h2>
      <p>Select by</p>
      <input type="radio" id="progress" name="select_by" value="progress">
      <label for="progress">Has learning progress during</label><br>
      <input type="radio" id="added" name="select_by" value="added">
      <label for="added">Enrolled or assigned during</label><br>
      <input type="radio" id="finished" name="select_by" value="finished">
      <label for="finished">Finished during</label>
      <br><br><hr><br>
      <input type="submit" value="Apply">
    </form>
  </div>
</template>

<style>
.home-body {
  width: 100%;
  display: flex;
  gap: 40px;
  flex-direction: row;
  align-items: center;
}
.home-body .button-container {
  display: flex;
  justify-content:center;
  flex-grow: 1;
}
.home-body form {
  flex-grow: 0;
}
</style>