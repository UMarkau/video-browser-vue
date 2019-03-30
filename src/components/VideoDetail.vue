<template>
    <div
        class="col-md-8"
        v-if="video"
    >
        <div class="embed-responsive embed-responsive-16by9">
            <iframe
                class="embed-responsive-item"
                :src="videoUrl"
            />
        </div>
        <div class="details">
            {{video.snippet.title}}
            <p>{{video.snippet.description}}</p>
        </div>
    </div>
</template>

<script>
export default {
    name: 'VideoDetail',
    props: {
        video: Object
    },
    computed: {
        videoUrl() {
            return `https://www.youtube.com/embed/${this.video.id.videoId}`;
        }
    }
};
</script>

<style scoped>
.details {
    margin-top: 10px;
    padding: 10px;
    border: 1px solid #ddd;
    border-radius: 4px;
}
</style>

