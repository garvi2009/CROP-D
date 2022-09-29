<div class="load-wrapper">
  <span class="loader"><span class="loader-inner" /></span>
</div>

<style>
  :root {
    --loader-wrapper-color: #e4f0ff;
    --loader-color: #0011ff6f;
  }
  .load-wrapper {
    width: 100%;
    height: 100%;
    position: fixed;
    top: 0;
    left: 0;
    background-color: var(--loader-wrapper-color);
    z-index: 99999;
    display: flex;
    justify-content: center;
  }

  .loader {
    display: inline-block;
    width: 30px;
    height: 30px;
    position: relative;
    border: 4px solid var(--loader-color);
    top: 50%;
    animation: loader 2s infinite ease;
  }

  .loader-inner {
    vertical-align: top;
    display: inline-block;
    width: 100%;
    background-color: var(--loader-color);
    animation: loader-inner 2s infinite ease-in;
  }

  @keyframes loader {
    0% {
      transform: rotate(0deg);
    }

    25% {
      transform: rotate(180deg);
    }

    50% {
      transform: rotate(180deg);
    }

    75% {
      transform: rotate(360deg);
    }

    100% {
      transform: rotate(360deg);
    }
  }

  @keyframes loader-inner {
    0% {
      height: 0%;
    }

    25% {
      height: 0%;
    }

    50% {
      height: 100%;
    }

    75% {
      height: 100%;
    }

    100% {
      height: 0%;
    }
  }
</style>
