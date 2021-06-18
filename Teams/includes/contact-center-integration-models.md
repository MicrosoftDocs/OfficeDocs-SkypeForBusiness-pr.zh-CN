## <a name="integration-models-for-solution-providers"></a>解决方案提供商的集成模型

<a name="steps"></a>

作为联系中心解决方案提供商，有三种模型可供选择，将连接的联系中心解决方案集成到 Teams 中：

- 如果要使用经过认证的 SDC 和直接路由将联系中心解决方案连接到 Teams，请参阅 [连接模型](?tabs=connect#steps)。

- 若要使用 Azure 机器人和 Microsoft Graph 通信 API 使解决方案提供商能够创建 Teams 应用，请参阅 [扩展模型](?tabs=extend#steps)。

- 如果要使用 SDK，使解决方案提供商能够将本机 Teams 体验 imbed 到其应用中，请参阅 [Power 模型](?tabs=power#steps)。 当 SDK 可用时（到 2021 年底）时，可以使用电源解决方案。

### <a name="the-connect-model"></a>[**连接模型**](#tab/connect)

Connect 模型使用 Microsoft 认证的 SDC 和直接路由将联系中心解决方案连接到 Teams 电话系统基础结构，实现增强的路由、配置和系统见解。

代理可以设置自动化虚拟助手和基于技能的路由队列，以收集信息并与客户主题专家联系。

**功能亮点：**

虽然这些功能不是此集成模型的功能综合列表，但关注领域包括：

  - Office 365 身份验证，使代理能够从集成的 CCaaS 客户端连接到其 Microsoft 租户 

  - 查看 Teams 何时提供代理

  - Teams 的转接和群组通话支持 

  - 用于与 Teams 集成的 Teams Graph API 和云通信 API 

  - 多租户 SIP 中继，支持解决方案提供商 SBC 上的多个客户。  

  - 解决方案提供商使用 [<span class="underline">Microsoft 认证的会话边界控制器 (SBC) </span>](../direct-routing-border-controllers.md)


### <a name="the-extend-model"></a>[**扩展模型**](#tab/extend)

扩展模型使用 Microsoft Graph 中的 [Teams](/microsoftteams/platform/overview)客户端平台 [、Teams Graph API](/graph/api/resources/teams-api-overview?view=graph-rest-1.0) 和 [云通信 API](/graph/api/resources/communications-api-overview?view=graph-rest-1.0)与 Teams 客户端集成。 扩展模型还针对所有联系中心呼叫和呼叫控制体验使用 Teams 电话系统，并且联系中心解决方案提供商与 Microsoft 365 一起充当电话运营商。

代理可以使用 Teams 进行内部协作和外部通信，并且可以在开始参与之前从多个系统关联数据的动态上下文笔记受益，避免进行代价高昂的上下文切换。

组织可以设计工作流和高级路由配置（向下到个人）并测量其系统和交互的质量。

**功能亮点：**

虽然这些功能不是此集成模型的功能综合列表，但关注领域包括：

  - 用于与 Teams 集成的 Teams Graph API 和云通信 API 

  - 用于代理体验的基于 Teams 的应用 

  - Teams 作为代理的主要调用终结点 

  - 用于所有呼叫控件的 Teams 客户端呼叫

  - 适用于 Teams Web 客户端和移动客户端的代理体验应用

  - Teams 中 CCaaS 应用中代理的分析、工作流管理、基于角色的体验

  - 与 Teams 客户端集成的聊天和协作体验 

  - 在所有应用中保留 Teams 客户端体验的性能和质量  

### <a name="the-power-model"></a>[**电源模型**](#tab/power)

借助 Power 模型，解决方案提供商能够使用 Teams 呼叫基础结构和客户端平台创建基于本机 Azure 的语音应用程序，为协作客户和代理连接提供现代智能解决方案。 Power 模型的目标是提供单应用、单屏幕联系中心体验。

**功能亮点：**

虽然这些功能不是此集成模型的功能综合列表，但关注领域包括：

  - 通过 Teams SDK 以本机方式为全渠道通信启用正式代理体验 

  - 使用 Teams 协作服务进行代理协作和客户交互  

  - 快速预配云服务，随时随地部署 

  - 在 Teams 对话期间直接进行对话控制和与用户交互 

>[!NOTE]
> Power 模型将在 2021 年底可用。
