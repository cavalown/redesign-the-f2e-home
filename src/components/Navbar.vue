<template>
  <div class="navbar">
    <ul>
      <li><a href="#">The F2E</a></li>
      <li>
        <a href="https://2022.thef2e.com/news" target="_blank">關卡資訊</a>
      </li>
      <li>
        <a href="https://2022.thef2e.com/jobs" target="_blank">求職專區</a>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
};
</script>

<style lang="scss">
.navbar {
  ul {
    display: flex;
    justify-content: flex-end;
    gap: 34px;
    margin-right: 25px;
    padding-top: 50px;

    li {
      font-weight: 400;
      font-size: 16px;

      a {
        text-decoration: none;
        color: #2a99d9;
      }

      &:hover {
        font-weight: 500;
        font-size: 18px;
      }
    }
  }
}
</style>
