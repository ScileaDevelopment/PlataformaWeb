<!-- =========================================================================================
    File Name: KnowledgeBaseCategory.vue
    Description: Knowledge Base Category Page
    ----------------------------------------------------------------------------------------
    Item Name: Vuesax Admin - VueJS Dashboard Admin Template
      Author: Pixinvent
    Author URL: http://www.themeforest.net/user/pixinvent
========================================================================================== -->


<template>
    <div id="knowledge-base-category-page">
        <p class="mb-4">{{ categorySubtitle }}</p>

        <div class="vx-row mt-8 match-height">
            <div class="vx-col w-full sm:w-1/2 md:w-1/3 mb-base" v-for="section in sections" :key="section.id">
                <vx-card>
                    <h4 class="mb-4">{{ section.title }}</h4>
                    <ul class="bordered-items">
                        <li v-for="que in section.questions" :key="que.question" class="py-2"><router-link :to="que.answerUrl">{{ que.question }}</router-link></li>
                    </ul>
                </vx-card>
            </div>
        </div>
    </div>
</template>

<script>

export default{
    data() {
        return {
            categoryTitle: 'Category Name',
            categorySubtitle: 'petiole antimasquer nonenduring hoofish unbed anergic sweetwood ailsyte.',
            sections: [
                {
                    "id": 0,
                    "title": 'Inteligencia Artificial',
                    "questions": [
                    {
                        "id": 0,
                        "question": 'Watson',
                        "answerUrl": "/pages/knowledge-base/category/question"
                    },
                    {
                        "id": 1,
                        "question": 'Jelly soufflé apple pie?',
                        "answerUrl": "/pages/knowledge-base/category/question"
                    },
                    {
                        "id": 2,
                        "question": 'Soufflé apple pie ice cream cotton?',
                        "answerUrl": "/pages/knowledge-base/category/question"
                    },
                    {
                        "id": 3,
                        "question": 'Powder wafer brownie?',
                        "answerUrl": "/pages/knowledge-base/category/question"
                    },
                    {
                        "id": 4,
                        "question": 'Toffee donut dragée cotton candy?',
                        "answerUrl": "/pages/knowledge-base/category/question"
                    },
                    {
                        "id": 5,
                        "question": 'Soufflé chupa chups chocolate bar?',
                        "answerUrl": "/pages/knowledge-base/category/question"
                    }]
                },
                {
                    "id": 1,
                    "title": 'Machine Learning',
                    "questions": [
                    {
                        "id": 0,
                        "question": 'Dessert halvah carrot cake sweet?',
                        "answerUrl": "/pages/knowledge-base/category/question"
                    },
                    {
                        "id": 1,
                        "question": 'Jelly beans bonbon marshmallow?',
                        "answerUrl": "/pages/knowledge-base/category/question"
                    },
                    {
                        "id": 2,
                        "question": 'Marzipan chocolate gummi bears bonbon powder?',
                        "answerUrl": "/pages/knowledge-base/category/question"
                    },
                    {
                        "id": 3,
                        "question": 'Chupa chups lemon drops caramels?',
                        "answerUrl": "/pages/knowledge-base/category/question"
                    }]
                },
                {
                    "id": 2,
                    "title": 'Desarrollo movil',
                    "questions": [
                    {
                        "id": 0,
                        "question": 'Android',
                        "answerUrl": "/pages/knowledge-base/category/question"
                    },
                    {
                        "id": 1,
                        "question": 'Flutter',
                        "answerUrl": "/pages/knowledge-base/category/question"
                    },
                    {
                        "id": 2,
                        "question": 'Swift',
                        "answerUrl": "/pages/knowledge-base/category/question"
                    },
                    {
                        "id": 3,
                        "question": 'Cake fruitcake chupa chups?',
                        "answerUrl": "/pages/knowledge-base/category/question"
                    },
                    {
                        "id": 4,
                        "question": 'Fruitcake bonbon dessert gingerbread powder?',
                        "answerUrl": "/pages/knowledge-base/category/question"
                    }]
                },
                {
                    "id": 3,
                    "title": 'Desarrollo web',
                    "questions": [
                    {
                        "id": 0,
                        "question": 'HTML5',
                        "answerUrl": "/pages/knowledge-base/category/question"
                    },
                    {
                        "id": 1,
                        "question": 'CSS',
                        "answerUrl": "/pages/knowledge-base/category/question"
                    },
                    {
                        "id": 2,
                        "question": 'Sesame snaps tart cake pie chocolate?',
                        "answerUrl": "/pages/knowledge-base/category/question"
                    },
                    {
                        "id": 3,
                        "question": 'Chocolate cake chocolate tootsi?',
                        "answerUrl": "/pages/knowledge-base/category/question"
                    },
                    {
                        "id": 4,
                        "question": 'Caramels lemon drops tiramisu cake?',
                        "answerUrl": "/pages/knowledge-base/category/question"
                    },
                    {
                        "id": 5,
                        "question": 'Brownie dessert gummies. Tiramisu bear claw apple?',
                        "answerUrl": "/pages/knowledge-base/category/question"
                    }],
                },
                {
                    "id": 4,
                    "title": 'Frameworks',
                    "questions": [
                    {
                        "id": 0,
                        "question": 'Laravel',
                        "answerUrl": "/pages/knowledge-base/category/question"
                    },
                    {
                        "id": 1,
                        "question": 'Spring',
                        "answerUrl": "/pages/knowledge-base/category/question"
                    },
                    {
                        "id": 2,
                        "question": 'Carrot cake topping tiramisu oat?',
                        "answerUrl": "/pages/knowledge-base/category/question"
                    },
                    {
                        "id": 3,
                        "question": 'Ice cream soufflé marshmallow?',
                        "answerUrl": "/pages/knowledge-base/category/question"
                    },
                    {
                        "id": 4,
                        "question": 'Dragée liquorice dragée jelly beans?',
                        "answerUrl": "/pages/knowledge-base/category/question"
                    },
                    {
                        "id": 5,
                        "question": 'Lemon drops gingerbread chupa chups tiramisu?',
                        "answerUrl": "/pages/knowledge-base/category/question"
                    }]
                },
                {
                    "id": 5,
                    "title": 'Lenguajes de programacion',
                    "questions": [
                    {
                        "id": 0,
                        "question": 'PHP',
                        "answerUrl": "/pages/knowledge-base/category/question"
                    },
                    {
                        "id": 1,
                        "question": 'JavaScript',
                        "answerUrl": "/pages/knowledge-base/category/question"
                    },
                    {
                        "id": 2,
                        "question": 'Python',
                        "answerUrl": "/pages/knowledge-base/category/question"
                    },
                    {
                        "id": 3,
                        "question": 'C++',
                        "answerUrl": "/pages/knowledge-base/category/question"
                    }]
                },
            ]
        }
    },
    computed: {
    },
    methods: {},
    components: {},
    mounted() {
        this.$emit('changeRouteTitle', 'Category');
    }
}
</script>
