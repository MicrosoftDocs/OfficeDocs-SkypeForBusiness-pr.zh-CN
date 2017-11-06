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
<a name="set-up-guest-access-to-microsoft-teams"></a>设置对 Microsoft Teams 的来宾访问
======================================

Microsoft Teams 建立在 Office 365 组之上，并且它还依赖 SharePoint Online。 这就是为什么除了在 Teams 中启用来宾访问功能之外，还必须在 Office 365 组和 SharePoint Online 中启用特定设置。


## <a name="allow-the-addition-of-guests-in-office-365-groups"></a>允许在 Office 365 组中添加来宾
<a name="bkmk_ControlAddingGuestUsers"> </a>


1. 在 [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) 上使用你的 Office 365 全局管理员帐户登录。
    
  
2. 在导航菜单中，依次选择**“设置”**和**“服务&amp;和外接程序”**。
    
  
3. 选择**“Office 365 组”**。
    
     ![Office 365 组](media/e25a7920-254c-4da3-bc5f-a8c7f6b61423.png)
  

  

  
4. 在“Office 365 组”页面上，将切换设置为**“开启”**或**“关闭”**，具体取决于你是否要允许贵组织外部的团队和组所有者访问 Office 365 组。 单击或点击**“允许组所有者将组织外部的人员添加到组”**旁边的切换将其设置为**“开启”**。


![此屏幕截图显示了“Office 365 组”面板，用于允许组织外部的组成员访问组内容和允许组所有者将组织外部的人员添加到组的选项已开启。](media/eee77abd-4425-4585-91a8-5541c17ee7b2.png)
    

## <a name="enable-sharing-in-sharepoint-online"></a>在 SharePoint Online 中启用共享

SharePoint Online 中的“共享”选项用于允许将来宾添加到贵组织。 默认情况下，启用“共享”选项。 有关如何关闭“共享”选项的信息，请参阅[开启或关闭“共享”选项](https://support.office.com/en-us/article/Turn-on-or-off-the-Sharing-option-7c713d74-a144-4eab-92e7-d50df526ff96#bkmk_beforeyoubegin)。
  
   管理员可以在 Azure Active Directory 中创建来宾帐户，与外部共享设置无关。 如果外部共享处于关闭状态，则仅管理员可以创建来宾帐户。 
    

> [!IMPORTANT]
> 如果你关闭“共享”选项，则来宾访问不可用。 
  

## <a name="turn-on-or-off-guest-access-to-microsoft-teams"></a>开启或关闭对 Microsoft Teams 的来宾访问
<a name="bkmk_TurnonOrTurnOff"> </a>

作为 Office 365 管理员，你必须先启用来宾功能，你或贵组织的用户（具体来说是团队所有者）才能添加来宾。 

在 Azure Active Directory 中设置来宾设置后， 更改在 Office 365 组织中生效需要 2 小时到 24 小时。 如果用户尝试向其团队添加来宾时看到“请与管理员联系”消息，很可能是尚未启用来宾功能，或设置尚未生效。



1. 在 [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) 上使用你的 Office 365 全局管理员帐户登录。
    
  
2. 在导航菜单中，依次选择**“设置”**和**“服务&amp;和外接程序”**。
    
     ![登录 Office 365，访问 Office 365 管理中心，转到“设置”，然后选择“服务&amp;和外接程序”](media/99e676d4-5b48-4525-9556-547031fa37d9.png)
  
 

  
3. 选择**“Microsoft Teams”**。
    
     ![此屏幕截图显示了在 Office 365 管理中心中选择的 Microsoft Teams 外接程序对应的选项。](media/17ac5608-d212-4fa8-ae3a-e78c62003968.png)
  
  
4. 在**“选择要配置的用户/许可证类型”**中，选择**“来宾”**。
   
    ![Microsoft Teams 外接程序的屏幕截图显示选择了“来宾”许可证且 Microsoft Teams 选项设置为“开启”。](media/92aabda5-431c-4fdd-803e-5ab49290f4f7.png)
      

  
  
5. 单击或点击**“对此类型的所有用户开启或关闭 Microsoft Teams”**旁边的切换将其设置为**“开启”**为贵组织开启 Teams 和来宾访问，然后选择**“保存”**。 
    
  

