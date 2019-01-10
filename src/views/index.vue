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
<template>
    <div>

        <div class="layout">
            <!--<Layout>-->
            <!--<Header>Header</Header>-->
            <!--<Content>Content</Content>-->
            <!--<Footer>Footer</Footer>-->
            <!--</Layout>-->

            <!--<Layout>-->
            <!--<Header>Header</Header>-->
            <!--<Layout>-->
            <!--<Sider hide-trigger>Sider</Sider>-->
            <!--<Content>Content</Content>-->
            <!--</Layout>-->
            <!--<Footer>Footer</Footer>-->
            <!--</Layout>-->

            <Layout>
                <Header>Header</Header>
                <Layout>
                    <Content>
                        <div>
                            <Row gutter="0" type="flex" justify="start" align="top">
                                <Col span="6">
                                    <Menu theme="dark">
                                        <Submenu name="1">
                                            <template slot="title">
                                                <Icon type="ios-paper"/>
                                                收藏管理
                                            </template>
                                            <MenuItem name="1-1">文章管理</MenuItem>
                                            <MenuItem name="1-2">评论管理</MenuItem>
                                            <MenuItem name="1-3">举报管理</MenuItem>
                                        </Submenu>
                                        <Submenu name="2">
                                            <template slot="title">
                                                <Icon type="ios-people"/>
                                                用户管理
                                            </template>
                                            <MenuItem name="2-1">新增用户</MenuItem>
                                            <MenuItem name="2-2">活跃用户</MenuItem>
                                        </Submenu>
                                        <Submenu name="3">
                                            <template slot="title">
                                                <Icon type="ios-stats"/>
                                                统计分析
                                            </template>
                                            <MenuGroup title="使用">
                                                <MenuItem name="3-1">新增和启动</MenuItem>
                                                <MenuItem name="3-2">活跃分析</MenuItem>
                                                <MenuItem name="3-3">时段分析</MenuItem>
                                            </MenuGroup>
                                            <MenuGroup title="留存">
                                                <MenuItem name="3-4">用户留存</MenuItem>
                                                <MenuItem name="3-5">流失用户</MenuItem>
                                            </MenuGroup>
                                        </Submenu>
                                    </Menu>
                                </Col>
                                <Col span="18"style="background-color: #2f54eb">
                                    <p style="height: 580px">dd</p>
                                </Col>
                            </Row>

                        </div>
                    </Content>

                </Layout>
                <Footer>Footer</Footer>
            </Layout>


            <!--<Layout>-->
            <!--<Sider hide-trigger>Sider</Sider>-->
            <!--<Layout>-->
            <!--<Header>Header</Header>-->
            <!--<Content>Content</Content>-->
            <!--<Footer>Footer</Footer>-->
            <!--</Layout>-->
            <!--</Layout>-->
        </div>
    </div>
</template>
<script>
    export default {
        data() {
            return {
                theme2: 'light'
            }
        }
    }
</script>




