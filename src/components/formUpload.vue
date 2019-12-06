<template>
    <div class="container">
        <div class="row justify-content-center mt-3">
            <div class="col-10">
              <div class="box border p-3 shadow text-center">
                  <p style="font-family: 'Righteous', cursive;">Upload your house</p>
                  <hr>
                <form>
                    <div class="row">
                      <div class="col-12">
                        <div class="form-group">
                            <label for="file" class="sr-only">File</label>
                            <div class="input-group">
                                <input type="text" name="filename" class="form-control" placeholder="No file selected" readonly>
                                <span class="input-group-btn">
                                <div class="btn btn-default  custom-file-uploader py-0">
                                    <input type="file" name="file" onchange="this.form.filename.value = this.files.length ? this.files[0].name : ''" />
                                <span class="btn btn-primary"> Select a file </span>
                                </div>
                                </span>
                            </div>
                        </div>
                        <div class="input-group mb-3">
                        <div class="input-group-prepend">
                            <span class="input-group-text">Rp</span>
                        </div>
                        <input type="text" class="form-control" aria-label="Amount (to the nearest dollar)">
                        <div class="input-group-append">
                            <span class="input-group-text">.00</span>
                        </div>
                        </div>
                      </div>
                    </div>
                    <button style="--content: 'Submit Your House';">
                        <div class="left"></div>
                            Submit Your House
                        <div class="right"></div>
                    </button>
                </form>
               </div> 
            </div>
        </div>
    </div>

 
</template>

<script>
export default {
    name: 'formUpload',
}
</script>

<style scoped>
.custom-file-uploader {
  position: relative;
}
.custom-file-uploader input[type='file'] {
  display: block;
  position: absolute;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  z-index: 5;
  width: 100%;
  height: 100%;
  opacity: 0;
  cursor: default;
}


* {
  box-sizing: border-box;
}

html,
#container {
  width: 100%;
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: var(--bg-color);
}

button {
  position: relative;
  padding: 9px 20px;
  border: none;
  background: none;
  cursor: pointer;

  font-family: "Source Code Pro";
  font-weight: 900;
  text-transform: uppercase;
  font-size: 30px;
  color: var(--text-color);

  background-color: var(--btn-color);
  box-shadow: var(--shadow-color) 2px 2px 22px;
  border-radius: 4px;
  z-index: 0;
  overflow: hidden;
}

button:focus {
  outline-color: transparent;
  box-shadow: var(--btn-color) 2px 2px 22px;
}

.right::after,
button::after {
  content: var(--content);
  display: block;
  position: absolute;
  white-space: nowrap;
  padding: 40px 40px;
  pointer-events: none;
}

button::after {
  font-weight: 200;
  top: -30px;
  left: -20px;
}

.right,
.left {
  position: absolute;
  width: 100%;
  height: 100%;
  top: 0;
}
.right {
  left: 66%;
}
.left {
  right: 66%;
}
.right::after {
  top: -30px;
  left: calc(-66% - 20px);

  background-color: var(--bg-color);
  color: transparent;
  transition: transform 0.4s ease-out;
  transform: translate(0, -90%) rotate(0deg);
}

button:hover .right::after {
  transform: translate(0, -47%) rotate(0deg);
}

button .right:hover::after {
  transform: translate(0, -50%) rotate(-7deg);
}

button .left:hover ~ .right::after {
  transform: translate(0, -50%) rotate(7deg);
}

/* bubbles */
button::before {
  content: "";
  pointer-events: none;
  opacity: 0.6;
  background: radial-gradient(
      circle at 20% 35%,
      transparent 0,
      transparent 2px,
      var(--text-color) 3px,
      var(--text-color) 4px,
      transparent 4px
    ),
    radial-gradient(
      circle at 75% 44%,
      transparent 0,
      transparent 2px,
      var(--text-color) 3px,
      var(--text-color) 4px,
      transparent 4px
    ),
    radial-gradient(
      circle at 46% 52%,
      transparent 0,
      transparent 4px,
      var(--text-color) 5px,
      var(--text-color) 6px,
      transparent 6px
    );

  width: 100%;
  height: 300%;
  top: 0;
  left: 0;
  position: absolute;
  animation: bubbles 5s linear infinite both;
}

@keyframes bubbles {
  from {
    transform: translate();
  }
  to {
    transform: translate(0, -66.666%);
  }
}

</style>