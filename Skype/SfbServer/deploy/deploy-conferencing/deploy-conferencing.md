---
title: 在 Skype for Business Server 2015 中部署会议
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26dff7d8-242a-4576-9870-d6d461758a37
description: 摘要： 阅读本主题，以了解如何部署业务服务器 2015年在 Skype 的会议。
ms.openlocfilehash: 996fd4515d4a5316b09082eee168881f9cd4a5da
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-conferencing-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中部署会议
 
**摘要：**阅读本主题，以了解如何部署业务服务器 2015年在 Skype 的会议。
  
有四种类型的会议在 Skype 业务服务器中可用： web 会议、 音频和视频 (A / V) 会议、 拨入会议和即时消息 (IM) 会议。 根据你的需要，可选择启用所有会议类型，或者只使用一种类型。 
  
当部署 Skype 业务服务器上时，会自动部署 IM 会议功能。 在使用拓扑生成器创建并发布新的拓扑时，可按照以下清单的说明，指定是否要部署 Web 会议、A/V 会议和电话拨入式会议： 
  
- [Deployment checklist for web and audio/video conferencing](deploy-conferencing.md#BKMK_ChecklistWebConferencing)
    
- [部署的流程图和用于拨入会议清单](deploy-conferencing.md#BKMK_DialinConferencing)
    
在部署会议之前，应阅读以下规划主题：
  
- [规划会议在 Skype 的业务服务器 2015](../../plan-your-deployment/conferencing/conferencing.md)
    
- [硬件和软件要求会议在 Skype 的业务服务器 2015](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md)
    
- [Skype 的业务服务器 2015年计划会议拓扑](../../plan-your-deployment/conferencing/conferencing-topology.md)
    
- [对于拨入会议在 Skype 业务服务器 2015年计划](../../plan-your-deployment/conferencing/dial-in-conferencing.md)
    
- [在 Skype 业务服务器 2015年的大型会议的计划](../../plan-your-deployment/conferencing/large-meetings.md)
    
## <a name="deployment-checklist-for-web-and-audiovideo-conferencing"></a>Web 会议和音频/视频会议的部署清单
<a name="BKMK_ChecklistWebConferencing"> </a>

下表提供了将 Web 会议和音频/视频会议部署到现有拓扑所需步骤的概述。 表中包含相关规划和过程文档的链接。 
  
|**阶段**|**步骤**|**角色和组成员身份**|**文档**|
|:-----|:-----|:-----|:-----|
|**安装必需的硬件和软件** <br/> |在前端服务器的前端池和标准版服务器上运行会议。 请参阅前端服务器的服务器和环境要求。  <br/> 如果要启用网络会议，您将需要确保 Skype 业务服务器可以与 Office Web 应用程序服务器，用来处理共享和呈现的 PowerPoint 演示文稿。  <br/> 对于 Web 会议，还需要指定要用作文件存储的文件共享。  <br/> 是否要允许使用 Skype for Business 客户端的外部用户加入会议？如果是，需要部署边缘服务器。  <br/> |属于本地 Administrators 组成员的域用户  <br/> |[业务服务器 2015 Skype 的的服务要求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [环境要求为 Skype 的业务服务器 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/> [硬件和软件要求会议在 Skype 的业务服务器 2015](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md) <br/> [业务服务器 2015年集成使用 Skype 在 Office Web 应用程序服务器配置](office-web-app-server.md) <br/> [商业服务器 2015 Skype 中创建的文件共享](../../deploy/install/create-a-file-share.md) <br/> [在 Skype 的业务服务器 2015年的边缘服务器部署计划](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) <br/> [部署边缘服务器在 Skype 业务服务器 2015](../../deploy/deploy-edge-server/deploy-edge-server.md) <br/> |
|**创建相应的内部拓扑以支持会议** <br/> |您需要运行拓扑生成器进行将会议添加到拓扑结构中，然后发布拓扑结构。  <br/> |若要定义拓扑，需具有本地 Users 组成员的帐户  <br/> 在文件共享用于业务服务器文件存储为 Skype 发布拓扑，帐户是域管理员组和 RTCUniversalServerAdmins 组的成员并具有完全控制权限 （读/写/修改） (以便拓扑生成器可以配置所需的 Dacl）  <br/> |[创建并发布新的拓扑结构在 Skype 业务服务器 2015](../../deploy/install/create-and-publish-new-topology.md) <br/> |
|**配置会议策略和配置设置** <br/> |使用 Skype 业务服务器的控制面板或 Skype 业务服务器管理外壳的配置会议策略和配置设置。  <br/> |RTCUniversalServerAdmins (仅适用于 Windows PowerShell) 组或将用户分配到 CSAdministrator 角色  <br/> |[管理业务服务器 2015 Skype 会议策略](../../manage/conferencing/conferencing-policies.md) <br/> [管理会议在 Skype 业务服务器 2015年的配置设置](../../manage/conferencing/meeting-configuration-settings.md) <br/> [新 CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> [一组 CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> [新 CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> [一组 CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> [新 CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> [一组 CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |
   
## <a name="deployment-flowchart-and-checklist-for-dial-in-conferencing"></a>电话拨入式会议的部署流程图和清单
<a name="BKMK_DialinConferencing"> </a>

 电话拨入式会议允许用户从公用电话交换网 (PSTN) 拨入来加入音频/视频会议。
  
一些对于拨入会议所需的组件也将使用企业语音。 例如，如果要部署企业语音，还必须部署中介服务器和 PSTN 网关 -- 这也是电话拨入式会议所需的组件。 因此，如何部署电话拨入式会议取决于是否还要部署企业语音解决方案。 
  
根据是否还要部署企业语音解决方案，电话拨入式会议流程图显示了必须遵循的步骤。 流程图后面的表概述了部署电话拨入式会议所需的步骤及推荐步骤。 表中还包含相关规划和过程文档的链接。 有关规划完整的企业语音解决方案的详细信息，请参阅[规划业务服务器 2015年的 Skype 在企业语音解决方案](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-solution.md)。
  
**拨入会议流程图**

![部署电话拨入式会议流程图](../../media/95d2f963-7705-4930-90bc-df6a71a700bf.png)
  
**拨入会议部署检查表**

|**阶段**|**步骤**|**角色和组成员资格**|**文档**|
|:-----|:-----|:-----|:-----|
|**安装必需的硬件和软件** <br/> | 在前端服务器的前端池和标准版服务器上运行会议。 请参阅前端服务器的服务器和环境要求。 <br/>  您需要确保以下安装配置拨入会议之前： <br/>  中介服务器 <br/>  PSTN 网关 <br/>  统一通信应用程序服务 (UCAS)（称为“应用程序服务”） <br/>  会议助理应用程序 <br/>  会议通知应用程序 <br/> |属于本地 Administrators 组成员的域用户  <br/> |[业务服务器 2015 Skype 的的服务要求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [环境要求为 Skype 的业务服务器 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/> [硬件和软件要求会议在 Skype 的业务服务器 2015](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md) <br/> [对于拨入会议在 Skype 业务服务器 2015年计划](../../plan-your-deployment/conferencing/dial-in-conferencing.md) <br/> [在业务服务器 2015年的 Skype 的中介服务器组件](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md) <br/> [在拓扑生成器在 Skype 中介服务器部署为业务服务器 2015](../../deploy/deploy-enterprise-voice/deploy-a-mediation-server.md) <br/> [一个网关定义在拓扑生成器在 Skype 业务服务器 2015](../../deploy/deploy-enterprise-voice/define-a-gateway.md) <br/> |
|**创建拓扑，包括会议的工作负载，包括中介服务器和 PSTN 网关，并将其部署的前端池或标准版服务器** <br/> |1.运行拓扑生成器来配置您的拓扑结构。 配置拓扑时，请选择电话拨入式会议选项。  <br/> 2.发布拓扑结构和部署前端池或标准版服务器。  <br/> 3.如果有必要，请创建独立的中介服务器，并将其与 PSTN 网关。  <br/> **注意：**只有在您不部署企业语音并没有布置与前结束服务器的企业版或标准版服务器中介服务器，则需要此步骤。 如果您部署企业语音，安装和配置中介服务器和 PSTN 网关作为企业语音部署的一部分。 如果您配置中介服务器，安装和配置中介服务器作为前端池或标准版服务器部署的一部分。 <br/> |Domain Admins  <br/> RTCUniversalServerAdmins  <br/> Administrator  <br/> |[创建并发布新的拓扑结构在 Skype 业务服务器 2015](../../deploy/install/create-and-publish-new-topology.md) <br/> [在拓扑生成器在 Skype 中介服务器部署为业务服务器 2015](../../deploy/deploy-enterprise-voice/deploy-a-mediation-server.md) <br/> [一个网关定义在拓扑生成器在 Skype 业务服务器 2015](../../deploy/deploy-enterprise-voice/define-a-gateway.md) <br/> |
|**配置拨号计划** <br/> |拨号计划是一组电话号码规范化规则，它将从特定位置拨打的电话号码转换为单一的标准 (E.164) 格式，以便进行电话授权和呼叫路由。 从不同位置拨打的同一电话号码可以基于各自的拨号计划针对每个具体位置解析为不同的 E.164 号码。 如果部署企业语音您设置拨号计划为该部署的一部分，您需要确保拨号计划还容纳拨入会议。 如果不部署企业语音，您需要设置会议拨入的拨号计划。  <br/> 使用 Skype 业务服务器的控制面板或 Skype 业务服务器命令行管理程序可以设置为拨号计划，如下所示：  <br/> 1.创建一个或多个路由拨号访问电话号码的拨号计划。  <br/> 2.将分配给每个池的默认拨号计划。 将“**电话拨入式会议区域**”设为应用拨号计划的地理位置。 该区域会将拨号计划与拨入访问号码相关联。 <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[在 Skype 为业务服务器 2015年配置拨入会议](dial-in-conferencing.md) <br/> [创建或修改业务服务器 2015 Skype 的拨号计划](../../deploy/deploy-enterprise-voice/dial-plans.md) <br/> [新 CsDialPlan](https://docs.microsoft.com/powershell/module/skype/new-csdialplan?view=skype-ps) <br/> |
|**确保已为拨号计划分配区域** <br/> |运行 **Get-CsDialPlan** 和 **Set-CsDialPlan** cmdlet 确保已为所有拨号计划分配区域。 <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[在 Skype 为业务服务器 2015年配置拨入会议](dial-in-conferencing.md) <br/> [创建或修改业务服务器 2015 Skype 的拨号计划](../../deploy/deploy-enterprise-voice/dial-plans.md) <br/> [获得 CsDialPlan](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps) <br/> [一组 CsDialPlan](https://docs.microsoft.com/powershell/module/skype/set-csdialplan?view=skype-ps) <br/> |
|**配置会议策略以支持电话拨入式会议** <br/> | 使用 Skype 业务服务器的控制面板或 Skype 的业务服务器管理外壳配置**会议策略**设置。 指定： <br/>  是否启用 PSTN 会议拨入。 <br/>  用户能否邀请匿名参与者。 <br/>  未经身份验证的用户能否通过拨出式电话加入会议。通过拨出式电话，会议服务器会呼叫用户，用户接听电话即可加入会议。<br/> |RTCUniversalServerAdmins  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[管理业务服务器 2015 Skype 会议策略](../../manage/conferencing/conferencing-policies.md) <br/> [新 CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> [一组 CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |
|**配置拨入访问号码** <br/> |使用 Skype 业务服务器的控制面板或 Skype 的业务服务器管理外壳程序设置拨入访问号码的用户调用拨号加入会议，并指定相应的拨号计划相关联的访问号码的地区。 组织者拨号计划指定的区域的前三个访问号码包含在会议邀请中。 所有访问号码都都拨入会议设置页上可用。  <br/> **注意：**创建拨入访问号码后，可以使用**一组 CsDialInConferencingAccessNumber** cmdlet 修改 Active Directory 联系对象的显示名称，以便用户可以更轻松地识别正确的访问号码。 <br/> |RTCUniversalServerAdmins  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[创建或修改业务服务器 2015 Skype 的拨号计划](../../deploy/deploy-enterprise-voice/dial-plans.md) <br/> [管理拨入会议访问号码在 Skype 业务服务器 2015](../../manage/conferencing/access-numbers.md) <br/> [新 CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingaccessnumber?view=skype-ps) <br/> [一组 CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) <br/> |
|**Assign a Line URI to a user account** <br/> |使用 Skype 业务服务器的控制面板或 Skype 的业务服务器管理外壳配置电话**线路的 URI**是唯一的规范化电话号码 (例如，电话： +14255550200)。 <br/> |RTCUniversalServerAdmins  <br/> CsAdministrator  <br/> CsUserAdministrator  <br/> |[Assign a Line URI to a user account](dial-in-conferencing.md#BKMK_AssignaLineURI) <br/> |
|**（可选）验证或修改用户个人标识号 (PIN) 要求** <br/> |使用 Skype 业务服务器的控制面板或业务服务器管理外壳的 Skype 来查看或修改会议**PIN 策略**。 可以指定最小 PIN 长度、最大登录尝试次数、PIN 到期时间以及是否允许使用通用模式。  <br/> |RTCUniversalServerAdmins  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[管理业务服务器 2015年拨入会议在 Skype 的 PIN 策略](../../manage/conferencing/pin-policies.md) <br/> [获得 CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) <br/> [一组 CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps) <br/> |
|**（可选）修改 DTMF 命令的键映射** <br/> |使用 **Set-CsDialinConferencingDtmfConfiguration** cmdlet 修改用于双音多频 (DTMF) 命令的键，参与者可使用这些命令控制会议设置（如静音和取消静音或锁定和解除锁定）。 <br/> |RTCUniversalServerAdmins  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[管理业务服务器 2015年在 Skype 的 DTMF 命令键映射](../../manage/conferencing/key-mapping-for-dtmf-commands.md) <br/> [一组 CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |
|**（可选）修改会议加入和离开通知行为** <br/> |使用 **Set-CsDialinConferencingConfiguration** 更改参与者加入和离开会议时通知的工作方式。 <br/> |RTCUniversalServerAdmins  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[参加会议的管理和使在 Skype 业务服务器 2015年公告](../../manage/conferencing/join-and-leave-announcements.md) <br/> [一组 CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) <br/> |
|**（推荐）配置会议目录** <br/> |使用 **New-CsConferenceDirectory** cmdlet 为池中的每 999 个用户创建一个会议目录。 <br/> |RTCUniversalServerAdmins  <br/> |[（推荐）创建会议目录](http://technet.microsoft.com/library/787f4c94-1c96-468a-a74d-e06b7bd4b8a3.aspx) <br/> [新 CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps) <br/> |
|**（可选）验证电话拨入式会议设置** <br/> |使用 **Get-CsDialinConferencingAccessNumber** cmdlet 搜索具有未被任何访问号码使用的电话拨入式会议区域的拨号计划，以及尚未分配区域的访问号码。 <br/> |RTCUniversalServerAdmins  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> CsViewOnlyAdministrator  <br/> CsHelpDesk  <br/> |[在 Skype 为业务服务器 2015年配置拨入会议](dial-in-conferencing.md) <br/> [测试拨入会议在 Skype 业务服务器 2015](../../manage/conferencing/tests.md) <br/> [获得 CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps) <br/> |
|**（可选）验证电话拨入式会议** <br/> |使用 **Test-CsDialInConferencing** cmdlet 测试指定池的访问号码是否正常工作。 <br/> |RTCUniversalServerAdmins  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[测试拨入会议在 Skype 业务服务器 2015](../../manage/conferencing/tests.md) <br/> [测试 CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/test-csdialinconferencing?view=skype-ps) <br/> |
|**（可选）欢迎用户参加电话拨入式会议并设置初始 PIN** <br/> |使用**一组 CsPinSendCAWelcomeMail**脚本来设置用户的初始针脚并发送欢迎电子邮件，其中包含初始 PIN 和拨入会议设置页面的链接。 <br/> |RTCUniversalServerAdmins  <br/> |[发送欢迎电子邮件要拨入的业务服务器 2015 Skype 的用户](../../manage/conferencing/welcome-emails.md) <br/> |
   

