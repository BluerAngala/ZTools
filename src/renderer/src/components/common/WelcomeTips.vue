<template>
  <div class="welcome-tips">
    <div class="tips-grid">
      <div v-for="tip in tips" :key="tip.key" class="tip-item">
        <div class="tip-keys">
          <span v-for="(key, i) in tip.keys" :key="i" class="tip-key">{{ key }}</span>
        </div>
        <span class="tip-label">{{ tip.label }}</span>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { computed } from 'vue'

const isMac = window.ztools?.getPlatform?.() === 'darwin'
const mod = computed(() => (isMac ? '⌘' : 'Ctrl'))

const tips = computed(() => [
  { key: 'paste', keys: ['⌘', 'V'], label: '粘贴文件或图片' },
  { key: 'filter', keys: [mod.value, 'F'], label: '二次筛选' },
  { key: 'setting', keys: [mod.value, ','], label: '打开设置' },
  { key: 'tab', keys: ['Tab'], label: '快速执行指令' }
])
</script>

<style scoped>
.welcome-tips {
  padding: 8px 12px 4px;
}

.tips-grid {
  display: flex;
  flex-wrap: wrap;
  gap: 6px 16px;
}

.tip-item {
  display: inline-flex;
  align-items: center;
  gap: 6px;
  opacity: 0.45;
  transition: opacity 0.15s;
}

.tip-item:hover {
  opacity: 0.75;
}

.tip-keys {
  display: inline-flex;
  gap: 2px;
}

.tip-key {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  min-width: 18px;
  height: 20px;
  padding: 0 5px;
  font-size: 11px;
  font-weight: 500;
  color: var(--text-color);
  background: var(--control-bg);
  border: 1px solid color-mix(in srgb, var(--text-color) 12%, transparent);
  border-radius: 4px;
  line-height: 1;
}

.tip-label {
  font-size: 12px;
  color: var(--text-color);
}
</style>
