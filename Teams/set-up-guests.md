---
title: "设置对 Microsoft Teams 的来宾访问"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 10/20/17
ms.topic: article
ms.service: msteams
description: "在 Microsoft Teams 中启用来宾访问功能。"
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 7b571d166ed1fdc078ecdb2ecc0f9bfc2ab5cdb3
ms.sourcegitcommit: f6c2673a2ccd951770296972234938e627bd49ad
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2017
---
<a name="set-up-guest-access-to-microsoft-teams"></a><span data-ttu-id="ebe85-103">设置对 Microsoft Teams 的来宾访问</span><span class="sxs-lookup"><span data-stu-id="ebe85-103">Set up guest access to Microsoft Teams</span></span>
======================================

<span data-ttu-id="ebe85-104">Microsoft Teams 建立在 Office 365 组之上，并且它还依赖 SharePoint Online。</span><span class="sxs-lookup"><span data-stu-id="ebe85-104">Microsoft Teams is built upon Office 365 Groups, and it also relies on SharePoint Online.</span></span> <span data-ttu-id="ebe85-105">这就是为什么除了在 Teams 中启用来宾访问功能之外，还必须在 Office 365 组和 SharePoint Online 中启用特定设置。</span><span class="sxs-lookup"><span data-stu-id="ebe85-105">That’s why specific settings must be enabled in Office 365 Groups and SharePoint Online in addition to turning on the guest access feature in Teams.</span></span>


## <a name="allow-the-addition-of-guests-in-office-365-groups"></a><span data-ttu-id="ebe85-106">允许在 Office 365 组中添加来宾</span><span class="sxs-lookup"><span data-stu-id="ebe85-106">Allow the addition of guests in Office 365 Groups</span></span>
<span data-ttu-id="ebe85-107"><a name="bkmk_ControlAddingGuestUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="ebe85-107"></span></span>


1. <span data-ttu-id="ebe85-108">在 [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) 上使用你的 Office 365 全局管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="ebe85-108">Sign in with your Office 365 global admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
  
2. <span data-ttu-id="ebe85-109">在导航菜单中，依次选择**“设置”**和**“服务&amp;和外接程序”**。</span><span class="sxs-lookup"><span data-stu-id="ebe85-109">In the navigation menu, choose **Settings** and then select **Services &amp; add-ins**.</span></span>
    
  
3. <span data-ttu-id="ebe85-110">选择**“Office 365 组”**。</span><span class="sxs-lookup"><span data-stu-id="ebe85-110">Select **Office 365 Groups**.</span></span>
    
     ![Office 365 组](media/e25a7920-254c-4da3-bc5f-a8c7f6b61423.png)
  

  

  
4. <span data-ttu-id="ebe85-112">在“Office 365 组”页面上，将切换设置为**“开启”**或**“关闭”**，具体取决于你是否要允许贵组织外部的团队和组所有者访问 Office 365 组。</span><span class="sxs-lookup"><span data-stu-id="ebe85-112">On the Office 365 Groups page, set the toggle to **On** or **Off**, depending if you want to let team and group owners outside your organization access Office 365 groups.</span></span> <span data-ttu-id="ebe85-113">单击或点击**“允许组所有者将组织外部的人员添加到组”**旁边的切换将其设置为**“开启”**。</span><span class="sxs-lookup"><span data-stu-id="ebe85-113">Click or tap the toggle to **On** next to **Let group owners add people outside the organization to groups**.</span></span>


![此屏幕截图显示了“Office 365 组”面板，用于允许组织外部的组成员访问组内容和允许组所有者将组织外部的人员添加到组的选项已开启。](media/eee77abd-4425-4585-91a8-5541c17ee7b2.png)
    

## <a name="enable-sharing-in-sharepoint-online"></a><span data-ttu-id="ebe85-115">在 SharePoint Online 中启用共享</span><span class="sxs-lookup"><span data-stu-id="ebe85-115">Enable sharing in SharePoint Online</span></span>

<span data-ttu-id="ebe85-116">SharePoint Online 中的“共享”选项用于允许将来宾添加到贵组织。</span><span class="sxs-lookup"><span data-stu-id="ebe85-116">The Sharing option in SharePoint Online allows guests to be added to your organization.</span></span> <span data-ttu-id="ebe85-117">默认情况下，启用“共享”选项。</span><span class="sxs-lookup"><span data-stu-id="ebe85-117">By default, neither option is enabled.</span></span> <span data-ttu-id="ebe85-118">有关如何关闭“共享”选项的信息，请参阅[开启或关闭“共享”选项](https://support.office.com/en-us/article/Turn-on-or-off-the-Sharing-option-7c713d74-a144-4eab-92e7-d50df526ff96#bkmk_beforeyoubegin)。</span><span class="sxs-lookup"><span data-stu-id="ebe85-118">For information about how to turn off the Sharing option, see [Turn on or off the Sharing option](https://support.office.com/en-us/article/Turn-on-or-off-the-Sharing-option-7c713d74-a144-4eab-92e7-d50df526ff96#bkmk_beforeyoubegin).</span></span>
  
   <span data-ttu-id="ebe85-119">管理员可以在 Azure Active Directory 中创建来宾帐户，与外部共享设置无关。</span><span class="sxs-lookup"><span data-stu-id="ebe85-119">Admins can create guest accounts in Azure Active Directory, independent from external sharing settings.</span></span> <span data-ttu-id="ebe85-120">如果外部共享处于关闭状态，则仅管理员可以创建来宾帐户。</span><span class="sxs-lookup"><span data-stu-id="ebe85-120">If external sharing is off, only an admin can create guest accounts.</span></span> 
    

> [!IMPORTANT]
> <span data-ttu-id="ebe85-121">如果你关闭“共享”选项，则来宾访问不可用。</span><span class="sxs-lookup"><span data-stu-id="ebe85-121">If you turn off the Sharing option, guest access isn't available.</span></span> 
  

## <a name="turn-on-or-off-guest-access-to-microsoft-teams"></a><span data-ttu-id="ebe85-122">开启或关闭对 Microsoft Teams 的来宾访问</span><span class="sxs-lookup"><span data-stu-id="ebe85-122">Turn on or off guest access to Microsoft Teams</span></span>
<span data-ttu-id="ebe85-123"><a name="bkmk_TurnonOrTurnOff"> </a></span><span class="sxs-lookup"><span data-stu-id="ebe85-123"></span></span>

<span data-ttu-id="ebe85-124">作为 Office 365 管理员，你必须先启用来宾功能，你或贵组织的用户（具体来说是团队所有者）才能添加来宾。</span><span class="sxs-lookup"><span data-stu-id="ebe85-124">As the Office 365 admin, you must enable the guest feature before you or your organization's users (specifically, team owners) can add guests.</span></span> 

<span data-ttu-id="ebe85-125">在 Azure Active Directory 中设置来宾设置后，</span><span class="sxs-lookup"><span data-stu-id="ebe85-125">The guest settings are set in Azure Active Directory.</span></span> <span data-ttu-id="ebe85-126">更改在 Office 365 组织中生效需要 2 小时到 24 小时。</span><span class="sxs-lookup"><span data-stu-id="ebe85-126">It takes 2 hours to 24 hours for the changes to be effective across your Office 365 organization.</span></span> <span data-ttu-id="ebe85-127">如果用户尝试向其团队添加来宾时看到“请与管理员联系”消息，很可能是尚未启用来宾功能，或设置尚未生效。</span><span class="sxs-lookup"><span data-stu-id="ebe85-127">If a user sees the message "Contact your administrator" when they try to add a guest to their team, it's likely that either the guest feature hasn't been enabled or the settings haven’t become effective yet.</span></span>



1. <span data-ttu-id="ebe85-128">在 [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) 上使用你的 Office 365 全局管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="ebe85-128">Sign in with your Office 365 global admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
  
2. <span data-ttu-id="ebe85-129">在导航菜单中，依次选择**“设置”**和**“服务&amp;和外接程序”**。</span><span class="sxs-lookup"><span data-stu-id="ebe85-129">In the navigation menu, choose **Settings** and then select **Services &amp; add-ins**.</span></span>
    
     ![登录 Office 365，访问 Office 365 管理中心，转到“设置”，然后选择“服务&amp;和外接程序”](media/99e676d4-5b48-4525-9556-547031fa37d9.png)
  
 

  
3. <span data-ttu-id="ebe85-131">选择**“Microsoft Teams”**。</span><span class="sxs-lookup"><span data-stu-id="ebe85-131">Select **Microsoft Teams**.</span></span>
    
     ![此屏幕截图显示了在 Office 365 管理中心中选择的 Microsoft Teams 外接程序对应的选项。](media/17ac5608-d212-4fa8-ae3a-e78c62003968.png)
  
  
4. <span data-ttu-id="ebe85-133">在**“选择要配置的用户/许可证类型”**中，选择**“来宾”**。</span><span class="sxs-lookup"><span data-stu-id="ebe85-133">In **Select the user/license type you want to configure**, select **Guest**.</span></span>
   
    ![Microsoft Teams 外接程序的屏幕截图显示选择了“来宾”许可证且 Microsoft Teams 选项设置为“开启”。](media/92aabda5-431c-4fdd-803e-5ab49290f4f7.png)
      

  
  
5. <span data-ttu-id="ebe85-135">单击或点击**“对此类型的所有用户开启或关闭 Microsoft Teams”**旁边的切换将其设置为**“开启”**为贵组织开启 Teams 和来宾访问，然后选择**“保存”**。</span><span class="sxs-lookup"><span data-stu-id="ebe85-135">Click or tap the toggle next to **Turn Microsoft Teams on or off for all users of this type** to **On** to turn on Teams and guest access for your organization, and then choose **Save**.</span></span> 
    
  

