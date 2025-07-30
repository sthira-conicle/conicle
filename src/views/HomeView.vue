<script setup lang="ts">

window.dataLayer = window.dataLayer || [];

function trigger_apply_tracking_filter() {
      window.dataLayer.push({
        event: "apply_tracking_filter",
        "filter_learner.count_filter": 5,
        "filter_learner.select_by": "by_condition",
        "filter_learner.select_learner": [],
        "filter_learner.department": [
          129,
          528
        ],
        "filter_learner.position": [
          1,
          21
        ],
        "filter_learner.level": [
          84,
          85,
          96
        ],
        "filter_learner.group": [
          134,
          133
        ],
        "filter_learner.onboard_date": [
          "04 Aug 2025",
          "20 Aug 2025"
        ],
        "filter_content.count_filter": 4,
        "filter_content.select_by": "by_condition",
        "filter_content.select_content": [],
        "filter_content.category": [
          140,
          144
        ],
        "filter_content.content_type": [
          3,
          4
        ],
        "filter_content.content_provider": [
          2,
          3
        ],
        "filter_content.content_requirement": [
          2
        ],
        "filter_learning_period.count_filter": 1,
        "filter_learning_period.select_by": "is_learning_progress",
        "filter_learning_period.period": 4,
        "filter_learning_period.period_date": [
          "11 Jul 2025",
          "18 Jul 2025"
        ],
        "filter_learning_condition.count_filter": 2,
        "filter_learning_condition.adding_method": [
          1
        ],
        "filter_learning_condition.learning_status": [
          4,
          2
        ]
      });

}

</script>

<template>
  <div class="home-body">
    <div class="button-container">
      <button tag="click_me_test">Click me</button>
    </div>
    <form id="tracking_filter" @submit.prevent="trigger_apply_tracking_filter">
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