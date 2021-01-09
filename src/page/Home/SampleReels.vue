<template>
    <div class="sample">
        <h2 class="sample-title">作品集</h2>
        <div class="sample-more">更多</div>
        <div class="sample-bigbox">
            <div class="sample-box" v-for="item of sampleData" :key="item">
                <div class="sample-box-img">
                    <img :src="require('assets/banner2.jpg')"></img>
                </div>
                <div class="sample-box-text">
                    <div class="sample-box-title">
                        斯坦·李逝世两周年纪念混检《感谢阿斯达斯的》
                    </div>
                    <div class="sample-box-extent">
                        创意混检·混检
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>

export default {
    components:{
    },
    data(){  
        return {
           sampleData: [1,2,3,4,5,6,7,8]
        }
    },
    methods:{
        
    }
}
</script>

<style lang="scss" scoped>
.sample{
    padding: 20px;
    margin: 0 auto;
    .sample-title{
        font-size: 16px;
        font-weight: 500;
        line-height: 60px;
        margin: 0;
    }
    .sample-more{
        font-size: 12px;
        font-weight: 600;
        text-align: right;
        padding: 0 66px;
    }
    .sample-bigbox{
        padding: 0 60px;
        margin-top: 10px;
        display: flex;
        flex-wrap: wrap;
        justify-content:space-around;
        .sample-box{
            width: 24%;
            height: 140px;
            .sample-box-img{
                width: 100%;
                height: 80px;
                img{
                    width: 100%;
                    height: 80px;
                }
            }
            .sample-box-text{
                background: #fff;
                .sample-box-title{
                    font-size: 12px;
                    font-weight: 600;
                    white-space: nowrap;
                    overflow: hidden;
                    text-overflow:ellipsis;
                    padding: 8px 10px 4px;
                    text-align: left;
                }
                .sample-box-extent{
                    font-size: 12px;
                    font-weight: 400;
                    color: #999;
                    padding: 0 10px 4px 10px;
                    text-align: left;
                }
            }
        }
    }
}
</style>