<template>
  <div class="features-section">
    <div class="header">
      <img src="@/assets/list.png" alt="Fashion and Visual Icon" class="main-icon" />
      <h1 class="title">Your Task Management Assistant</h1>
      <p>Bring your productivity to its peak</p>
    </div>
    <div class="features">
      <div class="feature">
        <img src="@/assets/add.png" alt="Add tasks Icon" />
        <p>Add tasks</p>
      </div>
      <div class="feature">
        <img src="@/assets/done.png" alt="Mark as done Icon" />
        <p>Mark as done</p>
      </div>
      <div class="feature">
        <img src="@/assets/edit.png" alt="Edit tasks Icon" />
        <p>Edit tasks</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
}
</script>

<style>

.title{
    font-size: 20px;
    font-weight: bold;
    text-align: center;
  }
  .features-section {
    width: 100%;
    box-sizing: border-box;
    text-align: center;
    padding: 50px;
    background-color: #fafafa;
  }
  
  .header {
    margin-bottom: 20px;
  }
  
  .main-icon {
    display: block ;
    margin: 20px auto;
    height: 50px;

  }
  
  .features {
    display: flex;
    justify-content: space-around;
  }
  
  .feature {
    text-align: center;
  }
  
  .feature img {
    width: 40px;
    height: 40px;
  }
  
  .feature p {
    margin-top: 10px;
    font-size: 16px;
  }
  </style>