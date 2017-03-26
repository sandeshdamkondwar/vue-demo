<template>
<div id="messages">
	<div class="messages">
    <img id="loader" src="./../assets/loader.svg" v-show="loading">
		<div v-for="message in messages">
			<div class="message" v-bind:class="{ left: message.source === 'from', right: message.source === 'to'}" >
				<span v-html="message.subject"></span>
			</div>
		</div>
	</div>

</div>
</template>

<script>
export default {
  name: 'messages',
  data () {
    return {
      loading: true,
      messages: []
    }
  },
  created () {
    var self = this
    this.$http.get('https://sandeshdamkondwar.firebaseio.com/messages.json').then(function (response) {
      self.loading = false
      self.messages = response.data
    }, function () {
      alert('There was an error while loading messages')
    })
  }
}
</script>

<style scoped>
.messages {
  border: 1px solid #DDD;
  border-width: 1px 1px 2px 1px;
  max-width: 400px;
  margin: 20px auto;
  padding: 20px;
  max-width: 380px;
}

.message {
	margin-bottom: 10px;
}

.message.right {
	text-align: right;
}

.message.left {
	text-align: left;
}

.message span {
	display: inline-block;
	padding: 10px;
	color: white;
  border-radius: 21px 21px 21px 21px;
  position: relative;
  max-width: 80%;
}

.message span:after {
  content: "";
  position: absolute;
  width: 10px;
  height: 20px;

  bottom: 0;
  right: 0;
  border-radius: 0 30% 0 290%;
}

.message.left span:after {
	bottom: 0;
  left: 0;
  border-radius: 30% 0 290% 0 ;
}

.message.right span:after {
	bottom: 0;
    right: 0;
    border-radius: 0 30% 0 290%;
    background: rgb(23, 179, 50);
}

.message.left span,
.message.left span:after {
	background: #28384B;
}

.message.right span,
.message.right span:after {
	background: #36A36D;
}

</style>
