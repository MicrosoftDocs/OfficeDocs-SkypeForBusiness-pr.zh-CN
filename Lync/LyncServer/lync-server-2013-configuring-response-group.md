---
title: Lync Server 2013：配置响应组
TOCTitle: 配置响应组
ms:assetid: c56db929-cb21-4af0-be3f-c8f807b78a5a
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205249(v=OCS.15)
ms:contentKeyID: 49314180
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中配置响应组

 

_**上一次修改主题：** 2016-12-08_

响应组是一项 企业语音功能，用于将传入呼叫路由至人员组（称为 *代理* ，如技术支持或客户服务台），并使呼叫在代理中排队等候。

响应组所需的组件将在部署 企业语音时在前端服务器或 Standard Edition Server 中自动安装并启用。要使 响应组对用户可用，必须依次配置代理组、队列和工作流。此外， 响应组管理员可将现有工作流的配置委派给 响应组管理员，后者可修改和重新配置工作流及其相关的代理组和队列。

本节指导您完成 Lync Server 2013响应组的配置过程。假设您已阅读与 响应组相关的规划部分，并部署了 企业语音的 Enterprise Edition Server 或 Standard Edition Server。

> [!TIP]
> 有关通过使用 Lync Server 命令行管理程序创建 响应组的详细信息（包括示例脚本），请参阅“使用 Lync Server 命令行管理程序创建第一个响应组”，网址为 <a href="http://go.microsoft.com/fwlink/p/?linkid=204108">http://go.microsoft.com/fwlink/p/?linkId=204108</a>。


## 本部分内容

  - [Lync Server 2013 中的响应组配置权限和先决条件](lync-server-2013-response-group-configuration-permissions-and-prerequisites.md)

  - [Lync Server 2013 中响应组的部署过程](lync-server-2013-deployment-process-for-response-group.md)

  - [Lync Server 2013 中的工作流创建方案概述](lync-server-2013-overview-of-workflow-creation-scenarios.md)

  - [在 Lync Server 2013 中创建响应组代理组](lync-server-2013-create-response-group-agent-groups.md)

  - [在 Lync Server 2013 中创建响应组队列](lync-server-2013-create-response-group-queues.md)

  - [（可选）在 Lync Server 2013 中定义响应组工作时间](lync-server-2013-optional-define-response-group-business-hours.md)

  - [（可选）定义响应组假日设置](lync-server-2013-optional-define-response-group-holiday-sets.md)

  - [在 Lync Server 2013 中创建响应组工作流](lync-server-2013-create-response-group-workflows.md)

  - [（可选）验证响应组部署](lync-server-2013-optional-verify-response-group-deployment.md)

## 另请参阅

#### 其他资源

[在 Lync Server 2013 中规划呼叫管理功能](lync-server-2013-planning-for-call-management-features.md)

