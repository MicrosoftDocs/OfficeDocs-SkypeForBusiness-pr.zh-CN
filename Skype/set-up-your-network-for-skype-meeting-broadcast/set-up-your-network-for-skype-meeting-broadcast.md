---
title: "设置 Skype 会议直播网络"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/16/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_Skype4B_Online
- Adm_Skype4B_Online_Top
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
ms.assetid: dfa736b9-4920-4f48-b8c0-b5487ec6086f
description: "Learn about the Skype Meeting Broadcast feature of Skype for Business Online that enables you to schedule, produce, and broadcast meetings or events to large online audiences up to 10,000 attendees."
---

# 设置 Skype 会议直播网络

> [!IMPORTANT]
> 本文是由机器翻译的，请参阅[免责声明](dfa736b9-4920-4f48-b8c0-b5487ec6086f.md#MT_Footer)。请在 [此处](https://support.office.com/en-us/article/dfa736b9-4920-4f48-b8c0-b5487ec6086f) 中查找本文的英文版本以便参考。
  
[启用 Skype 会议直播](enable-skype-meeting-broadcast.md) Skype 会议直播后，你需要配置网络。 如果希望面向企业外部的人员举办网络研讨会和其他直播活动，请执行此步骤。
  
如果你没有配置防火墙方面的经验，请考虑聘用 [Microsoft 合作伙伴](https://go.microsoft.com/fwlink/?linkid=391089)为你执行此步骤。
  
若要跳过此步骤，并改为将另一个业务添加到您的联合身份验证，以便您可以邀请其加入广播，请按照中[允许用户联系外部 Skype for Business 用户](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)的步骤操作。
  
## 第 1 步： 设置允许的域

使用 **一个** 下列方法之一设置允许的域：
  
### 

 **方法 1： 使用 Office 365 管理中心**
  
1. 转到 **Office 365 管理中心**，然后单击在左侧导航中的 **设置**> **服务和加载项**，然后选择 **Skype for Business**。
    
2. 在 **外部共享**的页面，在 **域例外项**下，选择 **所有域都受阻除外**，，然后输入下列域，用逗号 （，） 分隔：
    
  - noammeetings.lync.com
    
  - emeameetings.lync.com
    
  - apacmeetings.lync.com
    
  - resources.lync.com
    
3. 单击" **保存**"。
    
### 

 **方法 2： 使用 Windows PowerShell**
  
- 从 **开始菜单**中，右键单击 **Windows PowerShell** ，然后单击 **以管理员身份运行**。在 **Windows PowerShell**窗口中，键入每个行，然后按 Enter。
    
  ```
  $r = New-CsEdgeDomainPattern -Domain "noammeetings.lync.com"
  ```

  ```
  $s = New-CsEdgeDomainPattern -Domain "emeameetings.lync.com"
  ```

  ```
  $t = New-CsEdgeDomainPattern -Domain "apacmeetings.lync.com"
  ```

  ```
  $n = New-CsEdgeDomainPattern -Domain "resources.lync.com"
  ```

  ```
  $newAllowList = New-CsEdgeAllowList -AllowedDomain $r,$s,$t,$n
  ```

  ```
  Set-CsTenantFederationConfiguration -AllowedDomains $newAllowList
  ```

## 步骤 2： 添加 Skype 会议直播域、 Url 和 IP 地址

在安装过程中的第二步是为您要首先添加所需的然后添加 IP 地址和 Url 所需的 Skype 会议直播工作的域。
  
- **添加所需的域终结点：**
    
    要使用 Skype 会议直播，客户端计算机需要能够访问以下终结点。
    
|
|
|**行**|**用途**|**源 |凭据**|**目标**|**适用于 Office 365 BGP 的 ExpressRoute 社区**|**CIDR 地址**|**端口**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|1  <br/> |**必需：** Skype for Business 终结点。 <br/> |请参阅 [Skype for Business Online](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#BKMK_LYO)，并确保所有标记为"必需"的条目可访问。  <br/> ||||
|2  <br/> |**必需：**[Skype 会议直播](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)演示者和与会者  <br/> |客户端计算机/登录的用户  <br/> |
```
*.broadcast.skype.com
broadcast.skype.com
browser.pipe.aria.microsoft.com

```

|是  <br/> |[](8548a211-3fe7-47cb-abb1-355ea5aa88a2.md#BKMK_SfB_IP).  <br/> |TCP 443  <br/> |
|3  <br/> |**必需：**[Skype 会议直播](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)演示者和与会者  <br/> |客户端计算机/登录的用户  <br/> |
```
aka.ms
amp.azure.net

```

|否  <br/> |N/A  <br/> |TCP 443  <br/> |
|4  <br/> |**必需：**[Skype 会议直播](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)演示者和与会者（包括 CDN）  <br/> |客户端计算机/登录的用户  <br/> |
```
*.keydelivery.mediaservices.windows.net
*.msecnd.net
*.streaming.mediaservices.windows.net
ajax.aspnetcdn.com
mlccdn.blob.core.windows.net

```

|否  <br/> |N/A  <br/> |TCP 443  <br/> |
   
- **添加所需的 Skype for Business Online 终结点的 Url 和 IP 地址通过查看哪些是必需的**[下面](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo)。
    
## 在混合部署和组织中设置 Skype 会议直播

如果您有Skype for Business Online组织和Lync Server 2010、 Microsoft Lync Server 2013，和Skype for Business Server 2015本地部署和联机有两个用户和本地，您将需要执行另外于上面要启用的其他设置步骤使用Skype for Business Online进行通信，并允许您的所有用户能够创建并加入Skype 会议广播您的本地组织。若要查看这些要求是什么，请参阅[配置您的本地部署 Skype 会议直播](https://go.microsoft.com/fwlink/?LinkId=617070)。
  
## 相关主题

[启用 Skype 会议直播](enable-skype-meeting-broadcast.md)
  
[Office 365 URL 和 IP 地址范围](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[设置 Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **机器翻译免责声明**：本文是由无人工介入的计算机系统翻译的。Microsoft 提供机器翻译是为了帮助非英语国家/地区用户方便阅读有关 Microsoft 产品、服务和技术的内容。由于机器翻译的原因，本文可能包含词汇、语法或文法方面的错误。 
  

