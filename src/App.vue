<!--
<template>
  <h1>{{ message }}</h1>
  <HelloWorld />
  만약 error가 발생한다면 vuejs의 2버전에 해당하는 error인데 3버전인데 이 error가 발생하는 이유는 eslint가 연결이 되어 있지 않아서 발생함.
  terminal에서 npm i -D eslint eslint-plugin-vue babel-eslint 입력
</template>

<script>
import HelloWorld from '~/components/HelloWorld.vue'
export default {
    components: {
        HelloWorld
    },
    data() {
        return {
            message: 'Hello Vue!!!'
        }
    }
}
</script>
-->
<template>
  <h1 @click="increase">
    {{ count }}
  </h1>
  <div v-if="count > 4">
    4보다 큽니다!
  </div> <!-- v-if : 디렉티브 -->
  <ul>
    <Fruit
      v-for="fruit in fruits"
      :key="fruit"
      :name="fruit">
      {{ fruit }}
    </Fruit>
  </ul>
</template>

<script>
    import Fruit from '~/components/Fruit'
    export default {
        components: {
            Fruit
        },
        data() {
            return {
                count: 0,
                fruits: ['Apple', 'Banana', 'Cherry']
            }
        },
        methods: {
            increase() {
                this.count += 1
            }
        }
    }
</script>
<style>
h1 {
    font-size: 30px;
    color: red;
}
</style>