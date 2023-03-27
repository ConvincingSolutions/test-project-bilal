<script>
  // Please modify the code so when we click the button, we can see the actual input value that's entered.
  //Bilal: added bind:value to input.
  
  const obj = {
    value: 'world'
  };

  function onClick() {
    alert('hello, ' + obj.value);
  }

</script>

<h1>What's up {obj.value}?</h1>
<input bind:value={obj.value} />

<button type="submit" on:click={onClick}>Submit</button>