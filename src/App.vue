<template>
    <h1>영화 정보</h1>
    <div v-for="(movie, i) in data" :key="i">
        <h3 class="bg-yellow" :style="textRed">{{ movie.title }}</h3>
        <p>개봉: {{ movie.year }}</p>
        <p>장르: {{ movie.category }}</p>
        <button @:click="increaseLike(i)">좋아요</button>
        <span>{{ movie.like }}</span>
    </div>
    <p>{{ foods[0] }}</p>
    <p>{{ foods[1] }}</p>
    <p>{{ foods[2] }}</p>
    <p v-for="(item, i) in foods" :key="i">{{ item }}</p>
</template>
<script>
export default {
    name: "App",
    data() {
        // data 함수 안에 값 저장
        return {
            like: 0,
            foods: ["김밥", "순대", "만두"],
            data: [
                {
                    title: "노량",
                    year: 2023,
                    category: "액션, 드라마",
                    like: 0,
                },
                {
                    title: "아쿠아맨과 로스트 킹덤",
                    year: 2023,
                    category: "액션, 판타지, 어드벤쳐",
                    like: 0,
                },
                {
                    title: "3일의 휴가",
                    year: 2023,
                    category: "판타지, 드라마",
                    like: 0,
                },
            ],
        };
    },
    methods: {
        increaseLike(i) {
            this.data[i].like += 1;
        },
    },
};
</script>

<style>
.bg-yellow {
    background-color: gold;
    padding: 10px;
}
</style>
