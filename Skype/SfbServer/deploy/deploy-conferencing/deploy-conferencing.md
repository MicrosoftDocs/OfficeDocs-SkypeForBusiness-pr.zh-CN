---
title: 为业务服务器部署中 Skype 的会议
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26dff7d8-242a-4576-9870-d6d461758a37
description: 摘要： 阅读本主题可了解如何为业务服务器部署中 Skype 的会议。
ms.openlocfilehash: 5b67bef5ce55e9c4a2c4b71e80a26ffe2600ad92
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30893298"
---
# <a name="deploy-conferencing-in-skype-for-business-server"></a>为业务服务器部署中 Skype 的会议

**摘要：** 阅读本主题可了解如何为业务 Server 部署中 Skype 的会议。

有四种类型的会议中的业务服务器 Skype 可用： web 会议、 音频和视频 (A / V) 会议、 电话拨入式会议和即时消息 (IM) 会议。 根据你的需要，可选择启用所有会议类型，或者只使用一种类型。

在部署 Skype 业务服务器时，会自动部署 IM 会议功能。 在使用拓扑生成器创建并发布新的拓扑时，可按照以下清单的说明，指定是否要部署 Web 会议、A/V 会议和电话拨入式会议：

- [Deployment checklist for web and audio/video conferencing](deploy-conferencing.md#BKMK_ChecklistWebConferencing)

- [电话拨入式会议的部署流程图和清单](deploy-conferencing.md#BKMK_DialinConferencing)

部署会议之前，您应阅读以下规划主题：

- [规划业务服务器中 Skype 的会议](../../plan-your-deployment/conferencing/conferencing.md)

- [硬件和软件要求的 Skype 中的会议的企业服务器](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md)

- [规划业务 Server Skype 的会议拓扑](../../plan-your-deployment/conferencing/conferencing-topology.md)

- [规划电话拨入式会议中 Skype 业务服务器](../../plan-your-deployment/conferencing/dial-in-conferencing.md)

- [规划大型会议中 Skype 业务服务器](../../plan-your-deployment/conferencing/large-meetings.md)

## <a name="deployment-checklist-for-web-and-audiovideo-conferencing"></a>Web 会议和音频/视频会议的部署清单
<a name="BKMK_ChecklistWebConferencing"> </a>

下表提供了将 Web 会议和音频/视频会议部署到现有拓扑所需步骤的概述。 表中包含相关规划和过程文档的链接。

|**阶段**|**步骤**|**角色和组成员身份**|**文档**|
|:-----|:-----|:-----|:-----|
|**安装必需的硬件和软件** <br/> |前端池的前端服务器和 Standard Edition server 上，运行会议。 请参阅前端服务器的服务器和环境要求。  <br/> 如果要启用 web 会议，您需要确保 Skype 业务服务器可以相互 Office Web Apps Server，用来处理共享和呈现的 PowerPoint 演示文稿。  <br/> 对于 Web 会议，还需要指定要用作文件存储的文件共享。  <br/> 是否要允许使用 Skype for Business 客户端的外部用户加入会议？如果是，需要部署边缘服务器。  <br/> |属于本地 Administrators 组成员的域用户  <br/> | [Skype for Business Server 2019 服务器要求](../../../SfBServer2019/plan/system-requirements.md) <br> [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/> [硬件和软件要求的 Skype 中的会议的企业服务器](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md) <br/> [配置与 Skype 中的 Office Web Apps Server 的集成的企业服务器](office-web-app-server.md) <br/> [为 Business Server Skype 创建文件共享](../../deploy/install/create-a-file-share.md) <br/> [Plan for Edge Server deployments in Skype for Business Server 2015](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) <br/> [Deploy Edge Server in Skype for Business Server 2015](../../deploy/deploy-edge-server/deploy-edge-server.md) <br/> |
|**创建相应的内部拓扑以支持会议** <br/> |您需要运行拓扑生成器向拓扑中，添加会议，然后发布该拓扑。  <br/> |若要定义拓扑，需具有本地 Users 组成员的帐户  <br/> 用于 Business Server 文件存储的 Skype 的文件共享上发布拓扑，以 Domain Admins 组和 RTCUniversalServerAdmins 组的成员且具有完全控制权限 （读/写/修改） 的帐户 (以便拓扑生成器可以配置所需的 Dacl）  <br/> |[创建和发布新拓扑中 Skype 业务服务器](../../deploy/install/create-and-publish-new-topology.md) <br/> |
|**配置会议策略和配置设置** <br/> |使用业务 Server Control Panel 或业务 Server Management Shell 的 Skype Skype 配置会议策略和配置设置。  <br/> |RTCUniversalServerAdmins 组 (仅限于 Windows PowerShell) 或分配给 CSAdministrator 角色的用户  <br/> |[Skype 中的会议策略管理业务服务器 （英文）](../../manage/conferencing/conferencing-policies.md) <br/> [管理会议中 Skype 业务服务器的配置设置](../../manage/conferencing/meeting-configuration-settings.md) <br/> [New-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> [New-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> [Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> [New-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> [Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |

## <a name="deployment-flowchart-and-checklist-for-dial-in-conferencing"></a>电话拨入式会议的部署流程图和清单
<a name="BKMK_DialinConferencing"> </a>

 电话拨入式会议允许用户从公用电话交换网 (PSTN) 拨入来加入音频/视频会议。

电话拨入式会议所需的组件的一些还会使用企业语音。 例如，如果要部署企业语音，还必须部署中介服务器和 PSTN 网关 -- 这也是电话拨入式会议所需的组件。 因此，如何部署电话拨入式会议取决于是否还要部署企业语音解决方案。

根据是否还要部署企业语音解决方案，电话拨入式会议流程图显示了必须遵循的步骤。 流程图后面的表概述了部署电话拨入式会议所需的步骤及推荐步骤。 表中还包含相关规划和过程文档的链接。 有关规划完整的企业语音解决方案的详细信息，请参阅[规划企业语音解决方案中的业务服务器 Skype](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-solution.md)。

**电话拨入式会议流程图**

![部署电话拨入式会议流程图](../../media/95d2f963-7705-4930-90bc-df6a71a700bf.png)

**电话拨入式会议部署清单**

|**阶段**|**步骤**|**角色和组成员身份**|**文档**|
|:-----|:-----|:-----|:-----|
|**安装必需的硬件和软件** <br/> | 前端池的前端服务器和 Standard Edition server 上，运行会议。 请参阅前端服务器的服务器和环境要求。 <br/>  您需要确保以下安装之前配置电话拨入式会议： <br/>  中介服务器 <br/>  PSTN 网关 <br/>  统一通信应用程序服务 (UCAS)（称为“应用程序服务”） <br/>  会议助理应用程序 <br/>  会议通知应用程序 <br/> |属于本地 Administrators 组成员的域用户  <br/> |[Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/> [硬件和软件要求的 Skype 中的会议的企业服务器](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md) <br/> [规划电话拨入式会议中 Skype 业务服务器](../../plan-your-deployment/conferencing/dial-in-conferencing.md) <br/> [Skype 业务服务器中的中介服务器组件](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md) <br/> [业务服务器部署在拓扑生成器中 Skype 在中介服务器](../../deploy/deploy-enterprise-voice/deploy-a-mediation-server.md) <br/> [为业务服务器中 Skype 的拓扑生成器中定义网关](../../deploy/deploy-enterprise-voice/define-a-gateway.md) <br/> |
|**创建包含会议工作负荷，包括中介服务器和 PSTN 网关拓扑并部署前端池或 Standard Edition server** <br/> |1.运行拓扑生成器配置您的拓扑。 配置拓扑时，请选择电话拨入式会议选项。  <br/> 2.发布拓扑并部署前端池或 Standard Edition server。  <br/> 3.如果必要，创建独立的中介服务器，并将其与 PSTN 网关相关联。  <br/> **注意：** 仅当未部署企业语音并不将并置中介服务器与 Enterprise Edition 前端服务器或 Standard Edition 服务器，此步骤是必需。 如果您部署企业语音，安装和配置企业语音部署的一部分的中介服务器和 PSTN 网关。 如果您将并置中介服务器，您安装和配置前端池或 Standard Edition server 部署的一部分的中介服务器。 <br/> |Domain Admins  <br/> RTCUniversalServerAdmins  <br/> Administrator  <br/> |[创建和发布新拓扑中 Skype 业务服务器](../../deploy/install/create-and-publish-new-topology.md) <br/> [业务服务器部署在拓扑生成器中 Skype 在中介服务器](../../deploy/deploy-enterprise-voice/deploy-a-mediation-server.md) <br/> [为业务服务器中 Skype 的拓扑生成器中定义网关](../../deploy/deploy-enterprise-voice/define-a-gateway.md) <br/> |
|**Configure dial plans** <br/> |拨号计划是一组电话号码规范化规则，它将从特定位置拨打的电话号码转换为单一的标准 (E.164) 格式，以便进行电话授权和呼叫路由。 从不同位置拨打的同一电话号码可以基于各自的拨号计划针对每个具体位置解析为不同的 E.164 号码。 如果部署企业语音的部署的一部分设置拨号计划，您需要确保拨号计划也容纳电话拨入式会议。 如果未部署企业语音，您需要设置电话拨入式会议的拨号计划。  <br/> 使用 Skype 的业务 Server Control Panel 或业务 Server 命令行管理程序设置的 Skype 拨号计划，如下所示：  <br/> 1.创建路由的电话拨入式接入电话号码的一个或多个拨号的计划。  <br/> 2.分配给每个池的默认拨号计划。 将“**电话拨入式会议区域**”设为应用拨号计划的地理位置。 该区域会将拨号计划与拨入访问号码相关联。 <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[在 Skype for Business Server 中配置电话拨入式会议](dial-in-conferencing.md) <br/> [创建或修改拨号计划中 Skype 业务服务器](../../deploy/deploy-enterprise-voice/dial-plans.md) <br/> [New-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/new-csdialplan?view=skype-ps) <br/> |
|**确保已为拨号计划分配区域** <br/> |运行 **Get-CsDialPlan** 和 **Set-CsDialPlan** cmdlet 确保已为所有拨号计划分配区域。 <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[在 Skype for Business Server 中配置电话拨入式会议](dial-in-conferencing.md) <br/> [创建或修改拨号计划中 Skype 业务服务器](../../deploy/deploy-enterprise-voice/dial-plans.md) <br/> [Get-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps) <br/> [Set-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/set-csdialplan?view=skype-ps) <br/> |
|**配置会议策略以支持电话拨入式会议** <br/> | 使用业务 Server Control Panel 或业务 Server Management Shell 的 Skype Skype 配置**会议策略**设置。 指定： <br/>  是否启用 PSTN 会议拨入。 <br/>  用户能否邀请匿名参与者。 <br/>  未经身份验证的用户能否通过拨出式电话加入会议。通过拨出式电话，会议服务器会呼叫用户，用户接听电话即可加入会议。<br/> |RTCUniversalServerAdmins  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Skype 中的会议策略管理业务服务器 （英文）](../../manage/conferencing/conferencing-policies.md) <br/> [New-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |
|**Configure dial-in access numbers** <br/> |使用业务 Server Control Panel 或业务 Server Management Shell 的 Skype Skype 设置的用户呼叫会议，拨入电话拨入访问号码，并指定相应的拨号计划相关联的访问号码的区域。 组织者拨号计划指定的区域的前三个访问号码包含在会议邀请中。 所有的接入号码有电话拨入式会议设置页上。  <br/> **注意：** 创建电话拨入访问号码后，您可以使用**Set-csdialinconferencingaccessnumber** cmdlet 可以修改的 Active Directory 联系对象的显示名称，以便用户可以更轻松地识别的正确的访问号码。 <br/> |RTCUniversalServerAdmins  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[创建或修改拨号计划中 Skype 业务服务器](../../deploy/deploy-enterprise-voice/dial-plans.md) <br/> [管理 Business Server （英文） 中 Skype 的电话拨入式会议访问号码](../../manage/conferencing/access-numbers.md) <br/> [New-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingaccessnumber?view=skype-ps) <br/> [Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) <br/> |
|**Assign a Line URI to a user account** <br/> |使用 Skype 的业务 Server Control Panel 或业务 Server Management Shell 的 Skype 电话**线路 URI**配置为唯一的规范化电话号码 (例如，tel: + 14255550200)。 <br/> |RTCUniversalServerAdmins  <br/> CsAdministrator  <br/> CsUserAdministrator  <br/> |[Assign a Line URI to a user account](dial-in-conferencing.md#BKMK_AssignaLineURI) <br/> |
|**（可选）验证或修改用户个人标识号 (PIN) 要求** <br/> |使用业务 Server Control Panel 或业务 Server Management Shell 的 Skype Skype 查看或修改会议**PIN 策略**。 可以指定最小 PIN 长度、最大登录尝试次数、PIN 到期时间以及是否允许使用通用模式。  <br/> |RTCUniversalServerAdmins  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[管理 Business Server （英文） 中 Skype 电话拨入式会议 PIN 策略](../../manage/conferencing/pin-policies.md) <br/> [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) <br/> [Set-cspinpolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps) <br/> |
|**（可选）修改 DTMF 命令的键映射** <br/> |使用 **Set-CsDialinConferencingDtmfConfiguration** cmdlet 修改用于双音多频 (DTMF) 命令的键，参与者可使用这些命令控制会议设置（如静音和取消静音或锁定和解除锁定）。 <br/> |RTCUniversalServerAdmins  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[管理业务服务器中 Skype 的 DTMF 命令的键映射](../../manage/conferencing/key-mapping-for-dtmf-commands.md) <br/> [Set-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |
|**（可选）修改会议加入和离开通知行为** <br/> |使用 **Set-CsDialinConferencingConfiguration** 更改参与者加入和离开会议时通知的工作方式。 <br/> |RTCUniversalServerAdmins  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[管理会议加入和离开通知中 Skype 业务服务器](../../manage/conferencing/join-and-leave-announcements.md) <br/> [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) <br/> |
|**（推荐）配置会议目录** <br/> |使用 **New-CsConferenceDirectory** cmdlet 为池中的每 999 个用户创建一个会议目录。 <br/> |RTCUniversalServerAdmins  <br/> |[(Recommended) Create Conference Directories](https://technet.microsoft.com/library/787f4c94-1c96-468a-a74d-e06b7bd4b8a3.aspx) <br/> [New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps) <br/> |
|**（可选）验证电话拨入式会议设置** <br/> |使用 **Get-CsDialinConferencingAccessNumber** cmdlet 搜索具有未被任何访问号码使用的电话拨入式会议区域的拨号计划，以及尚未分配区域的访问号码。 <br/> |RTCUniversalServerAdmins  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> CsViewOnlyAdministrator  <br/> CsHelpDesk  <br/> |[在 Skype for Business Server 中配置电话拨入式会议](dial-in-conferencing.md) <br/> [测试电话拨入式会议中的业务服务器 Skype](../../manage/conferencing/tests.md) <br/> [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps) <br/> |
|**（可选）验证电话拨入式会议** <br/> |使用 **Test-CsDialInConferencing** cmdlet 测试指定池的访问号码是否正常工作。 <br/> |RTCUniversalServerAdmins  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[测试电话拨入式会议中的业务服务器 Skype](../../manage/conferencing/tests.md) <br/> [Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/test-csdialinconferencing?view=skype-ps) <br/> |
|**（可选）欢迎用户参加电话拨入式会议并设置初始 PIN** <br/> |使用**Set-cspinsendcawelcomemail**脚本设置用户的初始 Pin 并发送包含初始 PIN 和指向电话拨入式会议设置页的链接的欢迎电子邮件。 <br/> |RTCUniversalServerAdmins  <br/> |[发送欢迎电子邮件以电话拨入式 Skype 业务服务器中的用户](../../manage/conferencing/welcome-emails.md) <br/> |


