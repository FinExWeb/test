<script>
import Loading from './Loading.vue'

export default {
    data() {
        return {
            user: null
        }
    },
    mounted() {
        setTimeout(() => {
            this.user = [
                {
                    skillName: "html",
                    completed: 0,
                    questions: 55,
                    wrongCompleted: 0
                },
                {
                    skillName: "css",
                    completed: 0,
                    questions: 65,
                    wrongCompleted: 0
                },
                {
                    skillName: "sass",
                    completed: 0,
                    questions: 12,
                    wrongCompleted: 0
                },
                {
                    skillName: "javascript",
                    completed: 0,
                    questions: 98,
                    wrongCompleted: 0
                },
                {
                    skillName: "react.js",
                    completed: 0,
                    questions: 87,
                    wrongCompleted: 0
                },
                {
                    skillName: "vue.js",
                    completed: 0,
                    questions: 125,
                    wrongCompleted: 0
                },
            ];

            //         this.user.forEach((skill, index) => {
            //             setTimeout(() => {
            //                 Vue.set(this.user, index, { ...skill, completed: 60 });
            //             }, (index + 1) * 0);
            //         });
            //     }, 0);
            // }
        })
    }
}
</script>

<template>
    <div class="col-md-6 col-lg-5 col-xl-4 my-2 " v-for="skill in user">
        <div class="card ques p-2 py-4">
            <a href="/">
                <button class="text-uppercase w-100">{{ skill.skillName }}: {{ skill.questions }} Questions</button>

                <div class="content d-flex align-items-center my-2 justify-content-center">
                    <div class="d-flex align-items-center color">
                        <i class="fa-solid fa-check-double" style="color: green;"></i>
                        <p class="mb-0 ms-1" style="color: green;">Completed</p>
                        <section class="completed mx-1">
                            <p class="mb-0" style="color: green;">{{ skill.completed }}</p>
                        </section>
                    </div>
                    <div class="d-flex align-items-center color-mark mx-3">
                        <i class="fa-solid fa-xmark"></i>
                        <p class="mb-0 ms-1">Wrong answers</p>
                        <section class="completed mx-1">
                            <p class="mb-0" style="color: rgb(161, 0, 0);">{{ skill.wrongCompleted }}</p>
                        </section>
                    </div>
                </div>
            </a>
        </div>
        <hr>
    </div>
</template>
<style scoped>
.completed {
    background-color: #e5e7ebcc;
    width: 35px;
    height: 20px;
    display: flex;
    justify-content: center;
    align-items: center;
    border-radius: 5px;
}

.color {
    color: black;
    opacity: 0.7;
    font-family: 'Electrolize', sans-serif;
    font-size: 15px;
}

.color-mark {
    color: rgb(161, 0, 0);
    opacity: 0.7;
    font-size: 15px;
    font-family: 'Electrolize', sans-serif;
}

.container .ques button {
    opacity: 0.7;
    border: none;
    outline: none;
    background: none;
}

@media screen and (max-width: 576px) {
    .ques .content {
        flex-direction: column;
    }

    .content div {
        margin: 5px 0;
    }

    .color {
        font-size: 13px;
    }

    .color-mark {
        font-size: 13px;
    }
}
</style>