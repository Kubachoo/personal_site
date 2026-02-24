<script lang="ts">
  let copied = $state(false);

  function copyEmail() {
    navigator.clipboard.writeText('koichiseto792@gmail.com');
    copied = true;
    setTimeout(() => (copied = false), 2000);
  }
</script>

<main>
  <a href="/" class="absolute top-10 left-10 text-gray-400 text-base hover:text-black">← back</a>

  <form>
    <input type="email" placeholder="email" />
    <textarea placeholder="message"></textarea>
    <button type="button" onclick={copyEmail} class="email-copy">
      {copied ? 'copied!' : 'koichiseto792@gmail.com'}
    </button>
  </form>
</main>

<style>
  main {
    position: relative;
    height: 100vh;
    background-color: white;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  form {
    display: flex;
    flex-direction: column;
    gap: 12px;
    width: 400px;
  }

  input, textarea {
    font-family: inherit;
    font-size: 0.9rem;
    border: none;
    border-bottom: 1px solid black;
    outline: none;
    padding: 8px 0;
    background: transparent;
    color: black;
    resize: none;
  }

  input::placeholder, textarea::placeholder {
    color: #9ca3af;
  }

  textarea {
    height: 120px;
  }

  .email-copy {
    font-family: inherit;
    font-size: 0.9rem;
    background: none;
    border: none;
    padding: 0;
    cursor: pointer;
    text-decoration: underline;
    color: #9ca3af;
    text-align: left;
    transition: color 0.15s;
  }

  .email-copy:hover {
    color: black;
  }
</style>
