<template>
  <div class="home">
    <div class="field">
      <div class="control">
        <input
          type="text"
          v-model="description"
          class="input"
          placeholder="Placeholder try"
        />
      </div>
      <div class="control">
        <button class="button" @click="addItem" :disabled="!description">
          Add
        </button>
      </div>
    </div>
    <div class="notification" v-for="(item, i) in items" :key="item._id">
      <p>
        <span class="tag">{{ i + 1 }}</span>
        {{ item.description }}
      </p>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import axios from 'axios';

export default {
  name: 'Home',
  data() {
    return {
      items: [],
      description: ''
    };
  },
  async mounted() {
    const response = await axios.get('api/bucketListItems/');
    this.items = response.data;
    console.log(this.items);
  },
  methods: {
    async addItem() {
      const response = await axios.post('api/bucketListItems/', {
        description: this.description
      });
      this.items.push(response.data);
      console.log(this.items);
      this.description = '';
    }
  }
};
</script>

<style lang="scss" scoped>
.home {
  width: 100%;

  .field {
    display: flex;
  }
}

.notification {
  background: rgba(197, 197, 197, 1);
  padding: 5px;
  border-radius: 5px;
  color: #0a0924;

  .tag {
    background: rgba(76, 241, 117, 0.5);
    padding: 5px 8px;
    border-radius: 5px;
    margin-right: 15px;
    color: white;
  }
}
</style>
