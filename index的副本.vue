<template>
    <div class="nsp-hall">
        <div class="nsp-hall__list">
            <div class="nsp-hall__list__head">
                <g-dropdown>
                    <a class="ant-dropdown-link" @click.prevent>
                        综合排序
                        <DownOutlined />
                    </a>
                    <template #overlay>
                        <g-menu>
                            <g-menu-item>
                                <a href="javascript:;">综合排序</a>
                            </g-menu-item>
                            <g-menu-item>
                                <a href="javascript:;">最新收益</a>
                            </g-menu-item>
                            <g-menu-item>
                                <a href="javascript:;">最新发布</a>
                            </g-menu-item>
                        </g-menu>
                    </template>
                </g-dropdown>
                <g-dropdown>
                    <a class="ant-dropdown-link" @click.prevent>
                        所有类型
                        <DownOutlined />
                    </a>
                    <template #overlay>
                        <g-menu>
                            <g-menu-item>
                                <a href="javascript:;">1st menu item</a>
                            </g-menu-item>
                            <g-menu-item>
                                <a href="javascript:;">2nd menu item</a>
                            </g-menu-item>
                            <g-menu-item>
                                <a href="javascript:;">3rd menu item</a>
                            </g-menu-item>
                        </g-menu>
                    </template>
                </g-dropdown>
                <g-dropdown>
                    <a class="ant-dropdown-link" @click.prevent>
                        所有物料
                        <DownOutlined />
                    </a>
                    <template #overlay>
                        <g-menu>
                            <g-menu-item>
                                <a href="javascript:;">1st menu item</a>
                            </g-menu-item>
                            <g-menu-item>
                                <a href="javascript:;">2nd menu item</a>
                            </g-menu-item>
                            <g-menu-item>
                                <a href="javascript:;">3rd menu item</a>
                            </g-menu-item>
                        </g-menu>
                    </template>
                </g-dropdown>
                <g-dropdown>
                    <a class="ant-dropdown-link" @click.prevent>
                        设计手法
                        <DownOutlined />
                    </a>
                    <template #overlay>
                        <g-menu>
                            <g-menu-item>
                                <a href="javascript:;">1st menu item</a>
                            </g-menu-item>
                            <g-menu-item>
                                <a href="javascript:;">2nd menu item</a>
                            </g-menu-item>
                            <g-menu-item>
                                <a href="javascript:;">3rd menu item</a>
                            </g-menu-item>
                        </g-menu>
                    </template>
                </g-dropdown>
            </div>
            <div class="nsp-hall__list__item">
                <!-- 弹出框 -->
                <g-modal
                    v-model:visible="visible"
                    @ok="handleOk"
                    class="nsp-hall__modal"
                    width="800px"
                    centered="true"
                    okText="领取任务"
                >
                    <div class="nsp-hall__modal-title">2022年货节-春节不打烊-单个任务</div>
                    <div class="nsp-hall__modal-type">平面模版</div>
                    <div class="nsp-hall__modal-steps">
                        <g-steps :current="1">
                            <g-step>
                                <template #title>视觉设计</template>
                            </g-step>
                            <g-step title="文件回收" />
                            <g-step title="完成" />
                        </g-steps>
                    </div>
                    <div class="nsp-hall__modal-taskContent">
                        <p class="nsp-hall__modal-taskContent-title">任务内容</p>
                        <p class="modaltag">物料</p>
                        <p class="nsp-hall__modal-taskContent-info">淘宝详情图</p>
                        <br />
                        <p class="modaltag">规格</p>
                        <p class="nsp-hall__modal-taskContent-info">淘宝详情图</p>
                        <br />
                        <p class="modaltag">文案</p>
                        <p class="nsp-hall__modal-taskContent-info">淘宝详情图</p>
                    </div>
                    <div class="nsp-hall__modal-taskRequire">
                        <p class="nsp-hall__modal-taskRequire-title">内容要求</p>
                    </div>

                    <div class="nsp-hall__modal-source">
                        <p class="nsp-hall__modal-source-title">可用素材</p>
                        <p class="nsp-hall__modal-source-desc">
                            部分稿定素材、任务附件素材、原创素材，不允许使用第三方素材
                        </p>
                    </div>
                    <div class="nsp-hall__modal-captin">
                        <div class="nsp-hall__modal-captin-title">任务说明</div>
                        <div class="nsp-hall__modal-captin-desc">
                            请根据要求和文案，设计制作平面模版
                        </div>
                    </div>
                    <!-- <g-divider style="margin: 0" /> -->
                    <template #footer>
                        <p class="nsp-hall__modal-time">初稿时间</p>
                        <p class="nsp-hall__modal-timeinfo">2021-11-26</p>
                        <p class="nsp-hall__modal-time">截稿时间</p>
                        <p class="nsp-hall__modal-timeinfo">2021-12-05 18:00</p>
                        <p class="nsp-hall__modal-price">金额</p>
                        <p class="nsp-hall__modal-priceinfo">¥2738</p>
                        <g-button type="primary" class="nsp-hall__modal-gettask">领取任务</g-button>
                    </template>
                </g-modal>
                <div
                    v-for="item in [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18]"
                >
                    <g-card hoverable style="width: 240px" :bordered="false" @click="showModal">
                        <template #cover>
                            <img
                                alt="example"
                                src="https://cdn.dancf.com/fe-assets/img/eaf355e38ba56abea567cb8419fe0f0d.png"
                                width="240"
                                height="240"
                            />
                        </template>
                        <g-card-meta
                            title="金融保险保险人力增加"
                            class="nsp-hall__list__item-title"
                        ></g-card-meta>
                        <g-card-meta
                            title="海报设计-手机海报"
                            class="nsp-hall__list__item-type"
                        ></g-card-meta>
                        <g-card-meta :title="item" class="nsp-hall__list__item-price"></g-card-meta>
                    </g-card>
                </div>
            </div>
            <g-divider>没有更多可领取任务</g-divider>
            <!-- 其他任务类型 -->
            <div class="nsp-hall__more">
                <h3 class="nsp-hall__more__head">开通其他任务类型，领取更多任务</h3>
                <div class="nsp-hall__more__item">
                    <g-card
                        hoverable
                        style="width: 240px; border-radius: 8px"
                        v-for="item in [1, 2, 3, 4]"
                    >
                        <template #cover>
                            <img
                                alt="example"
                                src="https://os.alipayobjects.com/rmsportal/QBnOOoLaAfKPirc.png"
                                width="240"
                                height="120"
                            />
                        </template>
                        <g-card-meta
                            title="分镜设计"
                            class="nsp-hall__more__item-title"
                        ></g-card-meta>
                        <g-card-meta
                            title="当前任务236个，最高金额1000元"
                            class="nsp-hall__more__item-desc"
                        ></g-card-meta>
                        <g-card-meta
                            title="申请开通"
                            class="nsp-hall__more__item-button"
                        ></g-card-meta>
                    </g-card>
                </div>
            </div>
        </div>
    </div>
</template>
<script lang="ts">
import { defineComponent, ref } from 'vue';
import { DownOutlined } from '@gaoding/icons-vue';
// import { DDragSelect } from '@gaoding/dam-components';

export default defineComponent({
    components: {
        DownOutlined,
        // DDragSelect,
    },
    setup() {
        const visible = ref<boolean>(false);

        const showModal = () => {
            visible.value = true;
        };

        const handleOk = (e: MouseEvent) => {
            console.log(e);
            visible.value = false;
        };
        return {
            visible,
            showModal,
            handleOk,
        };
    },
});
</script>
<style lang="less">
.nsp-hall {
    &__list__item {
        display: flex;
        flex-flow: row wrap;
        justify-content: flex-start;
        margin-top: 25px;

        .gda-card {
            margin-right: 14px;
            margin-bottom: 20px;
            margin-left: 13px;
        }

        .gda-card-body {
            padding: 14px 10px 0 0;
        }

        &-title {
            font-family: PingFang SC;
            font-size: 14px;
            font-style: normal;
            font-weight: 500;
            line-height: 22px;
            color: #33383e;
        }

        &-type .gda-card-meta-title {
            margin-top: 6px;
            margin-bottom: 12px;
            font-family: PingFang SC;
            font-size: 12px;
            font-style: normal;
            font-weight: normal;
            line-height: 18px;
            color: #9da3ac;
        }
    }
    //任务的弹出框
    &__modal {
        .gda-modal-content {
            position: relative;
            width: 800px;
            height: 550px;
            padding-bottom: 72px;
        }

        .gda-modal-body {
            height: 100%;
            padding: 32px 40px 16px;
            overflow: auto;
        }

        &-title {
            font-family: PingFang SC;
            font-size: 22px;
            font-style: normal;
            font-weight: 600;
            line-height: 28px;
            color: #33383e;
        }

        &-type {
            margin-top: 8px;
            margin-bottom: 16px;
            font-family: PingFang SC;
            font-size: 14px;
            font-style: normal;
            font-weight: normal;
            line-height: 20px;
            color: #9da3ac;
        }
        //步骤条
        .gda-steps {
            padding: 20px 38px;
            background: #f4f6fa;
            border-radius: 4px;
        }

        //弹出框内部标题统一样式
        &-source-title,
        &-captin-title,
        &-taskRequire-title,
        &-taskContent-title {
            margin-top: 40px;
            margin-bottom: 16px;
            font-size: 16px;
            font-weight: 600;
            line-height: 22px;
            color: #33383e;
        }

        &-source-desc,
        &-captin-desc {
            font-family: PingFang SC;
            font-size: 14px;
            font-style: normal;
            font-weight: normal;
            line-height: 22px;
            color: #33383e;
        }
        //弹出框内灰色标签统一样式
        .modaltag {
            display: inline-block;
            padding: 2px 7px;
            background: #f3f3f3;
            border-radius: 4px;
        }

        &-taskContent-info {
            display: inline-block;
            margin: 0 10px;
            font-size: 14px;
            line-height: 22px;
            color: #33383e;
        }
        //弹出框footer
        .gda-modal-footer {
            position: absolute;
            bottom: 0;
            display: flex;
            flex-direction: row;
            align-items: flex-start;
            justify-content: flex-start;
            width: 100%;
            height: 72px;
            padding: 16px 24px;
            border-top: 1px solid #f6f6fa;
        }

        &-time,
        &-price {
            margin-right: 12px;
            font-family: PingFang SC;
            font-size: 14px;
            line-height: 40px;
            color: #7f8792;
        }

        &-timeinfo,
        &-priceinfo {
            margin-right: 38px;
            font-size: 14px;
            font-weight: 500;
            line-height: 40px;
            color: #33383e;
        }

        &-priceinfo {
            font-size: 18px;
            font-weight: 500;
            color: #faaa32;
            text-align: center;
        }

        &-gettask {
            margin-left: auto;
        }
    }

    // 中间那条分割线
    .gda-divider-inner-text {
        font-family: PingFang SC;
        font-size: 14px;
        font-style: normal;
        font-weight: normal;
        line-height: 22px;
        color: #9da3ac;
    }
    //更多任务
    &__more {
        padding-left: 5px;
    }

    &__more__head {
        width: 270px;
        height: 22px;
        margin-top: 56px;
        margin-left: 18px;
        font-family: PingFang SC;
        font-size: 18px;
        font-style: normal;
        font-weight: 500;
        line-height: 22px;
        color: #000;
    }

    &__more__item {
        display: flex;
        flex-flow: row wrap;
        justify-content: flex-start;
        margin-top: 20px;

        .gda-card {
            margin-bottom: 20px;
            margin-left: 20px;
        }

        .gda-card-body {
            padding: 16px;
        }

        &-title .gda-card-meta-title {
            font-family: PingFang SC;
            font-size: 16px;
            font-style: normal;
            font-weight: 500;
            line-height: 22px;
            color: #000;
        }

        &-desc .gda-card-meta-title {
            margin-top: 5px;
            font-family: PingFang SC;
            font-size: 12px;
            font-style: normal;
            font-weight: 500;
            line-height: 22px;
            color: #9da3ac;
        }

        &-button .gda-card-meta-title {
            display: flex;
            display: block;
            box-sizing: border-box;
            align-items: center;
            width: 206px;
            height: 42px;
            margin: 20px auto 2px;
            font-family: PingFang SC;
            font-size: 14px;
            font-style: normal;
            font-weight: 500;
            line-height: 42px;
            color: #2254f4;
            text-align: center;
            border: 1px solid #2254f4;
            border-radius: 4px;
        }
    }
}
</style>
<config lang="json">
{
    "title": "任务大厅",
    "name": "task-hall"
}
</config>
