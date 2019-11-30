<template>
  <div>
    <h1>N {{ user }} myThings {{ wheels }}</h1>
    <el-button @click="test()">
      ga
    </el-button>
  </div>
</template>

<script lang="ts">
import { Vue, Component } from 'vue-property-decorator'

import {
  State
} from 'vuex-class'

import { User } from '@/interfaces/User'

@Component({})
export default class Index extends Vue {
  @State(state => state.users.users) wheels: any
  // message: User = 'This is a message',
  user: User = {
    firstName: 'qwe'
  }

  // get myThings () {
  //   return this.$store.state.users
  // }

  get fullName (): string {
    return `${this.user.firstName}`
  }

  test (): void {
    console.warn('r')
    this.user.firstName = 'xxxxx'
  }

  mounted () {
    // console.warn(this.wheels)
  }
}
</script>
