---
title: "部署 Skype for Business Online 电话"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 11/10/2017
ms.audience: Admin
ms.topic: get-started-article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom: Adm_O365_FullSet
ms.assetid: faa17eb3-7483-4984-87f2-815d981b68ae
description: "Learn the deployment steps to get the correct firmware, update it if needed, assign licences, and configure settings for Skype for Business online phones"
---

# 部署 Skype for Business Online 电话

> [!重要信息]
> 本文是由机器翻译的，请参阅[免责声明](faa17eb3-7483-4984-87f2-815d981b68ae.md#MT_Footer)。请在 [此处](https://support.office.com/en-us/article/faa17eb3-7483-4984-87f2-815d981b68ae) 中查找本文的英文版本以便参考。
  
本部署指南将帮助你部署 Skype for Business Online IP 电话。
  
在所有类型的企业中，有电话号码使用户可以使和获取语音呼叫，并且有业务往来的重要要求。有电话号码的用户将能够跨所有Skype for Business设备包括 IP 电话、 Pc 和移动设备进行语音呼叫。您可以了解有关 Skype for Business IP 电话阅读[获取适用于 Skype for Business Online 的电话](getting-phones-for-skype-for-business-online.md)。
  
## 部署 IP 电话的步骤

### 第 1 步 - 下载制造商的管理员指南和电话手册

开始之前，最好先下载电话制造商的管理指南和电话用户手册。
  
- 对于 Polycom 电话，请参阅 [Polycom 部署指南](https://support.polycom.com/PolycomService/support/us/support/voice/polycom_uc/polycom_uc_software_for_lync.mdl)。
    
- Yealink 电话，请参阅[Yealink Skype for Business HD SIP 电话解决方案](http://www.yealink.com/solution_7.mdl)。
    
- 对于 AudioCodes 电话，请参阅 [Audiocodes 配置管理指南](https://www.audiocodes.com/products/ems)。
    
### 第 2 步 - 确保购买或迁移支持 Skype for Business 的 IP 电话和固件

Skype for Business Online 支持电话和固件是 Skype for Business Server 兼容，但相反始终不正确。以确保您正在购买或设置支持的电话和固件，请参阅[获取适用于 Skype for Business Online 的电话](getting-phones-for-skype-for-business-online.md)。
  
### 第 3 步 - 检查是否安装了正确的固件并根据需要更新固件。

检查您的电话上的固件版本。适用于：
  
- **Polycom VVX 电话** ，请转到" **设置** ">" **状态** ">" **平台** ">" **应用程序** ">" **主要** "。
    
- **Yealink 电话** ，请转到电话主屏幕上的" **状态** "。
    
- **AudioCodes 电话** ，请从开始屏幕转到" **菜单** ">" **设备状态** ">" **固件版本** "。
    
    > [!注释]
    > 远程访问电话详细信息，请参阅制造商管理指南。 用户指南和电话手册，请参见上面的链接。 
  
- **Lync Phone Edition (LPE) 电话** ，请从开始屏幕转到" **菜单** ">" **系统信息** "。
    
### 第 4 步 - 设备更新注意事项

> [!注释]
> Polycom 固件 5.5.1.X 之前已将被替换为 Skype for Business 实现"电话锁定"制造商特定设备锁定机制升级到 5.5.1.X"电话 lock"电话"设备 lock"保护 5.4.X.X 不继承从"设备锁，"可以保留不安全的电话的 PIN 代码。已激活"设备锁定"的用户需要启用下面的 Polycom 设备配置文件参数，以向用户提供的升级 (lync.deviceUpdate.popUpSK.enabled=1) 时间的控件。 
  
更新固件由 Skype for Business Service 管理。每个 Skype for Business 认证手机的固件上载到 Skype for Business 更新服务器，并且设备更新所有电话上启用了默认情况下。在电话和轮询间隔处于非活动状态时，根据电话将自动下载并安装最新的认证的生成。您可以通过使用[设置 CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) cmdlet 并将 _EnableDeviceUpdate_参数设置为 `false`禁用的设备更新设置。
  
![Deploying phones.](../../images/be727622-1924-439f-96ca-89230739db9e.png)
  
新的固件时可用，并准备好供下载并安装电话将通知用户。Polycom 电话将通知用户并让他们为 **更新** 或 **推迟** 选项。
  
![Deploying phones.](../../images/50956fa0-da0c-4085-9bb5-4a2e99aecebb.png)
  
对于 Polycom 电话，可以通过选择" **软件更新**"来更新电话上的固件。
  
![Deploying phones.](../../images/376c1998-6ce6-44b6-a84d-ae7d96b1c307.png)
  
还可以选择使用合作伙伴配置系统来管理固件更新。有关包含高级电话自定义的合作伙伴配置系统管理，请参考制造商管理指南。
  
> [!警告]
> 确保拥有单个设备更新授权（带内设备更新或第三方配置服务器），以避免更新循环。 
  
### 第 5 步-配置和基础结构的电话设置

你可以使用 Skype for Business 带内管理 Windows PowerShell cmdlet 来设置最常用的电话选项和策略。有关这些参数和设置的详细信息，请参阅 [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx)。
  
规划网络基础结构，请参阅[Skype 操作框架](https://www.skypeoperationsframework.com/)。
  
### 步骤 6-准备用户登录

若要使用户能够成功登录到 Skype for Business Online 的电话和进行呼叫，需要确保用户分配了正确的许可证。至少需要分配电话系统许可证和呼叫计划。有关其他信息，您可以查看[Skype for Business 和 Microsoft 团队许可加载项](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)和[分配 Skype for Business 和 Microsoft 团队合作的用户许可证](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。
  
可以通过阅读了解更多信息调用计划[什么是致电 Office 365 中计划？](../../what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365.md)
  
- Online 用户可以使用的 **登录选项** 包括：
    
  - **Polycom VVX 5XX/6XX** 电话的用户将看到：
    
     ![Deploying phones.](../../images/8a1ffb33-8a63-4242-bb76-d5fafb6a6472.png)
  
  - 具有 **Yealink T48G/T46G** 电话的用户将看到：
    
     ![Yealink phones logon.](../../images/2a2892ae-850d-4781-8be0-4ffb8af068c9.png)
  
    支持的制造商登录选项的详细信息，请参阅[获取适用于 Skype for Business Online 的电话](getting-phones-for-skype-for-business-online.md)。
    
- **用户 ID** 通过电话键盘或屏幕键盘（如有），用户可以使用其组织的用户名和密码登录电话。例如，他们应使用类似 *amosm@contoso.com*  的 UPN 格式作为其用户名。
    
     ![Deploying phones.](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
    > [!注释]
    > Skype for Business Online 不支持对 LPE 和合作伙伴 IP 电话进行 PIN 身份验证。 
  
- **使用 PC** 更好地协作通过以太网 (BToE) 软件是用户的 PC 上安装并启用，用户可以登录到其在其 Windows Skype for Business 应用上使用身份验证窗口中的电话。其他信息，请参阅[第 7 步（可选）- 如果拥有设备配对和 Better Together over Ethernet (BToE)](faa17eb3-7483-4984-87f2-815d981b68ae.md#BK_BTOE) 。
    
    > [!注释]
    > 用户需要使用其组织的用户名和密码登录电话。例如，他们应使用类似  *amosm@contoso.com*  的 UPN 格式作为其用户名。
  
     ![Deploying phones.](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
- **使用 Web 登录**： 这是一种新联机用户使用标准的 web 浏览器进行身份验证方法。用户将提供一组用户使用浏览器登录时，请按照说明。
    
  - **Polycom VVX 5XX/6XX** 电话的用户将看到：
    
     ![Deploying phones.](../../images/ba0df923-a6e5-4a9b-b40b-b03ca188e814.png)
  
  - 具有 **Yealink T48G/T46G** 电话的用户将看到：
    
     ![Yealink phone logon.](../../images/86551cc3-533a-4694-9683-bad907c9ad5a.png)
  
    生成的代码将在 15 分钟后过期。过期后，用户必须单击 **重试**或 **确定**以生成新的代码，具体取决于电话。
    
  - **Polycom VVX 5XX/6XX** 电话的用户将看到：
    
     ![PIN code expired.](../../images/b5d27037-aa26-4054-be95-d5a6c293d08c.png)
  
  - 具有 **Yealink T48G/T46G** 电话的用户将看到：
    
     ![Yealink phones logon.](../../images/3a4462ac-0c59-409e-a3bb-1451cdcc8676.png)
  
    使用浏览器，导航到电话上显示的地址，输入 Skype for Business 用户名。
    
     ![Deploying phones.](../../images/7c540b85-dc37-4ce7-a077-9e3454a0efd0.png)
  
    输入电话上显示的代码。
    
     ![Deploying phones.](../../images/d6b88016-35d2-41d1-a0da-81fef34521d4.png)
  
    验证该网站显示"[电话制造商名称] **Skype for Business 认证电话**，"并单击 **继续**。
    
     ![Deploying phones.](../../images/a8252b37-4ff5-4ece-9e2a-3e05bf928299.png)
  
    单击用户的凭据或单击" **使用其他帐户**"：
    
     ![Deploying phones.](../../images/8415028b-7924-4747-b639-052d9b0b961e.png)
  
    显示关注页面时，很安全关闭浏览器。
    
     ![Deploying phones.](../../images/1a873201-52fc-4a63-b7b5-e82bbd031fd2.png)
  
    > [!注释]
    > 适用于 Skype for Business Online 的 LPE 电话仅支持通过 USB 数据连线登录。 
  
- **支持的部署** 下表显示了当前支持的部署模式所支持的身份验证类型，包括 Exchange 集成、使用多因素身份验证 (MFA) 的新式验证以及 Skype for Business Online 和本地部署。
    
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Skype for Business** <br/> |**Exchange** <br/> |**电话登录方法** <br/> |**Skype for Business 访问** <br/> |**禁用新式验证和 MFA 的 Exchange 访问** <br/> |**启用新式验证和 MFA 的 Exchange 访问** <br/> |
|Online  <br/> |Online  <br/> |Web 登录  <br/> |是  <br/> |是  <br/> |是  <br/> |
|Online  <br/> |Online  <br/> |用户名/密码  <br/> |是  <br/> |支持  <br/> |否  <br/> |
|Online  <br/> |本地部署  <br/> |Web 登录  <br/> |是  <br/> |否  <br/> |否  <br/> |
|Online  <br/> |本地部署  <br/> |用户名/密码  <br/> |是  <br/> |支持  <br/> |否  <br/> |
|本地部署  <br/> |Online/本地部署  <br/> |PIN 身份验证  <br/> |支持  <br/> |否  <br/> |否  <br/> |
|本地部署  <br/> |Online/本地部署  <br/> |用户名/密码  <br/> |是  <br/> |是  <br/> |不适用  <br/> |
|本地部署  <br/> |Online/本地部署  <br/> |通过 PC 登录 (BTOE)  <br/> |是  <br/> |是  <br/> |N/A  <br/> |
   
- **电话功能** 功能集可能会有所不同略有基于 IP 电话合作伙伴。完成功能设置和的每个电话制造商的功能的详细信息，请参阅[获取适用于 Skype for Business Online 的电话](getting-phones-for-skype-for-business-online.md)。
    
- **电话锁定** 是 Skype for Business 认证电话用于安全电话最近引入的功能。如果已启用，用户将需要创建成功的身份验证时 PIN。创建后，空闲超时定义到期、 用户手动锁定他们的电话，或他们使用手机配对其 PC lock 同步其电话锁定时，将锁定电话。如果多次错误输入电话锁定 PIN，电话将注销用户或需要管理员的代码解锁电话，但这因电话合作伙伴。6 到 15 位之间应用户的 PIN。
    
    您可以为您的组织 （这默认已启用） 禁用电话锁定、 更改空闲超时，并选择是否处于锁定或不使用带内设置时，用户可以拨打电话。有关这些设置的更多详细信息，请参阅[设置 CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) 。
    
## 第 7 步（可选）- 如果拥有设备配对和 Better Together over Ethernet (BToE)
<a name="BK_BTOE"> </a>

BToE 是 paining 机制合作伙伴 IP 电话手机，对其 Windows Skype for Business 应用程序 BToE 与用户的电话使用户可以：
  
- 登录到其使用其 Skype for Business 桌面应用程序 （使用 PC） 的 IP 电话
    
- 与 PC 锁定同步电话锁定
    
- 单击以呼叫
    
可以将 BToE 配置为在两个模式下运行: （默认值） 的 *自动*  和 *手动*  。也可以启用 （默认值） / 禁用用户使用 Skype for Business 带内设置的。 *手动*  模式在运行，当用户需要采取额外步骤，以对其 Windows 应用其电话。
  
 **若要为用户部署 BToE**
  
1. 使用 PC 端口将 PC 与电话相连。
    
     ![Deploying phones.](../../images/e21d76c7-867c-4fe6-95c6-fc40c608ed0c.png)
  
2. 从制造商网站（链接如下所示）下载并安装最新的 BToE 软件。要获取更好的用户体验，可以使用 System Center Configuration Manager (SCCM) 等管理员分发解决方案来分发并安装 BToE 软件。有关使用 SCCM 的帮助，请参阅[ System Center Configuration Manager 中的软件包和程序](https://docs.microsoft.com/zh-cn/sccm/apps/deploy-use/packages-and-programs)。
    
  - [Polycom BToE 软件下载网站](https://support.polycom.com/PolycomService/support/us/support/voice/polycom_uc/polycom_uc_software_for_lync.mdl)
    
  - [Yealink BToE 软件下载](http://www.yealink.com/solution_info.aspx?ProductsCateID=1471&amp;parentcateid=1471&amp;cateid=1471&amp;BaseInfoCateId=1328&amp;Cate_Id=1471)
    
  - [AudioCodes BToE 软件下载](ftp://VoP-C12:IPPLync@ftp.audiocodes.com/Release/3.0.0.Beta/BToE_1.1.8/)
    
3. 默认情况下，BToE 的服务器设置设置为 **已启用** 和 **自动模式** 。若要更改这些设置，请参阅[设置 CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx)。
    
> [!注释]
> Mac 和 VDI 平台目前不支持 BToE。 
  
## 
<a name="MT_Footer"> </a>

> [!注释]
> **机器翻译免责声明**：本文是由无人工介入的计算机系统翻译的。Microsoft 提供机器翻译是为了帮助非英语国家/地区用户方便阅读有关 Microsoft 产品、服务和技术的内容。由于机器翻译的原因，本文可能包含词汇、语法或文法方面的错误。 
  

