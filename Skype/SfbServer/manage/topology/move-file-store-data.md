---
title: 将文件存储数据移动到 Skype for Business 服务器中的新文件存储
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8d1d5819-add2-4f5d-a436-74c00a281df0
description: 如果你需要删除当前充当 Skype for Business Server 部署的文件存储的文件服务器，或者你需要进行其他更改以使当前文件存储不可用，你首先需要创建新的共享。 然后需要执行以下步骤：
ms.openlocfilehash: 6ae09d2415b24a4337edbee3c66e8b9a8bd2009a
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991507"
---
# <a name="move-file-store-data-to-a-new-file-store-in-skype-for-business-server"></a>将文件存储数据移动到 Skype for Business 服务器中的新文件存储

如果你需要删除当前充当 Skype for Business Server 部署的文件存储的文件服务器，或者你需要进行其他更改以使当前文件存储不可用，你首先需要创建新的共享。 然后需要执行以下步骤：

1. 关闭使用您打算删除的文件存储的 Skype for Business 服务器服务。

2. 在拓扑生成器中定义文件存储并发布更改，使新文件存储可用于你的部署。

3. 将数据移动到新的文件存储。

4. 重新启动服务器或服务。

5. （可选）删除旧的文件共享和文件夹。

### <a name="to-move-file-store-data-from-one-file-store-to-a-new-file-store"></a>将文件存储数据从一个文件存储移动到新文件存储

1. 以 RTCUniversersalServerAdmins 或 CsServerAdministrator 组成员的身份登录到计算机，其中安装了 Skype for Business 服务器、管理工具。

2.  打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。

3. 在左侧导航栏中，单击“**拓扑**”，然后单击“**状态**”。

4. 对于每个使用你计划删除的文件存储的 Director 池、主管、标准版服务器和前端池，选择服务器或池，单击 "**操作**"，然后单击 "**停止所有服务**"。

5. 以 Domain Admins 组和 RTCUniversalServerAdmins 组成员的身份登录安装了拓扑生成器的计算机。

6. 启动拓扑生成器：单击 "**开始**"，单击 "**所有程序**"，单击 "skype for business**服务器**"，然后单击 " **skype for business 服务器拓扑生成器**"。

7. 选择使用文件存储的服务器或池，然后执行以下操作：

   a. 右键单击服务器或池，然后单击“**编辑属性**”。

   b. 在“**编辑属性**”中的“**关联**”下的“**文件存储**”下面，单击“**新建**”。

   c. 在“**定义新文件存储**”中的“**文件服务器 FQDN**”下，键入文件服务器的完全限定域名 (FQDN)。 在“**文件共享**”下，键入新文件共享的文件夹名称，然后单击“**确定**”。

    > [!IMPORTANT]
    > 此步骤定义要在拓扑生成器中使用的新文件存储。 只需定义一次，无需针对每台服务器定义。 发布拓扑之前，必须在定义的文件服务器上创建定义的文件共享。 有关详细信息，请参阅[Define the File Store for the Front End](https://technet.microsoft.com/library/90994400-c4e5-4509-af41-121ac716fbca.aspx)。

8. 对于每个使用文件存储的服务器或池，执行以下操作：

   a. 右键单击服务器或池，然后单击“**编辑属性**”。

   b. 在“**编辑属性**”中的“**关联**”下面的“**文件存储**”中，选择新的文件共享，然后单击“**确定**”。

9. 发布拓扑，检查复制状态，然后根据需要运行 Skype for Business 服务器部署向导。 有关详细信息，请参阅[Common Procedures for Removing Lync Servers and Components](https://technet.microsoft.com/library/5438ce1e-57fa-4031-8bdb-3af6581d901b.aspx)。

10. 启动命令提示符：单击 "**开始**"，单击 "**运行**"，然后键入 cmd.exe。

11. 在命令行中键入：

     ```console
     Robocopy \\<OldFileServer>\<OldShare> \\<NewFileServer>\<NewShare> /S /R:10 /W:10 /XF Meeting.Active /MT /LOG:<directory path\logname>

     ```

    > [!TIP]
    > /S 开关复制文件、目录和子目录。 /XF 开关跳过名为 Meeting.Active 的所有文件。 带有 /MT 开关的 robocopy.exe 的当前版本通过使用多个线程大大提高了复制速度。 对于/LOG 开关，使用 C:\Logfiles\log.txt. 形式的目录路径和日志文件名 该开关可在指定位置创建操作的日志文件。

12. 数据复制完成后，在 Lync Server 控制面板中单击 "**拓扑**"，然后单击 "**状态**"。

13. 对于已停止服务的每个服务器或池，选择该服务器或池，单击“**操作**”，然后单击“**启动所有服务**”。

14. 从拓扑中删除旧文件存储，然后发布拓扑。有关详细信息，请参阅[Remove a file store](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx)。

15. （可选）以本地 Administrators 组或 Domain Admins 组的成员身份登录到包含你刚删除的文件存储的计算机，然后删除旧文件共享和目录。

## <a name="see-also"></a>另请参阅


[将服务器重新分配到其他文件存储](https://technet.microsoft.com/library/18509cce-a4d2-4537-a822-f99de6d7598e.aspx)

[删除文件存储](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx)

