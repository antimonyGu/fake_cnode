<template>
    <div>
        <!-- 在数据未返回的时候，显示这个正加载的界面 -->
        <div class="loading" v-if="isLoading">
            <img src="../assets/loading.gif" alt="">
        </div>
        <!-- 主题帖子列表 -->
        <div>
            <ul>
                <li>
                    ul加载成功
                </li>
                <span>postlist挂载成功</span>
            </ul>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Postlist',
    data() {
        return {
            isLoading: false,
            posts: []         //页面的列表数组
        }
    },
    methods: {
        getData:function() {
            this.$http.get('https://cnodejs.org/api/v1/topics', {
                page: 1,
                limit: 20
            })
                .then(res=>{
                    this.isLoading = false; //加载成功，关闭加载动画
                    console.log(res)
                    this.posts = res.data.data;
                })
                .catch(err => {
                    //返回失败的问题
                    console.log(err)
                })
        },
        beforeMount() {
            this.isLoading = true;   //加载动画开启
            this.getData();
        },
    }
}
</script>

<style scoped>

</style>
