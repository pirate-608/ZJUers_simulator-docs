# 折姜大学招生减章
*该游戏仅供娱乐，不提供对任何学校、组织或个人的教育、学习和工作参考*
## 1.什么是ZJUers Simulator?
折姜大学模拟器：一个让你在一个虚拟平行世界中模拟折大生活的游戏。

## 2.为什么要做这个游戏？
因为寒假太无聊了。

## 3.为什么主域名叫“67656.fun”?
*   [什么是67656？](https://news.qq.com/rain/a/20241117A06MRE00)
*   为什么是“.fun”？
    *   ~~因为.fun域名比较便宜~~，因为在这个游戏中，你可能会被分配到一个不熟悉的专业，体验不一样的生活，触发各类随机事件，开发者希望这是一个能带来快乐的游戏。

## 3.数据处理
由于大类招生政策引入大量复杂因素，不利于游戏的数据流处理，该项目简化为开局直接随机分配专业，并根据json格式的“培养方案”文件进行游戏循环。详情请查看[培养方案列表](./world/majors.md)。

## 4.自定义大模型与API_KEY

!!! tip ""
    项目自身预算有限，默认的LLM免费额度坚持不了太久，因此用户可自定义LLM来驱动游戏（在首页填写），当默认LLM的额度耗尽时，若不填写自定义LLM不会影响游戏正常运行，但高级功能（如随机事件、98帖子等）将无法正常使用。
本游戏为技术演示项目，部分功能支持您自行配置第三方大模型API以实现个性化体验。请注意，这属于高级功能，所有第三方平台的选择、使用及产生的任何责任均与本站/本项目无关。

---

### 获取途径：
!!! tip ""
    首次尝试建议先使用平台免费额度(如果仍有😅)，确认模型可用后再决定是否长期配置。

1.  【开通平台】访问云服务商/ API提供商平台 ，登录/注册账号，可能需要实名认证。同意协议后开通大模型服务（大部分平台默认自动开通），大部分国内平台会为每个新用户提供免费额度。
2.  【获取密钥】点击进入左下角“密钥管理”页面，创建一个新的API Key，并**妥善保存**。
3.  【选择模型和base url】在同一平台查看“模型服务”列表，记下您想调用的模型名称（如`gpt-4-turbo`、`doubao-seed-1.6-lite
`、`qwen-turbo`、`deepseek-v3.2`）。
4.  【配置启动】
   *   应用场景：在登录界面填写你的模型型号、`Base URL`和`API Key`（注意隐私和安全，不要给陌生平台提供API_KEY）
   *   开发场景：将获得的 `API key` 和 `模型名称` 填入配置文件（不推荐直接写入后端代码）或作为环境变量，格式如下（以OpenAI为例）：
   ```
   LLM_BASE_URL=https://api.openai.com/v1
   LLM_API_KEY=sk-xxxxxxxx
   LLM=gpt-4-turbo
   ```


### 可选服务商：
*以下为部分可供参考的兼容服务商列表（排名不分先后），其服务条款、价格和政策由各平台独立制定，请在使用前仔细阅读。*

| 服务商（链接跳转至平台首页） | Base URL | API参考 |
|:---|:---|:---|
| [OpenAI](https://openai.com) | `https://api.openai.com/v1` | [查看](https://platform.openai.com/docs/api-reference) |
| [Google Gemini](https://deepmind.google/technologies/gemini/) | `https://generativelanguage.googleapis.com/v1beta` | [查看](https://ai.google.dev/gemini-api/docs) |
| [Groq](https://groq.com) | `https://api.groq.com/openai/v1` | [查看](https://console.groq.com/docs/api-reference) |
| [阿里云百炼 / 通义](https://www.aliyun.com/product/bailian) | `https://dashscope.aliyuncs.com/compatible-mode/v1` | [查看](https://help.aliyun.com/model-studio/get-api-key) |
| [智谱 AI / GLM](https://www.zhipuai.cn) | `https://open.bigmodel.cn/api/paas/v4` | [查看](https://docs.bigmodel.cn/cn/api) |
| [DeepSeek](https://www.deepseek.com) | `https://api.deepseek.com/v1` | [查看](https://platform.deepseek.com/api-docs/) |
| [字节跳动豆包](https://www.volcengine.com/product/doubao) | `https://ark.cn-beijing.volces.com/api/v3` | [查看](https://www.volcengine.com/docs/82379/1541594) |
| [SiliconFlow (硅基流动)](https://siliconflow.cn) | `https://api.siliconflow.cn/v1` | [查看](https://docs.siliconflow.cn/cn/api-reference/chat-completions/chat-completions) |
| [MiniMax](https://www.minimaxi.com) | `https://api.minimax.chat/v1` (国际)<br>`https://api.minimaxi.com/v1` (中国) | [查看](https://platform.minimaxi.com/docs/api-reference/api-overview) |
| [Moonshot (Kimi)](https://www.moonshot.cn) | `https://api.moonshot.ai/v1` (国际)<br>`https://api.moonshot.cn/v1` (中国) | [查看](https://platform.moonshot.cn/docs/guide/start-using-kimi-api) |
| [百度千帆](https://cloud.baidu.com/product/wenxinworkshop) | `https://qianfan.baidubce.com/v2` | [查看](https://cloud.baidu.com/doc/WENXINWORKSHOP/index.html) |

---

### 安全须知 {#security-notice}

1. 您提供的API_KEY仅用于您当前游戏会话，不会被永久保存。
2. 填写即代表您单独同意我们为调用您指定模型而临时处理此密钥。
3. 请妥善保管您的密钥，任何泄露可能导致您在该平台的资产损失或产生未授权费用。
4. 您可在游戏结束时清除已配置的密钥。