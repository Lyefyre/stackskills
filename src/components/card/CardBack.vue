<template>
  <div class="row">
    <div class="col-sm-6 card edit-area">
        <cc-image-upload @displayImageChanged="imageName = $event"></cc-image-upload><hr>
        <cc-section-completed></cc-section-completed>
    </div>
    <div class="col-sm-6 card edit-display">
        <cc-image-output :displayImage="imageName" :containerHeight="400" :clearImageProp="clearImage"></cc-image-output>
    </div>
  </div>
</template>

<script>
import ImageUpload from './ImageUpload'
import ImageOutput from './ImageOutput'
import SectionCompleted from './SectionCompleted'

export default {
    data: function() {
        return {
            imageName: ""
        }
    },
    methods: {
        clearImage: function() {
            if(this.imageName != '') {
                this.imageName = "history.PNG"
            }
        }
    },
    components: {
        ccImageUpload: ImageUpload,
        ccImageOutput: ImageOutput,
        ccSectionCompleted: SectionCompleted
    }
}
</script>