---
title: 为 Skype for Business 服务器创建 DNS 记录
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 798a663c-0b63-4f75-b0a3-9c553cef8c5f
description: '摘要: 了解如何为安装 Skype for Business 服务器配置 DNS 和创建 DNS 记录。 从 Microsoft 评估中心下载免费试用版 Skype for Business 服务器, 网址为: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server。'
ms.openlocfilehash: b5b36ffb55077e20a4c7a70c7e086c5596673f9f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34306645"
---
# <a name="create-dns-records-for-skype-for-business-server"></a>为 Skype for Business 服务器创建 DNS 记录
 
**摘要:** 了解如何为 Skype for business 服务器的安装配置 DNS 和创建 DNS 记录。 从 Microsoft 评估中心下载免费试用版 Skype for Business 服务器, 网址为: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)。
  
要使 Skype for Business 服务器正常工作, 必须有多个域名系统 (DNS) 设置。 从而使客户端知道该如何访问服务以及让服务器知道相互之间的情况。 每个部署仅需完成一次此类设置，因为在您分配 DNS 条目之后，该条目便在整个域中可用。 第 1 步至第 5 步可以按任意顺序执行。 但是，第 6、7、8 步必须在第 1 步至第 5 步之后按图表所示顺序执行。 创建 DNS 记录是 8 个步骤中的第 5 步。 有关规划 DNS 的详细信息, 请参阅适用于 Skype for business Server 2019 的 Skype for business 服务器或[服务器要求](../../../SfBServer2019/plan/system-requirements.md)[的环境要求](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)。
  
> [!IMPORTANT]
> 请注意，这只是一个有关如何在 Windows Server DNS 环境中创建 DNS 记录的示例。 Skype for Business 服务器需要多个其他 DNS 条目, 并且创建 DNS 记录的过程取决于用于管理组织中的 DNS 的系统。 有关 DNS 要求的完整列表, 请参阅[Skype for Business 服务器的 DNS 要求](../../plan-your-deployment/network-requirements/dns.md)。 
  
![概述图表](../../media/d2fc733c-6a80-4d17-a02f-93b8c4bfb999.png)
  
## <a name="configure-dns"></a>配置 DNS

要使 Skype for Business 服务器正常工作并可供用户访问, 需要 DNS 记录。
  
在此示例中，我们使用名为 pool.contoso.local 并经过 DNS 负载平衡的 FQDN。 此池由运行 Skype for business Server 企业版的三台服务器组成。 Standard Edition 前端服务器仅可包含一台服务器。 如果使用 Standard Edition，在引用前端角色（而非创建经过 DNS 负载平衡的服务器池）时，您将仅使用单台 Standard Edition 服务器的完全限定域名 (FQDN)，如该示例所示。 该简单示例仅使用前端角色，其包含了下表中的 DNS 条目。 若要规划特定的 DNS 要求, 请参阅[Skype for Business 服务器的 DNS 要求](../../plan-your-deployment/network-requirements/dns.md)。 
  
 
|**说明**|**记录类型**|**名称** - 按 WAN 链路进行筛选（筛选器位于图形右侧）。|**解析为**|**负载平衡类型**|
|:-----|:-----|:-----|:-----|:-----|
|内部 Web 服务 FQDN  <br/> |A  <br/> |webint.contoso.local  <br/> |内部 Web 服务的 VIP  <br/> |支持的软件和硬件  <br/> |
|池 FQDN  <br/> |A  <br/> |contoso. 本地  <br/> |服务器 SFB01 的 IP 地址  <br/> |DNS  <br/> |
|SFB01 FQDN  <br/> |A  <br/> |SFB01  <br/> |服务器 SFB01 的 IP 地址  <br/> |DNS  <br/> |
|池 FQDN  <br/> |A  <br/> |contoso. 本地  <br/> |服务器 SFB02 的 IP 地址  <br/> |DNS  <br/> |
|SFB02 FQDN  <br/> |A  <br/> |SFB02  <br/> |服务器 SFB02 的 IP 地址  <br/> |DNS  <br/> |
|池 FQDN  <br/> |A  <br/> |contoso. 本地  <br/> |服务器 SFB03 的 IP 地址  <br/> |DNS  <br/> |
|SFB03 FQDN  <br/> |A  <br/> |SFB03  <br/> |服务器 SFB03 的 IP 地址  <br/> |DNS  <br/> |
|Skype for Business 自动发现  <br/> |A  <br/> |lyncdiscoverinternal  <br/> |内部 Web 服务的 VIP  <br/> |支持的软件和硬件  <br/> |
|会议简单 URL  <br/> |A  <br/> |满足 contoso 本地的要求  <br/> |内部 Web 服务的 VIP  <br/> |支持的软件和硬件  <br/> |
|拨入式简单 URL  <br/> |A  <br/> |本地拨入 contoso。  <br/> |内部 Web 服务的 VIP  <br/> |支持的软件和硬件  <br/> |
|Web 计划程序简单 URL  <br/> |A  <br/> |本地调度。 contoso  <br/> |内部 Web 服务的 VIP  <br/> |支持的软件和硬件  <br/> |
|管理简单 URL  <br/> |A  <br/> |本地管理员  <br/> |内部 Web 服务的 VIP  <br/> |支持的软件和硬件  <br/> |
|旧版发现  <br/> |SRV  <br/> |_sipinternaltls _tcp  <br/> |池 FQDN (端口 5061)  <br/> |不适用  <br/> |
   
### <a name="create-dns-records"></a>创建 DNS 记录

1. 登录到 DNS 服务器, 然后打开**服务器管理器**。
    
2. 单击 "**工具**" 下拉菜单, 然后单击 " **DNS**"。
    
3. 在你的 SIP 域的控制台树中, 展开 "**正向查找区域**", 然后展开将在其中安装 Skype For business 服务器的 SIP 域。
    
4. 右键单击 SIP 域, 然后选择 "**新建主机 (A 或 AAAA)**", 如图所示。
    
     ![选择新的 A 记录](../../media/f89c5c1f-b5b7-428c-a6e3-2bcd12e878c3.png)
  
5. 在 "**名称**" 框中, 键入主机记录的名称 (将自动追加域名)。
    
6. 在 " **IP 地址" 框**中, 键入单个前端服务器的 IP 地址, 然后选择 "**创建关联的指针 (PTR) 记录**" 或 **"允许任何经过身份验证的用户使用同一所有者名称更新 DNS 记录**" (如果适用)。 请注意, 这假定在 web 服务例外情况下, 使用 DNS 对所有流量进行负载平衡。 在此示例中, 我们有三个前端服务器, 如表中所示。
    
   |**服务器名称**|**类型**|**数据**|
   |:-----|:-----|:-----|
   |SFB01  <br/> |主机 (A)  <br/> |10.0.0.5  <br/> |
   |SFB02  <br/> |主机 (A)  <br/> |10.0.0.6  <br/> |
   |SFB03  <br/> |主机 (A)  <br/> |10.0.0.7  <br/> |
   
7. 接下来, 为池创建 DNS 负载平衡条目。 DNS 负载平衡允许 DNS 将请求发送到池中的单个服务器, 同时使用相同的 DNS 池名称。 有关 DNS 和负载平衡的详细信息, 请参阅[Skype for Business 服务器的 DNS 要求](../../plan-your-deployment/network-requirements/dns.md)。 
    
    > [!NOTE]
    > 将多台服务器汇集在一起仅在企业版部署中可用。 如果要部署单个企业服务器或标准版服务器, 则只需为单个服务器创建一条记录。 
  
    例如, 如果你有一个名为 "pool. 本地和三台前端服务器" 的池, 你将创建以下 DNS 条目:
    
   |**域名**|**类型**|**数据**|
   |:-----|:-----|:-----|
   |contoso. 本地  <br/> |主机 (A)  <br/> |10.0.0.5  <br/> |
   |contoso. 本地  <br/> |主机 (A)  <br/> |10.0.0.6  <br/> |
   |contoso. 本地  <br/> |主机 (A)  <br/> |10.0.0.7  <br/> |
   
8. 继续为计划部署中的所有服务器创建记录。 
    
9. 若要创建旧发现的服务记录 (SRV) 记录, 请右键单击 SIP 域, 然后选择 "**其他新记录**"。
    
10. 在 "**选择资源记录类型**" 中, 单击 "**服务位置 (SRV)**", 然后单击 "**创建记录**"。
    
11. 单击 "**服务**", 然后键入 " **_sipinternaltls**"。
    
12. 单击 "**协议**", 然后键入 " **_tcp**"。
    
13. 单击 "**端口号**", 然后键入**5061**。
    
14. 单击 "**主机提供此服务**", 然后键入池或标准版服务器的 FQDN。
    
     ![“新资源记录”对话框的屏幕截图。](../../media/54b1aac5-a2ec-41fe-90c0-02eaeaa9d1b4.png)
  
15. 单击 **"确定**", 然后单击 "**完成**"。
    
### <a name="verify-dns-records"></a>验证 DNS 记录

1. 使用已验证用户组的成员的帐户登录到域中的客户端计算机或具有同等权限。
    
2. 单击 "**开始**", 然后键入**cmd**, 然后按 enter。
    
3. 键入 **" \<nslookup FQDN"\> ** ( ** \<标准版服务器或单个企业版服务器\>**) 的前端池或 fqdn, 然后按 enter。
    
4. 继续验证你的部署的其他记录。
    
5. 如果你支持旧版客户端并创建了 SRV 记录, 请通过在**nslookup**提示符处键入 " **set type = SRV** " 来验证它, 然后按 enter。
    
6. 键入 **_sipinternaltls。 _tcp。*域***(例如, _sipinternaltls), 然后按 Enter。
    
7. 预期输出应类似于图中所示的输出。 请注意, 并非所有 DNS 记录都显示在示例输出中, 但应验证所有记录。 
    
     ![验证 dns 设置。](../../media/4fcaa70f-7717-4939-9652-d2048d6293cc.png)
  

