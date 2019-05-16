---
title: AppLocker 应用程序控制策略中的 Microsoft 团队
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: rafarhi
search.appverid: MET150
description: 了解如何启用 AppLocker 应用程序控制策略的团队桌面客户端应用程序。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 04379cad0ab224915a02475b010f908d486284cc
ms.sourcegitcommit: 85b135cf622c9e9eb1857ef953bc618dc2cdb51e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "34063204"
---
# <a name="applocker-application-control-policies-in-microsoft-teams"></a><span data-ttu-id="189a0-103">AppLocker 应用程序控制策略中的 Microsoft 团队</span><span class="sxs-lookup"><span data-stu-id="189a0-103">AppLocker application control policies in Microsoft Teams</span></span>

<span data-ttu-id="189a0-104">本文介绍如何启用团队桌面客户端应用程序与 AppLocker 应用程序控制策略。</span><span class="sxs-lookup"><span data-stu-id="189a0-104">This article explains how to enable the Teams desktop client app with AppLocker application control policies.</span></span> <span data-ttu-id="189a0-105">利用 AppLocker 旨在通过非管理员用户限制程序和脚本执行。</span><span class="sxs-lookup"><span data-stu-id="189a0-105">Use of AppLocker is designed to restrict program and script execution by non-administrative users.</span></span> <span data-ttu-id="189a0-106">有关详细信息和 AppLocker 指南，请参阅[AppLocker 是什么？](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker)。</span><span class="sxs-lookup"><span data-stu-id="189a0-106">For more information and guidance on AppLocker, see [What is AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker).</span></span>

<span data-ttu-id="189a0-107">启用与 AppLocker 团队的过程需要创建的基于 AppLocker 添加到白名单策略。</span><span class="sxs-lookup"><span data-stu-id="189a0-107">The process for enabling Teams with AppLocker requires the creation of AppLocker-based whitelisting policies.</span></span> <span data-ttu-id="189a0-108">使用组策略管理软件和/或 AppLocker 使用 Windows PowerShell cmdlet 创建策略 （请参阅[AppLocker 技术参考](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)（英文） 的详细信息）。</span><span class="sxs-lookup"><span data-stu-id="189a0-108">Policies are created with Group Policy management software and/or the use of Windows PowerShell cmdlets for AppLocker (see the [AppLocker technical reference](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) for more information).</span></span> <span data-ttu-id="189a0-109">AppLocker 策略以 XML 格式保存，并且可以使用任何文本编辑器或 XML 编辑器进行编辑。</span><span class="sxs-lookup"><span data-stu-id="189a0-109">The AppLocker policy is saved in XML format and can be edited with any text or XML editor.</span></span>

## <a name="teams-whitelisting-with-applocker"></a><span data-ttu-id="189a0-110">与 AppLocker 团队白</span><span class="sxs-lookup"><span data-stu-id="189a0-110">Teams whitelisting with AppLocker</span></span>

<span data-ttu-id="189a0-111">AppLocker 规则均分成各种规则的集合。</span><span class="sxs-lookup"><span data-stu-id="189a0-111">AppLocker rules are organized into collections of rules.</span></span> <span data-ttu-id="189a0-112">AppLocker 规则适用于目标应用程序，它们是组成 AppLocker 策略的组件。</span><span class="sxs-lookup"><span data-stu-id="189a0-112">AppLocker rules apply to the targeted app, and they are the components that make up the AppLocker policy.</span></span>  

<span data-ttu-id="189a0-113">向白名单工作组，我们建议您使用[publisher 条件规则](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker)，因为所有团队应用程序文件经过数字都签名。</span><span class="sxs-lookup"><span data-stu-id="189a0-113">To whitelist Teams, we recommend that you use the [publisher condition rules](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) since all Teams app files are digitally signed.</span></span>
  
<span data-ttu-id="189a0-114">我们不建议使用路径规则，因为团队安装目录是用户可写。</span><span class="sxs-lookup"><span data-stu-id="189a0-114">We don't recommend the use of path rules because the Teams installation directory is user-writable.</span></span> <span data-ttu-id="189a0-115">由于这些规则将具有要更新每次更新团队客户端应用程序，我们还不建议使用哈希规则。</span><span class="sxs-lookup"><span data-stu-id="189a0-115">We also don't recommend the use of hash rules because the rules would have to be updated each time the Teams client app is updated.</span></span>

<span data-ttu-id="189a0-116">由于团队桌面可执行文件经过数字签名，publisher 条件标识基于它的数字签名和嵌入的版本属性的应用程序文件。</span><span class="sxs-lookup"><span data-stu-id="189a0-116">Since Teams desktop executable files are digitally signed, the publisher condition identifies an app file based on its digital signature and embedded version attributes.</span></span> <span data-ttu-id="189a0-117">数字签名包含有关创建应用程序文件 （发行商） 的公司的信息。</span><span class="sxs-lookup"><span data-stu-id="189a0-117">The digital signature contains information about the company that created the app file (the publisher).</span></span> <span data-ttu-id="189a0-118">版本信息，可获取从二进制资源，包括该文件的一部分的产品和应用程序文件的版本号的名称。</span><span class="sxs-lookup"><span data-stu-id="189a0-118">The version information, which is obtained from the binary resource, includes the name of the product that the file is part of and the version number of the application file.</span></span>

### <a name="example-of-publisher-condition-rules"></a><span data-ttu-id="189a0-119">Publisher 条件规则的示例</span><span class="sxs-lookup"><span data-stu-id="189a0-119">Example of publisher condition rules</span></span>

<span data-ttu-id="189a0-120">团队 （所有文件，所有版本） 的客户端将应用程序：</span><span class="sxs-lookup"><span data-stu-id="189a0-120">For the Teams client app (all files, all versions):</span></span>

```
Publisher: O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US
Product name: MICROSOFT TEAMS
```

## <a name="related-topics"></a><span data-ttu-id="189a0-121">相关主题</span><span class="sxs-lookup"><span data-stu-id="189a0-121">Related topics</span></span>
<span data-ttu-id="189a0-122">[什么是 AppLocker？](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker)
 [AppLocker 技术参考](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)</span><span class="sxs-lookup"><span data-stu-id="189a0-122">[What is AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker)
[AppLocker technical reference](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)</span></span>