<template>
    <div class="row g-3">
        <div class="col-md-6 col-12" v-for="proj in projects">

            <div class="">
                <div class="img-project">
                    <img class="" :src="proj.src" :alt="proj.name"/>
                </div>
                <div class="row g-2">
                    <div v-for="tcn in proj.technologies" class="col-auto d-flex">
                        <span :class="'tcn ' + tcn">{{ tcn }}</span>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup lang="ts">

enum Technology {
    TYPESCRIPT = "typescript",

    POSTGRESQL = "postgresql",
    MYSQL = "mysql",

    NESTJS = "nestjs",
    EXPRESSJS = "expressjs",

    REACT_NATIVE = "react-native",
    KOTLIN = "kotlin",
}

interface Project {
    name: string;
    src: string;
    description: string;
    technologies: Technology[];
}

const projects: Project[] = [
    {
        name: "FAPS", src: "/projects/FAPS.png", description: "",
        technologies: [Technology.TYPESCRIPT, Technology.MYSQL, Technology.EXPRESSJS, Technology.MYSQL]
    },
    {name: "BaikalHut", src: "/projects/baikal-hut.png", description: "", technologies: []},
    {name: "Barcode Scanner", src: "/projects/barcode.png", description: "", technologies: []},
    {name: "Owl (translator)", src: "/projects/owl.png", description: "", technologies: []},
    {name: "Yandex/Topvisor", src: "/projects/yandex-topvisor.png", description: "", technologies: []},


]
</script>


<style lang="scss" scoped>

.tcn {
  padding: var(--p-1) var(--p-2);
  border-radius: var(--border-radius);

  &.typescript {
    color: red;
  }
}

.img-project {
  border-radius: var(--border-radius) var(--border-radius) 0 0;
  overflow: hidden;
  width: 100%;
  height: 20rem;

  &:hover {
    & img {
      opacity: 1;
      transition: 0.6s;
    }

  }

  img {
    opacity: 0.8;
    width: 100%;
    height: 100%;
    object-fit: cover;
  }
}

@media (max-width: 576px) {
  .img-project {
    height: 15rem;
  }
}

</style>
