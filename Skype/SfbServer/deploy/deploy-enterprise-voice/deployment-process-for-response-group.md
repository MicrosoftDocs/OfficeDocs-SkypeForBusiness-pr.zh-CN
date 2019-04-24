---
title: Skype for Business 中的响应组部署过程
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d390c8a1-dc6e-44d8-b386-2be1fca9877c
description: 部署过程和步骤中的业务 Server 企业语音的 Skype 的响应组。
ms.openlocfilehash: 83438ec17bd78a60afbc08a1c72ef84469218652
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32223046"
---
# <a name="deployment-process-for-response-group-in-skype-for-business"></a>Skype for Business 中的响应组部署过程

部署过程和步骤中的业务 Server 企业语音的 Skype 的响应组。

响应组是一种企业语音功能，用于路由并排队至人员，称为代理，如技术支持或客户服务台组的传入呼叫。

安装和部署企业语音时，自动启用前端服务器或 Standard Edition 服务器上的响应组需要的组件。 若要使响应组可供用户使用，必须配置代理组，然后队列和工作流。 此外，响应组管理员可以委派的现有工作流到响应组管理器中，可以修改和重新配置工作流及其关联的代理组和队列的配置。

若要配置响应组，您必须至少成为以下管理角色之一的成员：

|**Active Directory 安全组 (1)** <br/> |创建工作流  <br/> |分派管理者  <br/> |创建/分派代理、队列  <br/> |创建/管理假日和工作时间  <br/> |激活/停用工作流  <br/> |配置工作流（IVR 或智能寻线）  <br/> |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|**CsResponseGroupAdministrator** <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |
|**CsResponseGroupManager** <br/> ||√(2)  <br/> |√(3)  <br/> |√(3)  <br/> |√(3)  <br/> |√(3)  <br/> |
|**CsVoiceAdministrator** <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |
|**CsServerAdministrator** <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |
|**CsAdministrator** <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |
|**CsViewOnlyAdministrator** <br/> |√(4)  <br/> |√(4)  <br/> |√(4)  <br/> |√(4)  <br/> |√(4)  <br/> |√(4)  <br/> |

> [!NOTE]
> **(1)** 的 Active Directory 域服务用户对象必须列出指定的 Active Directory 安全组的成员。 管理员或具有适当的权限，以将用户添加到安全组 （例如，管理员、 Account Operators） 其他委派 Active Directory 组成员必须将用户对象添加到能够列出的安全组或用户组执行列出的函数。 **(2)** 仅用于 CsResponseGroupAdministrator 分配了 CsResponseGroupManager 的工作流。 **(3)** 响应组经理可以对当前管理器已管理的工作流分配 CsResponseGroupManager 的另一个成员。 **(4)** CsViewOnlyAdministrator 只能运行动作"获取"cmdlet。

## <a name="response-group-configuration-prerequisites"></a>响应组配置的先决条件

响应组需要以下组件：

- 应用程序服务

- 响应组应用程序

- 语言包

- 文件存储（用于保存音频文件）

- Web 服务 （包括响应组配置工具和代理的登录和注销控制台）

部署企业语音时，所有这些组件是默认安装。

您可能需要在配置响应组之前执行以下任务：

- 为用户启用 Lync Server 2013 和企业语音。

- 修改配置文件以符合联邦信息处理标准 (FIPS)。

- 修改数据库排序规则以支持队列名称和代理组名称的 Yi、Meng 和 Zang 字符。

### <a name="enabling-users"></a>启用用户

配置响应组的第一步是创建代理组。 您可以创建代理组之前，必须启用的用户将成为业务和企业语音的 Skype 的响应组代理。 为用户启用 for Business 的 Skype 通常是 Enterprise Edition server 或 Standard Edition server 部署中的步骤。 有关为用户启用 for Business 的 Skype 详细信息，请参阅[Enable or Disable Users for Lync Server 2013 Preview](https://technet.microsoft.com/library/12497d00-f665-4a97-be68-854c5a8be4fc.aspx)。 为用户启用企业语音通常是企业语音部署中的步骤。 有关详细信息，请参阅[启用 Skype 业务服务器中的企业语音的用户](enable-users-for-enterprise-voice.md)。

### <a name="complying-with-fips-requirements"></a>符合 FIPS 要求

仅当您的组织需要符合联邦信息处理标准 (FIPS) 时，本节才适用。

要符合 FIPS，安装 Web 服务后需要修改应用程序级别 Web.config 文件，以使用不同的加密算法。 需要指定 ASP.NET 使用三重数据加密标准 (3DES) 算法，来处理视图状态数据。 响应组应用程序，这一要求适用于响应组配置工具和代理登录和注销控制台。 有关详细信息此要求，请参阅 Microsoft 知识库文章 911722，"您可能会收到一条错误消息时访问具有视图状态后从 ASP.NET 1.1 升级到 ASP.NET 2.0 中，启用的 ASP.NET 网页"在[https://go.microsoft.com/fwlink/p/?linkId=196183](https://go.microsoft.com/fwlink/p/?linkId=196183)。

若要修改 Web.config 文件，请执行以下操作：

1. 在文本编辑器（如记事本）中，打开应用程序级别 Web.config 文件。

2. 在 Web.config 文件中，找到`<system.web>`部分。

3. 添加以下`<machineKey>`节在`<system.web>`部分：

   ```
   <machineKey validationKey="AutoGenerate,IsolateApps" decryptionKey="AutoGenerate,IsolateApps" validation="3DES" decryption="3DES"/>
   ```

4. 保存 Web.config 文件。

5. 通过在命令提示符处运行以下命令重新启动 Internet 信息服务 (IIS) 服务：

   ```
   iisreset
   ```

### <a name="supporting-yi-meng-and-zang-characters"></a>支持 Yi、Meng 和 Zang 字符

仅当您的组织需要支持 Yi、Meng 或 Zang 字符时，本节才适用。

> [!NOTE]
> 什么是 Yi、 Meng 和 Zang 字符和为什么它们可能对您的部署重要信息，请参阅信息 GB18030 字符集[https://go.microsoft.com/fwlink/p/?linkId=240223](https://go.microsoft.com/fwlink/p/?linkId=240223)。

要支持 Yi、Meng 或 Zang 字符，需要修改 Rgsconfig 数据库的排序规则。在每个 Rgsconfig 数据库的下列各表中更改“Name”**** 列的排序规则：

- dbo.AgentGroups

- dbo.BusinessHours

- dbo.HolidaySets

- dbo.Queues

- dbo.Workflows

SQL Server 2008 R2 和 SQL Server 2012，使用 Latin_General_100 （区分重音） 排序规则。 如果使用此排序规则，则所有对象名称不区分大小写。

可以使用 Microsoft SQL Server Management Studio 来更改排序规则。 有关使用此工具的详细信息，请参阅["使用 SQL Server Management Studio"](https://go.microsoft.com/fwlink/p/?linkId=196184)。 执行下列步骤可更改排序规则：

1. 确保 SQL Server Management Studio 配置为允许要求重新创建表的更改。 有关详细信息，请参阅["保存 （不允许） 对话框中"](https://go.microsoft.com/fwlink/p/?linkId=196186)。 有关设置列排序规则的详细信息，请参阅在["操作方法： 设置列排序规则 （可视化数据库工具）"](https://go.microsoft.com/fwlink/p/?linkId=196185)。

2. 使用 Microsoft SQL Server Management Studio 连接到 Rgsconfig 数据库。

3. 在 Rgsconfig 数据库中查找要更改的表，右键单击该表，然后单击“设计”****。

4. 更改“名称”列**** 的排序规则并保存该表。

## <a name="response-group-deployment-steps"></a>响应组部署步骤

**响应组部署过程**

|**阶段**|**步骤**|**权限**|**部署文档**|
|:-----|:-----|:-----|:-----|
|为用户启用 Skype 业务和企业语音  <br/> |使用户成为代理 Skype 业务和企业语音。 必须先启用用户，然后才能将其添加到代理组。 通常情况下，为用户启用 for Business 的 Skype 在 Enterprise Edition 或 Standard Edition server 部署过程。 企业语音部署过程中用户启用企业语音。  <br/> |RTCUniversalUserAdmins  <br/> CsUserAdministrator  <br/> CsAdministrator  <br/> |[Enable or Disable Users for Lync Server 2013 Preview](https://technet.microsoft.com/library/12497d00-f665-4a97-be68-854c5a8be4fc.aspx) <br/> [Skype 中的企业语音的用户启用企业服务器](enable-users-for-enterprise-voice.md) <br/> |
|创建和配置由代理组、队列和工作流构成的响应组  <br/> |1.使用 Skype 业务 Server Control Panel 或业务 Server Management Shell 的 Skype 执行下列操作：  <br/> a. 创建和配置代理组。  <br/> b. 创建和配置队列。  <br/> 2.（可选） 使用 Skype 的业务 Server 命令行管理程序创建预定义的响应组工作时间和假日。  <br/> 3.使用响应组配置工具或 Skype 的业务 Server 命令行管理程序创建工作流 （智能寻线或互动语音响应 (IVR) 呼叫流），包括自定义响应组工作时间和假日。  <br/> 为业务 Server Control Panel，可以通过 Skype 访问响应组配置工具。  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> CsResponseGroupManager  <br/> |[Create Response Group Agent Groups](https://technet.microsoft.com/library/2a80de17-ead0-46e8-8a27-7a4e233dbde0.aspx) <br/> [Create Response Group Queues](https://technet.microsoft.com/library/49cb86c7-2cfd-4a53-8408-d407475174ed.aspx) <br/> [（可选）Skype for Business 中定义响应组工作时间](optional-define-response-group-business-hours.md) <br/> [（可选）Skype for Business 中定义响应组假日集](optional-define-response-group-holiday-sets.md) <br/> [设计和 Skype for Business 中创建响应组工作流](designing-and-creating-response-group-workflows.md) <br/> |
|（可选）自定义应用程序级别设置  <br/> |使用业务 Server Management Shell 的 Skype 自定义的默认保留音乐配置、 默认上保留音乐音频文件、 代理回拨宽限期和呼叫上下文配置。  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[管理应用程序级 Skype for Business 中的响应组设置](managing-application-level-response-group-settings.md) <br/> |
|（可选）委派响应组的管理  <br/> |将用户分配 CsResponseGroupManager 角色委派响应组的配置。 响应组管理员可以配置分配给它们的响应组。  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Planning for Role-Based Access Control](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx) <br/> |
|验证响应组部署  <br/> |测试智能寻线和互动语音响应工作流的应答呼叫，以确保您的配置按预期工作。  <br/> |-  <br/> |-  <br/> |

## <a name="overview-of-workflow-creation-scenarios"></a>工作流创建方案概述

创建工作流时，可以采用两种方案：

- **管理员创建和配置工作流** — CsResponseGroupAdministrator 角色成员（或等效身份）创建和激活工作流以及工作流中的所有元素，例如代理组、队列、假日和工作时间、保持音乐等等。

- **管理员创建工作流，经理配置选项** — CsResponseGroupAdministrator 角色成员（或等效身份）定义主要的 SIP URI 和显示名称，分配 CsResponseGroupManager 角色的成员并选择队列和激活工作流。CsResponseGroupManager 然后可以登录，并且通过创建代理组并将组分配给队列，配置电话号码、假日和工作时间以及保持音乐等来编辑工作流的配置。

    > [!NOTE]
    > 如果想要创建托管工作流，则需要创建活动状态的工作流。保存活动状态的托管工作流后，即可修改和停用该工作流。


