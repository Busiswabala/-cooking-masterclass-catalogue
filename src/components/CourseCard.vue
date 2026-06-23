<template>
  <div class="card">
    <h2>{{ course.title }}</h2>

    <p><strong>Chef:</strong> {{ course.chef }}</p>

    <p><strong>Level:</strong> {{ course.level }}</p>

    <p><strong>Price:</strong> R{{ course.price }}</p>

    <p :class="course.available ? 'available' : 'sold-out'">
      {{ course.available ? "Available" : "Sold Out" }}
    </p>

    <button @click="saveCourse" :disabled="!course.available">
      Save Course
    </button>
  </div>
</template>

<script setup>
const props = defineProps({
  course: Object,
});

const emit = defineEmits(["save"]);

function saveCourse() {
  emit("save");
}
</script>

<style scoped>
.card {
  background: #fffffe;
  border: 1px solid #e4e7eb;
  border-radius: 18px;
  padding: 24px;
  box-shadow: 0 10px 30px rgba(20, 33, 61, 0.06);
  transition:
    transform 0.2s ease,
    box-shadow 0.2s ease;
}

.card:hover {
  transform: translateY(-2px);
  box-shadow: 0 14px 40px rgba(20, 33, 61, 0.08);
}

h2 {
  margin: 0 0 0.75rem;
  font-size: 1.25rem;
  color: #102a43;
}

p {
  margin: 0.55rem 0;
  color: #52606d;
  line-height: 1.7;
}

.available,
.sold-out {
  margin-top: 0.85rem;
  font-weight: 700;
}

.available {
  color: #2e7d32;
}

.sold-out {
  color: #c62828;
}

button {
  margin-top: 1rem;
  width: 100%;
  padding: 0.9rem 1rem;
  border: none;
  border-radius: 999px;
  background: #ca8d1e;
  color: white;
  font-weight: 700;
  cursor: pointer;
  transition:
    background-color 0.2s ease,
    transform 0.2s ease;
}

button:hover:not(:disabled) {
  background: #eeab10;
  transform: translateY(-1px);
}

button:disabled {
  background: #cbd5e1;
  color: #7b8a99;
  cursor: not-allowed;
}
</style>
