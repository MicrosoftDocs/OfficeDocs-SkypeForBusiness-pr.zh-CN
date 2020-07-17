---
title: 团队语音 Contoso 个案研究
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: 多国公司的团队语音案例研究
appliesto:
- Microsoft Teams
ms.openlocfilehash: f58f3518202fd836ff962374e8f3b3a00ab71817
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/18/2020
ms.locfileid: "44785983"
---
# <a name="contoso-case-study-audio-conferencing"></a><span data-ttu-id="75800-103">Contoso 案例研究：音频会议</span><span class="sxs-lookup"><span data-stu-id="75800-103">Contoso case study: Audio Conferencing</span></span>

<span data-ttu-id="75800-104">若要了解音频会议的 &mdash; 内容、it 成本、可用性和工作原理， &mdash; Contoso[在 Office 365 中查看音频会议](deploy-audio-conferencing-teams-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="75800-104">To gain an understanding of audio conferencing&mdash;what it is, what it costs, availability, and how it works&mdash;Contoso reviewed [Audio Conferencing in Office 365](deploy-audio-conferencing-teams-landing-page.md).</span></span> 

## <a name="overview"></a><span data-ttu-id="75800-105">概述</span><span class="sxs-lookup"><span data-stu-id="75800-105">Overview</span></span> 

<span data-ttu-id="75800-106">对于音频会议，Contoso 使用了组织内部和外部的电话号码。</span><span class="sxs-lookup"><span data-stu-id="75800-106">For audio conferencing, Contoso used phone numbers that are well known within the organization as well as externally.</span></span> <span data-ttu-id="75800-107">由于 Contoso 希望在可能的情况下保留这些号码，他们已查看有关将专用电话号码和共享电话号码分配给音频会议桥的信息。</span><span class="sxs-lookup"><span data-stu-id="75800-107">Because Contoso wanted to maintain these numbers where possible, they reviewed the information on assigning dedicated and shared phone numbers to the audio conferencing bridge.</span></span> 

<span data-ttu-id="75800-108">根据其研究，Contoso 做出以下决策：</span><span class="sxs-lookup"><span data-stu-id="75800-108">Based on their research, Contoso made the following decisions:</span></span> 

- <span data-ttu-id="75800-109">只有定期托管音频会议呼叫的一段人口才会收到音频会议许可证。</span><span class="sxs-lookup"><span data-stu-id="75800-109">Only a segment of the population that regularly host audio conferencing calls would receive Audio Conferencing licenses.</span></span> 

- <span data-ttu-id="75800-110">Contoso 将使用专用电话号码，并将其现有号码与音频会议配合使用。</span><span class="sxs-lookup"><span data-stu-id="75800-110">Contoso would use dedicated phone numbers and port their existing numbers for use with Audio Conferencing.</span></span>   

<span data-ttu-id="75800-111">由于 Contoso 用户使用 Skype for Business，并且所有用户的邮箱处于联机状态，因此许多用户已安排了现有会议。</span><span class="sxs-lookup"><span data-stu-id="75800-111">Because Contoso users were using Skype for Business and all users' mailboxes reside online, many users have existing meetings scheduled.</span></span> <span data-ttu-id="75800-112">Contoso[使用会议迁移服务（MMS）](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)进行阅读，了解当用户将最终用户更改为 TeamsOnly 模式时，将自动为 Contoso 更新现有会议。</span><span class="sxs-lookup"><span data-stu-id="75800-112">Contoso read [Using the Meeting Migration Service (MMS)](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) to learn that existing meetings are updated automatically for Contoso when they change the end user to TeamsOnly mode.</span></span>  


## <a name="configuration"></a><span data-ttu-id="75800-113">配置</span><span class="sxs-lookup"><span data-stu-id="75800-113">Configuration</span></span>

<span data-ttu-id="75800-114">与音频会议关联的电话号码称为电话系统中的服务号码。</span><span class="sxs-lookup"><span data-stu-id="75800-114">Phone numbers that are associated with audio conferencing are referred to as service numbers within Phone System.</span></span> 

- <span data-ttu-id="75800-115">对于使用呼叫计划的位置，要将其电话运营商的现有电话号码移植到 Office 365，Contoso 按照[获取服务电话号码](getting-service-phone-numbers.md)中的步骤进行操作。</span><span class="sxs-lookup"><span data-stu-id="75800-115">For locations using Calling Plans, to port their existing phone numbers from their phone carrier to Office 365, Contoso followed the steps in [Getting service phone numbers](getting-service-phone-numbers.md).</span></span>

- <span data-ttu-id="75800-116">要将音频会议许可证分配给技术试验中的最终用户，Contoso 管理员按照[管理您的组织的音频会议设置](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md)中的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="75800-116">To assign the Audio Conferencing license to the end user in the technical pilot, the Contoso administrator followed the steps in [Manage the Audio Conferencing settings for your organization](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md).</span></span> 

- <span data-ttu-id="75800-117">对于商业试点和迁移，Contoso 使用基于组的许可，方法是按照在[Azure Active Directory 中按组成员身份将许可证分配给用户](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)的步骤进行操作。</span><span class="sxs-lookup"><span data-stu-id="75800-117">For the business pilot and migration, Contoso used group-based licensing by following the steps in [Assign licenses to users by group membership in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>  

 

 