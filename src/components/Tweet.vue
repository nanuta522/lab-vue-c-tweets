<template>
  <div class="tweet">
    <ProfileImage v-if="user" :img="user.image" />

    <div class="body">
      <div class="top">
        <User v-if="user" :user="user" />
        <Timestamp v-if="timestamp" :timestamp="timestamp"/>
      </div>

      <Message v-if="message" :message="message"/>

      <Actions />
    </div>

    <i class="fas fa-ellipsis-h"></i>
  </div>
</template>

<script>
import ProfileImage from './ProfileImage.vue'
import User from './User.vue'
import Timestamp from './Timestamp.vue'
import Message from './Message.vue'
import Actions from './Actions.vue'

export default {
  created() {
    this.user = this.tweet.user
    this.timestamp = this.tweet.timestamp
    this.message = this.tweet.message
  },
  data() {
    return {
      user: {},
      timestamp: '',
      message: ''
    }
  },
  props: {
    tweet: {
      type: Object
    }
  },
  components: {
    ProfileImage,
    User,
    Timestamp,
    Message,
    Actions
  }
}
</script>

<style scoped>
a {
  color: #42b983;
}

.tweet {
  margin-top: 2rem;
}
</style>
