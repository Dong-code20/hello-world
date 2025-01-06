<template>
    <div class="hello">
        <h1>{{ msg }}</h1>
        <el-button>默认按钮</el-button>
        <el-button size="large">中等按钮</el-button>
        <el-button size="small">小型按钮</el-button>
        <el-button size="mini">超小按钮</el-button>
        <el-empty description="空空如也~~~~~~~"></el-empty>
        <el-skeleton
            :rows="1"
            :loading="loading"
            :animated="true"
            :throttle="1000"
        >
            <h1>这里是真实的页面元素</h1>
            <p>{{ skeletonMsg }}</p>
        </el-skeleton>
    </div>
</template>

<script>
export default {
    name: "HelloWorld",
    props: {
        msg: String,
    },
    data() {
        return {
            loading: true,
            skeletonMsg: "",
        };
    },
    methods: {
        getData() {
            (this.skeletonMsg = "这里是请求到的数据"), (this.loading = false);
        },
    },
    mounted() {
        setTimeout(() => {
            this.getData();
        }, 3000);
    },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
