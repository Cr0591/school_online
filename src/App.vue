<template>
    <div class="layout">
      <Menu mode="horizontal" :theme="theme1" active-name="1">
        <MenuItem name="0" @click.native="go">
            <Avatar src="https://i.loli.net/2017/08/21/599a521472424.jpg" size="large" />
        </MenuItem>
        <MenuItem name="1" @click.native="clearCount1">
            <Icon type="ios-paper" />
            校园广场  
            <Badge :count="count1">
              <a href="#" class="demo-badge"></a>
            </Badge>
        </MenuItem>
        <MenuItem name="2" @click.native="clearCount2">
            <Icon type="ios-people" />
            校园官方
            <Badge :count="count2">
              <a href="#" class="demo-badge"></a>
            </Badge>
        </MenuItem>
        <MenuItem name="3" @click.native="clearCount3">
            <Icon type="ios-construct" />
            关注的动态
            <Badge :count="count3">
              <a href="#" class="demo-badge"></a>
            </Badge>
        </MenuItem>
    </Menu>
        <Layout>
            <Sider ref="side1" collapsible :collapsed-width="78" v-model="isCollapsed">
                <Menu active-name="1-2" theme="dark" width="auto" :class="menuitemClasses">
                    <Submenu name="1-1">
                      <template slot="title">
                        <Icon type="ios-contact" />
                        <span>我</span>
                      </template>
                      <!-- 这里用来渲染我的个人信息 -->
                        <MenuItem name="3-1">1</MenuItem>
                        <MenuItem name="3-2">2</MenuItem>
                        <MenuItem name="3-3">3</MenuItem>
                    </Submenu>
                    <Submenu name="1-2">
                      <template slot="title">
                        <Icon type="md-heart" />
                        <span>关注的人</span>
                      </template>
                      <!-- 这里用来渲染关注的人列表 -->
                        <MenuItem name="3-1">1</MenuItem>
                        <MenuItem name="3-2">2</MenuItem>
                        <MenuItem name="3-3">3</MenuItem>
                    </Submenu>
                    <Submenu name="1-3">
                      <template slot="title">
                        <Icon type="ios-people" />
                        <span>我的粉丝</span>
                      </template>
                      <!-- 这里用来渲染我的粉丝列表 -->
                        <MenuItem name="3-1">1</MenuItem>
                        <MenuItem name="3-2">2</MenuItem>
                        <MenuItem name="3-3">3</MenuItem>
                    </Submenu>
                </Menu>
            </Sider>
            <Layout>
                <Header :style="{padding: 0}" class="layout-header-bar">
                    <Icon @click.native="collapsedSider" :class="rotateIcon" :style="{margin: '0 20px'}" type="md-menu" size="24"></Icon>
                </Header>
                <Content :style="{margin: '20px', background: '#fff', minHeight: '260px'}">
                    <div class="showspace">
                      <List item-layout="vertical" border="true">
                        <ListItem v-for="item in data" :key="item.title">
                            <ListItemMeta :avatar="item.avatar" :title="item.title" :description="item.description" />
                            {{ item.content }}
                            <li>
                              <Icon type="ios-heart" />{{item.like}}
                              <Icon type="logo-twitch" />222
                            </li>
                            <template slot="extra">
                                <img :src="item.url1" style="width: 280px">
                                <img :src="item.url1" style="width: 280px">
                                <img :src="item.url1" style="width: 280px">
                            </template>
                        </ListItem>
                      </List>
                    </div>
                </Content>
            </Layout>
        </Layout>
        <BackTop></BackTop>
    </div>
</template>

<script>
    export default {
        data () {
            return {
                isCollapsed: false,
                theme1:'dark',
                count1:1,
                count2:2,
                count3:3,
                data: [
                    {
                        title: 'This is title 1',
                        description: 'This is description, this is description, this is description.',
                        avatar: 'https://dev-file.iviewui.com/userinfoPDvn9gKWYihR24SpgC319vXY8qniCqj4/avatar',
                        content: 'What a wonderful day',
                        like:'520',
                        url1:'http://img03.sogoucdn.com/app/a/100520146/d042f94479c0b82d19b3ae75891ab717',
                        
                    },
                    {
                        title: 'This is title 2',
                        description: 'This is description, this is description, this is description.',
                        avatar: 'https://dev-file.iviewui.com/userinfoPDvn9gKWYihR24SpgC319vXY8qniCqj4/avatar',
                        content: 'This is the content, this is the content, this is the content, this is the content.',
                        like:520,
                        url1:'http://img03.sogoucdn.com/app/a/100520146/d042f94479c0b82d19b3ae75891ab717',
                    },
                    {
                        title: 'This is title 3',
                        description: 'This is description, this is description, this is description.',
                        avatar: 'https://dev-file.iviewui.com/userinfoPDvn9gKWYihR24SpgC319vXY8qniCqj4/avatar',
                        content: 'This is the content, this is the content, this is the content, this is the content.',
                        like:520,
                        url1:'http://img03.sogoucdn.com/app/a/100520146/d042f94479c0b82d19b3ae75891ab717',
                    },
                    {
                        title: 'This is title 4',
                        description: 'This is description, this is description, this is description.',
                        avatar: 'https://dev-file.iviewui.com/userinfoPDvn9gKWYihR24SpgC319vXY8qniCqj4/avatar',
                        content: 'This is the content, this is the content, this is the content, this is the content.',
                        like:520,
                        url1:'http://img03.sogoucdn.com/app/a/100520146/d042f94479c0b82d19b3ae75891ab717',
                    },
                    {
                        title: 'This is title 5',
                        description: 'This is description, this is description, this is description.',
                        avatar: 'https://dev-file.iviewui.com/userinfoPDvn9gKWYihR24SpgC319vXY8qniCqj4/avatar',
                        content: 'This is the content, this is the content, this is the content, this is the content.',
                        like:520,
                        url1:'http://img03.sogoucdn.com/app/a/100520146/d042f94479c0b82d19b3ae75891ab717',
                    },
                    {
                        title: 'This is title 6',
                        description: 'This is description, this is description, this is description.',
                        avatar: 'https://dev-file.iviewui.com/userinfoPDvn9gKWYihR24SpgC319vXY8qniCqj4/avatar',
                        content: 'This is the content, this is the content, this is the content, this is the content.',
                        like:520,
                        url1:'http://img03.sogoucdn.com/app/a/100520146/d042f94479c0b82d19b3ae75891ab717',
                    },
                    {
                        title: 'This is title 7',
                        description: 'This is description, this is description, this is description.',
                        avatar: 'https://dev-file.iviewui.com/userinfoPDvn9gKWYihR24SpgC319vXY8qniCqj4/avatar',
                        content: 'This is the content, this is the content, this is the content, this is the content.',
                        like:520,
                        url1:'http://img03.sogoucdn.com/app/a/100520146/d042f94479c0b82d19b3ae75891ab717',
                    }
                ],
            }
        },
        computed: {
            rotateIcon () {
                return [
                    'menu-icon',
                    this.isCollapsed ? 'rotate-icon' : ''
                ];
            },
            menuitemClasses () {
                return [
                    'menu-item',
                    this.isCollapsed ? 'collapsed-menu' : ''
                ]
            }
        },
        methods: {
            collapsedSider () {
                this.$refs.side1.toggleCollapse();
            },
            /**清除提示点的函数 */
            clearCount1 (){
              this.count1 = 0;
            },
            clearCount2 (){
              this.count2 = 0;
            },
            clearCount3 (){
              this.count3 = 0;
            },
            /**页面跳转函数 */
            go(){
                alert('页面跳转')
            }
        }
    }
</script>

<style scoped>
    .layout{
        width: 100%;
        height: auto;
        border: 1px solid #d7dde4;
        background: #f5f7f9;
        position: relative;
        border-radius: 5px;
        overflow: hidden;
    }
    .layout-header-bar{
        background: #fff;
        box-shadow: 0 1px 1px rgba(0,0,0,.1);
    }
    .layout-logo-left{
        width: 90%;
        height: 50px;
        background: #5b6270;
        border-radius: 3px;
        margin: 15px auto;
    }
    .menu-icon{
        transition: all .3s;
    }
    .rotate-icon{
        transform: rotate(-90deg);
    }
    .menu-item span{
        display: inline-block;
        overflow: hidden;
        width: 69px;
        text-overflow: ellipsis;
        white-space: nowrap;
        vertical-align: bottom;
        transition: width .2s ease .2s;
    }
    .menu-item i{
        transform: translateX(0px);
        transition: font-size .2s ease, transform .2s ease;
        vertical-align: middle;
        font-size: 16px;
    }
    .collapsed-menu span{
        width: 0px;
        transition: width .2s ease;
    }
    .collapsed-menu i{
        transform: translateX(5px);
        transition: font-size .2s ease .2s, transform .2s ease .2s;
        vertical-align: middle;
        font-size: 22px;
    }
    .showspace ul > li{
        width: 100%;
        float: right;
        background-color: rgb(253, 255, 255);
        height: auto;
    }
</style>
