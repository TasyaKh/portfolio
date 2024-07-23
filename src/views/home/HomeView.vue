<template>
    <div class="container">
        <section class="mt-5">
            <div class="row my-2 g-2 justify-content-center">
                <div class="col">
                    <div class="mb-2 ">Find me</div>
                    <div class="flex-row d-flex" style="gap: var(--p-2)">
                        <div class="d-flex align-content-center">
                            <img class="icon" src="/github.svg" alt="github"/>
                            <span>projects</span>
                        </div>

                        <div class="d-flex align-content-center">
                            <img class="icon" src="/telegram.svg" alt="telegram"/>
                            <span>contact</span>
                        </div>
                    </div>

                </div>
                <div class="col-auto d-flex align-content-center justify-content-sm-end justify-content-center">
                    <div>
                        <h1 class="p-0 m-0">Tasya Kh</h1>
                        <hr class="thin"/>
                        <div>Web-developer</div>
                    </div>
                </div>
                <div class="col-auto d-flex align-content-center">
                    <img src="/profile.jpg" alt="profile" class="img-profile"/>
                </div>
            </div>
        </section>

        <section class="mb-4">
            <div class="sticky"><h2>About</h2></div>
            <AboutMe/>
        </section>

        <section class="mb-4">
            <div class="sticky"><h2>Projects</h2></div>
            <MyProjects/>
        </section>

    </div>
</template>

<script setup lang="ts">
import AboutMe from "@/views/home/sections/AboutMe.vue";
import MyProjects from "@/views/home/sections/MyProjects.vue";
</script>


<style lang="scss">


.icon {
  width: 32px !important;
  padding: 0 !important;
  margin: 0px 10px 0px 0px;
}

.img-profile {
  min-width: 100px;
  max-width: 200px;
  width: 20%;
  margin: auto;
  border-radius: 100px;
}

.sticky {
  backdrop-filter: blur(8px);
  position: sticky;
  top: 0;
  left: 0px;
}

</style>
