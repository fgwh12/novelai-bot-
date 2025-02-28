# 配置项

## 登录设置

### type

- 类型：`'login' | 'token'`
- 默认值：`'token'`

登录方式。`login` 表示使用账号密码登录，`token` 表示使用授权令牌登录。

### email

- 类型：`string`
- 当 `type` 为 `login` 时必填

你的账号邮箱。

### password

- 类型：`string`
- 当 `type` 为 `login` 时必填

你的账号密码。

### token

- 类型：`string`
- 当 `type` 为 `token` 时必填

授权令牌。获取方式如下：

1. 在网页中登录你的 NovelAI 账号
2. 打开控制台 (F12)，并切换到控制台 (Console) 标签页
3. 输入下面的代码并按下回车运行

```js
console.log(JSON.parse(localStorage.session).auth_token)
```

4. 输出的字符串就是你的授权令牌

### endpoint

- 类型：`string`
- 默认值：`'https://api.novelai.net'`

API 服务器地址。如果你搭建了私服，可以将此项设置为你的服务器地址。

## 功能设置

### model

- 类型：`'safe' | 'nai' | 'furry'`
- 默认值：`'nai'`

默认的生成模型。

### orient

- 类型：`'portrait' | 'square' | 'landscape'`
- 默认值：`'portrait'`

默认的图片方向。

### sampler

- 类型：`'k_euler_ancestral' | 'k_euler' | 'k_lms' | 'plms' | 'ddim'`
- 默认值：`'k_euler_ancestral'`

默认的采样器。

### anatomy

- 类型：`boolean`
- 默认值：`true`

默认情况下是否过滤不良构图。

### allowAnlas

- 类型：`boolean`
- 默认值：`true`

是否允许使用点数。禁用后部分功能 (如图片增强和步数设置) 将无法使用。

### basePrompt

- 类型: `string`
- 默认值: `'masterpiece, best quality'`

所有请求的附加标签。默认值相当于开启网页版的「Add Quality Tags」功能。

## 高级设置

### forbidden

- 类型：`string`
- 默认值：`''`

违禁词列表。含有违禁词的请求将被拒绝。

### requestTimeout

- 类型：`number`
- 默认值：`30000`

当请求超过这个时间时会中止并提示超时。

### recallTimeout

- 类型：`number`
- 默认值：`0`

图片发送后自动撤回的时间 (设置为 `0` 禁用此功能)。
