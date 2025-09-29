<script setup lang="ts">
const metrics = [
  {
    title: 'Components',
    value: '50+',
    description: 'Pre-styled building blocks ready to mix & match.',
  },
  {
    title: 'Themes',
    value: '30+',
    description: 'Switch instantly between curated color palettes.',
  },
  {
    title: 'Time saved',
    value: '8h',
    description: 'Average setup time reclaimed per project launch.',
  },
]

const featureCards = [
  {
    title: 'Hero + Call to Action',
    description: 'Combine layout primitives with animated buttons for bold first impressions.',
    badges: ['hero', 'btn', 'badge'],
  },
  {
    title: 'Data Displays',
    description: 'Display KPIs with responsive `stats`, progress bars, and rich mockups.',
    badges: ['stats', 'mockup'],
  },
  {
    title: 'Interactive Elements',
    description: 'Use accordions, drawers, dropdowns, and tabs without wiring up custom styles.',
    badges: ['collapse', 'dropdown', 'tabs'],
  },
]

const steps = [
  {
    label: 'Install dependencies',
    command: 'pnpm install',
  },
  {
    label: 'Start dev server',
    command: 'pnpm run dev',
  },
  {
    label: 'Customize theme',
    command: 'tailwind.config.ts',
  },
]
</script>

<template>
  <div class="min-h-screen bg-base-200 text-base-content">
    <div class="mx-auto flex w-full max-w-6xl flex-col gap-12 px-4 pb-16 pt-8 sm:gap-16 lg:px-8">
      <header class="navbar rounded-box bg-base-100/90 shadow-lg backdrop-blur">
        <div class="navbar-start gap-3">
          <div class="avatar">
            <div class="w-12 rounded-full bg-primary text-primary-content">
              <span class="flex h-full items-center justify-center text-xl font-black">d</span>
            </div>
          </div>
          <div>
            <p class="text-xl font-semibold leading-tight">daisyUI Starter</p>
            <p class="text-sm opacity-60">Vue + Tailwind template showcase</p>
          </div>
        </div>
        
        <div class="navbar-end hidden sm:flex gap-2">
          <a class="btn btn-ghost btn-sm" href="https://github.com/saadeghi/daisyui" target="_blank" rel="noopener">GitHub</a>
          <a class="btn btn-sm btn-primary" href="https://daisyui.com/components/" target="_blank" rel="noopener">View docs</a>
        </div>
       
      </header>

      <section class="hero rounded-3xl bg-base-100 shadow-xl">
        <div class="hero-content flex-col-reverse gap-10 lg:flex-row lg:items-stretch">
          <div class="flex w-full flex-col justify-center gap-6 text-center lg:w-1/2 lg:text-left">
            <div>
              <span class="badge badge-outline badge-lg">Why daisyUI</span>
            </div>
            <h1 class="text-4xl font-bold sm:text-5xl">Build polished UIs in minutes, not hours.</h1>
            <p class="text-base-content/70">
              daisyUI pairs perfectly with Tailwind CSS so you can assemble production-ready interfaces with
              semantic HTML and composable utility classes.
            </p>
            <div class="flex flex-wrap justify-center gap-3 lg:justify-start">
              <a class="btn btn-primary btn-wide btn-md " href="https://daisyui.com/" target="_blank" rel="noopener">Explore components</a>
              <a class="btn btn-ghost" href="https://github.com/saadeghi/daisyui" target="_blank" rel="noopener">GitHub</a>
            </div>
            <div class="flex flex-wrap items-center justify-center gap-3 text-sm text-base-content/60 lg:justify-start">
              <span class="badge badge-neutral badge-outline">Vue 3</span>
              <span class="badge badge-neutral badge-outline">Tailwind v4</span>
              <span class="badge badge-neutral badge-outline">daisyUI v5</span>
            </div>
          </div>
          <div class="mockup-browser h-full w-full border bg-base-300 lg:w-1/2">
            <div class="mockup-browser-toolbar">
              <div class="input">localhost:5173</div>
            </div>
            <div class="space-y-4 bg-base-200 px-6 py-8">
              <div class="badge badge-primary badge-lg">Quick preview</div>
              <div class="flex flex-wrap gap-3">
                <button class="btn btn-primary">Primary</button>
                <button class="btn btn-secondary">Secondary</button>
                <button class="btn btn-outline">Outline</button>
              </div>
              <div class="alert alert-success">
                <span class="font-medium">Success!</span>
                <span>Instant feedback with ready-made alert styles.</span>
              </div>
              <div class="stats stats-vertical gap-4 rounded-2xl bg-base-100 shadow lg:flex-row lg:gap-0">
                <div class="stat">
                  <div class="stat-title">Active users</div>
                  <div class="stat-value text-primary">86K</div>
                  <div class="stat-desc">↗︎ 18% from last week</div>
                </div>
                <div class="stat">
                  <div class="stat-title">New signups</div>
                  <div class="stat-value text-secondary">1.2K</div>
                  <div class="stat-desc">↗︎ 4% today</div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>

      <section class="rounded-3xl bg-base-100 p-6 shadow">
        <div class="stats stats-vertical gap-4 text-center sm:stats-horizontal sm:text-left">
          <div v-for="metric in metrics" :key="metric.title" class="stat">
            <div class="stat-title text-xs uppercase tracking-wide text-base-content/60">{{ metric.title }}</div>
            <div class="stat-value text-3xl font-bold text-primary">{{ metric.value }}</div>
            <div class="stat-desc text-base-content/70">{{ metric.description }}</div>
          </div>
        </div>
      </section>

      <section class="space-y-6">
        <div class="flex flex-col gap-2">
          <h2 class="text-3xl font-bold sm:text-4xl">Curated component sections</h2>
          <p class="text-base-content/70">Blend these DaisyUI patterns to jump-start dashboards, landing pages, or portals.</p>
        </div>
        <div class="grid gap-6 md:grid-cols-2 lg:grid-cols-3">
          <article
            v-for="feature in featureCards"
            :key="feature.title"
            class="card border border-base-200 bg-base-100 shadow-sm transition hover:-translate-y-1 hover:shadow-xl"
          >
            <div class="card-body">
              <h3 class="card-title">{{ feature.title }}</h3>
              <p class="text-base-content/70">{{ feature.description }}</p>
              <div class="card-actions flex flex-wrap gap-2 pt-4">
                <span v-for="badge in feature.badges" :key="badge" class="badge badge-outline">{{ badge }}</span>
              </div>
            </div>
          </article>
        </div>
      </section>

      <section class="grid gap-8 lg:grid-cols-[3fr_2fr]">
        <div class="rounded-3xl bg-base-100 p-8 shadow">
          <h2 class="text-3xl font-bold sm:text-4xl">From install to themed UI</h2>
          <p class="mt-2 text-base-content/70">
            Follow these guided steps to adapt the template for your product.
          </p>
          <ul class="steps steps-vertical mt-6 w-full gap-4 lg:steps-horizontal lg:gap-0">
            <li
              v-for="(step, index) in steps"
              :key="step.label"
              class="step"
              :class="{ 'step-primary': index === 0 }"
            >
              {{ step.label }}
            </li>
          </ul>
          <div class="mt-6 space-y-3">
            <h3 class="font-semibold">CLI snippets</h3>
            <div class="mockup-code bg-neutral text-neutral-content">
              <pre v-for="step in steps" :key="step.command" class="overflow-x-auto"><code>{{ step.command }}</code></pre>
            </div>
          </div>
        </div>
        <div class="card bg-base-100 shadow-xl">
          <div class="card-body gap-6">
            <h3 class="card-title">Customize themes instantly</h3>
            <p class="text-base-content/70">
              Update colors through Tailwind config or swap to one of the bundled palettes such as
              <span class="badge badge-primary badge-sm">corporate</span>,
              <span class="badge badge-secondary badge-sm">pastel</span>, or
              <span class="badge badge-accent badge-sm">forest</span>.
            </p>
            <div class="divider my-0">Preview</div>
            <div class="flex flex-wrap gap-3">
              <button class="btn btn-primary btn-sm">Primary</button>
              <button class="btn btn-secondary btn-sm">Secondary</button>
              <button class="btn btn-accent btn-sm">Accent</button>
            </div>
            <div class="divider my-0">Info cards</div>
            <div class="alert alert-info">
              <span>Need dark mode? Change the theme attribute and you are done.</span>
            </div>
          </div>
        </div>
      </section>

      <footer class="footer gap-8 rounded-box bg-base-100 p-8 shadow sm:grid-cols-2 lg:grid-cols-3">
        <nav>
          <h4 class="footer-title">Resources</h4>
          <a class="link link-hover" href="https://daisyui.com/docs/install/" target="_blank" rel="noopener">Install</a>
          <a class="link link-hover" href="https://daisyui.com/docs/themes/" target="_blank" rel="noopener">Themes</a>
          <a class="link link-hover" href="https://daisyui.com/components/" target="_blank" rel="noopener">Components</a>
        </nav>
        <nav>
          <h4 class="footer-title">Template</h4>
          <a class="link link-hover" href="https://vitejs.dev/" target="_blank" rel="noopener">Vite</a>
          <a class="link link-hover" href="https://vuejs.org/" target="_blank" rel="noopener">Vue 3</a>
          <a class="link link-hover" href="https://tailwindcss.com/" target="_blank" rel="noopener">Tailwind CSS</a>
        </nav>
        <div class="place-items-center text-center lg:text-left">
          <h4 class="footer-title">Enjoying the stack?</h4>
          <p class="text-base-content/70">Clone, configure, and ship beautiful interfaces faster.</p>
          <a class="btn btn-sm btn-primary mt-4" href="https://github.com/saadeghi/daisyui" target="_blank" rel="noopener">Star daisyUI</a>
        </div>
      </footer>
    </div>
  </div>
</template>

