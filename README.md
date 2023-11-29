## 本项目实现的最终作用是基于JSP旅游网站管理系统
## 分为2个角色
### 第1个角色为管理员角色，实现了如下功能：
 - 图片库管理
 - 景点管理
 - 留言管理
 - 管理员登录
 - 管理员管理
 - 管留言信息修改
 - 资讯管理
### 第2个角色为用户角色，实现了如下功能：
 - 人文地理
 - 地区资讯
 - 景点介绍
 - 用户首页
 - 留言
## 数据库设计如下：
# 数据库设计文档

**数据库名：** travel_website

**文档版本：** 


| 表名                  | 说明       |
| :---: | :---: |
| [t_banner](#t_banner) | 图片轮播 |
| [t_food](#t_food) |  |
| [t_group](#t_group) | 管理员级别 |
| [t_info](#t_info) | 资讯表 |
| [t_msg](#t_msg) | 留言表 |
| [t_pic](#t_pic) | 全表图片 |
| [t_scen](#t_scen) | 景点信息 |
| [t_scen_pic](#t_scen_pic) | 景点图片库 |
| [t_site](#t_site) | 网站基本设置 |
| [t_user](#t_user) | 用户表 |
| [t_video](#t_video) | 视频 |

**表名：** <a id="t_banner">t_banner</a>

**说明：** 图片轮播

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | ban_id |   int   | 10 |   0    |    N     |  Y   |       |   |
|  2   | ban_name |   varchar   | 255 |   0    |    Y     |  N   |   NULL    |   |
|  3   | ban_title |   varchar   | 80 |   0    |    Y     |  N   |   NULL    |   |
|  4   | ban_path |   varchar   | 255 |   0    |    Y     |  N   |   ''    | 轮播图路径  |
|  5   | scen_id |   int   | 10 |   0    |    Y     |  N   |   NULL    | 景点  |

**表名：** <a id="t_food">t_food</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | f_id |   int   | 10 |   0    |    N     |  Y   |       |   |
|  2   | f_name |   varchar   | 255 |   0    |    N     |  N   |       |   |
|  3   | f_introduce |   varchar   | 255 |   0    |    N     |  N   |       |   |
|  4   | pic_path |   varchar   | 255 |   0    |    N     |  N   |       |   |

**表名：** <a id="t_group">t_group</a>

**说明：** 管理员级别

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | group_id |   int   | 10 |   0    |    N     |  Y   |       |   |
|  2   | group_name |   varchar   | 255 |   0    |    N     |  N   |       | 级别  |

**表名：** <a id="t_info">t_info</a>

**说明：** 资讯表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | info_id |   int   | 10 |   0    |    N     |  Y   |       | Id  |
|  2   | info_title |   varchar   | 255 |   0    |    N     |  N   |       | 标题  |
|  3   | info_txt |   varchar   | 255 |   0    |    N     |  N   |       | 内容  |
|  4   | info_tag |   varchar   | 255 |   0    |    Y     |  N   |   NULL    |   |
|  5   | info_pic |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 图片  |
|  6   | info_video |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 视频  |
|  7   | info_url |   varchar   | 80 |   0    |    Y     |  N   |   NULL    | URl  |
|  8   | info_date |   date   | 10 |   0    |    Y     |  N   |   NULL    | 日期  |
|  9   | info_order |   int   | 10 |   0    |    Y     |  N   |   NULL    | 排序  |

**表名：** <a id="t_msg">t_msg</a>

**说明：** 留言表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | msg_id |   int   | 10 |   0    |    N     |  Y   |       |   |
|  2   | author |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 用户昵称  |
|  3   | msg_text |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 内容  |
|  4   | msg_time |   datetime   | 19 |   0    |    Y     |  N   |   NULL    | 留言时间  |
|  5   | msg_ip |   varchar   | 64 |   0    |    Y     |  N   |   NULL    | 留言IP  |
|  6   | email |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 邮箱  |

**表名：** <a id="t_pic">t_pic</a>

**说明：** 全表图片

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | pic_id |   int   | 10 |   0    |    N     |  N   |       |   |
|  2   | pic_name |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 图片名  |
|  3   | pic_title |   varchar   | 255 |   0    |    Y     |  N   |   ''    | 标题  |
|  4   | pic_path |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 路径  |
|  5   | pic_url |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 路径  |

**表名：** <a id="t_scen">t_scen</a>

**说明：** 景点信息

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | scen_id |   int   | 10 |   0    |    N     |  Y   |       | Id  |
|  2   | scen_name |   varchar   | 255 |   0    |    N     |  N   |       | 景点名称  |
|  3   | scen_intro |   varchar   | 1000 |   0    |    Y     |  N   |   NULL    | 介绍  |
|  4   | scen_level |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 等级  |
|  5   | scen_title |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 标题  |
|  6   | scen_feature |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 特色  |
|  7   | scen_traff |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 交通  |
|  8   | scen_map |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 地图描述  |
|  9   | pic_path |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 展示图片  |
|  10   | video_path |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 视频路径  |
|  11   | scen_add |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 地址  |
|  12   | scen_name_en |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 英文名  |
|  13   | scen_order |   int   | 10 |   0    |    Y     |  N   |   NULL    | 排序  |
|  14   | scen_url |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | URL地址  |

**表名：** <a id="t_scen_pic">t_scen_pic</a>

**说明：** 景点图片库

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | scen_id |   int   | 10 |   0    |    Y     |  N   |   NULL    |   |
|  2   | pic_id |   int   | 10 |   0    |    N     |  Y   |       |   |
|  3   | pic_title |   varchar   | 255 |   0    |    Y     |  N   |   NULL    |   |
|  4   | pic_name |   varchar   | 255 |   0    |    Y     |  N   |   NULL    |   |
|  5   | pic_path |   varchar   | 255 |   0    |    Y     |  N   |   NULL    |   |
|  6   | pic_url |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 路径  |

**表名：** <a id="t_site">t_site</a>

**说明：** 网站基本设置

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | site_name |   varchar   | 255 |   0    |    N     |  Y   |   ''    |   |
|  2   | site_keyword |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 关键词  |
|  3   | site_desc |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 描述  |
|  4   | site_copy |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 版权信息  |
|  5   | site_beian |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 备案号  |

**表名：** <a id="t_user">t_user</a>

**说明：** 用户表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | user_id |   int   | 10 |   0    |    N     |  Y   |       | 用户ID  |
|  2   | username |   varchar   | 255 |   0    |    N     |  N   |       | 用户名  |
|  3   | password |   char   | 32 |   0    |    N     |  N   |       | 密码  |
|  4   | email |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 邮箱  |
|  5   | register_time |   date   | 10 |   0    |    N     |  N   |       | 注册时间  |
|  6   | register_ip |   varchar   | 255 |   0    |    N     |  N   |   '127.0.0.1'    | 注册IP  |
|  7   | group_id |   int   | 10 |   0    |    N     |  N   |   0    | 管理员级别  |
|  8   | gender |   varchar   | 3 |   0    |    Y     |  N   |   NULL    | 性别  |
|  9   | user_pic |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 用户头像  |
|  10   | user_stat |   int   | 10 |   0    |    Y     |  N   |   1    | 状态  |

**表名：** <a id="t_video">t_video</a>

**说明：** 视频

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | video_id |   int   | 10 |   0    |    N     |  Y   |       |   |
|  2   | video_name |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 视频名称  |
|  3   | video_path |   varchar   | 255 |   0    |    N     |  N   |       | 视频路径  |
|  4   | video_title |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 标题  |
|  5   | video_url |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 路径  |

**运行不出来可以微信 javape 我的公众号：源码码头**
