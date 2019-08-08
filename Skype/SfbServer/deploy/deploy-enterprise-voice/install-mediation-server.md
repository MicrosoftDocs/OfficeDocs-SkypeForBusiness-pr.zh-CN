---
title: 在 Skype for Business Server 中安装中介服务器的文件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
description: '摘要: 了解如何在 Skype for Business Server 中为中介服务器安装文件。'
ms.openlocfilehash: b73832586ba4a09cc51f67bddcaf30c2f85fcca1
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240295"
---
# <a name="install-the-files-for-mediation-server-in-skype-for-business-server"></a>在 Skype for Business Server 中安装中介服务器的文件
 
**摘要:** 了解如何在 Skype for Business Server 中为中介服务器安装文件。
  
要成功完成此过程，应至少以本地管理员身份和至少在 RTCUniversalReadOnlyAdmins 组中具有成员身份的域用户身份登录服务器。
  
使用本主题中的步骤运行 Skype for Business 服务器部署向导, 以便在已使用拓扑生成器定义和发布池后添加到中介服务器池中的计算机上安装中介服务器的文件。 在安装 "中介服务器" 时, 你还可以在中介服务器池中安装和分配每台计算机所需的证书。 
  
> [!NOTE]
> 本主题假定你已在拓扑中定义并发布了独立的中介服务器池, 如在[Skype for Business 服务器的拓扑生成器中部署中介服务器](deploy-a-mediation-server.md)中所述。 
  
### <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a>为独立的中介服务器池安装文件

1. 在安装媒体中, 右键单击_ \<"安装媒体\> _ **\Setup\amd64\Setup.exe**", 然后单击 "以**管理员身份运行**"。
    
2. 在“安装位置”**** 页上，单击“确定”****。
    
3. 在“最终用户许可协议”**** 页上，单击“我接受”****，然后单击“确定”****。（必须单击该按钮才能继续。）
    
4. 在 " **Skype For Business 服务器部署向导**" 页面上, 单击 "**安装或更新 Skype For business 服务器系统**"。
    
5. 单击“步骤 1: 安装本地配置存储”**** 旁边的“运行”****，然后按照屏幕上的说明进行操作。
    
6. 在“配置中央管理存储的本地副本”**** 页上，接受默认的“直接从中央管理存储检索”****，然后单击“下一步”****。
    
7. 在“正在执行命令”**** 页上，当任务状态显示为“已完成”**** 时，单击“完成”****。
    
8. 在 "**步骤 2: 设置" 或 "删除 Skype For Business 服务器组件**" 旁边, 单击 "**运行**", 然后单击 "**下一步**"。
    
9. 在“正在执行命令”**** 页上，当任务状态显示为“已完成”**** 时，单击“完成”****。
    
10. 单击“步骤 3: 请求、安装或分配证书”**** 旁边的“运行”****。按照屏幕上的说明进行操作，接受默认设置。中介服务器需要一个证书，因此要运行“步骤 3”**** 两次：第一次是颁发所需证书，第二次是分配该证书。
    
11. 正确颁发并分配证书后，在“步骤 4: 启动服务”**** 旁边，单击“运行”****，然后按照屏幕上的说明进行操作。
    
12. 成功完成“步骤 4”**** 后，重新启动服务器，然后以 DomainAdmins 组的成员身份登录到服务器。
    
13. 在运行 Skype for business Server 控制面板的计算机上, 验证中介服务器的服务状态显示为绿色复选标记的 Skype for business Server 控制面板的 "**拓扑**" 页面。 如果显示红色 X，请选择相应的中介服务器。 在“操作”**** 菜单上，单击“启动所有服务”****。 
    
如果向中介服务器池添加了多台计算机, 请在中介服务器池中的所有其他计算机上执行此过程中的步骤。 如果不需要为任何其他计算机安装中介服务器的文件, 请按照在[Skype For Business 服务器中配置中继](configure-trunks.md)中的过程配置此中介服务器池 (或所有中介) 之间的中继连接设置。站点上的服务器) 及其对等。

