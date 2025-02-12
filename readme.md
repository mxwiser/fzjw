## 基本原理
通过调用查分项API获得xlsx文件，其中包含平时分等分项。
---
### 请求URL
      你的学校教务系统前缀 + /cjcx/cjcx_dcXsKccjList.html 
      如: ...xxx.edu.cn/cjcx/cjcx_dcXsKccjList.html 
      如: ...xxx.edu.cn/jwglxt/cjcx/cjcx_dcXsKccjList.html 
### 请求方式
POST请求
### 请求参数 (PostBodyParams)
请求时请带上账号登录后的Cookie
``` js
            [
                ['gnmkdmKey', 'N305005'],
                ['xnm', xnm],//学年号 查分页面F12调试界面可找到
                ['xqm', xqm],//学期号 查分页面F12调试界面可找到
                ['dcclbh', 'JW_N305005_GLY'],
                ...[
                    'kcmc@课程名称',
                    'xnmmc@学年',
                    'xqmmc@学期',
                    'kkbmmc@开课学院',
                    'kch@课程代码',
                    'jxbmc@教学班',
                    'xf@学分',
                    'xmcj@成绩',
                    'xmblmc@成绩分项'
                ].map(col => ['exportModel.selectCol', col]),
                ['exportModel.exportWjgs', 'xls'],
                ['fileName', '成绩单']
            ]
 ```     
### 返回结果
即成绩单
