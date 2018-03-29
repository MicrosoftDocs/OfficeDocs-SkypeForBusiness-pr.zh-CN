---
title: Skype for Business 2015 中响应组的部署过程
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: d390c8a1-dc6e-44d8-b386-2be1fca9877c
description: 部署过程，并在 Skype 的业务服务器企业语音响应组的步骤。
ms.openlocfilehash: ca390f19b98921f6c8d7fa2a02c8e5065e605a94
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="deployment-process-for-response-group-in-skype-for-business-2015"></a>Skype for Business 2015 中响应组的部署过程
 
部署过程，并在 Skype 的业务服务器企业语音响应组的步骤。
  
响应组是企业语音功能，路由，并排队向一组人称为代理，如帮助台或客户服务台的传入呼叫。
  
安装和部署企业语音时，会自动启用前端服务器或标准版服务器响应组需要的组件。 要对用户进行响应组可用，您必须配置代理组，则队列和工作流。 另外，响应组管理员可以委派给一个响应组管理器，用户可以修改和重新配置工作流及其关联的代理程序组和队列的现有工作流的配置。
  
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
> **(1)** Active Directory 域服务用户对象必须列出指定 Active Directory 安全组的成员。 管理员或具有相应的权限才能将用户添加到安全组 （例如，管理员、 帐户操作员） 其他委派的 Active Directory 组成员必须将用户对象添加到能够列出的安全组或用户组执行列出的函数。 **(2)**仅为 CsResponseGroupAdministrator 分配给 CsResponseGroupManager 的工作流。 **(3)**响应组管理器可以将 CsResponseGroupManager 的另一个成员分配给当前管理器已经管理工作流。 **(4)** CsViewOnlyAdministrator 只能运行动词"Get"cmdlet。
  
## <a name="response-group-configuration-prerequisites"></a>响应组配置的系统必备组件

响应组需要以下组件：
  
- 应用程序服务
    
- 响应组应用程序
    
- 语言包
    
- 文件存储（用于保存音频文件）
    
- Web 服务 （包括响应组配置工具和代理的登录和注销控制台）
    
所有这些组件是默认安装的部署企业语音时。
  
您可能需要在配置响应组之前执行以下任务：
  
- 启用用户配置 Lync Server 2013 和企业语音。
    
- 修改配置文件以符合联邦信息处理标准 (FIPS)。
    
- 修改数据库排序规则以支持队列名称和代理组名称的 Yi、Meng 和 Zang 字符。
    
### <a name="enabling-users"></a>启用用户

配置响应组的第一步是创建代理组。 您可以创建一个代理组之前，必须启用将代理业务和企业语音的 Skype 的响应组的用户。 为用户启用 Skype 业务通常是企业版或标准版服务器部署中的一个步骤。 有关启用用户的 Skype 业务的详细信息，请参阅[启用或禁用用户配置 Lync 服务器 2013年预览](http://technet.microsoft.com/library/12497d00-f665-4a97-be68-854c5a8be4fc.aspx)。 为用户启用企业语音通常是企业语音部署中的一个步骤。 有关详细信息，请参阅[企业语音中的业务服务器 2015年的 Skype 用户启用](enable-users-for-enterprise-voice.md)。 
  
### <a name="complying-with-fips-requirements"></a>符合 FIPS 要求

仅当您的组织需要符合联邦信息处理标准 (FIPS) 时，本节才适用。
  
要符合 FIPS，安装 Web 服务后需要修改应用程序级别 Web.config 文件，以使用不同的加密算法。 需要指定 ASP.NET 使用三重数据加密标准 (3DES) 算法，来处理视图状态数据。 为响应组的应用程序，这一要求适用于响应组配置工具和代理登录和注销控制台。 对于这种要求，有关的详细信息，请参阅 Microsoft 知识库文章 911722，"您可能会收到一条错误消息当您访问已启用后从 ASP.NET 1.1 版升级到 ASP.NET 2.0 中，视图状态的 ASP.NET 网页"在[https://go.microsoft.com/fwlink/p/?linkId=196183](https://go.microsoft.com/fwlink/p/?linkId=196183)。
  
若要修改 Web.config 文件，请执行以下操作：
  
1. 在文本编辑器（如记事本）中，打开应用程序级别 Web.config 文件。
    
2. 在 Web.config 文件中，找到`<system.web>`部分。
    
3. 添加以下`<machineKey>`部分中的`<system.web>`部分中：
    
   ```
   <machineKey validationKey="AutoGenerate,IsolateApps" decryptionKey="AutoGenerate,IsolateApps" validation="3DES" decryption="3DES"/>
   ```

4. 保存 Web.config 文件。
    
5. 通过在命令提示符下运行以下命令来重新启动 Internet Information Services (IIS) 服务： 
    
   ```
   iisreset
   ```

### <a name="supporting-yi-meng-and-zang-characters"></a>支持 Yi、Meng 和 Zang 字符

仅当您的组织需要支持 Yi、Meng 或 Zang 字符时，本节才适用。
  
> [!NOTE]
> Yi、 孟和 Zang 字符是什么和为什么它们可能会部署对重要的信息，请参阅信息 GB18030 字符组[https://go.microsoft.com/fwlink/p/?linkId=240223](https://go.microsoft.com/fwlink/p/?linkId=240223)。 
  
要支持 Yi、Meng 或 Zang 字符，需要修改 Rgsconfig 数据库的排序规则。在每个 Rgsconfig 数据库的下列各表中更改“Name”****列的排序规则：
  
- dbo。AgentGroups
    
- dbo。BusinessHours
    
- dbo。HolidaySets
    
- dbo。队列
    
- dbo。工作流
    
SQL Server 2008 R2 和 SQL Server 2012，使用 Latin_General_100 （重音） 排序规则。 如果使用此排序规则，则所有对象名称不区分大小写。
  
可以使用 Microsoft SQL Server Management Studio 来更改排序规则。 使用此工具的详细信息，请参阅["使用 SQL Server 管理 Studio"](https://go.microsoft.com/fwlink/p/?linkId=196184)。 执行下列步骤可更改排序规则：
  
1. 确保 SQL Server Management Studio 配置为允许要求重新创建表的更改。 有关详细信息，请参阅["保存 （不允许） 对话框"](https://go.microsoft.com/fwlink/p/?linkId=196186)。 有关设置列排序规则的详细信息，请参阅["如何： 设置列的排序规则 （可视化数据库工具）"](https://go.microsoft.com/fwlink/p/?linkId=196185)。
    
2. 使用 Microsoft SQL Server Management Studio 连接到 Rgsconfig 数据库。
    
3. 在 Rgsconfig 数据库中查找要更改的表，右键单击该表，然后单击“设计”****。 
    
4. 更改“名称”列****的排序规则并保存该表。
    
## <a name="response-group-deployment-steps"></a>响应组部署步骤

**响应组部署过程**

|**阶段**|**步骤**|**权限**|**部署文档**|
|:-----|:-----|:-----|:-----|
|Skype 允许用户使用业务和企业语音  <br/> |启用将代理业务和企业语音的 Skype 的用户。 必须先启用用户，然后才能将其添加到代理组。 通常情况下，为用户启用 Skype 业务为企业版或标准版服务器部署过程。 为用户启用企业语音企业语音部署过程。  <br/> |RTCUniversalUserAdmins  <br/> CsUserAdministrator  <br/> CsAdministrator  <br/> |[启用或禁用用户配置 Lync 服务器 2013年预览](http://technet.microsoft.com/library/12497d00-f665-4a97-be68-854c5a8be4fc.aspx) <br/> [启用用户的 Skype 在企业语音的业务服务器 2015](enable-users-for-enterprise-voice.md) <br/> |
|创建和配置由代理组、队列和工作流构成的响应组  <br/> |1.使用 Skype 业务服务器的控制面板或业务服务器管理外壳的 Skype 执行下列操作：  <br/> a. 创建和配置代理组。  <br/> b. 创建和配置队列。  <br/> 2.（可选） 使用 Skype 的业务服务器管理外壳程序创建预定义的响应组工作时间和节假日。  <br/> 3.使用响应组配置工具或 Skype 的业务服务器管理外壳程序创建工作流 （查寻组或交互式语音响应 (IVR) 调用流），包括自定义响应组工作时间和节假日。  <br/> 用于业务服务器控件面板，您可以通过 Skype 访问响应组配置工具。  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> CsResponseGroupManager  <br/> |[创建响应组代理组](http://technet.microsoft.com/library/2a80de17-ead0-46e8-8a27-7a4e233dbde0.aspx) <br/> [创建响应组队列](http://technet.microsoft.com/library/49cb86c7-2cfd-4a53-8408-d407475174ed.aspx) <br/> [（可选）在业务 2015年的 Skype 的定义响应组营业时间](optional-define-response-group-business-hours.md) <br/> [（可选）在业务 2015年的 Skype 的定义响应组假日集](optional-define-response-group-holiday-sets.md) <br/> [设计和创建响应组的工作流业务 2015年的 Skype](designing-and-creating-response-group-workflows.md) <br/> |
|（可选）自定义应用程序级别设置  <br/> |使用 Skype 业务服务器管理外壳程序的自定义默认音乐上保留配置、 默认音乐上保留音频文件、 代理回响限期和调用上下文配置。  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[管理在业务 2015年的 Skype 应用程序级响应组设置](managing-application-level-response-group-settings.md) <br/> |
|（可选）委派响应组的管理  <br/> |为用户分配 CsResponseGroupManager 角色委派响应组的配置。 然后，响应组管理员可以配置分配给它们的响应组。  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[基于角色的访问控制规划](http://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx) <br/> |
|验证响应组部署  <br/> |测试智能寻线和互动语音响应工作流的应答呼叫，以确保您的配置按预期工作。  <br/> |-  <br/> |-  <br/> |
   
## <a name="overview-of-workflow-creation-scenarios"></a>工作流创建方案概述

创建工作流时，可以采用两种方案：
  
- **管理员创建和配置工作流** — CsResponseGroupAdministrator 角色成员（或等效身份）创建和激活工作流以及工作流中的所有元素，例如代理组、队列、假日和工作时间、保持音乐等等。
    
- **管理员创建工作流，经理配置选项** — CsResponseGroupAdministrator 角色成员（或等效身份）定义主要的 SIP URI 和显示名称，分配 CsResponseGroupManager 角色的成员并选择队列和激活工作流。CsResponseGroupManager 然后可以登录，并且通过创建代理组并将组分配给队列，配置电话号码、假日和工作时间以及保持音乐等来编辑工作流的配置。
    
    > [!NOTE]
    > 如果想要创建托管工作流，则需要创建活动状态的工作流。保存活动状态的托管工作流后，即可修改和停用该工作流。 
  

