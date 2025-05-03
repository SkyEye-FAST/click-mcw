<template>
  <div class="container">
    <nav class="nav-links">
      <div class="left-links">
        <a href="https://zh.minecraft.wiki/w/方块">方块</a>
        <a href="https://zh.minecraft.wiki/w/物品">物品</a>
        <a href="https://zh.minecraft.wiki/w/生物">生物</a>
        <a href="https://zh.minecraft.wiki/w/合成">合成</a>
        <a href="https://zh.minecraft.wiki/w/酿造">酿造</a>
        <a href="https://zh.minecraft.wiki/w/附魔">附魔</a>
        <a href="https://zh.minecraft.wiki/w/交易">交易</a>
        <a href="https://zh.minecraft.wiki/w/教程">教程</a>
        <a href="https://zh.minecraft.wiki/w/Category:游戏内容">更多</a>
      </div>
      <div class="right-links">
        <a href="https://zh.minecraft.wiki/w/Minecraft">Minecraft</a>
        <a href="https://zh.minecraft.wiki/w/中国版">中国版</a>
        <a href="https://zh.minecraft.wiki/w/Minecraft_Dungeons">Dungeons</a>
        <a href="https://zh.minecraft.wiki/w/Minecraft_Legends">Legends</a>
        <a href="https://zh.minecraft.wiki/w/Minecraft_Earth">Earth</a>
        <a href="https://zh.minecraft.wiki/w/Minecraft:_Story_Mode">Story Mode</a>
      </div>
    </nav>
    <div class="search-box">
      <img src="@/assets/Minecraft_Wiki_header.svg" alt="Minecraft Wiki Logo" class="logo" />
      <div class="search-input">
        <input
          type="text"
          v-model="searchQuery"
          @keyup.enter="performSearch"
          placeholder="搜索 Minecraft Wiki…"
        />
        <button @click="performSearch">搜索</button>
      </div>
      <div class="hot-search">
        <a href="https://zh.minecraft.wiki/w/Special:SearchDigest" class="hot-search-title">
          MCW热搜 〉
        </a>
        <div class="hot-search-items">
          <div class="hot-search-column">
            <a href="https://zh.minecraft.wiki/w/2025夏季小更新" class="hot-item">
              <span class="hot-rank">1</span>
              2025夏季小更新
            </a>
            <a href="https://zh.minecraft.wiki/w/春意盎然" class="hot-item">
              <span class="hot-rank">2</span>
              春意盎然
            </a>
            <a href="https://zh.minecraft.wiki/w/苍园觉醒" class="hot-item">
              <span class="hot-rank">3</span>
              苍园觉醒
            </a>
            <a href="https://zh.minecraft.wiki/w/快乐恶魂" class="hot-item">
              <span class="hot-rank">4</span>
              快乐恶魂
            </a>
            <a href="https://zh.minecraft.wiki/w/挽具" class="hot-item">
              <span class="hot-rank">5</span>
              挽具
            </a>
          </div>
          <div class="hot-search-column">
            <a href="https://zh.minecraft.wiki/w/实验性玩法" class="hot-item">
              <span class="hot-rank">6</span>
              实验性玩法
            </a>
            <a href="https://zh.minecraft.wiki/w/语言" class="hot-item">
              <span class="hot-rank">7</span>
              语言
            </a>
            <a href="https://zh.minecraft.wiki/w/Mojang_Studios" class="hot-item">
              <span class="hot-rank">8</span>
              Mojang Studios
            </a>
            <a href="https://zh.minecraft.wiki/w/资源包" class="hot-item">
              <span class="hot-rank">9</span>
              资源包
            </a>
            <a href="https://zh.minecraft.wiki/w/红石电路" class="hot-item">
              <span class="hot-rank">10</span>
              红石电路
            </a>
          </div>
        </div>
      </div>
    </div>
    <div class="disclaimer">本站并非Minecraft官方网站，与Mojang和微软亦无从属关系。</div>
    <div class="footer-links">
      <a href="https://zh.minecraft.wiki/w/Minecraft_Wiki:关于">关于Minecraft Wiki</a>
      <span class="separator">·</span>
      <a href="https://minecraft.wiki/w/Minecraft_Wiki:About">About Minecraft Wiki</a>
      <span class="separator">·</span>
      <a href="https://zh.minecraft.wiki/w/Help:如何帮助">帮助中心</a>
      <span class="separator">·</span>
      <a href="https://weirdgloop.org/privacy">隐私政策</a>
      <span class="separator">·</span>
      <a href="https://zh.minecraft.wiki/w/Minecraft_Wiki:著作权">著作权</a>
      <span class="separator">·</span>
      <a href="https://zh.minecraft.wiki/w/Minecraft_Wiki:一般免责声明">一般免责声明</a>
      <span class="separator">·</span>
      <a href="https://weirdgloop.org/terms">使用条款</a>
      <span class="separator">·</span>
      <a href="https://zh.minecraft.wiki/w/Minecraft_Wiki:Wiki条例">Wiki条例</a>
      <span class="separator">·</span>
      © 2025 SkyEye_FAST
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'

const searchQuery = ref('')

const performSearch = () => {
  if (searchQuery.value.trim()) {
    window.location.href = `https://zh.minecraft.wiki/w/Special:Search?search=${encodeURIComponent(searchQuery.value)}`
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.container {
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: #fff;
}

.search-box {
  text-align: center;
  transform: translateY(-10%);
}

.logo {
  width: 270px;
  margin-bottom: 20px;
  user-select: none;
}

.search-input {
  display: flex;
  justify-content: center;
  position: relative;
  width: 654px;
  margin: 0 auto;
}

input {
  width: 550px;
  height: 44px;
  padding: 0 16px;
  font-size: 16px;
  border: 2px solid #c4c7ce;
  border-radius: 10px 0 0 10px;
  outline: none;
  box-shadow: none;
  transition: all 0.2s;
}

input:hover {
  border-color: #a7aab5;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
}

input:focus {
  border-color: #4e6ef2;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
}

button {
  width: 104px;
  height: 44px;
  background-color: #4e6ef2;
  color: white;
  border: none;
  border-radius: 0 10px 10px 0;
  cursor: pointer;
  font-size: 17px;
  font-weight: 500;
  transition: all 0.2s;
}

button:hover {
  background-color: #4662d9;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
}

.search-input::before {
  content: '';
  position: absolute;
  top: -16px;
  width: 100%;
  height: 16px;
}

.search-input::after {
  content: '';
  position: absolute;
  bottom: -16px;
  width: 100%;
  height: 16px;
}

.nav-links {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  display: flex;
  justify-content: space-between;
  padding: 15px 20px;
  font-size: 13px;
}

.left-links,
.right-links {
  display: flex;
  gap: 25px;
}

.nav-links a {
  color: #222;
  text-decoration: none;
  transition: color 0.2s;
}

.nav-links a:hover {
  color: #4e6ef2;
}

.footer-links {
  position: fixed;
  bottom: 20px;
  left: 0;
  right: 0;
  text-align: center;
  font-size: 12px;
  color: #999;
}

.footer-links a {
  color: #999;
  text-decoration: none;
  transition: color 0.2s;
}

.footer-links a:hover {
  color: #4e6ef2;
}

.separator {
  margin: 0 8px;
  color: #999;
}

.disclaimer {
  position: fixed;
  bottom: 50px;
  left: 0;
  right: 0;
  text-align: center;
  font-size: 12px;
  color: #999;
}

.hot-search {
  margin-top: 30px;
  width: 654px;
  margin-left: auto;
  margin-right: auto;
  text-align: left;
}

.hot-search-title {
  font-size: 16px;
  color: #666;
  margin-bottom: 12px;
  padding-left: 5px;
  font-weight: bold;
  text-decoration: none;
  display: inline-block;
}

.hot-search-title:hover {
  color: #4e6ef2;
}

.hot-search-items {
  display: flex;
  gap: 30px;
}

.hot-search-column {
  flex: 1;
  display: flex;
  flex-direction: column;
  gap: 12px;
}

.hot-item {
  display: flex;
  align-items: center;
  text-decoration: none;
  color: #626675;
  font-size: 14px;
  padding: 5px;
  transition: all 0.2s;
}

.hot-item:hover {
  background-color: #f5f5f6;
  border-radius: 6px;
}

.hot-rank {
  width: 18px;
  height: 18px;
  line-height: 18px;
  text-align: center;
  border-radius: 2px;
  font-size: 13px;
  margin-right: 12px;
  font-weight: 500;
}

.hot-item .hot-rank {
  color: #666;
  background: #f4f4f4;
}

.hot-search-column:first-child .hot-item:nth-child(1) .hot-rank {
  color: #fff;
  background: #f1404b;
}

.hot-search-column:first-child .hot-item:nth-child(2) .hot-rank {
  color: #fff;
  background: #ff6a3c;
}

.hot-search-column:first-child .hot-item:nth-child(3) .hot-rank {
  color: #fff;
  background: #faa90e;
}
</style>
