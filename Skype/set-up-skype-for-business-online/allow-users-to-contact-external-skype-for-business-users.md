---
title: "允许用户联系外部 Skype for Business 用户"
ms.author: TONYSMIT
author: tonysmit
manager: scotv
ms.date: 11/9/2017
ms.audience: Admin
ms.topic: article
f1_keywords:
- For O365M_ShareLync
- ms.lync.lac.OrgExternalAccess
- ms.lync.lac.skypefederation
- O365E_HRCLYNC _ SipFederationSrvRecordVerified_FL312122
- O365E_ShareLync
- O365M_ShareLync
- O365P_ExternalCommDesc
- O365P_ShareLync
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_Skype4B_Online
- Adm_Skype4B_Online_Top
- Adm_UI_Elements
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
- LIL_Placement
ms.assetid: b414873a-0059-4cd5-aea1-e5d0857dbc94

description: "See how to configure Skype for Business to let users talk to users in another organization, or let outside contacts to them. "
---

# 允许用户联系外部 Skype for Business 用户

> [!IMPORTANT]
> 本文是由机器翻译的，请参阅[免责声明]。
  
> [!NOTE]
> Skype for Business 联合身份验证不适用于由 21Vianet 和 Office 365 德国组织运营的 Office 365。 
  
在下列情况下，请按照本文的步骤进行操作：
  
- 你的用户在企业内的不同域中。例如，Rob@ContosoEast.com 和 Ann@ContosoWest.com。
    
- 希望你组织的人员使用 Skype for Business 联系你组织外特定企业中的人员。
    
- 或者，你希望世界各地使用 Skype for Business 的所有其他人都能够通过使用你的电子邮件地址找到并联系你。如果你和他们都使用默认的 Skype for Business 设置，此功能会自动运行。如果他们更改了默认设置，他们需要确认其配置没有阻止你的域。
    
## 为你的用户启用企业到企业通信
<a name="bk_preview"> </a>

只有 Office 365 的[关于 Office 365 管理员角色](about-office-365-admin-roles.md)才能执行此操作。
  
1. 使用您的Office 365管理员帐户登录。
    
2. 在 Office 365 管理中心，转到" **管理中心**">" **Skype for Business**"。
    
    ![Choose the Skype for Business admin center.](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. 在 **Skype for Business 管理中心**中，选择 **组织**> **外部通信**。
    
4. 若要设置的通信与特定的企业或用户在另一个域，在下拉列表框中，选择 **仅在允许的域**。
    
    或者，你希望能够与世界各地采用公开的 Skype for Business 策略的所有其他人通信，请选择" **打开(被阻止的域除外)**"。这是默认设置。
    
5. 在 **阻止或允许的域**，选择 **+** ，并添加您希望允许的域的名称。
    
6. 请确保其他组织中的管理员在其 **Skype for Business 管理中心**同样的步骤。例如，在其 **允许的域**列表中，其管理员需要先为您的企业中输入的域。
    
7. 如果你使用的是 Windows 防火墙，Skype for Business 将自动打开所需端口。
    
    如果您的组织正在使用不同的防火墙解决方案来限制在您的网络的计算机连接到 Internet，确保您的客户端计算机无法访问以下[Office 365 URL 和 IP 地址范围](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)。这可能需要添加到出站 Fqdn 允许列表中您的防火墙或代理服务器基础结构配置： ***。 api.skype.com，*。 users.storage.live.com 和 graph.skype.com** 。如何在您的防火墙中打开这些端口的说明，请与之附带的文档。
    
    您需要打开的所有端口的列表，请参阅[Office 365 URL 和 IP 地址范围](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)文章中的[Office 365 URL 和 IP 地址范围](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_lyo) 。
    
8. **等待多达 24 小时，进行测试** 。每当您更改了外部通信设置，它可能需要多达 24 小时所做的更改来填充跨所有数据中心。
    
![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png)您可以使用的每个用户使用 Skype，免费消费者应用程序允许您的用户搜索和即时消息 ！若要了解详细信息，请参阅[允许 Skype for Business 用户添加 Skype 联系人](let-skype-for-business-users-add-skype-contacts.md)。
  
## 测试和故障排除
<a name="bk_preview"> </a>

 **最常见的问题设置企业到企业通信时遇到的人员将收到其[Office 365 URL 和 IP 地址范围](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)正确。**
  
若要测试您的设置，您需要在您的公司防火墙不是Skype for Business联系人。
  
1. 在更改外部通信设置后， **直到等待 24 小时后再进行测试** 。
    
2. 在 Skype for Business 中，搜索你的 Skype for Business 联系人，然后发送聊天请求。
    
    如果收到一条消息，则无法发送由于公司政策，您需要请仔细检查您的[Office 365 URL 和 IP 地址范围](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)。
    
3. 要求你的 Skype for Business 联系人向你发送聊天请求。如果你未收到其请求，那么你的防火墙有问题（假设他们已确认其防火墙设置正确）。
    
4. 测试您的防火墙问题是否另一种方法是转到不防火墙您咖啡店，如 wifi 位置，然后使用Skype for Business将请求发送到您的联系人的聊天室。如果邮件经历，但不是时在工作，然后您知道问题是您的防火墙。
    
## 在与其他企业连接时如何查找其他人以及如何被找到
<a name="bk_preview"> </a>

您的用户启用外部通信与其他Skype for Business用户之后，可以通过搜索其登录名称来查找联合的Skype for Business用户： 例如，Rob@contoso.com。然后，他们需要将用户添加到其联系人列表。
  
![To find a user in a federated business, you must search for their email address (this is usally also their sign in name).](../images/20242f85-0636-463b-8df3-1e123784d7fa.png)
  
## 设置联盟企业通信的提示
<a name="bk_preview"> </a>

- 要配置 Skype for Business 2015 与 Skype for Business Online 之间的联盟，请参阅 TechNet 文章：[配置与 Skype for Business Online 联盟](https://technet.microsoft.com/en-us/library/jj205126.aspx)。
    
- 要配置 Lync 与 Skype for Business Online 之间的联盟，请参阅 TechNet 文章：[为 Lync Online 客户配置联盟支持](https://technet.microsoft.com/en-us/library/hh202193.aspx)。
    
- 当 Office 365 中的两个 Skype for Business 用户在单独的域上相互通信时，他们只能使用在两个组织中都启用的 Skype for Business 功能（例如，视频对话或桌面共享）。
    
- 如果您的组织内的Skype for Business用户置于现场或诉讼按住，该用户和其他Skype for Business或 Skype 用户之间的 IM 对话将保存在 **可恢复的项目**在其邮箱中。这些对话未保存在其邮箱中的 **对话历史记录**文件夹中。
    
## 关闭特定个人的外部通信
<a name="bk_preview"> </a>

为你的整个企业启用外部通信后，你可以仅为特定的个人关闭它。
  
1. 使用您的Office 365管理员帐户登录。
    
2. 在Office 365 管理中心中，转到 **用户**> **活动用户**。
    
3. 在用户列表中，选择用户，然后在" **其他设置**"下单击" **编辑 Skype for Business 属性**"。
    
    ![Choose Skype for Business](../images/2b0f9a7b-3fee-4f4b-968a-68c429eeb395.png)
  
4. 在 **Skype for Business 管理中心**中，选择 **外部通信**。
    
    在 **选项**页面中，将被选中所有选项。清除要禁用的通信。下图显示 Jakob 能够与其他受信任的公司中的人员，但不能使用其他 Skype 用户通信。
    
    ![Choose External contacts](../images/4e546321-a065-48ed-8ac7-1e112a780eab.png)
  
5. 选择" **保存**"。
    
> [!NOTE]
> 你可能必须等待长达 24 小时，更改才会生效。 
  
## 
<a name="bk_preview"> </a>

 *文章上次更新时间：2017 年 3 月 23* 
  
## 
<a name="bk_preview"> </a>

||
|:-----|
|![领英学习快捷图标。](../images/7e5cb7c8-dc66-4c9a-a16d-a30f10a970bd.png) **刚开始使用 Office 365？**         探索由 LinkedIn Learning 提供的适用于 **Office 365 管理员和 IT 专业人士**的免费视频课程。 |
   
## 相关主题
<a name="bk_preview"> </a>

[设置 Skype for Business Online](set-up-skype-for-business-online.md)
  
[允许 Skype for Business 用户添加 Skype 联系人](let-skype-for-business-users-add-skype-contacts.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **机器翻译免责声明**：本文是由无人工介入的计算机系统翻译的。Microsoft 提供机器翻译是为了帮助非英语国家/地区用户方便阅读有关 Microsoft 产品、服务和技术的内容。由于机器翻译的原因，本文可能包含词汇、语法或文法方面的错误。 
  

