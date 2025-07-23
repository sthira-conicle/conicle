<script setup lang="ts">
</script>

<template>
  <div class="home-body">
    <div class="button-container">
      <button id="click_me" tag="click_me_test">Click me</button>
    </div>
    <form id="filter">
      <h2>Learner</h2>
      <label for="department">Department</label><br>
      <input type="text" id="department" name="department" value="product"><br>
      <label for="position">Position</label><br>
      <input type="text" id="position" name="position" value="uxui"><br>
      <br><hr><br>
      <h2>Learning period</h2>
      <p>Select by</p>
      <input type="radio" id="progress" name="learning_period" value="progress">
      <label for="progress">Has learning progress during</label><br>
      <input type="radio" id="added" name="learning_period" value="added">
      <label for="added">Enrolled or assigned during</label><br>
      <input type="radio" id="finished" name="learning_period" value="finished">
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