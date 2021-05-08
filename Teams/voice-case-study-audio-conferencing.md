---
title: Teams Contoso 案例研究
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
description: Teams多语言公司语音案例研究
appliesto:
- Microsoft Teams
ms.openlocfilehash: 085c9994bc2522d1ab56abc1670113e22d35f642
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121300"
---
# <a name="contoso-case-study-audio-conferencing"></a><span data-ttu-id="c7692-103">Contoso 案例研究：音频会议</span><span class="sxs-lookup"><span data-stu-id="c7692-103">Contoso case study: Audio Conferencing</span></span>

<span data-ttu-id="c7692-104">为了了解音频会议是什么、它的成本、可用性及其工作原理，Contoso 在 Office 365 中查看了 &mdash; &mdash; 音频[Office 365。](deploy-audio-conferencing-teams-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="c7692-104">To gain an understanding of audio conferencing&mdash;what it is, what it costs, availability, and how it works&mdash;Contoso reviewed [Audio Conferencing in Office 365](deploy-audio-conferencing-teams-landing-page.md).</span></span> 

## <a name="overview"></a><span data-ttu-id="c7692-105">概述</span><span class="sxs-lookup"><span data-stu-id="c7692-105">Overview</span></span> 

<span data-ttu-id="c7692-106">对于音频会议，Contoso 使用组织内部以及外部已知的电话号码。</span><span class="sxs-lookup"><span data-stu-id="c7692-106">For audio conferencing, Contoso used phone numbers that are well known within the organization as well as externally.</span></span> <span data-ttu-id="c7692-107">由于 Contoso 希望尽可能保留这些号码，因此他们查看了有关向音频会议网桥分配专用和共享电话号码的信息。</span><span class="sxs-lookup"><span data-stu-id="c7692-107">Because Contoso wanted to maintain these numbers where possible, they reviewed the information on assigning dedicated and shared phone numbers to the audio conferencing bridge.</span></span> 

<span data-ttu-id="c7692-108">Contoso 根据他们的研究做出以下决策：</span><span class="sxs-lookup"><span data-stu-id="c7692-108">Based on their research, Contoso made the following decisions:</span></span> 

- <span data-ttu-id="c7692-109">只有定期主持音频会议呼叫的一部分用户会收到音频会议许可证。</span><span class="sxs-lookup"><span data-stu-id="c7692-109">Only a segment of the population that regularly host audio conferencing calls would receive Audio Conferencing licenses.</span></span> 

- <span data-ttu-id="c7692-110">Contoso 将使用专用电话号码并移植其现有号码以用于音频会议。</span><span class="sxs-lookup"><span data-stu-id="c7692-110">Contoso would use dedicated phone numbers and port their existing numbers for use with Audio Conferencing.</span></span>   

<span data-ttu-id="c7692-111">由于 Contoso 用户使用 Skype for Business并且所有用户的邮箱都驻留在联机状态，因此许多用户已计划现有会议。</span><span class="sxs-lookup"><span data-stu-id="c7692-111">Because Contoso users were using Skype for Business and all users' mailboxes reside online, many users have existing meetings scheduled.</span></span> <span data-ttu-id="c7692-112">Contoso 阅读使用会议迁移 [服务 (MMS ](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json)) 了解当 Contoso 将最终用户更改为 TeamsOnly 模式时，会自动更新现有会议。</span><span class="sxs-lookup"><span data-stu-id="c7692-112">Contoso read [Using the Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json) to learn that existing meetings are updated automatically for Contoso when they change the end user to TeamsOnly mode.</span></span>  


## <a name="configuration"></a><span data-ttu-id="c7692-113">配置</span><span class="sxs-lookup"><span data-stu-id="c7692-113">Configuration</span></span>

<span data-ttu-id="c7692-114">电话音频会议关联的号码称为会议内电话系统。</span><span class="sxs-lookup"><span data-stu-id="c7692-114">Phone numbers that are associated with audio conferencing are referred to as service numbers within Phone System.</span></span> 

- <span data-ttu-id="c7692-115">对于使用呼叫计划的位置，为了将现有电话号码从电话运营商移植到 Office 365，Contoso 按照获取服务电话号码[中的步骤操作](getting-service-phone-numbers.md)。</span><span class="sxs-lookup"><span data-stu-id="c7692-115">For locations using Calling Plans, to port their existing phone numbers from their phone carrier to Office 365, Contoso followed the steps in [Getting service phone numbers](getting-service-phone-numbers.md).</span></span>

- <span data-ttu-id="c7692-116">为了在技术试点中向最终用户分配音频会议许可证，Contoso 管理员按照管理组织的音频会议设置中的 [步骤操作](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="c7692-116">To assign the Audio Conferencing license to the end user in the technical pilot, the Contoso administrator followed the steps in [Manage the Audio Conferencing settings for your organization](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md).</span></span> 

- <span data-ttu-id="c7692-117">对于业务试点和迁移，Contoso 按照在 中按组成员身份向用户分配许可证中的步骤使用[基于](/azure/active-directory/users-groups-roles/licensing-groups-assign)Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="c7692-117">For the business pilot and migration, Contoso used group-based licensing by following the steps in [Assign licenses to users by group membership in Azure Active Directory](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>  

 

