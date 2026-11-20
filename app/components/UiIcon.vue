<script setup lang="ts">
const props = withDefaults(defineProps<{
  name: string
  size?: number
  strokeWidth?: number
}>(), {
  size: 20,
  strokeWidth: 1.8,
})

type IconNode = {
  element: string
  attrs: Record<string, string | number>
}

const icons: Record<string, IconNode[]> = {
  'arrow-right': [
    { element: 'path', attrs: { d: 'M5 12h14' } },
    { element: 'path', attrs: { d: 'm12 5 7 7-7 7' } },
  ],
  'arrow-up-right': [
    { element: 'path', attrs: { d: 'M7 17 17 7' } },
    { element: 'path', attrs: { d: 'M7 7h10v10' } },
  ],
  'arrow-down-right': [
    { element: 'path', attrs: { d: 'm7 7 10 10' } },
    { element: 'path', attrs: { d: 'M17 7v10H7' } },
  ],
  braces: [
    { element: 'path', attrs: { d: 'M8 3H6a2 2 0 0 0-2 2v4a2 2 0 0 1-2 2 2 2 0 0 1 2 2v4a2 2 0 0 0 2 2h2' } },
    { element: 'path', attrs: { d: 'M16 3h2a2 2 0 0 1 2 2v4a2 2 0 0 0 2 2 2 2 0 0 0-2 2v4a2 2 0 0 1-2 2h-2' } },
  ],
  code: [
    { element: 'path', attrs: { d: 'm8 8-4 4 4 4' } },
    { element: 'path', attrs: { d: 'm16 8 4 4-4 4' } },
    { element: 'path', attrs: { d: 'm14 4-4 16' } },
  ],
  compass: [
    { element: 'circle', attrs: { cx: 12, cy: 12, r: 10 } },
    { element: 'path', attrs: { d: 'm16.2 7.8-2.5 6-5.9 2.4 2.4-5.9 6-2.5Z' } },
  ],
  globe: [
    { element: 'circle', attrs: { cx: 12, cy: 12, r: 10 } },
    { element: 'path', attrs: { d: 'M2 12h20' } },
    { element: 'path', attrs: { d: 'M12 2a15.3 15.3 0 0 1 4 10 15.3 15.3 0 0 1-4 10 15.3 15.3 0 0 1-4-10 15.3 15.3 0 0 1 4-10Z' } },
  ],
  graduation: [
    { element: 'path', attrs: { d: 'm22 10-10-5L2 10l10 5 10-5Z' } },
    { element: 'path', attrs: { d: 'M6 12v5c3.5 2.7 8.5 2.7 12 0v-5' } },
    { element: 'path', attrs: { d: 'M22 10v6' } },
  ],
  lightbulb: [
    { element: 'path', attrs: { d: 'M9 18h6' } },
    { element: 'path', attrs: { d: 'M10 22h4' } },
    { element: 'path', attrs: { d: 'M8.5 14.5A6 6 0 1 1 15.5 14.5c-.8.7-1.3 1.5-1.5 2.5h-4c-.2-1-.7-1.8-1.5-2.5Z' } },
  ],
  music: [
    { element: 'path', attrs: { d: 'M9 18V5l12-2v13' } },
    { element: 'circle', attrs: { cx: 6, cy: 18, r: 3 } },
    { element: 'circle', attrs: { cx: 18, cy: 16, r: 3 } },
  ],
  panels: [
    { element: 'rect', attrs: { x: 3, y: 3, width: 18, height: 18, rx: 2 } },
    { element: 'path', attrs: { d: 'M9 3v18' } },
  ],
  sparkles: [
    { element: 'path', attrs: { d: 'm12 3 1.9 5.8L20 11l-6.1 2.2L12 19l-1.9-5.8L4 11l6.1-2.2L12 3Z' } },
    { element: 'path', attrs: { d: 'm19 14 1.1 2.9L23 18l-2.9 1.1L19 22l-1.1-2.9L15 18l2.9-1.1L19 14Z' } },
  ],
  terminal: [
    { element: 'path', attrs: { d: 'm4 17 6-6-6-6' } },
    { element: 'path', attrs: { d: 'M12 19h8' } },
  ],
}

const iconNodes = computed(() => icons[props.name] ?? icons.sparkles)
</script>

<template>
  <svg
    :width="size"
    :height="size"
    :stroke-width="strokeWidth"
    viewBox="0 0 24 24"
    fill="none"
    stroke="currentColor"
    stroke-linecap="round"
    stroke-linejoin="round"
    aria-hidden="true"
    focusable="false"
  >
    <component
      :is="node.element"
      v-for="(node, index) in iconNodes"
      :key="`${name}-${index}`"
      v-bind="node.attrs"
    />
  </svg>
</template>
