<template>
    <div class="page-about">
        <ui-header></ui-header>
        <main class="page-body">
            <div class="container">
                <article class="article">
                    <h2>关于我们</h2>
                    <p>云设教程致力于提供最新、最全、最好的入门基础教程。</p>
                    <p>我们的目标是，让技术入门不再有难度，让人人都能学会编程，让每个人都能实现自己的产品梦想。</p>
                    <p>本站提供了 HTML、CSS、JavaScript 等各种基础教程，有各种讲解，有示例，有测试，让学习不再枯燥。</p>
                    <p>通过本站，你只要花几天的时间，就可以实现一个简单的网站或 App。</p>
                    <p>当然，由于人力有限，本站内容还有很多不足之处，欢迎广大编程爱好者在本站留言提供意见。</p>
                </article>
            </div>
        </main>
        <ui-footer></ui-footer>
    </div>
</template>

<script>
    export default {
        data () {
            return {
                version: 'v1.0.1'
            }
        },
        mounted() {
            this.$http.get('/version').then(
                response => {
                    let data = response.data
                    if (data.code === 200) {
                        console.log(data)
                        this.version = data.data
                    }
                },
                response => {
                    console.log(response)
                })
//            this.$http.post('/example', this.$qs.stringify({
//                param1: 'value1',
//                param2: 'value2'
//            })).then(
//                response => {
//                    let data = response.data
//                    if (data.code === 200) {
//                        console.log(data.data)
//                    }
//                },
//                response => {
//                    console.log(response)
//                })
        }
    }
</script>

<style scoped>
</style>
