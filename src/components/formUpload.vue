<template>
    <div class="container">
        <div class="row justify-content-center mt-3">
            <div class="col-10">
              <div class="box border p-3 shadow text-center">
                  <p>Upload your house</p>
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

</style>