<script>
  let d = 0;
  let h = 0;
  let m = 0;
  let s = 0;

  const newYearTime = new Date(`Jan 01 2023 00:00:00 GMT-0400`);
  function updateCountdown() {
    const currentTime = new Date();
    const diff = newYearTime - currentTime;
    d = Math.floor(diff / 1000 / 60 / 60 / 24);
    d = d < 10 ? "0" + d : d;
    h = Math.floor(diff / 1000 / 60 / 60) % 24;
    h = h < 10 ? "0" + h : h;
    m = Math.floor(diff / 1000 / 60) % 60;
    m = m < 10 ? "0" + m : m;
    s = Math.floor(diff / 1000) % 60;
    s = s < 10 ? "0" + s : s;
  }

  setInterval(updateCountdown, 1000);
</script>

<main>
  <div class="year" id="year" />
  <h1>New Year Coming</h1>
  <div class="countdown" id="countdown">
    <div class="time">
      <h2 id="days">{d}</h2>
      <small>Days</small>
    </div>

    <div class="time">
      <h2 id="hours">{h}</h2>
      <small>Hours</small>
    </div>

    <div class="time">
      <h2 id="minutes">{m}</h2>
      <small>Minutes</small>
    </div>

    <div class="time">
      <h2 id="seconds">{s}</h2>
      <small>Seconds</small>
    </div>
  </div>

  <!-- <img src="/loading.gif" alt="Loading Info" class="loading" id="loading" /> -->
</main>

<style>
  @import url("https://fonts.googleapis.com/css2?family=Gemunu+Libre&display=swap");
  * {
    box-sizing: border-box;
  }

  :global(body) {
    background-image: url("../photo1.jpg");
    background-repeat: no-repeat;
    background-size: cover;
    background-position: center center;
    height: 100vh;
    color: white;
    font-family: "Gemunu Libre", sans-serif;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    text-align: center;
    margin: 0;
    overflow: hidden;
  }

  :global(body)::after {
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.4);
  }

  :global(body) * {
    z-index: 1;
  }

  h1 {
    font-size: 4rem;
    margin: -80px 0 40px;
  }

  .countdown {
    display: flex;
    transform: scale(2);
    align-items: center;
    justify-content: center;
  }

  .time {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    margin: 15px;
  }

  .time h2 {
    margin: 0 0 5px;
  }

  @media (max-width: 500px) {
    h1 {
      font-size: 45px;
    }

    .time {
      margin: 5px;
    }

    .time h2 {
      font-size: 12px;
      margin: 0;
    }

    .time small {
      font-size: 10px;
    }
  }
</style>
