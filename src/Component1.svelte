<script>
	// Please fix the following bug.
	// Bilal: Wrapped the init()method call inside a document.addEventListener("DOMContentLoaded"
	// so that the getElementById is called when the DOM is ready.
	export let name = 'Harold';
    function init() {
      document.getElementById('my-name').style = 'font-size: 2rem;';
    }
    document.addEventListener("DOMContentLoaded", function(e){
       init();     
    });
</script>


<p id="my-name">My name is {name}</p>