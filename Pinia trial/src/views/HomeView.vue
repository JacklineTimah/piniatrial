<script setup>

</script>

<template>
<main>
    <div class="Box">
      <div class="tasks">
        <h1>Manage your tasks effectively</h1>
        <p>Modern todo list application to help you track your activities and stay productive.</p>
      <button class="start">Get started</button>
      </div>
      <img src="../assets/hero-illustration.png"/>
    </div>
</main>
</template>

<style scoped>

.Box{
  display: flex;
  padding-top: 50px;
  padding: 27px 370px 0px 370px;
}
.tasks{
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  gap: 15px;
}
.tasks h1{
color: #000;
font-family: Inter;
font-size: 40px;
font-style: normal;
font-weight: 600;
letter-spacing: -1.2px;
width: 324px;
gap: 12px;
}
.tasks p{
color: #000;
font-family: Inter;
font-size: 16px;
font-style: normal;
font-weight: 400;
line-height: 160%;
gap: 12px;
 /* 25.6px */
}
.start{
border-radius: 8px;
background: #5222D0;
display: inline-flex;
padding: 8px 24px;
align-items: flex-start;
gap: 10px;
color: white;

}
</style>

