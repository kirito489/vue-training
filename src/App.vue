<script setup>
  import { ref, computed } from 'vue';
  
  const gender = ref('');
  const content = ref('');
  const clearContent = function() {
    content.value = '';
  }
  const interests = ref([]);
  const interestsText = computed(() => {
    if (interests.value.length === 0) return '尚未選擇';
    return interests.value.join('、');
  });
  const color = ref('');
	const jutsu = ref('');
</script>

<template> 
	<nav>基本的導覽列</nav>

	<div>
    <label for="genderSelect">性別：</label>
    <select id="genderSelect" name="gender" v-model="gender">
      <option value="">請選擇</option>
      <option value="male">男</option>
      <option value="female">女</option>
    </select>
    <div>選擇的性別: {{ gender || '尚未選擇' }}</div>
  </div>

	<main>
		<h3>單行輸入框</h3>
		<div>
      <label for="contentInput">輸入內容：</label>
      <input type="text" id="contentInput" name="content" v-model="content">
      <div>使用者輸入的文字: {{ content || '無內容' }}</div>
      <button @click="clearContent">清空輸入框</button>
    </div>

		<h3>多選框</h3>
		<div class="game-interests">
      <span>遊戲類型偏好：</span>
      <label for="interest-rpg">
        <input type="checkbox" name="game_type" id="interest-rpg" value="rpg" v-model="interests">
        角色扮演
      </label>
      <label for="interest-rts">
        <input type="checkbox" name="game_type" id="interest-rts" value="rts" v-model="interests">
        即時策略
      </label>
      <label for="interest-action">
        <input type="checkbox" name="game_type" id="interest-action" value="action" v-model="interests">
        動作遊戲
      </label>
    </div>
		<div><strong>喜歡的遊戲類型:</strong> {{ interestsText }} </div>
    <div>
      <h4>喜歡的遊戲類型:</h4>
      <p v-if="interests.length === 0">尚未選擇</p>
      <ul v-else>
        <li v-for="(interest, index) in interests" :key="index"> {{ index + 1 }} . {{ interest }}</li>
      </ul>
    </div>

		<h3>單選框</h3>
		<div>
      <span>顏色偏好：</span>
      <label for="red">
        <input type="radio" name="favorite-color" id="red" value="red" v-model="color">
        紅色
      </label>
      <label for="green">
        <input type="radio" name="favorite-color" id="green" value="green" v-model="color">
        綠色
      </label>
		</div>
		<div>
      <h4>使用者選擇的顏色:</h4>
      <p v-if="!color">尚未選擇</p>
      <p v-else :class="color"> {{ color }} </p>
    </div>

		<h3>下拉式選單</h3>
    <label for="skillTypeSelect">
      <select name="skillType" id="skillTypeSelect" v-model="jutsu">
        <option value="">請選擇</option>
        <option value="fire">火遁</option>
        <option value="water">水遁</option>
        <option value="wind">風遁</option>
        <option value="thunder">雷遁</option>
        <option value="terra">土遁</option>
        <option value="yang">陽遁</option>
        <option value="yin">陰遁</option>
      </select>
    </label>
		<div>
      <h4>使用者喜歡的忍術:</h4>
      <p v-if="!jutsu">尚未選擇</p>
      <p v-else> {{ jutsu }} </p>
    </div>
	</main>
</template>

<style scoped> 
  .red {
		color: red;
	}

	.green {
		color: green;
	}
</style>
