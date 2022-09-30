<script>
</script>

<!-- <head
  ><link
    href="https://cdn.jsdelivr.net/npm/bootstrap@5.2.0-beta1/dist/css/bootstrap.min.css"
    rel="stylesheet"
    integrity="sha384-0evHe/X+R7YkIZDRvuzKMRqM+OrBnVFBL6DOitfPri4tjfHxaWutUpFmBp4vmVor"
    crossorigin="anonymous"
  /></head
> -->
<div class="container py-4">
  <div class="row g-4 row-cols-1 row-cols-md-2 mb-4">
    <!-- live analysis card -->

    <div class=" col">
      <div class="card h-100 more-purple">
        <div class="card-header pb-0">
          <h3 class="fw-bold my-0">Live Analysis</h3>
        </div>
        <div class="card-body">
          <p class="card-text">Stream-in a Live Feed for analysis</p>
        </div>
        <div
          class="card-footer pt-0 d-flex flex-row justify-content-between align-items-center"
        >
          <div
            class="d-flex flex-column flex-lg-row align-items-start align-items-lg-center flex-grow-1"
          />
          <div>
            <button
              class="btn btn-rounded stream-btn"
              on:click={() => {
                window.location.pathname = "/image";
              }}>Start</button
            >
          </div>
        </div>
      </div>
    </div>
  </div>
</div>

<style>
  * {
    user-select: none;
    text-decoration: none;
    transition: all 0.3s;
  }
  .more-purple {
    background-color: #7700ff17;
  }
  .more-blue {
    background-color: #0077ff17;
  }

  .btn {
    background-color: whitesmoke;
    box-shadow: 0px 0px 2px px rgba(0, 0, 0, 0.75);
    transition: all 0.3s ease-in-out;
  }
  .btn:hover {
    background-color: #ffffff85;
    transform: skew(0deg, -5deg);
  }

  .card-text {
    font-size: 20px;
  }
</style>
