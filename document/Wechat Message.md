# Wechat Message

## 小程序订阅消息事件

[订阅消息文档地址](https://developers.weixin.qq.com/miniprogram/dev/framework/open-ability/subscribe-message.html)

[接口文档地址](https://developers.weixin.qq.com/miniprogram/dev/api-backend/open-api/subscribe-message/subscribeMessage.addTemplate.html)

事件:

* 当用户触发订阅消息弹框后: subscribe_msg_popup_event
* 管理消息(只推送取消订阅的事件): subscribe_msg_change_event
* 调用订阅消息接口发送消息给用户的最终结果: subscribe_msg_sent_event

| 值 | 说明 |
| ---- | ---- |
| 40003 | touser字段openid为空或者不正确 |
| 40037 | 订阅模板id为空不正确 |
| 43101 | 用户拒绝接受消息，如果用户之前曾经订阅过，则表示用户取消了订阅关系 |
| 47003 | 模板参数不准确，可能为空或者不满足规则，errmsg会提示具体是哪个字段出错 |
| 41030 | page路径不正确，需要保证在现网版本小程序中存在，与app.json保持一致 |

接口限制
次数限制：开通支付能力的是3kw/日，没开通的是1kw/日

## 公众号一次性订阅消息

[文档地址](https://developers.weixin.qq.com/doc/offiaccount/Message_Management/One-time_subscription_info.html)

## 公众号订阅通知

[文档地址](https://developers.weixin.qq.com/doc/offiaccount/Subscription_Messages/api.html#send%E5%8F%91%E9%80%81%E8%AE%A2%E9%98%85%E9%80%9A)

事件:

* 当用户触发订阅消息弹框后: subscribe_msg_popup_event
* 管理消息(只推送取消订阅的事件): subscribe_msg_change_event
* 调用订阅消息接口发送消息给用户的最终结果: subscribe_msg_sent_event

| 值 | 说明 |
| ---- | ---- |
| 40003 | touser字段openid为空或者不正确 |
| 40037 | 订阅模板id为空不正确 |
| 43101 | 用户拒绝接受消息，如果用户之前曾经订阅过，则表示用户取消了订阅关系 |
| 47003 | 模板参数不准确，可能为空或者不满足规则，errmsg会提示具体是哪个字段出错 |
| 41030 | page路径不正确，需要保证在现网版本小程序中存在，与app.json保持一致 |

## 模板消息

[文档地址](https://developers.weixin.qq.com/doc/offiaccount/Message_Management/Template_Message_Interface.html)

* 每个账号可以同时使用25个模板。
* 当前每个账号的模板消息的日调用上限为10万次，单个模板没有特殊限制。【2014年11月18日将接口调用频率从默认的日1万次提升为日10万次，可在MP登录后的开发者中心查看】。当账号粉丝数超过10W/100W/1000W时，模板消息的日调用上限会相应提升，以公众号MP后台开发者中心页面中标明的数字为准。

事件(TEMPLATESENDJOBFINISH):

* 送达成功时(Status): success
* 送达由于(Status): failed:user block
* 送达由于其他原因失败时(Status): failed: system failed
