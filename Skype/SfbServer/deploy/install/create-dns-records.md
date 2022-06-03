---
title: 为Skype for Business Server创建 DNS 记录
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 798a663c-0b63-4f75-b0a3-9c553cef8c5f
description: 摘要：了解如何配置 DNS 并为安装Skype for Business Server创建 DNS 记录。
ms.openlocfilehash: 5e974df94aba8b879c672250b69432dfd0a5f1f3
ms.sourcegitcommit: e99471689ff60f9ab1095bc075f8b4c5569c9634
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860533"
---
# <a name="create-dns-records-for-skype-for-business-server"></a>为Skype for Business Server创建 DNS 记录
 
**总结：** 了解如何配置 DNS 并为安装Skype for Business Server创建 DNS 记录。
  
若要使Skype for Business Server正常工作，必须设置多个域名系统 (DNS) 设置。 这样，客户端就知道如何访问服务，并且服务器彼此了解。 每个部署只需完成一次这些设置，因为分配 DNS 条目后，它在整个域中可用。 可以按任何顺序执行步骤 1 到 5。 但是，必须按顺序执行步骤 6、7 和 8，步骤 1 到步骤 5 之后，如下图所述。 创建 DNS 记录包括步骤 5（共 8 个）。 有关规划 DNS 的详细信息，请参阅 [2019](../../../SfBServer2019/plan/system-requirements.md) Skype for Business Server Skype for Business Server或服务器要求[的环境要求](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)。
  
> [!IMPORTANT]
> 请务必注意，这只是如何在 Windows 服务器 DNS 环境中创建 DNS 记录的示例。 Skype for Business Server需要许多其他 DNS 条目，创建 DNS 记录的过程取决于用于管理组织中的 DNS 的系统。 有关 DNS 要求的完整列表，请参阅[Skype for Business Server的 DNS 要求](../../plan-your-deployment/network-requirements/dns.md)。 
  
![概述图。](../../media/d2fc733c-6a80-4d17-a02f-93b8c4bfb999.png)
  
## <a name="configure-dns"></a>配置 DNS

Skype for Business Server必须使用 DNS 记录才能正常工作，并且用户可以访问这些记录。
  
此示例使用名为 pool.contoso.local 的 DNS 负载均衡 FQDN。 此池由运行Skype for Business Server Enterprise Edition的三台服务器组成。 Standard Edition前端服务器只能包含单个服务器。 使用Standard Edition，在引用前端角色时，只能使用单Standard Edition服务器的完全限定域名 (FQDN) ，而不是创建 DNS 负载均衡的服务器池，如此示例所示。 此仅使用前端角色的简单示例包括下表中的 DNS 条目。 若要规划特定的 DNS 要求，请参阅[Skype for Business Server的 DNS 要求](../../plan-your-deployment/network-requirements/dns.md)。 
  
 
|**说明**|**记录类型**|**名称**|**解析为**|**负载均衡类型**|
|:-----|:-----|:-----|:-----|:-----|
|内部 Web 服务 FQDN  <br/> |A  <br/> |webint.contoso.local  <br/> |内部 Web 服务的 VIP  <br/> |支持的软件和硬件  <br/> |
|池 FQDN  <br/> |A  <br/> |pool.contoso.local  <br/> |服务器 SFB01 的 IP 地址  <br/> |DNS  <br/> |
|SFB01 FQDN  <br/> |A  <br/> |SFB01.contoso.local  <br/> |服务器 SFB01 的 IP 地址  <br/> |DNS  <br/> |
|池 FQDN  <br/> |A  <br/> |pool.contoso.local  <br/> |服务器 SFB02 的 IP 地址  <br/> |DNS  <br/> |
|SFB02 FQDN  <br/> |A  <br/> |SFB02.contoso.local  <br/> |服务器 SFB02 的 IP 地址  <br/> |DNS  <br/> |
|池 FQDN  <br/> |A  <br/> |pool.contoso.local  <br/> |服务器 SFB03 的 IP 地址  <br/> |DNS  <br/> |
|SFB03 FQDN  <br/> |A  <br/> |SFB03.contoso.local  <br/> |服务器 SFB03 的 IP 地址  <br/> |DNS  <br/> |
|Skype for Business自动发现  <br/> |A  <br/> |lyncdiscoverinternal.contoso.local  <br/> |内部 Web 服务的 VIP  <br/> |支持的软件和硬件  <br/> |
|会议简单 URL  <br/> |A  <br/> |meet.contoso.local  <br/> |内部 Web 服务的 VIP  <br/> |支持的软件和硬件  <br/> |
|拨入式简单 URL  <br/> |A  <br/> |dialin.contoso.local  <br/> |内部 Web 服务的 VIP  <br/> |支持的软件和硬件  <br/> |
|Web 计划程序简单 URL  <br/> |A  <br/> |scheduler.contoso.local  <br/> |内部 Web 服务的 VIP  <br/> |支持的软件和硬件  <br/> |
|管理简单 URL  <br/> |A  <br/> |admin.contoso.local  <br/> |内部 Web 服务的 VIP  <br/> |支持的软件和硬件  <br/> |
|旧发现  <br/> |SRV  <br/> |_sipinternaltls._tcp.contoso.local  <br/> |池 FQDN (端口 5061)   <br/> |不适用  <br/> |
   
### <a name="create-dns-records"></a>创建 DNS 记录

1. 登录到 DNS 服务器，并打开 **服务器管理器**。
    
2. 单击 **“工具”** 下拉菜单，然后单击 **“DNS**”。
    
3. 在 SIP 域的控制台树中，展开 **“向前查找区域**”，然后展开要在其中安装Skype for Business Server的 SIP 域。
    
4. 右键单击 SIP 域，然后选择 **“新建主机” (A 或 AAAA)**，如图所示。
    
     ![选择新的 A 记录。](../../media/f89c5c1f-b5b7-428c-a6e3-2bcd12e878c3.png)
  
5. 在 **“名称”** 框中，键入主机记录的名称 (域名将自动追加) 。
    
6. 在 **“IP 地址”框** 中，键入单个前端服务器的 IP 地址，然后选择 **“创建关联指针” (PTR) 记录** 或 **允许任何经过身份验证的用户更新具有相同所有者名称的 DNS 记录**（如果适用）。 请注意，这假定 DNS 用于对除 Web 服务外的所有流量进行负载均衡。 在此示例中，我们有三个前端服务器，如表中所示。
    
   |**服务器名称**|**类型**|**数据**|
   |:-----|:-----|:-----|
   |SFB01  <br/> |主机 (A)  <br/> |10.0.0.5  <br/> |
   |SFB02  <br/> |主机 (A)  <br/> |10.0.0.6  <br/> |
   |SFB03  <br/> |主机 (A)  <br/> |10.0.0.7  <br/> |
   
7. 接下来，为池创建 DNS 负载均衡条目。 DNS 负载均衡允许 DNS 使用相同的 DNS 池名称将请求发送到池中的各个服务器。 有关 DNS 和负载均衡的详细信息，请参阅[Skype for Business Server的 DNS 要求](../../plan-your-deployment/network-requirements/dns.md)。 
    
    > [!NOTE]
    > 将多个服务器汇集在一起仅在Enterprise Edition部署中可用。 如果要部署单个Enterprise服务器或Standard Edition服务器，则只需为单个服务器创建 A 记录。 
  
    例如，如果有一个名为 pool.contoso.local 的池和三个前端服务器，则会创建以下 DNS 条目：
    
   |**FQDN**|**类型**|**数据**|
   |:-----|:-----|:-----|
   |pool.contoso.local  <br/> |主机 (A)  <br/> |10.0.0.5  <br/> |
   |pool.contoso.local  <br/> |主机 (A)  <br/> |10.0.0.6  <br/> |
   |pool.contoso.local  <br/> |主机 (A)  <br/> |10.0.0.7  <br/> |
   
8. 继续为计划部署中的所有服务器创建 A 记录。 
    
9. 若要为旧发现创建服务记录 (SRV) 记录，请右键单击 SIP 域，然后选择 **“其他新记录**”。
    
10. 在“选择资源记录类型”中，单击“服务位置(SRV)”，然后单击“创建记录”。
    
11. 单击“服务”，然后键入 **_sipinternaltls**。
    
12. 单击“协议”，然后键入 **_tcp**。
    
13. 单击“端口号”，再键入“5061”。
    
14. 单击 **提供此服务的主机**，然后键入池或Standard Edition服务器的 FQDN。
    
     ![新资源记录对话框的屏幕截图。](../../media/54b1aac5-a2ec-41fe-90c0-02eaeaa9d1b4.png)
  
15. 单击“确定”，再单击“完成”。
    
### <a name="verify-dns-records"></a>验证 DNS 记录

1. 使用属于 Authenticated Users 组成员的帐户或具有等效权限的帐户登录到域中的客户端计算机。
    
2. 单击 **"开始"菜单**，然后键 **入 cmd**，然后按 Enter。
    
3. 键 **入 nslookup \<FQDN of the Front End pool\>** 或 **\<FQDN of the Standard Edition server or single Enterprise Edition server\>**，然后按 Enter。
    
4. 继续验证部署的其余 A 记录。
    
5. 如果支持旧客户端并创建了 SRV 记录，请在 **nslookup** 提示符处键入 **set type=srv** 进行验证，然后按 Enter。
    
6. 键 **入_sipinternaltls._tcp。 *域*** 例如， (_sipinternaltls._tcp.contoso.local) ，然后按 Enter。
    
7. 预期输出应与图中所示的输出类似。 请注意，并非所有 DNS 记录都显示在示例输出中，但应验证所有记录。 
    
     ![验证 dns 设置。](../../media/4fcaa70f-7717-4939-9652-d2048d6293cc.png)
  

