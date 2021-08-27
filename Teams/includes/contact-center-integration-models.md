## <a name="integration-models-for-solution-providers"></a>解决方案提供商的集成模型

<a name="steps"></a>

作为联系中心解决方案提供商，有三种模型可供选择，将连接的联系中心解决方案集成到Teams：

- 如果要使用经过认证的 SDC 和直接路由将联系中心解决方案连接到 Teams，请参阅连接[模型](?tabs=connect#steps)。

- 若要使用 Azure 机器人和 Microsoft Graph 通信 API 使解决方案提供商能够创建 Teams 应用，请参阅[扩展模型](?tabs=extend#steps)。

- 如果要使用 SDK，使解决方案提供商能够在其应用中Teams本机应用体验，请参阅[Power 模型](?tabs=power#steps)。 当 SDK 可用时（到 2021 年底）时，可以使用电源解决方案。

### <a name="the-connect-model"></a>[**连接模型**](#tab/connect)

此连接模型使用 Microsoft 认证的 SDC 和直接路由将联系中心解决方案连接到 Teams 电话系统基础结构，实现增强的路由、配置和系统见解。

代理可以设置自动化虚拟助手和基于技能的路由队列，以收集信息并与客户主题专家联系。

**功能亮点：**

虽然这些功能不是此集成模型的功能综合列表，但关注领域包括：

  - Office 365身份验证N，使代理从集成的 CCaaS 客户端连接到其 Microsoft 租户 

  - 查看代理何时可用于Teams

  - 通过转接和群组通话支持Teams 

  - Teams Graph API 和云通信 API 来与 Teams 

  - 多租户 SIP 中继，支持解决方案提供商 SBC 上的多个客户。  

  - 解决方案提供商使用 [<span class="underline">Microsoft 认证的会话边界控制器 (SBC) </span>](../direct-routing-border-controllers.md)


### <a name="the-extend-model"></a>[**扩展模型**](#tab/extend)

扩展模型使用 Microsoft Teams 中的 Teams 客户端[](/microsoftteams/platform/overview)平台、Teams Graph [API 和](/graph/api/resources/teams-api-overview?view=graph-rest-1.0)云通信 API 与[Graph](/graph/api/resources/communications-api-overview?view=graph-rest-1.0)集成。 扩展模型还Teams电话系统进行所有联系中心呼叫和呼叫控制体验，并且联系中心解决方案提供商充当电话运营商Microsoft 365。

代理可以将 Teams用于内部协作和外部通信，并且可以从动态上下文笔记中获益，这些注释在启动参与之前关联来自多个系统的数据，然后避免代价高昂的上下文切换。

组织可以设计工作流和高级路由配置（向下到个人）并测量其系统和交互的质量。

**功能亮点：**

虽然这些功能不是此集成模型的功能综合列表，但关注领域包括：

  - Teams Graph API 和云通信 API 来与 Teams 

  - Teams基于应用提供代理体验 

  - Teams代理的主调用终结点 

  - Teams调用所有呼叫控件的客户端调用

  - 适用于 Web 客户端Teams移动客户端的代理体验应用

  - Teams 中 CCaaS 应用中的代理的分析、工作流管理、基于角色Teams

  - 与客户端集成的聊天和Teams体验 

  - 保留所有应用中Teams客户端体验的性能和质量  

### <a name="the-power-model"></a>[**电源模型**](#tab/power)

借助 Power 模型，解决方案提供商能够使用 Teams 呼叫基础结构和客户端平台创建基于 Azure 的本机语音应用程序，为协作客户和代理连接提供现代智能解决方案。 Power 模型的目标是提供单应用、单屏幕联系中心体验。

**功能亮点：**

虽然这些功能不是此集成模型的功能综合列表，但关注领域包括：

  - 通过 Teams SDK 以本机方式为全通道通信启用的正式代理体验 

  - 使用Teams服务进行代理协作和客户交互  

  - 快速预配云服务，随时随地部署 

  - 在对话过程中直接进行聊天控制和Teams交互 

>[!NOTE]
> Power 模型将在 2021 年底可用。
