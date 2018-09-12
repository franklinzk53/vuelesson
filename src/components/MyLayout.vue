
<style scoped>
  .layout{
    border: 1px solid #d7dde4;
    background: #f5f7f9;
    position: relative;
    border-radius: 4px;
    overflow: hidden;
  }
  .layout-logo{
    width: 100px;
    height: 30px;
    background: #5b6270;
    border-radius: 3px;
    float: left;
    position: relative;
    top: 15px;
    left: 20px;
  }
  .layout-nav{
    width: 420px;
    margin: 0 auto;
    margin-right: 20px;
  }
</style>
<template>
  <div class="layout">
    <Layout>
      <Header :style="{position:'fixed',width:'100%',left:0}">
        <img src="../assets/logo.png" alt="" :style="{height:'100%'}">
      </Header>
      <Layout :style="pageStyle">
        <Sider  collapsible :collapsed-width="78" v-model="isCollapsed"  :style="{background: '#515a6e'}">
          <Menu accordion :active-name="'passinfo'" theme="dark" width="auto" :open-names="['statistics']" :class="menuitemClasses">
            <Submenu v-for=" menu in menus" :name="menu.name">
              <template slot="title">
                <Icon :title="menu.mname" :type="menu.icon"></Icon>
                <span :title="menu.mname">{{menu.mname}}</span>
              </template>
              <MenuItem v-for="sub in menu.submenu" :name="sub.name" :style="{paddingLeft:(!isCollapsed?43:23)+'px'}">
                <Icon :title="sub.mname" :type="sub.icon"></Icon>
                <span :title="sub.mname">{{sub.mname}}</span>
              </MenuItem>
            </Submenu>
          </Menu>
        </Sider>
        <Layout :style="{padding: '0 24px 24px'}">
          <Content :style="{padding: '24px', minHeight: '768px', background: '#fff'}">
            Content
          </Content>
        </Layout>
      </Layout>
    </Layout>
  </div>
</template>
<script>
  export default {
    data(){
      return {
        isCollapsed: false
        ,pageStyle:{position:'fixed', height: '100%',width:'100%', left: 0, top:'64px',overflow: 'auto'}
        ,menus:[{
          name:'statistics'
          ,icon:'ios-search'
          ,mname:'统计查询'
          ,submenu:[{
            name:'facecompareinfo'
            ,mname:'人像比对信息'
            ,icon:'ios-people'
          },{
            name:'passinfo'
            ,icon:'ios-person'
            ,mname:'旅客基本信息'
          },{
            name:'passcheckinfo'
            ,mname:'旅客安检信息'
            ,icon:'md-body'
          }]
        },{
          name:'resource'
          ,icon:'md-cog'
          ,mname:'资源管理'
          ,submenu:[{
            name:'area'
            ,mname:'区域管理'
            ,icon:'md-cloud'
          },{
            name:'machine'
            ,mname:'设备管理'
            ,icon:'md-apps'
          },{
            name:'server'
            ,mname:'服务器管理'
            ,icon:'md-cube'
          },{
            name:'base'
            ,mname:'底库管理'
            ,icon:'md-desktop'
          },{
            name:'face'
            ,mname:'人像管理'
            ,icon:'md-happy'
          }]
        },{
          name:'system'
          ,icon:'md-settings'
          ,mname:'系统管理'
          ,submenu:[{
            name:'organ'
            ,mname:'组织管理'
            ,icon:'md-happy'
          },{
            name:'rule'
            ,mname:'角色管理'
            ,icon:'md-man'
          },{
            name:'user'
            ,mname:'用户管理'
            ,icon:'ios-man'
          },{
            name:'version'
            ,mname:'版本信息'
            ,icon:'ios-paper'
          },{
            name:'syscss'
            ,mname:'系统样式'
            ,icon:'logo-windows'
          }]
        }]
      }
    }
    ,computed: {
      menuitemClasses: function () {
        return [
          'menu-item',
          this.isCollapsed ? 'collapsed-menu' : ''
        ]
      }
    }
  }
</script>
<style scoped>
  .menu-item span{
    display: inline-block;
    overflow: hidden;
    width: 100px;
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
</style>

