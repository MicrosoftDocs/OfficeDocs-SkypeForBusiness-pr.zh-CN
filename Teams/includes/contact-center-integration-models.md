## <a name="integration-models-for-solution-providers"></a>解决方案提供商的集成模型

<a name="steps"></a>

作为联系人中心解决方案提供商，有三种模型可供选择，以便将连接的联系人中心解决方案集成到Teams：

- 若要使用经过认证的 SBC 和直接路由将联系人中心解决方案连接到Teams，请参阅[连接模型](?tabs=connect#steps)。

- 如果要使用 Azure 机器人和 Microsoft Graph通信 API 使解决方案提供商能够创建Teams应用，请参阅[扩展模型](?tabs=extend#steps)。

- 如果想要使用使解决方案提供商能够在其应用中嵌入本机Teams体验的 SDK，请参阅 [Power 模型](?tabs=power#steps)。 当 SDK 在 2021 年底推出时，将可以使用电源解决方案。

### <a name="the-connect-model"></a>[**连接模型**](#tab/connect)

连接模型使用 Microsoft 认证的 SBC 和直接路由将联系人中心解决方案连接到Teams电话系统基础结构，从而实现增强的路由、配置和系统见解。

代理可以设置自动虚拟助理和基于技能的路由队列，以收集信息并将客户与主题专家连接。

**功能突出显示：**

虽然这些功能不是此集成模型的功能功能的完整列表，但重点领域包括：

- Office 365身份验证，使代理能够从其集成的 CCaaS 客户端连接到其 Microsoft 租户

- 查看代理何时可用于Teams

- 使用Teams传输和组呼叫支持

- Teams Graph API 和云通信 API 与 Teams 集成

- 多租户 SIP 中继，用于在解决方案提供商的 SBC 上支持多个客户。

- 使用 [<span class="underline">Microsoft 认证会话边框控制器 (SBC) </span>的解决方案提供商](../direct-routing-border-controllers.md)

### <a name="the-extend-model"></a>[**扩展模型**](#tab/extend)

扩展模型使用 [Teams 客户端平台、Teams Graph](/microsoftteams/platform/overview) [API](/graph/api/resources/teams-api-overview) 和 [Microsoft Graph 中的云通信 API 与Teams客户端](/graph/api/resources/communications-api-overview)集成。 扩展模型还对所有联系人中心呼叫和呼叫控制体验使用Teams电话系统，联系中心解决方案提供商充当电话运营商和Microsoft 365。

代理可以使用Teams进行内部协作和外部通信，并且可以在开始参与之前从多个系统关联数据的动态上下文说明中受益，然后避免昂贵的上下文切换。

组织可以将工作流和高级路由配置设计到个人，并衡量其系统和交互的质量。

**功能突出显示：**

虽然这些功能不是此集成模型的功能功能的完整列表，但重点领域包括：

- Teams Graph API 和云通信 API 与 Teams 集成

- Teams基于代理体验的应用

- Teams作为代理的主要调用终结点

- Teams客户端调用所有调用控件

- Teams Web 和移动客户端的代理体验应用

- Teams中 CCaaS 应用中代理的分析、工作流管理、基于角色的体验

- 与Teams客户端集成的聊天和协作体验

- 保留所有应用中Teams客户端体验的性能和质量

### <a name="the-power-model"></a>[**Power 模型**](#tab/power)

Power 模型使解决方案提供商能够使用调用基础结构和客户端平台Teams创建基于 Azure 的本机语音应用程序，为协作客户和代理连接提供新式智能解决方案。 Power 模型的目标是提供单应用的单屏联系人中心体验。

**功能突出显示：**

虽然这些功能不是此集成模型的功能功能的完整列表，但重点领域包括：

- 通过 Teams SDK 本机启用了全通道通信的正式代理体验

- 使用Teams协作服务进行代理协作和客户交互

- 快速预配云服务，随时随地部署

- 在Teams对话期间与用户直接对话控制和交互

> [!NOTE]
> Power 模型将于 2021 年底推出。
