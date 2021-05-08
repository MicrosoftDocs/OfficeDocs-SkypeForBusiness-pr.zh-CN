---
title: AppLocker 控制策略
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: rafarhi
search.appverid: MET150
f1.keywords:
- NOCSH
description: 了解如何使用 AppLocker Teams策略启用桌面客户端应用程序。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d6e6040956ba5e5469076b4fbbab337f58268c68
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120844"
---
# <a name="applocker-application-control-policies-in-microsoft-teams"></a><span data-ttu-id="d02d4-103">应用中的 AppLocker 应用程序控制Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d02d4-103">AppLocker application control policies in Microsoft Teams</span></span>

<span data-ttu-id="d02d4-104">本文介绍如何使用 AppLocker Teams策略启用桌面客户端应用。</span><span class="sxs-lookup"><span data-stu-id="d02d4-104">This article explains how to enable the Teams desktop client app with AppLocker application control policies.</span></span> <span data-ttu-id="d02d4-105">AppLocker 的使用旨在限制非管理用户的程序和脚本执行。</span><span class="sxs-lookup"><span data-stu-id="d02d4-105">Use of AppLocker is designed to restrict program and script execution by non-administrative users.</span></span> <span data-ttu-id="d02d4-106">有关 AppLocker 的信息和指南，请参阅[什么是 AppLocker？。](/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker)</span><span class="sxs-lookup"><span data-stu-id="d02d4-106">For more information and guidance on AppLocker, see [What is AppLocker?](/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker).</span></span>

<span data-ttu-id="d02d4-107">使用 AppLocker Teams应用的过程需要创建基于 AppLocker 的允许列表策略。</span><span class="sxs-lookup"><span data-stu-id="d02d4-107">The process for enabling Teams with AppLocker requires the creation of AppLocker-based allow listing policies.</span></span> <span data-ttu-id="d02d4-108">策略是使用组策略管理软件和/或使用 Windows PowerShell cmdlet 为 AppLocker 创建的 (请参阅[AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)技术参考，了解) 。</span><span class="sxs-lookup"><span data-stu-id="d02d4-108">Policies are created with Group Policy management software and/or the use of Windows PowerShell cmdlets for AppLocker (see the [AppLocker technical reference](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) for more information).</span></span> <span data-ttu-id="d02d4-109">AppLocker 策略以 XML 格式保存，可以使用任何文本或 XML 编辑器进行编辑。</span><span class="sxs-lookup"><span data-stu-id="d02d4-109">The AppLocker policy is saved in XML format and can be edited with any text or XML editor.</span></span>

## <a name="teams-allow-list-with-applocker"></a><span data-ttu-id="d02d4-110">Teams AppLocker 创建允许列表</span><span class="sxs-lookup"><span data-stu-id="d02d4-110">Teams allow list with AppLocker</span></span>

<span data-ttu-id="d02d4-111">AppLocker 规则组织成规则集合。</span><span class="sxs-lookup"><span data-stu-id="d02d4-111">AppLocker rules are organized into collections of rules.</span></span> <span data-ttu-id="d02d4-112">AppLocker 规则适用于目标应用，它们是构成 AppLocker 策略的组件。</span><span class="sxs-lookup"><span data-stu-id="d02d4-112">AppLocker rules apply to the targeted app, and they are the components that make up the AppLocker policy.</span></span>  

<span data-ttu-id="d02d4-113">若要Teams，建议使用发布者条件规则，因为Teams文件都是数字签名[](/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker)的。</span><span class="sxs-lookup"><span data-stu-id="d02d4-113">To allow Teams, we recommend that you use the [publisher condition rules](/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) since all Teams app files are digitally signed.</span></span>
  
<span data-ttu-id="d02d4-114">不建议使用路径规则，因为Teams目录是用户可写的。</span><span class="sxs-lookup"><span data-stu-id="d02d4-114">We don't recommend the use of path rules because the Teams installation directory is user-writable.</span></span> <span data-ttu-id="d02d4-115">我们不建议使用哈希规则，因为每次更新客户端应用时，Teams更新规则。</span><span class="sxs-lookup"><span data-stu-id="d02d4-115">We also don't recommend the use of hash rules because the rules would have to be updated each time the Teams client app is updated.</span></span>

<span data-ttu-id="d02d4-116">由于Teams可执行文件是数字签名的，因此发布者条件会基于应用的数字签名和嵌入式版本属性来标识应用文件。</span><span class="sxs-lookup"><span data-stu-id="d02d4-116">Since Teams desktop executable files are digitally signed, the publisher condition identifies an app file based on its digital signature and embedded version attributes.</span></span> <span data-ttu-id="d02d4-117">数字签名包含有关创建应用文件的公司的信息， (发布者) 。</span><span class="sxs-lookup"><span data-stu-id="d02d4-117">The digital signature contains information about the company that created the app file (the publisher).</span></span> <span data-ttu-id="d02d4-118">从二进制资源获取的版本信息包括该文件所包含产品的名称和应用程序文件的版本号。</span><span class="sxs-lookup"><span data-stu-id="d02d4-118">The version information, which is obtained from the binary resource, includes the name of the product that the file is part of and the version number of the application file.</span></span>

### <a name="example-of-publisher-condition-rules"></a><span data-ttu-id="d02d4-119">发布者条件规则示例</span><span class="sxs-lookup"><span data-stu-id="d02d4-119">Example of publisher condition rules</span></span>

<span data-ttu-id="d02d4-120">对于Teams客户端应用 (文件，所有版本) 添加到 DLL 规则的可执行&规则：</span><span class="sxs-lookup"><span data-stu-id="d02d4-120">For the Teams client app (all files, all versions) add the following to the Executable Rules & DLL Rules:</span></span>

```console
Publisher: O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US
Product name: MICROSOFT TEAMS
Product name: MICROSOFT TEAMS UPDATE
```

## <a name="related-topics"></a><span data-ttu-id="d02d4-121">相关主题</span><span class="sxs-lookup"><span data-stu-id="d02d4-121">Related topics</span></span>
<span data-ttu-id="d02d4-122">[什么是 AppLocker？](/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker) 
[AppLocker 技术参考](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)</span><span class="sxs-lookup"><span data-stu-id="d02d4-122">[What is AppLocker?](/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker)
[AppLocker technical reference](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)</span></span>