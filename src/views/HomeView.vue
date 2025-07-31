<script setup lang="ts">

function generateRandomString(length) {
  return Math.random().toString(36).substring(2, 2 + length);
}

window.dataLayer = window.dataLayer || [];

function push_batch_event(data, category, prefix) {
  for (const key in data) {
    window.dataLayer.push({
      event: prefix ? `${prefix}${key}` : `${key}`,
      [key]: data[key],
      ...(category ? { event_category: category } : {})
    });
  }
}

function trigger_events() {

push_batch_event({
  "learner_count_filter": Math.round(Math.random()*4)+1,
  "learner_select_by": generateRandomString(Math.round(Math.random()*7)+3),
  "learner_select_learner": generateRandomString(Math.round(Math.random()*7)+3),
  "learner_department": generateRandomString(Math.round(Math.random()*7)+3),
  "learner_position": generateRandomString(Math.round(Math.random()*7)+3),
  "learner_level": generateRandomString(Math.round(Math.random()*7)+3),
  "learner_group": generateRandomString(Math.round(Math.random()*7)+3),
  "learner_onboard_date": generateRandomString(Math.round(Math.random()*7)+3),
  "content_count_filter": Math.round(Math.random()*3)+1,
  "content_select_by": generateRandomString(Math.round(Math.random()*7)+3),
  "content_select_content": generateRandomString(Math.round(Math.random()*7)+3),
  "content_category": generateRandomString(Math.round(Math.random()*7)+3),
  "content_content_type": generateRandomString(Math.round(Math.random()*7)+3),
  "content_content_provider": generateRandomString(Math.round(Math.random()*7)+3),
  "content_content_requirement": generateRandomString(Math.round(Math.random()*7)+3),
  "learning_period_count_filter": generateRandomString(Math.round(Math.random()*7)+3),
  "learning_period_select_by": generateRandomString(Math.round(Math.random()*7)+3),
  "learning_period_period": Math.round(Math.random()*3)+1,
  "learning_period_period_date": generateRandomString(Math.round(Math.random()*7)+3),
  "learning_condition_count_filter": Math.round(Math.random()*1)+1,
  "learning_condition_adding_method": generateRandomString(Math.round(Math.random()*7)+3),
  "learning_condition_status": generateRandomString(Math.round(Math.random()*7)+3)
},'tracking_filter','apply_filter_');

push_batch_event({
  "hide_leraner_not_active": Math.round(Math.random()) ? true : false,
  "include_sub_content": Math.round(Math.random()) ? true : false
},'tracking_option','apply_option_');

push_batch_event({
  "admin": Math.round(Math.random()) ? true : false,
  "manager": Math.round(Math.random()) ? true : false,
  "one_level": Math.round(Math.random()) ? true : false,
  "full_line": Math.round(Math.random()) ? true : false
},'tracking_view_as','apply_view_as_');

push_batch_event({
  "learning_status": Math.round(Math.random()) ? true : false,
  "completion_date": Math.round(Math.random()) ? true : false
},'tracking_table_customization','apply_table_customization_');

}

</script>

<template>
  <div class="home-body">
    <div class="button-container">
      <button tag="click_me_test">Click me</button>
    </div>
    <form id="tracking_filter" @submit.prevent="trigger_events">
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