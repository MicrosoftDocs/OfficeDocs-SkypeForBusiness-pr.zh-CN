---
title: Microsoft 团队中的应用程序控制策略 AppLocker
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: rafarhi
search.appverid: MET150
description: 了解如何启用 AppLocker 应用程序控制策略的团队桌面客户端应用程序。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8d87eb5328f5200479f719dc22d9244c46af8944
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244938"
---
# <a name="applocker-application-control-policies-in-microsoft-teams"></a><span data-ttu-id="34d23-103">Microsoft 团队中的应用程序控制策略 AppLocker</span><span class="sxs-lookup"><span data-stu-id="34d23-103">AppLocker application control policies in Microsoft Teams</span></span>

<span data-ttu-id="34d23-104">本文介绍如何启用 AppLocker 应用程序控制策略的团队桌面客户端应用。</span><span class="sxs-lookup"><span data-stu-id="34d23-104">This article explains how to enable the Teams desktop client app with AppLocker application control policies.</span></span> <span data-ttu-id="34d23-105">使用 AppLocker 旨在限制非管理用户执行的程序和脚本执行。</span><span class="sxs-lookup"><span data-stu-id="34d23-105">Use of AppLocker is designed to restrict program and script execution by non-administrative users.</span></span> <span data-ttu-id="34d23-106">有关 AppLocker 的详细信息和指南, 请参阅[什么是 applocker？](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker)。</span><span class="sxs-lookup"><span data-stu-id="34d23-106">For more information and guidance on AppLocker, see [What is AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker).</span></span>

<span data-ttu-id="34d23-107">启用具有 AppLocker 的团队的过程需要创建基于 AppLocker 的 whitelisting 策略。</span><span class="sxs-lookup"><span data-stu-id="34d23-107">The process for enabling Teams with AppLocker requires the creation of AppLocker-based whitelisting policies.</span></span> <span data-ttu-id="34d23-108">使用组策略管理软件和/或用于 AppLocker 的 Windows PowerShell cmdlet 创建策略 (有关详细信息, 请参阅[AppLocker 技术参考](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference))。</span><span class="sxs-lookup"><span data-stu-id="34d23-108">Policies are created with Group Policy management software and/or the use of Windows PowerShell cmdlets for AppLocker (see the [AppLocker technical reference](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) for more information).</span></span> <span data-ttu-id="34d23-109">AppLocker 策略以 XML 格式保存, 并且可以通过任何文本或 XML 编辑器进行编辑。</span><span class="sxs-lookup"><span data-stu-id="34d23-109">The AppLocker policy is saved in XML format and can be edited with any text or XML editor.</span></span>

## <a name="teams-whitelisting-with-applocker"></a><span data-ttu-id="34d23-110">与 AppLocker whitelisting 的团队</span><span class="sxs-lookup"><span data-stu-id="34d23-110">Teams whitelisting with AppLocker</span></span>

<span data-ttu-id="34d23-111">AppLocker 规则组织为规则集合。</span><span class="sxs-lookup"><span data-stu-id="34d23-111">AppLocker rules are organized into collections of rules.</span></span> <span data-ttu-id="34d23-112">AppLocker 规则适用于目标应用, 它们是构成 AppLocker 策略的组件。</span><span class="sxs-lookup"><span data-stu-id="34d23-112">AppLocker rules apply to the targeted app, and they are the components that make up the AppLocker policy.</span></span>  

<span data-ttu-id="34d23-113">对于白名单团队, 建议使用[发布者条件规则](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker), 因为所有团队应用文件都经过数字签名。</span><span class="sxs-lookup"><span data-stu-id="34d23-113">To whitelist Teams, we recommend that you use the [publisher condition rules](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) since all Teams app files are digitally signed.</span></span>
  
<span data-ttu-id="34d23-114">我们不建议使用路径规则, 因为团队安装目录可由用户写入。</span><span class="sxs-lookup"><span data-stu-id="34d23-114">We don't recommend the use of path rules because the Teams installation directory is user-writable.</span></span> <span data-ttu-id="34d23-115">我们也不建议使用哈希规则, 因为每次更新团队客户端应用时, 都必须更新规则。</span><span class="sxs-lookup"><span data-stu-id="34d23-115">We also don't recommend the use of hash rules because the rules would have to be updated each time the Teams client app is updated.</span></span>

<span data-ttu-id="34d23-116">由于团队桌面可执行文件经过数字签名, 发布者条件基于其数字签名和嵌入的版本属性来标识应用文件。</span><span class="sxs-lookup"><span data-stu-id="34d23-116">Since Teams desktop executable files are digitally signed, the publisher condition identifies an app file based on its digital signature and embedded version attributes.</span></span> <span data-ttu-id="34d23-117">数字签名包含有关创建应用文件 (发布者) 的公司的信息。</span><span class="sxs-lookup"><span data-stu-id="34d23-117">The digital signature contains information about the company that created the app file (the publisher).</span></span> <span data-ttu-id="34d23-118">从二进制资源获取的版本信息, 包括文件所属的产品的名称以及应用程序文件的版本号。</span><span class="sxs-lookup"><span data-stu-id="34d23-118">The version information, which is obtained from the binary resource, includes the name of the product that the file is part of and the version number of the application file.</span></span>

### <a name="example-of-publisher-condition-rules"></a><span data-ttu-id="34d23-119">Publisher 条件规则的示例</span><span class="sxs-lookup"><span data-stu-id="34d23-119">Example of publisher condition rules</span></span>

<span data-ttu-id="34d23-120">对于团队客户端应用 (所有文件, 所有版本):</span><span class="sxs-lookup"><span data-stu-id="34d23-120">For the Teams client app (all files, all versions):</span></span>

```
Publisher: O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US
Product name: MICROSOFT TEAMS
```

## <a name="related-topics"></a><span data-ttu-id="34d23-121">相关主题</span><span class="sxs-lookup"><span data-stu-id="34d23-121">Related topics</span></span>
<span data-ttu-id="34d23-122">[什么是 AppLocker？](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker)
 [AppLocker 技术参考](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)</span><span class="sxs-lookup"><span data-stu-id="34d23-122">[What is AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker)
[AppLocker technical reference](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)</span></span>