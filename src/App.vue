<script setup>
import { reactive } from 'vue'
import { ElMessage } from 'element-plus'

const form = reactive({
  account: '',
  password: '',
  remember: true,
})

const handleSubmit = () => {
  ElMessage.success(`Welcome back, ${form.account || 'guest'}!`)
}
</script>

<template>
  <main class="page-shell">
    <div class="orb orb-left"></div>
    <div class="orb orb-center"></div>
    <div class="orb orb-right"></div>

    <section class="glass-card">
      <div class="brand-row">
        <div class="brand-mark">MBL</div>
        <div>
          <p class="eyebrow">Vue Glassmorphism</p>
          <h1>Liquid Glass Sign In</h1>
        </div>
      </div>

      <p class="intro">
        Inspired by Apple's WWDC 2025 Liquid Glass direction, with floating depth, soft refraction, layered translucency, and rounded geometry.
      </p>

      <el-form class="login-form" label-position="top" @submit.prevent="handleSubmit">
        <el-form-item label="Email or username">
          <el-input
            v-model="form.account"
            size="large"
            placeholder="Enter your email or username"
          />
        </el-form-item>

        <el-form-item label="Password">
          <el-input
            v-model="form.password"
            size="large"
            type="password"
            show-password
            placeholder="Enter your password"
          />
        </el-form-item>

        <div class="form-meta">
          <el-checkbox v-model="form.remember">Keep me signed in for 7 days</el-checkbox>
          <a href="/" @click.prevent>Forgot password?</a>
        </div>

        <el-button class="submit-btn" type="primary" size="large" @click="handleSubmit">
          Sign In
        </el-button>
      </el-form>

      <div class="feature-grid">
        <article>
          <span>Material</span>
          <strong>Liquid Glass</strong>
        </article>
        <article>
          <span>Motion</span>
          <strong>Adaptive Glow</strong>
        </article>
        <article>
          <span>Surface</span>
          <strong>Soft Lens</strong>
        </article>
      </div>
    </section>
  </main>
</template>
