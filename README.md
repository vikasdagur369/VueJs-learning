
# Vue.js Notes

Vue.js is a **progressive JavaScript framework** that is:

- ✅ Easy to learn  
- 🔄 Flexible  
- 🧱 Component-based  
- ⚡ Lightweight  
- 🌍 Popular  

---

## 🚀 Getting Started

```bash
npm create vue@latest
```

1. Choose options or skip setup.
2. Vue project structure will be created.

Each component typically has 3 sections:

```vue
<script>
// JS logic
</script>

<template>
  <!-- UI markup -->
</template>

<style>
/* Styling */
</style>
```

---

## 🧠 Basics

### ✅ Text Interpolation

Used to display JavaScript expressions or variables in HTML:

```html
<h1>{{ message }}</h1>
```

> ⚠️ Variables must be declared in `<script>` — not inside `{{ }}`.

---

### 🔗 Attribute Binding

```html
<a v-bind:href="myLink">Click here</a>
<!-- shorthand -->
<a :href="myLink">Click here</a>
```

---

## 🔄 Reactivity

Vue automatically updates the DOM when data changes.

### 1. `reactive()`

Used for **objects**:

```js
import { reactive } from 'vue';

const state = reactive({ count: 0 });
```

```html
<h1>{{ state.count }}</h1>
<button @click="state.count++">Increment</button>
```

> ❌ Not for primitives.

---

### 2. `ref()`

Used for **primitive** or **single reference values**:

```js
import { ref } from 'vue';

const username = ref("Vikas");
```

```html
<h1>{{ username }}</h1>
<button @click="username = 'Dagur'">Change Name</button>
```

---

## 🧮 Computed Properties

```js
import { ref, computed } from 'vue';

const firstName = ref("Vikas");
const lastName = ref("Dagur");

const fullName = computed(() => `${firstName.value} ${lastName.value}`);
```

---

## 🎯 Conditional Rendering

```html
<p v-if="isLoggedIn">Welcome</p>
<p v-else>Login first</p>

<p v-show="isVisible">This is visible</p>
```

> `v-if` removes element from DOM, `v-show` toggles visibility with CSS.

---

## 🔁 Looping with `v-for`

```html
<ul>
  <li v-for="(person, index) in people" :key="index">
    {{ person.name }}
  </li>
</ul>
```

> `:key` helps Vue optimize DOM updates efficiently.

---

## 📦 Props (Parent ➝ Child)

### In Parent:

```vue
<ChildComponent name="Vikas" />
```

### In Child:

```js
const props = defineProps(['name']);
```

---

## 🔳 Slots

Used to insert custom content into a reusable component.

### Basic Slot (Default)

**Child Component:**

```vue
<slot>Fallback content</slot>
```

**Parent Component:**

```vue
<ChildComponent>
  <p>This is custom content</p>
</ChildComponent>
```

### Named Slot

**Child:**

```vue
<slot name="header"></slot>
<slot></slot>
```

**Parent:**

```vue
<ChildComponent>
  <template #header>
    <h1>Header content</h1>
  </template>

  <p>Main content</p>
</ChildComponent>
```

---

## 🌐 Provide / Inject

Like React's Context API.

### Parent:

```js
import { provide } from 'vue';

provide('employeeName', 'Vikas');
provide('age', 20);
```

### Child:

```js
import { inject } from 'vue';

const name = inject('employeeName');
const age = inject('age');
```

---

## 👀 Watchers

React to data changes:

```js
import { ref, watch } from 'vue';

const count = ref(0);

watch(count, (newVal, oldVal) => {
  console.log(`Changed from ${oldVal} ➝ ${newVal}`);
});
```

**Options:**

- `immediate`
- `deep`
- `flush`
- `onTrack`

---

## 🔗 Template Refs

Get reference to DOM elements or components.

### Template:

```html
<input ref="myInput" />
```

### Script:

```js
import { ref, onMounted } from 'vue';

const myInput = ref(null);

onMounted(() => {
  myInput.value.focus();
});
```

---

## ✅ Bonus Tips

- Prefer `<script setup>` for simpler syntax.
- Vue DevTools is a must for debugging.
- Use Composition API (`ref`, `reactive`, `computed`, etc.) for better scalability.
- Use **Pinia** for global state management (Vuex alternative).

---

Happy Coding! 🎉
