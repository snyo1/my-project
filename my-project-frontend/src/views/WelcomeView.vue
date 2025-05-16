<script setup>

</script>

<template>
  <div style="width: 100vw;height: 100vh;overflow: hidden;display: flex">
    <div style="flex: 1;background-color: black">
      <el-image style="width: 100%;height: 100%" fit="cover"
          src="https://img-baofun.zhhainiao.com/fs/a4b3f3ed657fbed8fddb4205f0c95c47.jpg"/>
    </div>

    <div class="welcome-title">
      <div style="font-size: 30px;font-weight:bold">欢迎来到银月snyo学习的小项目</div>
      <div style="margin-top: 10px">不过所谓幸福或是不幸 都取决于你的内心 心中有枷锁 那无论在哪儿都是牢笼</div>
      <div style="margin-top: 5px">世界很大 生活很大 没必要死缠烂打纠缠不休 生命中应该还有很多别的美好等着你去追求</div>
    </div>

    <div class="right-card">
      <router-view/>
    </div>
  </div>
</template>

<style scoped>
.welcome-title{
  position: absolute;
  bottom: 30px;
  left: 30px;
  color: white;
  text-shadow: 0 0 10px black;
}

.right-card{
  width: 400px;
  z-index: 1;
  background-color: white;
}
</style>