<script>
  let time = new Date().toLocaleTimeString();

  const timer = setInterval(() => {
    time = new Date().toLocaleTimeString();
  }, 1000);

  $effect(() => {
    return () => clearInterval(timer);
  });
</script>

<p>Current time: {time}</p>
