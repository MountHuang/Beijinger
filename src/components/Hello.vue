<template>
	<div class="hello">
		<h1>{{ msg }}</h1>
		<span>土逼这么说:</span>
		<br>
		<textarea v-model="message" placeholder="add multiple lines"></textarea>
		<br>
		<span>体面北京人这么说:</span>
		<p style="white-space: pre-line;">{{ beijinglish }}</p>
	</div>
</template>

<script>
	export default {
  name: 'hello',
  data () {
    return {
      msg: 'Welcome to be a Beijinger',
			message : ''
    }
  },
	computed : {
		beijinglish : function(){
			var splitted = this.message.split("")
			return this.insertIntoArray(splitted, "儿").join("");
		}
	},

	methods:{
			insertIntoArray : function(arr, value) {
				return arr.reduce((result, element, index, array) => {
					result.push(element);
					if (index < array.length - 1) {
            result.push(value);
        	}
					return result;
    		}, []);
			}
	}
	
	

	
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
	h1,
	h2 {
		font-weight: normal;
	}

	ul {
		list-style-type: none;
		padding: 0;
	}

	li {
		display: inline-block;
		margin: 0 10px;
	}

	a {
		color: #42b983;
	}
</style>