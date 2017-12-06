---
title: "允许 Skype for Business 用户添加 Skype 联系人"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/13/2017
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
- LIL_Placement
ms.assetid: 08666236-1894-42ae-8846-e49232bbc460

description: "See how to  let people who are using Skype for Business contact Skype for Business users from outside your organization and add them to their list of contacts. "
---

# 允许 Skype for Business 用户添加 Skype 联系人

> [!IMPORTANT]
> 本文是由机器翻译的，请参阅[免责声明](08666236-1894-42ae-8846-e49232bbc460.md#MT_Footer)。请在 [此处](https://support.office.com/en-us/article/08666236-1894-42ae-8846-e49232bbc460) 中查找本文的英文版本以便参考。
  
通过 Skype for Business，你的用户可以搜索使用 Skype 这一免费应用的任何人并与其进行即时消息通信！本文介绍为使你的用户能够添加 Skype 联系人，你需要执行的操作。
  
只有 Office 365 的[关于 Office 365 管理员角色](about-office-365-admin-roles.md)才能执行此操作。
  
1. 使用 Office 365 管理员帐户登录 [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage)。
    
2. 在 Office 365 管理中心，转到" **管理中心**">" **Skype for Business**"。
    
    ![Choose the Skype for Business admin center.](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. 在 **Skype for Business 管理中心**中，选择 **组织**> **外部通信**。
    
4. 默认情况下，你的用户可以与世界各地使用 Skype for Business 的所有其他人通信（假设你的防火墙已配置为允许这样）。
    
    ![Choose Let people use Skype for Business to communicate with Skype.](../images/333789f8-2ea6-4bbd-805b-18130f427999.png)
  
    如果你希望你的用户与 Skype 用户聊天，但不希望他们与使用 Skype for Business 的其他人聊天，请选择" **打开(仅针对被允许的域)**"。当你允许与 Skype 用户联系时，系统会在后台自动将 skype.com 添加为允许的域。
    
    如果你希望允许世界各地使用 Skype for Business 的所有其他企业与你联系，但特定企业除外，请选择" **打开(被阻止的域除外)**"，并选择 **+** 添加那些域。除了那些特定域中的人之外，所有人都将能够与你联系（有些企业可能选择此选项，例如，如果他们处于诉讼状态，并需要确保不与其他企业联系。）
    
5. 选择" **让用户能够使用 Skype for Business 与组织外的 Skype 用户进行通信**"。
    
6. 如果你使用的是 Windows 防火墙，Skype for Business 将自动打开所需端口。
    
    如果贵组织使用其他解决方案限制网络中的计算机连接至互联网，请确保客户端计算机能够访问用于 Skype 连接和 Skype 目录搜索的所有 [Office 365 URL 和 IP 地址范围](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)。为此，可能需要将其添加到你的防火墙或代理基础结构配置中的出站允许列表内。
    
7. **测试最长需要等待 24 小时** 。如果你更改了外部通信设置，最长需要等待 24 小时才能让更改传播到所有数据中心。
    
8. 向你的用户演示如何查找 Skype 联系人并将他们添加到其 Skype for Business 联系人列表。请指示他们查看[在 Skype for Business 中搜索人员](https://support.office.com/article/b12500ef-e37f-4d22-aade-c11277e53f19)。
    
## 测试和故障排除

要测试你的设置，你需要一个不受你公司防火墙保护的 Skype 联系人。他们可以使用 Gmail 帐户、Outlook.com 帐户或其他类型的电子邮件帐户登录 Skype。
  
1. 在更改外部通信设置后， **直到等待 24 小时后再进行测试** 。
    
2. 注销 Skype for Business，然后重新登录，这样你会看到用于搜索 Skype Directory 的选项。
    
    ![When Skype Directory is highlighted, you can search for people who have Skype accounts.](../images/76ee9fab-1ac3-4f4a-9569-f5f2606dbb7a.png)
  
3. 在 Skype for Business 中，搜索你的 Skype 联系人，然后发送聊天请求。
    
    如果收到由于公司策略无法发送的消息，你需要再次检查你的[Office 365 URL 和 IP 地址范围](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)。
    
4. 另一个测试问题是否出自你的防火墙的方法是在不受你的防火墙保护的 WiFi 位置（例如咖啡店）使用 Skype for Business 向你的 Skype 联系人发送聊天请求。
    
  - **如果你向你的 Skype 联系人发送了请求，但他们从未收到** ，请要求他们向你发送聊天请求。如果问题是无法在 Skype 与 Skype for Business 之间建立连接，这样做通常会解决问题。
    
  - 此时如果在咖啡店里消息顺利传送，但不是在你工作的时候，那么问题出自你的防火墙。
    
## 可以执行的操作和不能执行的操作

- **Skype for Business在 Mac 中** 无法搜索 Skype 联系人并与之通信。
    
- 虽然您可以搜索和查找 Skype 用户，他们不能搜索和查找Skype for Business用户。您必须向他们发送一个联系人请求，并他们需要登录到 Skype 并接受它，您可以与他们的即时消息之前。
    
- 不可能允许与其他 IM 提供商（如 Google 或 Facebook）建立 IM 连接。不能使用 Skype for Business 发送手机短信。
    
## 添加 Skype 联系人时可使用哪些功能？

使用自己的 Microsoft 帐户 (以前称为 Windows Live ID) 登录的Skype联系人可以获得一些，但不是所有功能时Skype for Business用户交谈。
  
|**对 Skype 联系人可用**|**对 Skype 联系人不可用**|
|:-----|:-----|
| 视频对话 <br/>  个人对个人的即时消息 <br/>  状态 <br/> | 多方 IM 对话 <br/>  与三人或多人的音频和视频对话 <br/>  桌面和程序共享 <br/> |
   
## 

 *更新时间：2017 年 3月 23 日* 
  
||
|:-----|
|![领英学习快捷图标。](../images/7e5cb7c8-dc66-4c9a-a16d-a30f10a970bd.png) **刚开始使用 Office 365？**         探索由 LinkedIn Learning 提供的适用于 **Office 365 管理员和 IT 专业人士**的免费视频课程。 |
   
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **机器翻译免责声明**：本文是由无人工介入的计算机系统翻译的。Microsoft 提供机器翻译是为了帮助非英语国家/地区用户方便阅读有关 Microsoft 产品、服务和技术的内容。由于机器翻译的原因，本文可能包含词汇、语法或文法方面的错误。 
  
## 另请参阅
<a name="MT_Footer"> </a>

#### 其他资源

[允许用户联系外部 Skype for Business 用户](allow-users-to-contact-external-skype-for-business-users.md)
  
[设置 Skype for Business Online](set-up-skype-for-business-online.md)

