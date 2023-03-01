<script lang="ts">
  function handleClick() {
    alert('clicked');
  }
  function handle(test: string) {
    switch (test) {
      case '1':
        return 'red';
      case '2':
        return 'blue';
      default:
        return 'green';
    }
  }
  // # need a summation function
  // q: what is the capital of srilanka
  // a:
</script>

<section class="footer">
  <div>
    <div>LET'S CONNECT</div>
    <div>Send Me an Email</div>
    <div>
      <input type="text" />
      <button on:click={handleClick} class="btn" />
    </div>
  </div>
</section>

<style>
  .footer {
    font-family: 'Teko', sans-serif;
    background: #000;
    color: #fff;
    min-height: 50vh;
  }
  .btn {
    background-color: red;
  }
  .test {
    background-color: green;
  }
</style>
