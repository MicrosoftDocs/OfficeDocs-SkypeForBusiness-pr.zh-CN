---
title: 在 Microsoft Teams 中对内容进行电子数据展示调查
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/12/2018
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: anach
search.appverid: MET150
description: 了解你需要执行电子数据展示时（例如，你需要提交所有电子方式存储的信息用于法律程序时）要完成的事项。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 54ccb21e33c6acc1747023fc7c3eb174040d5746
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32233489"
---
<a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a><span data-ttu-id="610e5-103">在 Microsoft Teams 中对内容进行电子数据展示调查</span><span class="sxs-lookup"><span data-stu-id="610e5-103">Conduct an eDiscovery investigation of content in Microsoft Teams</span></span>
============================

<span data-ttu-id="610e5-104">大型企业通常公开给提交的所有以电子方式存储信息 (ESI) 的需求的高损失法律程序。</span><span class="sxs-lookup"><span data-stu-id="610e5-104">Large Enterprises are often exposed to high penalty legal proceedings that demand submission of all Electronically Stored Information (ESI).</span></span>

<span data-ttu-id="610e5-105">所有团队 1:1 或群聊都是通过记录到各个用户的邮箱，并且日记通过对组邮箱表示团队频道的所有邮件。</span><span class="sxs-lookup"><span data-stu-id="610e5-105">All Teams 1:1 or group chats are journaled through to the respective users’ mailboxes, and all channel messages are journaled through to the group mailbox representing the team.</span></span> <span data-ttu-id="610e5-106">SharePoint Online 和 OneDrive for Business 的电子数据展示功能的对象涵盖上载的文件。</span><span class="sxs-lookup"><span data-stu-id="610e5-106">Files uploaded are covered under the eDiscovery functionality for SharePoint Online and OneDrive for Business.</span></span>

1.  <span data-ttu-id="610e5-107">进行电子数据展示调查的 Microsoft 团队内容，请查看步骤 1 中[此](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da)链接。</span><span class="sxs-lookup"><span data-stu-id="610e5-107">To conduct an eDiscovery investigation with Microsoft Teams content, review step 1 in [this](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) link.</span></span>

2.  <span data-ttu-id="610e5-108">Microsoft 团队数据将显示为 IM 或对话 Excel 电子数据展示导出输出，并且可以装入。在 Outlook 中查看这些邮件 PST 发布导出。</span><span class="sxs-lookup"><span data-stu-id="610e5-108">Microsoft Teams data will appear as IM or Conversations in the Excel eDiscovery export output, and you can mount the .PST in Outlook to view those messages post export.</span></span>

    <span data-ttu-id="610e5-109">装载团队的 .PST 时，请注意，所有对话均保留在“对话历史记录”下的“团队聊天”文件夹中。</span><span class="sxs-lookup"><span data-stu-id="610e5-109">When mounting the .PST for the Team, note that all conversations are kept in the Team Chat folder under Conversation History.</span></span> <span data-ttu-id="610e5-110">消息的标题与团队和频道一致。</span><span class="sxs-lookup"><span data-stu-id="610e5-110">The title of the message aligns to Team and Channel.</span></span> <span data-ttu-id="610e5-111">如下图所示，你可以看到 Bob 在 Manufacturing Specs 团队的“Project 7”频道中发送的此消息。</span><span class="sxs-lookup"><span data-stu-id="610e5-111">From reviewing the image below, you can see this message from Bob who messaged the Project 7 channel of the Manufacturing Specs team.</span></span>

    ![在 Outlook 中的用户的邮箱中的团队聊天文件夹的屏幕截图](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

3.  <span data-ttu-id="610e5-113">要查看某个用户的邮箱中的私人聊天，也在“对话历史记录”下的“团队聊天”文件夹中找到它们。</span><span class="sxs-lookup"><span data-stu-id="610e5-113">To see private chats in a user’s Mailbox, they are also located inside the Team Chat folder under Conversation History.</span></span>

## <a name="ediscovery-of-guest-to-guest-chats"></a><span data-ttu-id="610e5-114">电子数据展示的来宾与访客聊天</span><span class="sxs-lookup"><span data-stu-id="610e5-114">eDiscovery of guest-to-guest chats</span></span>

<span data-ttu-id="610e5-115">没有邮箱来宾与访客聊天 （在其中没有主租户用户 1xN 聊天） 将编制索引，和结果是，将不会包含电子数据展示中。</span><span class="sxs-lookup"><span data-stu-id="610e5-115">Without a mailbox, guest-to-guest chats (1xN chats in which there are no home tenant users) would not be indexed, and as a result, would not be included in eDiscovery.</span></span> <span data-ttu-id="610e5-116">为了方便电子数据展示的来宾与访客聊天，基于云的邮箱创建 （或幻像邮箱） 是用于存储 1xN 数据。</span><span class="sxs-lookup"><span data-stu-id="610e5-116">To facilitate eDiscovery for guest-to-guest chats, a cloud-based mailbox (or phantom mailbox) is created to store the 1xN data.</span></span> <span data-ttu-id="610e5-117">团队聊天数据存储在基于云的邮箱后，会将其编制索引的电子数据展示和合规性内容的搜索。</span><span class="sxs-lookup"><span data-stu-id="610e5-117">After the Teams chat data is stored in the cloud-based mailbox, it is indexed for eDiscovery and compliance content search.</span></span>

<span data-ttu-id="610e5-118">下图显示了对在其中没有邮箱的来宾与访客聊天电子数据展示的方式。</span><span class="sxs-lookup"><span data-stu-id="610e5-118">The following illustration shows how eDiscovery works for guest-to-guest chats in which there isn’t a mailbox.</span></span>

![guest-to-guest-chats-with-no-mailbox](media/conduct-an-ediscovery-investigation-of-content-in-microsoft-teams-image2.png)
