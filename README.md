# Baidu Express Query API
百度快递运单号查询接口

该接口为百度搜索页快递100提供的接口,几乎可以自动识别和查询所有的快递单号
### 接口地址
`https://sp0.baidu.com/9_Q4sjW91Qh3otqbppnN2DJv/pae/channel/data/asyncqury`
### 参数(GET)
```
payload = {
  'cb': '',
  'appid': 4001,
  'nu': '欲查询的快递运单号',
  'vcode' : '',
  'token' : '',
  '_' : '时间戳(毫秒)'
}
```

###返回结果
JSON格式
```
{
  "msg":"",                  #查询状态信息,查询成功时为空
  "status":"0",              #查询状态,0为成功
  "error_code":"0",          #查询状态,0为成功
  "data":{
    "notice":"物流信息与官网实时同步，已耗时X天X时XX分",
     "com":"yunda",          #快递公司英文
     "company":{...},        #快递公司信息
     "source":{...},         #数据来源
     "kuaidiSource":{...},   #快递接口来源
    "info":{
      "status":"1",           #查询状态?
      "com":"yunda",          #快递公司英文
      "state":"0",            #签收状态?
      "context":{
        {
          "time":"1482000831",      #快递动态发生 时间戳
          "desc":"在X,即将发往：X"   #发生事件描述
        },
        {...}
      },
      "_source_com":"yunda",       #数据来源公司
      "_support_from":"partner"    #没几把用
    }
}
```
