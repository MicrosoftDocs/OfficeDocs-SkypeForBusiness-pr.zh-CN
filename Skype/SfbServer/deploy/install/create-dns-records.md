---
title: 为 Skype for Business 服务器创建 DNS 记录
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 798a663c-0b63-4f75-b0a3-9c553cef8c5f
description: 摘要： 了解如何配置 DNS 和业务服务器创建 DNS 记录的 Skype 安装。 下载免费试用版 Skype 业务服务器从 Microsoft 评估中心，网址为： https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server。
ms.openlocfilehash: 35e8aecea74cc74cda6ea086a1765642885a091e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30890681"
---
# <a name="create-dns-records-for-skype-for-business-server"></a>为 Skype for Business 服务器创建 DNS 记录
 
**摘要：** 了解如何配置 DNS 和业务服务器创建 DNS 记录的 Skype 安装。 下载免费试用版 Skype 业务服务器从 Microsoft 评估中心，网址为： [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)。
  
为业务服务器可以正常运行的 Skype，大量域名系统 (DNS) 设置必须就地。 从而使客户端知道该如何访问服务以及让服务器知道相互之间的情况。 每个部署仅需完成一次此类设置，因为在您分配 DNS 条目之后，该条目便在整个域中可用。 第 1 步至第 5 步可以按任意顺序执行。 但是，第 6、7、8 步必须在第 1 步至第 5 步之后按图表所示顺序执行。 创建 DNS 记录是 8 个步骤中的第 5 步。 有关规划 DNS 的详细信息，请参阅[环境要求 Skype 业务服务器](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)或[服务器要求的业务服务器 2019 Skype](../../../SfBServer2019/plan/system-requirements.md)。
  
> [!IMPORTANT]
> 请注意，这只是一个有关如何在 Windows Server DNS 环境中创建 DNS 记录的示例。 有许多其他所需的 Skype 业务服务器的 DNS 项，创建 DNS 记录的过程取决于您使用您的组织中管理 DNS 系统。 有关 DNS 要求的完整列表，请参阅[Skype 业务服务器的 DNS 要求](../../plan-your-deployment/network-requirements/dns.md)。 
  
![概述图表](../../media/d2fc733c-6a80-4d17-a02f-93b8c4bfb999.png)
  
## <a name="configure-dns"></a>配置 DNS

DNS 记录所需的 Skype 业务服务器能正常工作，可以访问用户。
  
在此示例中，我们使用名为 pool.contoso.local 并经过 DNS 负载平衡的 FQDN。 此池包含业务 Server Enterprise edition 运行 Skype 的三个服务器。 Standard Edition 前端服务器仅可包含一台服务器。 如果使用 Standard Edition，在引用前端角色（而非创建经过 DNS 负载平衡的服务器池）时，您将仅使用单台 Standard Edition 服务器的完全限定域名 (FQDN)，如该示例所示。 该简单示例仅使用前端角色，其包含了下表中的 DNS 条目。 若要规划您的特定 DNS 要求，请参阅[Skype 业务服务器的 DNS 要求](../../plan-your-deployment/network-requirements/dns.md)。 
  
 
|**说明**|**记录类型**|**名称** - 按 WAN 链路进行筛选（筛选器位于图形右侧）。|**解析为**|**负载平衡类型**|
|:-----|:-----|:-----|:-----|:-----|
|内部 Web 服务 FQDN  <br/> |A  <br/> |webint.contoso.local  <br/> |VIP 的内部 Web 服务  <br/> |支持的软硬件  <br/> |
|池 FQDN  <br/> |A  <br/> |pool.contoso.local  <br/> |服务器 SFB01 IP 地址  <br/> |DNS  <br/> |
|SFB01 FQDN  <br/> |A  <br/> |SFB01.contoso.local  <br/> |服务器 SFB01 IP 地址  <br/> |DNS  <br/> |
|池 FQDN  <br/> |A  <br/> |pool.contoso.local  <br/> |服务器 SFB02 IP 地址  <br/> |DNS  <br/> |
|SFB02 FQDN  <br/> |A  <br/> |SFB02.contoso.local  <br/> |服务器 SFB02 IP 地址  <br/> |DNS  <br/> |
|池 FQDN  <br/> |A  <br/> |pool.contoso.local  <br/> |服务器 SFB03 IP 地址  <br/> |DNS  <br/> |
|SFB03 FQDN  <br/> |A  <br/> |SFB03.contoso.local  <br/> |服务器 SFB03 IP 地址  <br/> |DNS  <br/> |
|Skype 的业务自动发现  <br/> |A  <br/> |lyncdiscoverinternal.contoso.local  <br/> |VIP 的内部 Web 服务  <br/> |支持的软硬件  <br/> |
|会议简单 URL  <br/> |A  <br/> |meet.contoso.local  <br/> |VIP 的内部 Web 服务  <br/> |支持的软硬件  <br/> |
|电话拨入式简单 URL  <br/> |A  <br/> |dialin.contoso.local  <br/> |VIP 的内部 Web 服务  <br/> |支持的软硬件  <br/> |
|Web 计划程序简单 URL  <br/> |A  <br/> |scheduler.contoso.local  <br/> |VIP 的内部 Web 服务  <br/> |支持的软硬件  <br/> |
|管理简单 URL  <br/> |A  <br/> |admin.contoso.local  <br/> |VIP 的内部 Web 服务  <br/> |支持的软硬件  <br/> |
|旧的发现  <br/> |SRV  <br/> |_sipinternaltls._tcp.contoso.local  <br/> |池 FQDN （端口 5061）  <br/> |不适用  <br/> |
   
### <a name="create-dns-records"></a>创建 DNS 记录

1. 登录到 DNS 服务器，并打开**服务器管理器**。
    
2. 单击**工具**下拉列表菜单，然后单击**DNS**。
    
3. 在您的 SIP 域的控制台树中，展开**正向查找区域**，，然后展开将在安装 Skype 业务服务器的 SIP 域。
    
4. 右键单击 SIP 域，然后选择**新建主机 （A 或 AAAA）**，如图所示。
    
     ![选择新的 A 记录](../../media/f89c5c1f-b5b7-428c-a6e3-2bcd12e878c3.png)
  
5. 在**名称**框中，键入主机记录 （将会自动追加域名） 的名称。
    
6. **IP 地址框**中，键入单个前端服务器的 IP 地址，然后选择**创建相关的指针 (PTR) 记录**或**允许任何身份验证的用户更新 DNS 记录具有相同所有者名称**，如果适用。 请注意，此，假定，使用 DNS 负载平衡 web 服务除外的所有通信。 本示例中，我们已三台前端服务器，如下表所示。
    
   |**服务器名称**|**类型**|**数据**|
   |:-----|:-----|:-----|
   |SFB01  <br/> |主机 (A)  <br/> |10.0.0.5  <br/> |
   |SFB02  <br/> |主机 (A)  <br/> |10.0.0.6  <br/> |
   |SFB03  <br/> |主机 (A)  <br/> |10.0.0.7  <br/> |
   
7. 接下来，创建 DNS 负载平衡的池的条目。 DNS 负载平衡允许 DNS 以使用相同 DNS 池名称时将请求发送到池中的各个服务器。 有关 DNS 和负载平衡的详细信息，请参阅[Skype 业务服务器的 DNS 要求](../../plan-your-deployment/network-requirements/dns.md)。 
    
    > [!NOTE]
    > 在一起池多台服务器是仅在 Enterprise Edition 部署中可用。 如果要部署的单个企业服务器或 Standard Edition 服务器，您需要创建仅为单个服务器的 A 记录。 
  
    例如，如果必须名为 pool.contoso.local 和三个前端服务器池，您将创建以下 DNS 条目：
    
   |**FQDN**|**类型**|**数据**|
   |:-----|:-----|:-----|
   |pool.contoso.local  <br/> |主机 (A)  <br/> |10.0.0.5  <br/> |
   |pool.contoso.local  <br/> |主机 (A)  <br/> |10.0.0.6  <br/> |
   |pool.contoso.local  <br/> |主机 (A)  <br/> |10.0.0.7  <br/> |
   
8. 继续在计划部署中创建的所有服务器的 A 记录。 
    
9. 要创建旧发现服务记录 (SRV) 记录，请右键单击 SIP 域，并选择**其他新记录**。
    
10. 在**选择资源记录类型**，单击**服务位置 (SRV)**，，然后单击**创建记录**。
    
11. 单击**服务**，然后键入 **_sipinternaltls**。
    
12. 单击**协议**，，然后键入 **_tcp**。
    
13. 单击**端口号**，然后键入**5061**。
    
14. 单击**主机提供此服务**，，然后键入池或 Standard Edition server 的 FQDN。
    
     ![“新资源记录”对话框的屏幕截图。](../../media/54b1aac5-a2ec-41fe-90c0-02eaeaa9d1b4.png)
  
15. 单击**确定**，，然后单击**完成**。
    
### <a name="verify-dns-records"></a>验证 DNS 记录

1. 登录到 Authenticated Users 组的成员或具有同等权限的帐户的域中的客户端计算机上。
    
2. 单击**开始**，然后键入**cmd**，并按 Enter。
    
3. 类型**nslookup\<的前端池的 FQDN\>** 或**\<Standard Edition server 或单个 Enterprise Edition server 的 FQDN\>**，然后按 Enter。
    
4. 继续验证您部署的 A 记录的其余部分。
    
5. 如果要支持旧客户端和创建的 SRV 记录，键入以下命令以验证它**设置类型 = srv**在**nslookup**提示符处，然后按 Enter。
    
6. 键入 **_sipinternaltls._tcp。*域***(例如，_sipinternaltls._tcp.contoso.local)，然后按 Enter。
    
7. 预期的输出应类似于图所示。 请注意，不是所有的 DNS 记录所示的示例输出，但应验证所有记录。 
    
     ![验证 dns 设置。](../../media/4fcaa70f-7717-4939-9652-d2048d6293cc.png)
  

