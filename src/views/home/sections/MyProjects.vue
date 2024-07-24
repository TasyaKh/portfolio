<template>
<!--    <div class="" style="display: grid; grid-template-columns: 1fr 1fr">-->
<!--        <div>dddeded</div>-->
<!--        <div style="display: flex; justify-content: end">eeeee</div>-->
<!--    </div>-->
    <div class="row g-3">
        <div class="col-md-6 col-12" v-for="proj in projects">

            <div class="card">
                <div class="card-project">
                    <img class="" :src="proj.src" :alt="proj.name"/>
                    <div class="description">
                        <div class="description-content">
                            <h3>{{ proj.name }}</h3>
                            <hr class="thin"/>
                            {{ proj.description }}
                        </div>
                    </div>
                </div>
                <div class="technologies">
                    <div class="row g-2 py-2">
                        <div v-for="tcn in proj.technologies" class="col-auto d-flex">
                            <span :class="'crumb ' + tcn">{{ tcn }}</span>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup lang="ts">

enum Technology {
    TYPESCRIPT = "typescript",

    REACT = "react",
    ANGULAR = "angular",
    VUE = "vue",

    NEXTJS = "nextjs",

    POSTGRESQL = "postgresql",
    MYSQL = "mysql",

    NESTJS = "nestjs",
    EXPRESSJS = "expressjs",

    REACT_NATIVE = "react-native",
    KOTLIN = "kotlin",

    ANDROID = "android",
}

interface Project {
    name: string;
    src: string;
    description: string;
    technologies: Technology[];
}

const projects: Project[] = [
    {
        name: "FAPS", src: "/projects/FAPS.png",
        description: `Project created to know information about medical help
            in rural areas`,
        technologies: [Technology.TYPESCRIPT, Technology.MYSQL, Technology.EXPRESSJS, Technology.REACT]
    },
    {
        name: "Baikal Hut", src: "/projects/baikal-hut.png", description: `Order a house on the lake`,
        technologies: [Technology.TYPESCRIPT, Technology.NEXTJS]
    },
    {
        name: "Barcode Scanner", src: "/projects/barcode.png", description: `
        Scan Barcode and save information about product in android applications
        `,
        technologies: [Technology.ANDROID, Technology.REACT_NATIVE]
    },
    {
        name: "Owl (translator)", src: "/projects/owl.png", description: `
        Android application - translator en/ru
        `,
        technologies: [Technology.ANDROID, Technology.KOTLIN]
    },
    {
        name: "Yandex/Topvisor", src: "/projects/yandex-topvisor.png",
        description: `Web-application which can interact with Topvisor and Yandex.Metric
        services and represent data in diagrams from them`,
        technologies: [Technology.TYPESCRIPT, Technology.VUE, Technology.NESTJS]
    },


]
</script>


<style lang="scss" scoped>

.technologies {
  border-radius:  0 0 var(--border-radius) 50px;
  //display: grid;
  //grid-template-columns: repeat(3, 1fr);
  //grid-auto-rows: minmax(100px, auto);
}

.card-project {
  position: relative;
  border-radius: var(--border-radius) 50px 0 0;
  overflow: hidden;
  width: 100%;
  height: 20rem;
  cursor: url("/paw.ico"), pointer;

  &:hover {
    & .description {
      opacity: 1;
      transition: opacity .3s ease-in;
    }

    & img {
      filter: brightness(40%);
    }
  }

  img {
    filter: brightness(70%);
    width: 100%;
    height: 100%;
    object-fit: cover;
  }

  .description {
    backdrop-filter: blur(8px);
    bottom: 0;
    display: flex;
    align-items: center;
    position: absolute;
    opacity: 0;
    width: 100%;
    height: 100%;
    transition: opacity .3s ease-out;

    .description-content {
      width: 100%;
      margin: var(--m-3);
    }
  }
}

@media (max-width: 576px) {
  .card-project {
    height: 15rem;
  }
}

.crumb {
  padding: 1px var(--p-3);
  border-radius: 50px;
  border: 1px solid var(--border-color);
  font-weight: 500;

  &.typescript {
    color: var(--bg-blue-500);
    border-color: var(--bg-blue-500);
  }

  &.mysql {
    color: var(--bg-blue-700);
    border-color: var(--bg-blue-700);
  }

  &.postgresql {
    color: var(--bg-blue-600);
    border-color: var(--bg-blue-600);
  }

  &.expressjs {
    color: var(--bg-gray-800);
    border-color: var(--bg-gray-800);
  }

  &.react, &.react-native {
    color: var(--bg-blue-400);
    border-color: var(--bg-blue-400);
  }

  &.vue {
    color: var(--bg-teal-400);
    border-color: var(--bg-teal-400);
  }

  &.angular {
    color: var(--bg-purple-700);
    border-color: var(--bg-purple-700);
  }

  &.nestjs {
    color: var(--bg-red-700);
    border-color: var(--bg-red-700);
  }

  &.android {
    color: var(--bg-green-400);
    border-color: var(--bg-green-400);
  }

  &.kotlin {
    color: var(--bg-purple-500);
    border-color: var(--bg-purple-500);
  }

}


</style>
