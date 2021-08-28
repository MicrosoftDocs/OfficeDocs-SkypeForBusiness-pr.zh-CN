---
title: 响应组的部署Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d390c8a1-dc6e-44d8-b386-2be1fca9877c
description: Skype for Business Server 企业语音 中的响应组的部署过程和Skype for Business Server 企业语音。
ms.openlocfilehash: 1cb85ac95025b71de8a071758befb5287a6fafa4
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58620178"
---
# <a name="deployment-process-for-response-group-in-skype-for-business"></a>响应组的部署Skype for Business

Skype for Business Server 企业语音 中的响应组的部署过程和Skype for Business Server 企业语音。

响应组是一企业语音一项功能，它向人员组（称为代理，如技术支持或客户服务台）路由传入呼叫并排入队列。

响应组所需的组件将在部署企业语音时在前端服务器或 Standard Edition Server 中自动安装并启用。 要使响应组对用户可用，必须依次配置代理组、队列和工作流。 此外，响应组管理员可以将现有工作流的配置委派给响应组管理员，该管理员随后可以修改和重新配置工作流及其关联的代理组和队列。

若要配置响应组，您必须至少成为以下管理角色之一的成员：

|**Active Directory 安全组 (1)** <br/> |创建工作流  <br/> |分派管理者  <br/> |创建/分派代理、队列  <br/> |创建/管理假日和工作时间  <br/> |激活/停用工作流  <br/> |配置工作流（IVR 或智能寻线）  <br/> |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|**CsResponseGroupAdministrator** <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |
|**CsResponseGroupManager** <br/> ||√ (2)   <br/> |√ (3)   <br/> |√ (3)   <br/> |√ (3)   <br/> |√ (3)   <br/> |
|**CsVoiceAdministrator** <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |
|**CsServerAdministrator** <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |
|**CsAdministrator** <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |
|**CsViewOnlyAdministrator** <br/> |√ (4)   <br/> |√ (4)   <br/> |√ (4)   <br/> |√ (4)   <br/> |√ (4)   <br/> |√ (4)   <br/> |

> [!NOTE]
> **(1)** Active Directory 域服务用户对象必须是列出的指定 Active Directory 安全组的成员。 具有向安全组 (添加用户的适当权限的管理员或其他委派 Active Directory 组的成员例如，管理员、帐户操作员) 必须将用户对象添加到列出的安全组或组中，用户才能执行列出的功能。 **(2)** 仅适用于 CsResponseGroupAdministrator 已分配给 CsResponseGroupManager 的工作流。 **(3)** 响应组管理器可以将 CsResponseGroupManager 的另一个成员分配给当前管理员已管理的工作流。 **(4)** CsViewOnlyAdministrator 只能运行动词"Get"cmdlet。

## <a name="response-group-configuration-prerequisites"></a>响应组配置的先决条件

响应组需要以下组件：

- 应用程序服务

- 响应组应用程序

- 语言包

- 文件存储（用于保存音频文件）

- Web (包括响应组配置工具以及代理的登录和注销控制台) 

部署企业语音时，默认安装上述所有组件。

在配置响应组之前，可能需要执行以下任务：

- 为用户启用 Lync Server 2013 和 企业语音。

- 修改配置文件以符合联邦信息处理标准 (FIPS)。

- 修改数据库排序规则以支持队列名称和代理组名称的 Yi、Meng 和 Zang 字符。

### <a name="enabling-users"></a>启用用户

配置响应组的第一步是创建代理组。 必须先启用将成为响应组代理的用户，然后才能创建代理组Skype for Business企业语音。 为用户启用Skype for Business通常是 Enterprise Edition 或 Standard Edition 部署中的一个步骤。 有关为用户启用Skype for Business的详细信息，请参阅 Enable or [Disable Users for Lync Server 2013 Preview](/previous-versions/office/lync-server-2013/lync-server-2013-disable-or-re-enable-user-account-for-lync-server)。 为用户启用企业语音通常是企业语音部署中的一个步骤。 有关详细信息，请参阅在 Skype for Business Server 中企业语音[用户进行Skype for Business Server。](enable-users-for-enterprise-voice.md)

### <a name="complying-with-fips-requirements"></a>符合 FIPS 要求

仅当您的组织需要符合联邦信息处理标准 (FIPS) 时，本节才适用。

要符合 FIPS，安装 Web 服务后需要修改应用程序级别 Web.config 文件，以使用不同的加密算法。 需要指定 ASP.NET 使用三重数据加密标准 (3DES) 算法，来处理视图状态数据。 对于响应组应用程序，此要求适用于响应组配置工具以及代理登录和注销控制台。 有关此要求的详细信息，请参阅 Microsoft 知识库文章 911722，"在从 ASP.NET 1.1 升级到 ASP.NET 2.0 后，访问启用了 ViewState 的 ASP.NET 网页时，可能会收到错误消息。" [https://go.microsoft.com/fwlink/p/?linkId=196183](https://go.microsoft.com/fwlink/p/?linkId=196183)

要修改 Web.config 文件，请执行以下操作：

1. 在文本编辑器（如记事本）中，打开应用程序级别 Web.config 文件。

2. 在Web.config文件中，找到  `<system.web>` 部分。

3. 将以下  `<machineKey>` 部分添加到 `<system.web>` 部分：

   ```xml
   <machineKey validationKey="AutoGenerate,IsolateApps" decryptionKey="AutoGenerate,IsolateApps" validation="3DES" decryption="3DES"/>
   ```

4. 保存 Web.config 文件。

5. 在命令Internet Information Services (运行) ，重新启动 IIS 服务：

   ```console
   iisreset
   ```

### <a name="supporting-yi-meng-and-zang-characters"></a>支持 Yi、Meng 和 Zang 字符

仅当您的组织需要支持 Yi、Meng 或 Zang 字符时，本节才适用。

> [!NOTE]
> 有关 Yi、Meng 和 Zang 字符是什么以及它们为什么对部署很重要的信息，请参阅 GB18030 字符集上的信息 [https://go.microsoft.com/fwlink/p/?linkId=240223](/previous-versions/sql/sql-server-2008-r2/ms180991(v=sql.105)) 。

要支持 Yi、Meng 或 Zang 字符，需要修改 Rgsconfig 数据库的排序规则。在每个 Rgsconfig 数据库的下列各表中更改 **“Name”** 列的排序规则：

- dbo。AgentGroups

- dbo。BusinessHours

- dbo。HolidaySets

- dbo。队列

- dbo。工作流

对于 SQL Server 2008 R2 和 SQL Server 2012，请使用Latin_General_100 (重音) 排序规则。 如果使用此排序规则，则所有对象名称不区分大小写。

可以使用 Microsoft SQL Server Management Studio 来更改排序规则。 有关使用此工具的详细信息，请参阅["使用SQL Server Management Studio"。](/sql/ssms/sql-server-management-studio-ssms) 执行下列步骤可更改排序规则：

1. 确保 SQL Server Management Studio 配置为允许要求重新创建表的更改。 有关详细信息，请参阅"保存 ([不允许) 对话框"。](/sql/ssms/visual-db-tools/save-not-permitted-dialog-box) 有关设置列排序规则的详细信息，请参阅"如何：设置列排序规则 ([Visual Database Tools) "。](/previous-versions/sql/sql-server-2008-r2/ms187473(v=sql.105))

2. 使用 Microsoft SQL Server Management Studio 连接到 Rgsconfig 数据库。

3. 在 Rgsconfig 数据库中查找要更改的表，右键单击该表，然后单击 **“设计”**。

4. 更改 **“Name”** 列的排序规则并保存该表。

## <a name="response-group-deployment-steps"></a>响应组部署步骤

**响应组部署过程**

|**阶段**|**步骤**|**权限**|**部署文档**|
|:-----|:-----|:-----|:-----|
|为用户启用Skype for Business和启用企业语音  <br/> |启用将成为代理的用户Skype for Business企业语音。 必须先启用用户，然后才能将其添加到代理组。 通常，在部署服务器Skype for Business或Enterprise Edition Standard Edition启用用户。 在部署期间企业语音启用企业语音用户。  <br/> |RTCUniversalUserAdmins  <br/> CsUserAdministrator  <br/> CsAdministrator  <br/> |[Enable or Disable Users for Lync Server 2013 Preview](/previous-versions/office/lync-server-2013/lync-server-2013-disable-or-re-enable-user-account-for-lync-server) <br/> [为用户启用企业语音Skype for Business Server](enable-users-for-enterprise-voice.md) <br/> |
|创建和配置由代理组、队列和工作流构成的响应组  <br/> |1. 使用Skype for Business Server控制面板Skype for Business Server命令行管理程序执行以下操作：  <br/> a. 创建和配置代理组。  <br/> b. 创建和配置队列。  <br/> 2. （可选）Skype for Business Server命令行管理程序创建预定义的响应组工作时间和假日。  <br/> 3. 使用响应组配置工具或 Skype for Business Server 命令行管理程序创建工作流 (寻线或互动语音响应 (IVR) 呼叫流) ，包括自定义响应组工作时间和假日。  <br/> 可以通过控制面板访问响应组Skype for Business Server工具。  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> CsResponseGroupManager  <br/> |[创建响应组代理组](/previous-versions/office/lync-server-2013/lync-server-2013-create-response-group-agent-groups) <br/> [创建响应组队列](/previous-versions/office/lync-server-2013/lync-server-2013-create-response-group-queues) <br/> [ (可选) 定义响应组工作时间（以Skype for Business](optional-define-response-group-business-hours.md) <br/> [ (在) 定义响应组假日集的可选Skype for Business](optional-define-response-group-holiday-sets.md) <br/> [在工作流中设计和创建响应组Skype for Business](designing-and-creating-response-group-workflows.md) <br/> |
|（可选）自定义应用程序级别设置  <br/> |使用 Skype for Business Server命令行管理程序自定义默认的保持音乐配置、默认的保持音乐音频文件、代理回响宽限期和呼叫上下文配置。  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[管理应用程序中的应用程序级响应组Skype for Business](managing-application-level-response-group-settings.md) <br/> |
|（可选）委派响应组的管理  <br/> |为用户分配 CsResponseGroupManager 角色以委派响应组配置。 然后，响应组管理员可配置分配给他们的响应组。  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[规划基于角色的访问控制](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-role-based-access-control) <br/> |
|验证响应组部署  <br/> |测试智能寻线和互动语音响应工作流的应答呼叫，以确保您的配置按预期工作。  <br/> |-  <br/> |-  <br/> |

## <a name="overview-of-workflow-creation-scenarios"></a>工作流创建方案概述

创建工作流时，可以采用两种方案：

- **管理员创建和配置工作流** — CsResponseGroupAdministrator 角色成员（或等效身份）创建和激活工作流以及工作流中的所有元素，例如代理组、队列、假日和工作时间、保持音乐等等。

- **管理员创建工作流，经理配置选项** — CsResponseGroupAdministrator 角色成员（或等效身份）定义主要的 SIP URI 和显示名称，分配 CsResponseGroupManager 角色的成员并选择队列和激活工作流。CsResponseGroupManager 然后可以登录，并且通过创建代理组并将组分配给队列，配置电话号码、假日和工作时间以及保持音乐等来编辑工作流的配置。

    > [!NOTE]
    > 如果想要创建托管工作流，则需要创建活动状态的工作流。保存活动状态的托管工作流后，即可修改和停用该工作流。