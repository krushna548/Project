<template>
    
    
    <div class="FieldField_Wrapper">
        <div class="from-control"><input id="txt" type="text" name="movie" placeholder="Enter the movie title"></div>
        <br><br>
        <img v-bind:src="imagePreview" class="preview-image" v-on:click="uploads" width="300" hight="400" >
  
        <input name="image" type="file" id="file-field" v-on:change="updatePreview">
        <br><br><br>
        <div class="row">
            <div class="col-sm-12">
                <form method="POST" enctype="multipart/form-data"> 
                    <button class="btn-primary">
                        UPLOAD
                    </button>
                </form>
            </div>
         </div>
    </div>     
</template>

<script>
export default {
    data(){
        return{
            imagePreview: 'upload_image.png'
        }
    },
    methods:{
        uploads (){
            document.getElementById('file-field').click()
        },

        updatePreview (e)
        {
            var reader, files =e.target.files

            reader = new FileReader()

            reader.onload=(e) =>{
                this.imagePreview = e.target.result
            }
            reader.readAsDataURL(files[0])
        }
    }
}
</script>

<style>
#file-field {
    width: 200px;
    height: 50px;
    background-position: center center;
    background-size: cover;
    border-style: solid;
    display: inline-block;
}
.btn-primary {
    width:  100px;
    height: 50px;
    background-color: turquoise;
    font:bold;
    
}
.txt{
    width: 200px;
    height: 50px;
    background-position: center center;
    background-size: cover;
    border-style: solid;
    display: inline-block;
}
</style>