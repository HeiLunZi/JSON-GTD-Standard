# JSON-GTD-Standard
在GTD系统中用JSON格式来描述stuff

# JSON格式

格式非常简单，一共就是三部分。

```json
{
    "StuffID":"",
    "StuffDescription":{},
    "StuffDetailed":{}
}
```

- StuffID：Stuff的唯一身份证号码。
  
- StuffDescription：描述Stuff的内容。
  
- StuffDetailed：记录Stuff的详细内容。
  

详细请看接下来的小节

## StuffID

Stuff的唯一身份证号码。

- 类型：字符串
  
- 规则：12位定长
  
- 字符集：`0123456789abcdefghijklnmopqrstuvwxyz`（共35个字符）
  
- 示例
  

```json
{
    "StuffID":"a2k9n7x8y1z3",
    "StuffDescription":{},
    "StuffDetailed":{}
}
```

t.b.d

## StuffDescription

描述Stuff的内容。

- 可扩展
  
- 示例
  

```json
{
    "StuffID":"",
    "StuffDescription":{
        "status":"open/close/hold/repeal",
        "5W2H_Description":{
            "who":"",
            "where":""
        }
    },
    "StuffDetailed":{}
}
```

t.b.d

## StuffDetailed

记录Stuff的详细内容。可以用来记录stuff推进时收到或者产生的内容类似与日志。

- 可扩展
  
- 示例
  

```json
{
    "StuffID":"",
    "StuffDescription":{},
    "StuffDetailed":{
        "Log":[
            {"timestamp": "2023-11-20T10:00:00Z","comment": "与产品经理达成一致"},
            {"timestamp": "2023-11-20T14:00:00Z","comment": "完成基础解析框架"},
            {"timestamp": "2023-11-21T09:00:00Z","comment": "与产品经理达成一致"}
        ]
    }
}
```

## 扩展性原则

1. 三大核心字段（StuffID/Description/Detailed）必须存在
2. 各字段内部结构允许使用者自由扩展

# GTD管理软件

GTD管理软件就是可以读取以JSON-GTD Standard 协议整理的stuff内容的软件。

GTD最最基本的能力就是对stuff进行增/删/改/查，然后就是一些中级功能日程管理提醒等等，高级功能就是Agent推进。
