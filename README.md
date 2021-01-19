# Scraper

收集的和自己写的一些web scraper的sitemaps配置文件


# sitemap列表
## 微信

### 抓取公众号标题、时间、内容链接

>`{"_id":"gongzhonghao","startUrl":["https://mp.weixin.qq.com/mp/profile_ext?action=home&__biz=MzIxODUxMDM5MQ==&scene=124&#wechat_redirect"],"selectors":[{"id":"total","type":"SelectorElementScroll","parentSelectors":["_root"],"selector":"div.weui_msg_card:nth-of-type(n+2)","multiple":true,"delay":"1000"},{"id":"title","type":"SelectorText","parentSelectors":["total"],"selector":"h4.weui_media_title","multiple":false,"regex":"","delay":0},{"id":"date","type":"SelectorText","parentSelectors":["total"],"selector":"p.weui_media_extra_info","multiple":false,"regex":"","delay":0},{"id":"link","type":"SelectorElementAttribute","parentSelectors":["total"],"selector":"h4.weui_media_title","multiple":false,"extractAttribute":"hrefs","delay":0}]}`

## 知乎

### 知乎大 V 所有文章标题、链接、点赞数、评论数

>`{"_id":"zhihu-article","startUrl":["https://www.zhihu.com/people/zhang-jia-wei/posts?page=[1-44]"],"selectors":[{"id":"aaa","type":"SelectorElement","parentSelectors":["_root"],"selector":"div.List-item","multiple":true,"delay":"2000"},{"id":"title","type":"SelectorLink","parentSelectors":["aaa"],"selector":"h2.ContentItem-title a","multiple":false,"delay":0},{"id":"like","type":"SelectorText","parentSelectors":["aaa"],"selector":"button.Button.VoteButton--up","multiple":false,"regex":"","delay":0},{"id":"comments","type":"SelectorText","parentSelectors":["aaa"],"selector":"button.Button.ContentItem-action:nth-of-type(1)","multiple":false,"regex":"","delay":0}]}`


### 知乎大 V 所有回答、链接、点赞数、评论数

>`{"_id":"zhihu-questions","startUrl":["https://www.zhihu.com/people/zhang-jia-wei/answers?page=[1-169]"],"selectors":[{"id":"total","type":"SelectorElement","parentSelectors":["_root"],"selector":"div.List-item","multiple":true,"delay":"2000"},{"id":"questions","type":"SelectorLink","parentSelectors":["total"],"selector":"h2.ContentItem-title a","multiple":false,"delay":0},{"id":"likes","type":"SelectorText","parentSelectors":["total"],"selector":"button.Button.VoteButton--up","multiple":false,"regex":"","delay":0},{"id":"comments","type":"SelectorText","parentSelectors":["total"],"selector":"button.Button.ContentItem-action:nth-of-type(1)","multiple":false,"regex":"","delay":0}]}`

### 抓取知乎搜索关键字，所有结果标题、链接、点赞数、评论数

>`{"_id":"zhihu-search","startUrl":["https://www.zhihu.com/search?q=%E8%B5%9A%E9%92%B1&type=content"],"selectors":[{"id":"total","type":"SelectorElementScroll","parentSelectors":["_root"],"selector":"div.List div div.List-item","multiple":true,"delay":"3000"},{"id":"link","type":"SelectorLink","parentSelectors":["total"],"selector":"h2.ContentItem-title a","multiple":false,"delay":0},{"id":"likes","type":"SelectorText","parentSelectors":["total"],"selector":"button.Button.VoteButton--up","multiple":false,"regex":"","delay":0},{"id":"comments","type":"SelectorText","parentSelectors":["total"],"selector":"button.Button.ContentItem-action","multiple":false,"regex":"","delay":0}]}`

## 头条

### 抓取头条热点文章标题、发布源、评论数、发布时间

>`{"_id":"toutiao","startUrl":["https://www.toutiao.com/ch/news_hot/"],"selectors":[{"id":"total","type":"SelectorElementScroll","parentSelectors":["_root"],"selector":"div.item-inner","multiple":true,"delay":"4000"},{"id":"link","type":"SelectorLink","parentSelectors":["total"],"selector":"a.link","multiple":false,"delay":0},{"id":"source","type":"SelectorText","parentSelectors":["total"],"selector":"a.lbtn.source","multiple":false,"regex":"","delay":0},{"id":"comments","type":"SelectorText","parentSelectors":["total"],"selector":"a.lbtn.comment","multiple":false,"regex":"","delay":0},{"id":"time","type":"SelectorText","parentSelectors":["total"],"selector":"span.lbtn","multiple":false,"regex":"","delay":0}]}`


## fofa


## 微博

### 抓取微博内容、转发链接、转发数、评论数、点赞数、发布时间

>`{"_id":"weibo","startUrl":["https://weibo.com/bylixiaolai?is_search=0&visible=0&is_hot=1&is_tag=0&profile_ftype=1&page=[1-60]#feedtop"],"selectors":[{"id":"total","type":"SelectorElementScroll","parentSelectors":["_root"],"selector":"div.WB_cardwrap.WB_feed_type:nth-of-type(n+2)","multiple":true,"delay":"1000"},{"id":"click","type":"SelectorElementClick","parentSelectors":["_root"],"selector":"div.WB_cardwrap:nth-of-type(2) div.WB_text","multiple":true,"delay":"2000","clickElementSelector":"div.WB_text.W_f14 a.WB_text_opt","clickType":"clickOnce","discardInitialElements":false,"clickElementUniquenessType":"uniqueText"},{"id":"real-total","type":"SelectorElementScroll","parentSelectors":["_root"],"selector":"div.WB_cardwrap.WB_feed_type:nth-of-type(n+2)","multiple":true,"delay":"10000"},{"id":"content","type":"SelectorText","parentSelectors":["real-total"],"selector":"div.WB_text","multiple":false,"regex":"","delay":0},{"id":"forward","type":"SelectorLink","parentSelectors":["real-total"],"selector":"a.S_func1.W_autocut","multiple":false,"delay":0},{"id":"shares","type":"SelectorText","parentSelectors":["real-total"],"selector":"li:nth-of-type(2) em:nth-of-type(2)","multiple":false,"regex":"","delay":0},{"id":"comments","type":"SelectorText","parentSelectors":["real-total"],"selector":"li:nth-of-type(3) em:nth-of-type(2)","multiple":false,"regex":"","delay":0},{"id":"likes","type":"SelectorText","parentSelectors":["real-total"],"selector":"li:nth-of-type(4) em:nth-of-type(2)","multiple":false,"regex":"","delay":0},{"id":"time","type":"SelectorText","parentSelectors":["real-total"],"selector":"div.WB_detail > div.WB_from a.S_txt2:nth-of-type(1)","multiple":false,"regex":"","delay":0}]}`

## 抓取微博所有评论

>`{"_id":"weibo-comment","startUrl":["https://weibo.com/1576218000/Gqjfh0VYa?filter=hot&root_comment_id=0&type=comment"],"selectors":[{"id":"scroll","type":"SelectorElementScroll","parentSelectors":["_root"],"selector":"div.list_box > div.list_ul > div.list_li:nth-of-type(1) > div.list_con > div.WB_text","multiple":true,"delay":"1000"},{"id":"click","type":"SelectorElementClick","parentSelectors":["_root"],"selector":"div.list_box > div.list_ul > div.list_li > div.list_con > div.WB_text","multiple":true,"delay":"3000","clickElementSelector":"span.more_txt","clickType":"clickMore","discardInitialElements":false,"clickElementUniquenessType":"uniqueCSSSelector"},{"id":"content","type":"SelectorText","parentSelectors":["click"],"selector":"parent","multiple":false,"regex":"","delay":0}]}`


## 豆瓣



## 油管


