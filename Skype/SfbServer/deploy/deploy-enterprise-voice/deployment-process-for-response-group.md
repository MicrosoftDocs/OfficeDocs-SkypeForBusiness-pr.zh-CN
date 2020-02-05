---
title: Skype for Business 中响应组的部署过程
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d390c8a1-dc6e-44d8-b386-2be1fca9877c
description: Skype for business Server Enterprise Voice 中的部署过程和响应组的步骤。
ms.openlocfilehash: 810bf635794f58ad8f28295549023a3ef2450f69
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767525"
---
# <a name="deployment-process-for-response-group-in-skype-for-business"></a>Skype for Business 中响应组的部署过程

Skype for business Server Enterprise Voice 中的部署过程和响应组的步骤。

响应组是一种企业语音功能，用于将传入呼叫路由和排队到一组人员（称为工程师，如帮助桌面或客户服务桌面）。

部署 "企业语音" 时，将在前端服务器或标准版服务器上自动安装和启用响应组所需的组件。 若要使 "响应组" 对用户可用，必须先配置代理组、"队列" 和 "工作流"。 此外，响应组管理员可以将现有工作流的配置委派给响应组管理器，然后这些管理员可以修改和重新配置工作流及其关联的代理组和队列。

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
> **（1）** Active Directory 域服务用户对象必须是所列的指定 Active directory 安全组的成员。 具有将用户添加到安全组的相应权限的管理员或其他委派的 Active Directory 组成员（例如管理员、帐户操作员）必须将用户对象添加到列出的安全组或组中，以便用户能够执行列出的函数。 **（2）** 仅适用于 CsResponseGroupAdministrator 分配给 CsResponseGroupManager 的工作流。 **（3）** 响应组管理器可以将 CsResponseGroupManager 的另一个成员分配给当前管理器已管理的工作流。 **（4）** CsViewOnlyAdministrator 仅可运行动词 "Get" cmdlet。

## <a name="response-group-configuration-prerequisites"></a>响应组配置先决条件

响应组需要以下组件：

- 应用程序服务

- 响应组应用程序

- 语言包

- 文件存储（用于保存音频文件）

- Web 服务（包括响应组配置工具和代理的登录和注销控制台）

在部署企业语音时，默认情况下会安装所有这些组件。

在配置响应组之前，可能需要执行以下任务：

- 为 Lync Server 2013 和企业语音启用用户。

- 修改配置文件以符合联邦信息处理标准 (FIPS)。

- 修改数据库排序规则以支持队列名称和代理组名称的 Yi、Meng 和 Zang 字符。

### <a name="enabling-users"></a>启用用户

配置响应组的第一步是创建代理组。 在创建代理组之前，必须启用将用作 Skype for business 和企业语音的 "响应" 组的代理用户。 为 Skype for business 启用用户通常是企业版服务器或标准版服务器部署中的一个步骤。 有关为 Skype for business 启用用户的详细信息，请参阅[启用或禁用 Lync Server 2013 预览版的用户](https://technet.microsoft.com/library/12497d00-f665-4a97-be68-854c5a8be4fc.aspx)。 为企业语音启用用户通常是企业语音部署中的一个步骤。 有关详细信息，请参阅[在 Skype For Business 服务器中启用企业语音用户](enable-users-for-enterprise-voice.md)。

### <a name="complying-with-fips-requirements"></a>符合 FIPS 要求

仅当您的组织需要符合联邦信息处理标准 (FIPS) 时，本节才适用。

要符合 FIPS，安装 Web 服务后需要修改应用程序级别 Web.config 文件，以使用不同的加密算法。 需要指定 ASP.NET 使用三重数据加密标准 (3DES) 算法，来处理视图状态数据。 对于响应组应用程序，此要求适用于响应组配置工具和代理登录和注销控制台。 有关此要求的详细信息，请参阅 Microsoft 知识库文章911722，当你访问在从 ASP.NET 1.1 升级到 ASP.NET 2.0 后启用了 ViewState 的 ASP.NET 网页时，你可能会收到错误消息[https://go.microsoft.com/fwlink/p/?linkId=196183](https://go.microsoft.com/fwlink/p/?linkId=196183)。

若要修改 Web.config 文件，请执行以下操作：

1. 在文本编辑器（如记事本）中，打开应用程序级别 Web.config 文件。

2. 在 web.config 文件中，找到相应的`<system.web>`部分。

3. 将以下`<machineKey>`部分添加到 "" `<system.web>`部分中：

   ```xml
   <machineKey validationKey="AutoGenerate,IsolateApps" decryptionKey="AutoGenerate,IsolateApps" validation="3DES" decryption="3DES"/>
   ```

4. 保存 Web.config 文件。

5. 通过在命令提示符处运行以下命令，重启 Internet 信息服务（IIS）服务：

   ```console
   iisreset
   ```

### <a name="supporting-yi-meng-and-zang-characters"></a>支持 Yi、Meng 和 Zang 字符

仅当您的组织需要支持 Yi、Meng 或 Zang 字符时，本节才适用。

> [!NOTE]
> 有关 Yi、Meng 和 Zang 字符的内容以及它们对部署很重要的原因的信息，请参阅 GB18030 字符集[https://go.microsoft.com/fwlink/p/?linkId=240223](https://go.microsoft.com/fwlink/p/?linkId=240223)的相关信息。

要支持 Yi、Meng 或 Zang 字符，需要修改 Rgsconfig 数据库的排序规则。在每个 Rgsconfig 数据库的下列各表中更改“Name”**** 列的排序规则：

- dbo.AgentGroups

- dbo.BusinessHours

- dbo.HolidaySets

- dbo.Queues

- dbo.Workflows

对于 SQL Server 2008 R2 和 SQL Server 2012，请使用 Latin_General_100 （区分重音）排序规则。 如果使用此排序规则，则所有对象名称不区分大小写。

可以使用 Microsoft SQL Server Management Studio 来更改排序规则。 有关使用此工具的详细信息，请参阅["使用 SQL Server Management Studio"](https://go.microsoft.com/fwlink/p/?linkId=196184)。 执行下列步骤可更改排序规则：

1. 确保 SQL Server Management Studio 配置为允许要求重新创建表的更改。 有关详细信息，请参阅["保存（不允许）" 对话框](https://go.microsoft.com/fwlink/p/?linkId=196186)。 有关设置列排序规则的详细信息，请参阅["操作方法：设置列排序规则（可视化数据库工具）"](https://go.microsoft.com/fwlink/p/?linkId=196185)。

2. 使用 Microsoft SQL Server Management Studio 连接到 Rgsconfig 数据库。

3. 在 Rgsconfig 数据库中查找要更改的表，右键单击该表，然后单击“设计”****。

4. 更改“名称”列**** 的排序规则并保存该表。

## <a name="response-group-deployment-steps"></a>响应组部署步骤

**响应组部署过程**

|**阶段**|**步骤**|**权限**|**部署文档**|
|:-----|:-----|:-----|:-----|
|为用户启用 Skype for business 和企业语音  <br/> |启用将用作 Skype for business 和企业语音的代理的用户。 必须先启用用户，然后才能将其添加到代理组。 通常，在企业版或标准版服务器部署期间启用 Skype for business 的用户。 在企业语音部署期间，用户可用于企业语音。  <br/> |RTCUniversalUserAdmins  <br/> CsUserAdministrator  <br/> CsAdministrator  <br/> |[Enable or Disable Users for Lync Server 2013 Preview](https://technet.microsoft.com/library/12497d00-f665-4a97-be68-854c5a8be4fc.aspx) <br/> [在 Skype for business 服务器中启用企业语音用户](enable-users-for-enterprise-voice.md) <br/> |
|创建和配置由代理组、队列和工作流构成的响应组  <br/> |1. 使用 Skype for Business 服务器控制面板或 Skype for business Server 命令行管理程序执行下列操作：  <br/> a. 创建和配置代理组。  <br/> b. 创建和配置队列。  <br/> 2. （可选）使用 Skype for Business Server Management Shell 创建预定义的响应组业务时间和假日。  <br/> 3. 使用 "响应组配置" 工具或 "Skype for Business 服务器" 命令行管理程序创建工作流（查寻组或交互式语音响应（IVR）调用流程），包括自定义响应组的业务时间和假日。  <br/> 您可以通过 "Skype for Business 服务器控制面板" 访问 "响应组配置" 工具。  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> CsResponseGroupManager  <br/> |[Create Response Group Agent Groups](https://technet.microsoft.com/library/2a80de17-ead0-46e8-8a27-7a4e233dbde0.aspx) <br/> [Create Response Group Queues](https://technet.microsoft.com/library/49cb86c7-2cfd-4a53-8408-d407475174ed.aspx) <br/> [可选在 Skype for Business 中定义响应组工作时间](optional-define-response-group-business-hours.md) <br/> [可选在 Skype for Business 中定义响应组假日集](optional-define-response-group-holiday-sets.md) <br/> [在 Skype for Business 中设计和创建响应组工作流](designing-and-creating-response-group-workflows.md) <br/> |
|（可选）自定义应用程序级别设置  <br/> |使用 Skype for Business Server Management Shell 自定义默认的音乐保留配置、默认的音乐保留音频文件、代理 ringback 宽限期和呼叫上下文配置。  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[管理 Skype for Business 中的应用程序级响应组设置](managing-application-level-response-group-settings.md) <br/> |
|（可选）委派响应组的管理  <br/> |为用户分配 CsResponseGroupManager 角色以委派响应组的配置。 然后，响应组管理员可以配置分配给他们的响应组。  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Planning for Role-Based Access Control](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx) <br/> |
|验证响应组部署  <br/> |测试智能寻线和互动语音响应工作流的应答呼叫，以确保您的配置按预期工作。  <br/> |-  <br/> |-  <br/> |

## <a name="overview-of-workflow-creation-scenarios"></a>工作流创建方案概述

创建工作流时，可以采用两种方案：

- **管理员创建和配置工作流** — CsResponseGroupAdministrator 角色成员（或等效身份）创建和激活工作流以及工作流中的所有元素，例如代理组、队列、假日和工作时间、保持音乐等等。

- **管理员创建工作流，经理配置选项** — CsResponseGroupAdministrator 角色成员（或等效身份）定义主要的 SIP URI 和显示名称，分配 CsResponseGroupManager 角色的成员并选择队列和激活工作流。CsResponseGroupManager 然后可以登录，并且通过创建代理组并将组分配给队列，配置电话号码、假日和工作时间以及保持音乐等来编辑工作流的配置。

    > [!NOTE]
    > 如果想要创建托管工作流，则需要创建活动状态的工作流。保存活动状态的托管工作流后，即可修改和停用该工作流。


