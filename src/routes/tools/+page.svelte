<script>
    
    var result = $state("")
    var one = $state("")
    var two = $state("")
    function add() {
        result = one+two
    }
</script>

<h1>Calculator</h1>
<input bind:value = {one} type="text" placeholder="First number"/>
<input bind:value = {two} type="text" placeholder="Second number"/>
<button onclick={add}>Calculate!</button>

<h1>Result: {result}</h1>