---
title: Microsoft Teams for RealWear 客户端 ITAdmin 信息（预览版）
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Microsoft Teams for RealWear 客户端 ITAdmin 演练。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: e95440652111dbcd39b756ef942e7a974ef31de0
ms.sourcegitcommit: dc6108917392754d950cea47b92f871211bf4212
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/03/2020
ms.locfileid: "43131200"
---
# <a name="microsoft-teams-for-realwear"></a><span data-ttu-id="1cd50-103">Microsoft Teams for RealWear</span><span class="sxs-lookup"><span data-stu-id="1cd50-103">Microsoft Teams for RealWear</span></span>

> [!NOTE]
> <span data-ttu-id="1cd50-104">这是预览版或早期版本功能。</span><span class="sxs-lookup"><span data-stu-id="1cd50-104">This is a preview or early release feature.</span></span>

<span data-ttu-id="1cd50-105">本文介绍适用于 RealWear 头戴型可穿戴设备的 Microsoft Teams 客户端。</span><span class="sxs-lookup"><span data-stu-id="1cd50-105">This article covers the Microsoft Teams client for RealWear head-mounted wearables.</span></span> <span data-ttu-id="1cd50-106">使用 RealWear HMT-1 和 HMT-1Z1 的一线员工现在可通过在 Teams 上进行视频通话与远程专家进行协作。</span><span class="sxs-lookup"><span data-stu-id="1cd50-106">FirstLine Workers using RealWear HMT-1 and HMT-1Z1 can now collaborate with a remote expert using video calling on Teams.</span></span> <span data-ttu-id="1cd50-107">通过语音控制用户界面，RealWear 团队允许现场工作人员 100% 释放双手，同时在嘈杂和危险环境中了解态势。</span><span class="sxs-lookup"><span data-stu-id="1cd50-107">Through a voice-controlled user interface, Teams for RealWear allows field workers to remain 100% hands-free while maintaining situational awareness in loud and hazardous environments.</span></span> <span data-ttu-id="1cd50-108">通过实时显示所看到的情况，现场工作人员可以加快解决问题的时间，并降低高昂的停机风险。</span><span class="sxs-lookup"><span data-stu-id="1cd50-108">By showing what they see in real-time, field workers can accelerate the time to resolve issues and reduce the risk of an expensive downtime.</span></span>

## <a name="how-to-deploy-microsoft-teams-for-realwear"></a><span data-ttu-id="1cd50-109">如何部署 Microsoft Teams for RealWear</span><span class="sxs-lookup"><span data-stu-id="1cd50-109">How to deploy Microsoft Teams for RealWear</span></span>

<span data-ttu-id="1cd50-110">Microsoft Teams for RealWear 客户端目前处于公共预览版。</span><span class="sxs-lookup"><span data-stu-id="1cd50-110">Microsoft Teams client for RealWear is currently in Public Preview.</span></span> <span data-ttu-id="1cd50-111">若要参与此预览，需要执行以下条件：</span><span class="sxs-lookup"><span data-stu-id="1cd50-111">To participate in this preview, you will need the following:</span></span>

<span data-ttu-id="1cd50-112">RealWear 设备已更新到发布10.5.0 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="1cd50-112">RealWear devices updated to release 10.5.0 or above.</span></span> <span data-ttu-id="1cd50-113">有关更多信息，请参阅[此处](https://realwear.com/knowledge-center/configure-on-release-10/wireless-update/)。</span><span class="sxs-lookup"><span data-stu-id="1cd50-113">More information [here](https://realwear.com/knowledge-center/configure-on-release-10/wireless-update/).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1cd50-114">[点击这里](https://www.realwear.com/solutions/microsoft-teams/#C1)注册，以在 [RealWear Foresight](https://cloud.realwear.com/) 中访问 Teams for RealWear 客户端。</span><span class="sxs-lookup"><span data-stu-id="1cd50-114">Register [here](https://www.realwear.com/solutions/microsoft-teams/#C1) for access to Teams for RealWear client in [RealWear Foresight](https://cloud.realwear.com/).</span></span>

## <a name="required-licenses"></a><span data-ttu-id="1cd50-115">需要的许可证</span><span class="sxs-lookup"><span data-stu-id="1cd50-115">Required Licenses</span></span>

<span data-ttu-id="1cd50-116">Microsoft Teams 许可证是 Office 365 订阅的一部分。</span><span class="sxs-lookup"><span data-stu-id="1cd50-116">Microsoft Teams licenses are part of Office 365 subscriptions.</span></span> <span data-ttu-id="1cd50-117">使用 Teams for RealWear 不需要其他许可证。</span><span class="sxs-lookup"><span data-stu-id="1cd50-117">No additional licensing is required to use Teams for RealWear.</span></span> <span data-ttu-id="1cd50-118">有关获取 Teams 的详细信息，请参阅 [如何访问 Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)。</span><span class="sxs-lookup"><span data-stu-id="1cd50-118">For more information about getting Teams, check out [How do I get access to Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b).</span></span>

## <a name="managing-realwear-devices"></a><span data-ttu-id="1cd50-119">管理 RealWear 设备</span><span class="sxs-lookup"><span data-stu-id="1cd50-119">Managing RealWear devices</span></span>

### <a name="microsoft-endpoint-manager"></a><span data-ttu-id="1cd50-120">Microsoft 终结点管理器</span><span class="sxs-lookup"><span data-stu-id="1cd50-120">Microsoft Endpoint Manager</span></span>

<span data-ttu-id="1cd50-121">RealWear 设备可以使用 Android 设备管理员模式托管。</span><span class="sxs-lookup"><span data-stu-id="1cd50-121">RealWear devices can be managed using Android Device Administrator mode.</span></span> <span data-ttu-id="1cd50-122">由于当前未提供 Google Mobile Services （GMS），因此通过 Android 企业版管理支持受限。</span><span class="sxs-lookup"><span data-stu-id="1cd50-122">Support for management via Android Enterprise is limited, as the devices currently don't have Google Mobile Services (GMS) available.</span></span>

- <span data-ttu-id="1cd50-123">要了解有关在 Microsoft 终结点管理器上管理 RealWear 设备的详细信息，请参阅 [Intune 中的 Android 设备管理员注册](https://docs.microsoft.com/mem/intune/enrollment/android-enroll-device-administrator)。</span><span class="sxs-lookup"><span data-stu-id="1cd50-123">To learn more about managing RealWear devices on Microsoft Endpoint Manager, see [Android device administrator enrollment in Intune](https://docs.microsoft.com/mem/intune/enrollment/android-enroll-device-administrator).</span></span>
- <span data-ttu-id="1cd50-124">有关策略的更多详细信息，请参阅[如何在没有 Google 移动服务的环境中使用 Intune](https://docs.microsoft.com/mem/intune/apps/manage-without-gms)。</span><span class="sxs-lookup"><span data-stu-id="1cd50-124">For more details on policies, see [How to use Intune in environments without Google Mobile Services](https://docs.microsoft.com/mem/intune/apps/manage-without-gms).</span></span>

### <a name="third-party-enterprise-mobility-managers-emms"></a><span data-ttu-id="1cd50-125">第三方企业移动性管理器 (EMM)</span><span class="sxs-lookup"><span data-stu-id="1cd50-125">Third-party Enterprise Mobility Managers (EMMs)</span></span>

<span data-ttu-id="1cd50-126">第三方企业移动性管理器的指南，请参阅 [支持的企业移动性管理提供商](https://www.realwear.com/knowledge-center/configure-on-release-10/remote-from-a-web-browser/emm/)。</span><span class="sxs-lookup"><span data-stu-id="1cd50-126">For guidance on third-party EMMs, see [Supported Enterprise Mobility Management Providers](https://www.realwear.com/knowledge-center/configure-on-release-10/remote-from-a-web-browser/emm/).</span></span>

## <a name="end-user-content"></a><span data-ttu-id="1cd50-127">最终用户内容</span><span class="sxs-lookup"><span data-stu-id="1cd50-127">End-user content</span></span>

<span data-ttu-id="1cd50-128">有关最终用户的进一步观点，请参阅 [Microsoft Teams for RealWear](https://support.office.com/article/using-microsoft-teams-for-realwear-af20d232-d18c-476f-8031-843a4edccd5f)。</span><span class="sxs-lookup"><span data-stu-id="1cd50-128">For further reading on this from an end-user perspective, please check out [Using Microsoft Teams for RealWear](https://support.office.com/article/using-microsoft-teams-for-realwear-af20d232-d18c-476f-8031-843a4edccd5f).</span></span>
