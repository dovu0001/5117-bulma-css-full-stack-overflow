<template>
<!-- <div class="column is-four-fifths"> -->
    <div class="box ml-2">
    <article class="media">
      <div class="media-left">
        <figure class="image is-64x64">
          <img src="https://bulma.io/images/placeholders/128x128.png" alt="Image">
        </figure>
      </div>
      <div class="media-content">
        <div class="content">
          <p>
            <strong>{{ name }}</strong> <small>@{{ name }}</small> <small>31m ago</small>
            <br>
            {{ body }}
          </p>
        </div>
        <nav class="level is-mobile">
          <div class="level-left">
            <a class="level-item" aria-label="reply">
              <span class="icon is-small">
                <i class="fas fa-reply" aria-hidden="true"></i>
              </span>
            </a>
            <a class="level-item" aria-label="retweet">
              <span class="icon is-small">
                <i class="fas fa-retweet" aria-hidden="true"></i>
              </span>
            </a>
            <a class="level-item" aria-label="like">
              <span class="icon is-small">
                <i class="fas fa-heart" aria-hidden="true"></i>
              </span>
            </a>
          </div>
        </nav>

        <div class="tags">
          <span class="tag is-info">{{ hashtag }}</span>
          <span class="tag">{{ hashtag }}</span>
        </div>

        <div class="field is-grouped is-grouped-multiline">
          <div class="control">
            <div class="tags has-addons">
                <span class="tag is-danger">{{ hashtag }}</span>
                <a class="tag is-delete"></a>
            </div>   
          </div>

          <div class="control">
            <div class="tags has-addons">
                <span class="tag is-dark">{{ hashtag }}</span>
                <span class="tag is-info">0.0.0</span>
            </div>  
            </div>        
          </div>

            

      </div>
    </article>
  </div>
<!-- </div> -->
</template>

<script>
export default {
  props: {
    'name': String,
    'body': String,
    'hashtag': String
  }
}
</script>

<style>

</style>