<template>
  <div>
    <NavBar></NavBar>
    <section class="hero is-link">
      <div class="hero-body">
        <p class="title">Thinkr</p>
        <p class="subtitle">Post your thoughts!</p>
      </div>
    </section>
    <section class="section">
      <div class="columns">
    
        <!-- First Column -->
        <div class="column is-one-fifth has-background-white is-hidden-mobile">
        <SimpleMenu />
        </div>

        <!-- Second Column -->
        <div class="column is-three-fifths has-background-light">
          <SingleThought
            v-for="thought in thoughts"
            :name="thought.name"
            :body="thought.body"
            :hashtag="thought.hashtag"
            :key="thought"
          ></SingleThought>
          <SimplePagination></SimplePagination>

        </div>

        <!-- Third Column-->
        <div class="column is-one-fifth has-background-white has-text-centered">
            <button
            @click="formActive = true"
            class="form-modal-trigger button is-dark">
            Add a Thought
            
          </button>
        </div>
      </div>

      <!-- form modal -->
      <div :class="{ 'is-active': formActive }" id="form-modal" class="modal">
        <div class="modal-background" @click="formActive = false" />
        <div class="modal-content p-4">
          <div class="card has-background-white">
            <header class="card-header">
              <p class="card-header-title is-size-3">Post a New Thought</p>
            </header>

            <div class="card-content">
              <p class="title is-size-5 has-text-weight-bold">Progress:</p>
              <progress
                class="progress is-info is-medium"
                v-bind:value="progress"
                max="100"
              >
                {{ progress }}
              </progress>

              <form @submit.prevent="addThought">
                <div class="field">
                  <label class="label" for="newName">What's your name?</label>
                  <div class="control" id="newName">
                    <input
                      v-model="newName"
                      class="input"
                      type="text"
                      placeholder="Your name"
                    />
                  </div>
                </div>
                <div class="field">
                  <label class="label" for="newThought"
                    >What's on your mind?</label
                  >
                  <div class="control" id="newThought">
                    <input
                      v-model="newThought"
                      class="input"
                      type="text"
                      placeholder="What's happening?"
                    />
                  </div>
                </div>
                <div class="field">
                  <label class="label" for="newHashtag"
                    >Hashtag</label
                  >
                  <div class="control" id="newHashtag">
                    <input
                      v-model="newHashtag"
                      class="input"
                      type="text"
                      placeholder="#amazing"
                    />
                  </div>
                </div>

                <footer class="card-footer">
                  <div class="field card-footer-item">
                    <div class="control">
                      <button @click="formActive = false" class="button is-link">
                        Add Thought
                      </button>
                    </div>
                  </div>
                </footer>
                
              </form>


            </div>
          </div>
        </div>
        <button
          @click="formActive = false"
          class="modal-close is-large"
          aria-label="close"
        ></button>
      </div>
      
    </section>
  </div>
</template>

<script>
import SimpleMenu from "./components/SimpleMenu.vue";
import NavBar from "./components/NavBar.vue";
import SingleThought from "./components/SingleThought.vue";
import SimplePagination from "./components/SimplePagination.vue"

export default {
  components: {
    NavBar,
    SingleThought,
    SimpleMenu,
    SimplePagination
  },
  data() {
    return {
      newThought: "",
      newName: "",
      newHashtag: "",
      formActive: false,
      thoughts: [
        {
          name: "someuser1",
          body: "Might go rake some leaves...",
          hashtag: "#lazy"
        },
        {
          name: "someuser2",
          body: "Going on a walk!",
          hashtag: "#exercise"
        },
      ],
    };
  },
  computed: {
    progress() {
      let prog = 0;
      if (this.newName !== "") {
        prog = prog + 33;
      }
      if (this.newThought !== "") {
        prog = prog + 33;
      }
      if (this.newHashtag !== "") {
        prog = prog + 34;
      }
      return prog;
    },
  },
  methods: {
    addThought() {
      this.thoughts.push({ name: this.newName, body: this.newThought, hashtag: this.newHashtag });
      this.newThought = "";
      this.newName = "";
      this.newHashtag = "";
    },
  },
};
</script>

<style>
@import "https://cdn.jsdelivr.net/npm/bulma@0.9.3/css/bulma.min.css";
@import "https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.1.1/css/all.min.css";
.done {
  text-decoration: line-through;
}
.modal-content {
  background-color: white;
}
</style>
