---
title: 设置 Microsoft 团队的云视频互操作
author: lolaj
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: srividhc
description: 本文介绍如何规划和在您的组织中设置用户云视频互操作。
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: e2090036aa5e1a05e46581d365d9b6b4aeb94b32
ms.sourcegitcommit: fbef2bfa4e5eb27799aa25f0e890cfb18013cf72
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2018
ms.locfileid: "25040777"
---
# <a name="set-up-cloud-video-interop-for-microsoft-teams"></a>设置 Microsoft 团队的云视频互操作

[选择上您云视频互操作的合作伙伴](cloud-video-interop.md)后，您需要规划您的部署，提供设置的详细信息和合作伙伴租户密钥和同意您的组织中的视频互操作应用程序获取设置。 下图概述的过程。 

![组织中部署 CVI](media/deploying-cvi.png)

## <a name="plan"></a>规划

关于标识合作伙伴在组织中使用的信息，请参阅[Microsoft 团队的云视频互操作](cloud-video-interop.md)。 

若要规划用户基于/并发/网站范围启用： 

- 选取您使用的部署模型/承载模型
- 选择适合您的组织的许可计划。 
- 虚拟机的容量规划是将承载视频基础结构。

## <a name="configure"></a>配置 

若要配置云视频互操作，请按照下列步骤。 

1. 从合作伙伴/合作伙伴必须获取所选 （租户密钥、 appIds...） 的配置信息。 您可以使用一个或多个视频互操作的合作伙伴组织 

2. 确保您的网络配置正确。 配置基于标准的视频防火墙的外围网络遍历支持。 例如： 
    - Cisco VCS-e                  
    - Polycom RPAD

3. 配置 exchange 和 OTD 集成的聊天室。 在大多数情况下，其他中继需要设置和配置您的环境中。


## <a name="provision"></a>设置
 
租户密钥将与合作伙伴服务的拨出。 以下示例中，在 813878896@t.plcm.vc 是租户密钥。 

![租户密钥示例](media/tenant-key-example.png) 

您需要执行以下 cmdlet 设置的租户密钥，并还允许选择用户或整个组织使用视频互操作性坐标创建会议。

 
- ** [Get CsTeamsVideoInteropServicepolicy](https://docs.microsoft.com/en-us/powershell/module/skype/get-csteamsvideointeropservicepolicy):** Microsoft 提供的预构建的策略用于每个允许您指定其中合作伙伴用于云视频互操作的支持合作伙伴。

    此 cmdlet，可以确定可以在组织中使用的预构建的策略。 您可以将此策略分配给一个或多个用户利用授予 CsTeamsVideoInteropServicePolicy cmdlet。
 
- **[授予 CsTeamsVideoInteropServicePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-csteamsvideointeropservicepolicy):** 授予 CsTeamsVideoInteropServicePolicy cmdlet 可以分配组织中使用的预构建的策略或将策略分配给特定用户。
 
- **[新 CsVideoInteropServiceProvider](https://docs.microsoft.com/en-us/powershell/module/skype/new-csvideointeropserviceprovider):** 新建 CsVideoInteropServiceProvider 用于指定有关支持 CVI 合作伙伴组织希望使用的信息。
 
- **[集 CsVideoInteropServiceProvider](https://docs.microsoft.com/en-us/powershell/module/skype/set-csvideointeropserviceprovider):** 使用组 CsVideoInteropServiceProvider 更新您的组织使用的支持 CVI 合作伙伴的信息。
 
- ** [Get CsVideoInteropServiceProvider](https://docs.microsoft.com/en-us/powershell/module/skype/get-csvideointeropserviceprovider):** 获取组织中使用的所有已配置提供程序。
 
- **[删除 CsVideoInteropServiceProvider](https://docs.microsoft.com/en-us/powershell/module/skype/remove-csvideointeropserviceprovider):** 使用删除 CsVideoInteropServiceProvider 删除有关您的组织不再使用的提供程序的所有提供商信息。  
 
## <a name="consent"></a>同意

您需要为远程视频会议设备 (VTCs) 加入您的组织会议，通过合作伙伴服务提供权限同意。 此外将由您的合作伙伴提供此同意链接。  
 
完成这些步骤后，如果已启用租户，单独启用通过授予 cmdlet，或在组织中的用户的所有用户将他们安排的团队会议中具有 VTC 坐标。 任何 VTC 可以加入这些会议，通过这些坐标。


|名称|应用程序权限的简短说明| 说明|
|--|--|---|
|Calls.JoinGroupCall.All|加入组呼叫和会议作为应用程序 （预览）|允许应用程序以在组织中，已登录的用户的情况下加入组呼叫和计划的会议。  应用程序将被加入的会议在您的租户中的目录用户权限。|
|Calls.JoinGroupCallasGuest.All|作为来宾用户 （预览） 加入组呼叫和会议|允许应用程序以匿名方式加入您的组织，没有已登录的用户组呼叫和计划的会议。  将以来宾身份加入会议租户中加入应用程序。|
|Calls.AccessMedia.All|访问呼叫作为应用程序 (preview) 中的媒体流|允许应用程序以获取对媒体流进行通话，已登录的用户的情况下直接访问。|
|OnlineMeetings.Read.All|读取联机会议详细信息 （预览）|允许应用程序读取登录用户的情况下在组织中的联机会议详细信息。|

## <a name="schedule"></a>计划

接下来，安排团队会议视频互操作的坐标。 启用的用户可以安排通过团队会议：
- [会议外接程序 Outlook 的团队](teams-add-in-for-outlook.md)
- 桌面和移动的团队客户端


## <a name="join"></a>Join

您可以按以下方式与 VTC 设备加入团队会议：
 
- IVR （互动语音响应）
    - 您可以使用 tenantkey@domain 的合作伙伴的 IVR 拨入。 
    - 伙伴 IVR 中后，将提示您输入 VTC conferenceId，其中将然后将您连接到团队会议。
- 直接拨号
    - 可以不使用 tenantkey 的完整字符串的直拨功能与合作伙伴的 IVR 交互直接拨入团队会议。VTC ConferenceId@domain。
- 一站式拨号
    - 如果您有集成的团队会议室，您可以使用 （而无需键入任何拨号串） 由您的合作伙伴提供的一站式拨号功能。

最后，使用与团队用户参加会议使用音频、 视频以及内容共享。 