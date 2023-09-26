<script lang="ts">
  let num: number = 0;
  // count.subscribe(x => num= x);
  const increment = () => {
    num += 1
    // count.set(num);
  }
  $: doubled = num * 2;
  $: {
    console.log(`the count is ${num}`);
    console.log(`this will also be logged whenever count changes`);
  }
  $: if (num >= 10) {
    alert('count is dangerously high!');
  }

  let numbers = [1, 2, 3, 4];
  function addNumber() {
    numbers = [...numbers, numbers.length + 1];
  }

  $: sum = numbers.reduce((total, currentNumber) => total + currentNumber, 0);
</script>

<button on:click={increment}>
  count is {num} <br>
  double count is {doubled}
</button>

<p> alert:
  {#if num > 10}
    <p>{num} is greater than 10</p>
  {:else if num < 5}
    <p>{num} is less than 5</p>
  {:else}
    <p>{num} is between 5 and 10</p>
  {/if}
</p>


<button on:click={addNumber}>
  Add a number
</button>

<p>{numbers.join(' + ')} = {sum}</p>

