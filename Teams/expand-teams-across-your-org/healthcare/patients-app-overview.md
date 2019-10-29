---
title: '适用于团队管理员的患者应用 '
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
MS.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto: Microsoft Teams
ms.reviewer: anach
description: 适用于团队管理员的患者应用
ms.openlocfilehash: 1ed3efc1aa5a6d3eb4554fca6ee3bd7cfe57f4c0
ms.sourcegitcommit: 25b6bf2c3050390cd668d2495ffcf31c44d0ff62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/28/2019
ms.locfileid: "37749554"
---
# <a name="patients-app-overview"></a><span data-ttu-id="8f136-103">患者应用概述</span><span class="sxs-lookup"><span data-stu-id="8f136-103">Patients app overview</span></span>

<span data-ttu-id="8f136-104">患者应用程序是适用于所有团队用户的 Microsoft 团队应用商店应用程序。</span><span class="sxs-lookup"><span data-stu-id="8f136-104">The Patients application is a Microsoft Teams store app available to all Teams users.</span></span> <span data-ttu-id="8f136-105">该应用支持由临床工作者（如护士、医生、社会工作者）组成的患者护理团队，可策展和查看患者的列表，这些方案包括从倒圆角和 interdisciplinary 团队会议到常规患者监控。</span><span class="sxs-lookup"><span data-stu-id="8f136-105">The app enables patient care teams consisting of clinical workers (e.g. Nurses, physicians, social workers) can curate and review lists of patients for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span>   

<span data-ttu-id="8f136-106">应用具有两种模式：</span><span class="sxs-lookup"><span data-stu-id="8f136-106">The app has two modes:</span></span> 

- <span data-ttu-id="8f136-107">通过 FHIR 连接到 EMRs 的 EMR 连接模式。</span><span class="sxs-lookup"><span data-stu-id="8f136-107">The EMR Connected mode that connects to EMRs through FHIR.</span></span> <span data-ttu-id="8f136-108">EMR 连接模式应用保留在私人预览版中，并且感兴趣的客户或管理员可能会通过在 teamsforhealthcare@service.microsoft.com 中删除 Microsoft 电子邮件，获取有关 Office 365 租户的信息，请求对应用的访问权限。</span><span class="sxs-lookup"><span data-stu-id="8f136-108">The EMR Connected mode app stays in private preview and interested customers or admins may request access to the app by dropping Microsoft an email at teamsforhealthcare@service.microsoft.com with information about their Office 365 tenant.</span></span> 
- <span data-ttu-id="8f136-109">允许护理团队手动添加/添加患者信息的手动模式。</span><span class="sxs-lookup"><span data-stu-id="8f136-109">The manual mode that enables care teams to manually add/bring in patient information.</span></span> <span data-ttu-id="8f136-110">应用程序位于团队应用商店中，供最终用户在默认情况下下载并处于公共预览版中。</span><span class="sxs-lookup"><span data-stu-id="8f136-110">The application is available in the Teams app store for end users to download by default and is in public preview.</span></span> <span data-ttu-id="8f136-111">使用[Microsoft 团队中的应用设置策略](../../teams-app-setup-policies.md)，可以将应用限制到特定部分的用户</span><span class="sxs-lookup"><span data-stu-id="8f136-111">The app can be restricted to certain sections of users using [app setup policies in Microsoft Teams](../../teams-app-setup-policies.md)</span></span>



## <a name="usage-example"></a><span data-ttu-id="8f136-112">用法示例</span><span class="sxs-lookup"><span data-stu-id="8f136-112">Usage example</span></span>

<span data-ttu-id="8f136-113">在医疗 wards 中每个班次的舍入期内，临床医生在 nursing 工作站上进行收集，以便在拖动中讨论患者的最新更新。</span><span class="sxs-lookup"><span data-stu-id="8f136-113">During rounding sessions on every shift in medical wards, clinicians gather at the nursing station to discuss the latest updates on the progress with patients in the ward.</span></span>  <span data-ttu-id="8f136-114">他们突出显示关键指标（不一定是医疗或对患者病历的明确指标），并确保患者在合适的 glide 路径上，以根据其诊断而放电。</span><span class="sxs-lookup"><span data-stu-id="8f136-114">They highlight the key critical metrics (not necessarily medical or that its explicit on the patients’ medical records) and ensure the patient is on the right glide path to discharge based on their diagnosis.</span></span> <span data-ttu-id="8f136-115">为了围绕这些患者，"费用" 护士在一个团队中设置患者应用，其中添加了所有临床医生，并将患者添加到患者列表。</span><span class="sxs-lookup"><span data-stu-id="8f136-115">In order to round around these patients, the charge nurse sets up the patient app in a team where all the clinicians are added and adds patients to a patient list.</span></span> <span data-ttu-id="8f136-116">在舍入期间，护士和其他护理 givers 在其移动设备上的患者 access Microsoft 团队和患者应用，并在其设备上更新相关的患者信息，并且在护理团队中的其他人可以看到这些更新和笔记以及保持同步。一天两次，在班次的开始和结束时间，他们还拥有多 displicinary 团队会议，让他们能够通过患者列表，并使用患者应用在大型显示屏上使用患者应用共享有关每个患者的信息。</span><span class="sxs-lookup"><span data-stu-id="8f136-116">During the rounds, the nurses and the other care givers for the patient access Microsoft Teams and the Patients app on their mobile devices and update relevant patient information on their device and then everyone else in the care team can see those updates and notes and stay in sync. Twice a day, at the start and end of a shift, they also have multi-displicinary team meetings to go over the patient list and use the Patients App to ground themselves and share information about each patient using the Patients app on a large display screen.</span></span> <span data-ttu-id="8f136-117">通常情况下，某些临床医生可能还会远程拨入这些团队会议，并且仍是讨论的一部分。</span><span class="sxs-lookup"><span data-stu-id="8f136-117">Often times, certain clinicians may also dial in to these Teams meetings remotely and still be part of the discussion.</span></span> 

## <a name="configure-patients-app"></a><span data-ttu-id="8f136-118">配置患者应用</span><span class="sxs-lookup"><span data-stu-id="8f136-118">Configure Patients app</span></span>

<span data-ttu-id="8f136-119">有关如何准备您的环境以使用 EMR 模式患者应用的信息，请参阅将[电子医疗保健记录集成到 Microsoft 团队](patients-app.md)。</span><span class="sxs-lookup"><span data-stu-id="8f136-119">For information on how to prepare your environment to use the EMR mode Patients app, see [Integrating Electronic Healthcare Records into Microsoft Teams](patients-app.md).</span></span> <span data-ttu-id="8f136-120">你还需要查看[Microsoft 团队中的 "管理应用设置策略"](../../teams-app-setup-policies.md)以为你的组织启用患者应用。</span><span class="sxs-lookup"><span data-stu-id="8f136-120">You will also need to see [Manage app setup policies in Microsoft Teams](../../teams-app-setup-policies.md) to enable Patients app for your organization.</span></span>

<!-- For information on how your end users can access and install the Patients App to a team that they own or manage, you will need to see [End user documentation for the Patients App]() -->

<!-- add link out to client doc, doesn't seem to be available yet, Grant is finalizing -->

## <a name="related-topics"></a><span data-ttu-id="8f136-121">相关主题</span><span class="sxs-lookup"><span data-stu-id="8f136-121">Related topics</span></span>

[<span data-ttu-id="8f136-122">将电子医疗记录集成到 Microsoft Teams 中</span><span class="sxs-lookup"><span data-stu-id="8f136-122">Integrating Electronic Healthcare Records into Microsoft Teams</span></span>](patients-app.md)
