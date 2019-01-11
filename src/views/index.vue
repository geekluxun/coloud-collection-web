<style scoped lang="less">
    .index {
        width: 100%;
        position: absolute;
        top: 0;
        bottom: 0;
        left: 0;
        text-align: center;

        h1 {
            height: 150px;

            img {
                height: 100%;
            }
        }

        h2 {
            color: #666;
            margin-bottom: 200px;

            p {
                margin: 0 0 50px;
            }
        }

        .ivu-row-flex {
            height: 100%;
        }
    }
</style>
<!--<template>-->
<!--<div>-->

<!--<div class="layout">-->
<!--&lt;!&ndash;<Layout>&ndash;&gt;-->
<!--&lt;!&ndash;<Header>Header</Header>&ndash;&gt;-->
<!--&lt;!&ndash;<Content>Content</Content>&ndash;&gt;-->
<!--&lt;!&ndash;<Footer>Footer</Footer>&ndash;&gt;-->
<!--&lt;!&ndash;</Layout>&ndash;&gt;-->

<!--&lt;!&ndash;<Layout>&ndash;&gt;-->
<!--&lt;!&ndash;<Header>Header</Header>&ndash;&gt;-->
<!--&lt;!&ndash;<Layout>&ndash;&gt;-->
<!--&lt;!&ndash;<Sider hide-trigger>Sider</Sider>&ndash;&gt;-->
<!--&lt;!&ndash;<Content>Content</Content>&ndash;&gt;-->
<!--&lt;!&ndash;</Layout>&ndash;&gt;-->
<!--&lt;!&ndash;<Footer>Footer</Footer>&ndash;&gt;-->
<!--&lt;!&ndash;</Layout>&ndash;&gt;-->

<!--<Layout>-->
<!--<Header>Header</Header>-->
<!--<Layout>-->
<!--<Content>-->
<!--<div>-->
<!--<Row gutter="310" type="flex" justify="start" align="top">-->
<!--<Col span="6">-->
<!--<Menu theme="dark">-->
<!--<Submenu name="1">-->
<!--<template slot="title">-->
<!--<Icon type="ios-paper"/>-->
<!--收藏管理-->
<!--</template>-->
<!--<MenuItem name="addCollection">新增收藏</MenuItem>-->
<!--<MenuItem name="allCollection">所有收藏</MenuItem>-->
<!--</Submenu>-->

<!--<Submenu name="3">-->
<!--<template slot="title">-->
<!--<Icon type="ios-stats"/>-->
<!--统计分析-->
<!--</template>-->
<!--<MenuGroup title="浏览">-->
<!--<MenuItem name="3-1">最近一周</MenuItem>-->
<!--<MenuItem name="3-2">最近一月</MenuItem>-->
<!--<MenuItem name="3-3">最近一年</MenuItem>-->
<!--</MenuGroup>-->
<!--</Submenu>-->
<!--</Menu>-->
<!--</Col>-->
<!--<Col span="18"style="background-color: #2f54eb">-->
<!--<p style="height: 580px">dd</p>-->
<!--</Col>-->
<!--</Row>-->

<!--</div>-->
<!--</Content>-->

<!--</Layout>-->
<!--<Footer>Footer</Footer>-->
<!--</Layout>-->


<!--&lt;!&ndash;<Layout>&ndash;&gt;-->
<!--&lt;!&ndash;<Sider hide-trigger>Sider</Sider>&ndash;&gt;-->
<!--&lt;!&ndash;<Layout>&ndash;&gt;-->
<!--&lt;!&ndash;<Header>Header</Header>&ndash;&gt;-->
<!--&lt;!&ndash;<Content>Content</Content>&ndash;&gt;-->
<!--&lt;!&ndash;<Footer>Footer</Footer>&ndash;&gt;-->
<!--&lt;!&ndash;</Layout>&ndash;&gt;-->
<!--&lt;!&ndash;</Layout>&ndash;&gt;-->
<!--</div>-->
<!--</div>-->
<!--</template>-->
<!--<script>-->
<!--export default {-->
<!--data() {-->
<!--return {-->
<!--theme2: 'light'-->
<!--}-->
<!--}-->
<!--}-->
<!--</script>-->

<style scoped>
    .layout {
        border: 1px solid #d7dde4;
        /*background: #f5f7f9;*/
        position: relative;
        border-radius: 4px;
        overflow: hidden;
    }

    .layout-logo {
        width: 100px;
        height: 30px;
        background: #5b6270;
        border-radius: 3px;
        float: left;
        position: relative;
        top: 15px;
        left: 20px;
    }

    .layout-nav {
        width: 420px;
        margin: 0 auto;
        margin-right: 20px;
    }

    .layout-footer-center {
        align: center;
        text-align: right;
        margin: 0 auto;
        background: #4d5669;
    }
</style>
<template>
    <div class="layout">
        <Layout>
            <Drawer title="用户管理" :closable="false" v-model="value1">
                <p>Some contents...</p>
                <p>Some contents...</p>
                <p>Some contents...</p>
            </Drawer>

            <Sider hide-trigger :style="{padding: '50px 0px'}">
                <Menu active-name="1-2" theme="dark" width="auto" :open-names="['1']">
                    <Submenu name="1">
                        <template slot="title">
                            <Icon type="ios-navigate"></Icon>
                            收藏管理
                        </template>
                        <MenuItem name="1-1">添加收藏</MenuItem>
                        <MenuItem name="1-2">浏览收藏</MenuItem>
                    </Submenu>
                    <Submenu name="2">
                        <template slot="title">
                            <Icon type="ios-keypad"></Icon>
                            统计管理
                        </template>
                        <MenuItem name="2-1">最近一周</MenuItem>
                        <MenuItem name="2-2">最近一月</MenuItem>
                    </Submenu>
                </Menu>
            </Sider>

            <Layout>
                <Header>

                    <Row gutter = "20" type="flex" justify="end" align="top">
                        <Col>
                            <Input style="width: auto" search placeholder="Enter something..."/>
                        </Col>
                        <Col>
                            <div @click="value1 = true">
                                <Avatar icon="ios-person" size="large"/>
                            </div>
                        </Col>
                        <Col>
                            <div>
                                <Button @click="queryPages">测试</Button>
                            </div>
                        </Col>

                    </Row>
                </Header>

                <Content :style="{ minHeight: '580px'}">

                    <!--<Layout>-->
                    <!--<Collection></Collection>-->
                    <!--&lt;!&ndash;<Content :style="{padding: '24px', minHeight: '580px', background: '#fff'}">&ndash;&gt;-->
                    <!--&lt;!&ndash;&ndash;&gt;-->
                    <!--&lt;!&ndash;</Content>&ndash;&gt;-->
                    <!--</Layout>-->
                    <Table border :columns="collection_col" :data="pageList">
                        <template slot-scope="{ row }" slot="name">
                            <strong>{{ row.name }}</strong>
                        </template>
                        <template slot-scope="{ row, index }" slot="action">
                            <Button type="primary" size="small" style="margin-right: 5px" @click="show(index)">View
                            </Button>
                            <Button type="error" size="small" @click="remove(index)">Delete</Button>
                        </template>
                    </Table>
                </Content>
                <Footer align="center" style="background-color: #fff">2019-2020 &copy; geekluxun.com</Footer>
            </Layout>
        </Layout>
    </div>
</template>

<script>
    import collection from './collection.vue'
    import Button from "../../dist/vendors";

    export default {
        data() {
            return {
                value1: true,
                collection_col: [
                    {
                        title: '网页名字',
                        key: 'name'
                    },
                    {
                        title: '重要性',
                        key: 'level'
                    },
                    {
                        title: '浏览次数',
                        key: 'browseTotalCount'
                    },
                    {
                        title: '最近一次浏览时间',
                        key: 'lastBrowseTime',
                    }
                ],
                pageList: []
            }
        },
        components: {},
        methods: {
            testGetRequest: function () {
                axios.get('http://localhost:8084/user/test')
                    .then(function (response) {
                        // handle success
                        console.log(response.data().body);
                    })
                    .catch(function (error) {
                        // handle error
                        console.log(error);
                    })
                    .then(function () {
                        // always executed
                    });
            },
            queryPages: function () {
                var _this = this;
                axios.get('http://localhost:8084/pagecollection/queryPages', {
                    headers: {'X-Requested-With': 'XMLHttpRequest'},
                })
                    .then((response) => {
                        console.log(response.data.data.pageList);
                        // _this.value1 = false;
                        this.pageList = response.data.data.pageList;
                    });
                ;

            }
        }
    }

    const axios = require('axios');


</script>







