---
title: "允许 Skype for Business 用户添加 Skype 联系人"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 08666236-1894-42ae-8846-e49232bbc460
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Setup
- LIL_Placement
description: 'See how to  let people who are using Skype for Business contact Skype for Business users from outside your organization and add them to their list of contacts. '
ms.openlocfilehash: 1add1f6e907613d1ac536c92b57cfce7f3cdaf66
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/15/2017
---
# <a name="let-skype-for-business-users-add-skype-contacts"></a>允许 Skype for Business 用户添加 Skype 联系人

通过 Skype for Business，你的用户可以搜索使用 Skype 这一免费应用的任何人并与其进行即时消息通信！本文介绍为使你的用户能够添加 Skype 联系人，你需要执行的操作。 
  
在 Office 365，为此必须[管理权限](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US)。
  
1. 使用 Office 365 管理员帐户登录 [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage)。
    
2. 在 Office 365 管理中心，转到**管理中心** > **业务的 Skype**。 
    
    ![Choose the Skype for Business admin center.](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. 在**Skype 的业务管理中心**，选择**组织** > **外部通信**。 
    
4. 默认情况下，你的用户可以与世界各地使用 Skype for Business 的所有其他人通信（假设你的防火墙已配置为允许这样）。 
    
    ![Choose Let people use Skype for Business to communicate with Skype.](../images/333789f8-2ea6-4bbd-805b-18130f427999.png)
  
    如果你希望你的用户与 Skype 用户聊天，但不希望他们与使用 Skype for Business 的其他人聊天，请选择" **打开(仅针对被允许的域)**"。当你允许与 Skype 用户联系时，系统会在后台自动将 skype.com 添加为允许的域。 
    
    如果你希望允许世界各地使用 Skype for Business 的所有其他企业与你联系，但特定企业除外，请选择" **打开(被阻止的域除外)**"，并选择 **+** 添加那些域。除了那些特定域中的人之外，所有人都将能够与你联系（有些企业可能选择此选项，例如，如果他们处于诉讼状态，并需要确保不与其他企业联系。）
    
5. 选择" **让用户能够使用 Skype for Business 与组织外的 Skype 用户进行通信**"。 
    
6.  如果你使用的是 Windows 防火墙，Skype for Business 将自动打开所需端口。
    
    如果您的组织使用另一种解决方案来限制网络上的计算机连接到 Internet，请确保客户端计算机都可以访问所有的[IP 地址和 Url](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)的 Skype 连接和 Skype 目录搜索。 这可能需要将它们添加到出站防火墙或代理服务器的基础结构配置中允许列表。
    
7. **测试最长需要等待 24 小时** 。如果你更改了外部通信设置，最长需要等待 24 小时才能让更改传播到所有数据中心。
    
8. 向你的用户演示如何查找 Skype 联系人并将他们添加到其 Skype for Business 联系人列表。请指示他们查看[在 Skype for Business 中搜索人员](https://support.office.com/en-us/article/b12500ef-e37f-4d22-aade-c11277e53f19)。
    
## <a name="test-and-troubleshoot"></a>测试和故障排除

要测试你的设置，你需要一个不受你公司防火墙保护的 Skype 联系人。他们可以使用 Gmail 帐户、Outlook.com 帐户或其他类型的电子邮件帐户登录 Skype。
  
1. 在更改外部通信设置后， **直到等待 24 小时后再进行测试** 。
    
2. 注销 Skype for Business，然后重新登录，这样你会看到用于搜索 Skype Directory 的选项。 
    
    ![When Skype Directory is highlighted, you can search for people who have Skype accounts.](../images/76ee9fab-1ac3-4f4a-9569-f5f2606dbb7a.png)
  
3. 在 Skype for Business 中，搜索你的 Skype 联系人，然后发送聊天请求。 
    
    如果它不能由于公司策略发送的邮件，您需要仔细检查您的[防火墙设置](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)。 
    
4. 另一个测试问题是否出自你的防火墙的方法是在不受你的防火墙保护的 WiFi 位置（例如咖啡店）使用 Skype for Business 向你的 Skype 联系人发送聊天请求。 
    
  - **如果你向你的 Skype 联系人发送了请求，但他们从未收到** ，请要求他们向你发送聊天请求。如果问题是无法在 Skype 与 Skype for Business 之间建立连接，这样做通常会解决问题。
    
  - 此时如果在咖啡店里消息顺利传送，但不是在你工作的时候，那么问题出自你的防火墙。 
    
## <a name="what-you-can-and-cant-do"></a>可以执行的操作和不能执行的操作

- **Skype for Business在 Mac 中** 无法搜索 Skype 联系人并与之通信。
    
- 虽然您可以搜索并找到 Skype 用户，他们不能搜索和查找适用于业务用户的 Skype。 您必须将它们发送联系的请求，和他们必须在登录 Skype 和接受，才能与它们，您可以即时消息。 
    
- 不可能允许与其他 IM 提供商（如 Google 或 Facebook）建立 IM 连接。不能使用 Skype for Business 发送手机短信。
    
## <a name="what-features-are-available-when-adding-skype-contacts"></a>添加 Skype 联系人时可使用哪些功能？

Skype 联系人登录 Microsoft 帐户 (以前称为 Windows Live™ ID) 可以获得一些，但并不是所有的功能，当他们在与您的业务用户的 Skype。
  
|**对 Skype 联系人可用**|**对 Skype 联系人不可用**|
|:-----|:-----|
| 视频对话 <br/>  个人对个人的即时消息 <br/>  状态 <br/> | 多方 IM 对话 <br/>  与三人或多人的音频和视频对话 <br/>  桌面和程序共享 <br/> |
   
[!INCLUDE [LinkedIn Learning Info](../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a>相关主题

[允许用户联系外部 Skype for Business 用户](allow-users-to-contact-external-skype-for-business-users.md)
  
[设置 Skype for Business Online](set-up-skype-for-business-online.md)
