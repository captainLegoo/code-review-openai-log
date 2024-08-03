### 代码评审

#### 文件：`.github/workflows/main-maven-jar.yml`
- **变更**：添加了两个新的环境变量 `CHATGPT_API_HOST` 和 `CHATGPT_API_KEY`。
- **分析**：这个变更似乎是为了支持一个新的 ChatGPT API。这可能是为了增加对 ChatGPT 服务的支持，或者作为 ChatGLM 的备份方案。
- **建议**：确保这两个环境变量在所有需要它们的环境中都已正确设置。此外，考虑在文档中添加关于如何使用 ChatGPT API 的说明。

#### 文件：`code-review-openai-sdk/src/main/java/cn/dcy/review/sdk/CodeReviewOpenAiSdk.java`
- **变更**：从 `ChatGLM` 更改为 `ChatGPT` 作为 OpenAI 的实现。
- **分析**：这个变更意味着代码现在将使用 ChatGPT 而不是 ChatGLM 进行代码审查。
- **建议**：
  - 确保ChatGPT的依赖项和配置正确设置。
  - 检查与ChatGPT API交互的代码，确保它符合API的要求。
  - 测试新功能以确保它按预期工作。
  - 如果ChatGLM和ChatGPT可以共存，考虑将两者作为可选功能提供，并允许用户选择他们想要使用的服务。

#### 文件：`code-review-openai-sdk/src/main/java/cn/dcy/review/sdk/domain/model/ChatGPTModel.java`
- **变更**：新增了一个名为 `ChatGPTModel` 的枚举类，用于定义不同的ChatGPT模型。
- **分析**：这个枚举类提供了对ChatGPT不同模型的支持，允许用户选择不同的模型进行代码审查。
- **建议**：
  - 确保所有模型都是有效的，并且API可以正确地识别这些模型。
  - 考虑添加文档说明如何根据需求选择不同的模型。
  - 如果可能，添加一个默认模型或一个机制来选择最佳模型。

### 总结
这些更改引入了新的功能和服务，这可能会增强代码审查工具的能力。在进行这些更改时，重要的是要确保所有新的依赖项和配置都已正确设置，并且代码经过充分的测试以确保其正确性和稳定性。