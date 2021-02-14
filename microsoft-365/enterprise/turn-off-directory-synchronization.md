---
title: Microsoft 365에 대한 디렉터리 동기화 끄기
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED150
ms.assetid: ee5f861e-bd48-4267-83d1-a4ead4b4a00d
description: 이 문서에서는 PowerShell을 사용하여 Microsoft 365에 대한 디렉터리 동기화를 해제하는 방법을 찾아야 합니다.
ms.openlocfilehash: 0bd8591f91dcf20cb1061b3cd93f69511027bab1
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46692260"
---
# <a name="turn-off-directory-synchronization-for-microsoft-365"></a><span data-ttu-id="88140-103">Microsoft 365에 대한 디렉터리 동기화 끄기</span><span class="sxs-lookup"><span data-stu-id="88140-103">Turn off directory synchronization for Microsoft 365</span></span>
<span data-ttu-id="88140-104">PowerShell을 사용하여 디렉터리 동기화를 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88140-104">You can use PowerShell to turn off directory synchronization.</span></span> <span data-ttu-id="88140-105">그러나 문제 해결 단계로 디렉터리 동기화를 해제하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="88140-105">However, it is not recommended that you turn off directory synchronization as a troubleshooting step.</span></span> <span data-ttu-id="88140-106">디렉터리 동기화 문제 해결에 대한 도움이 필요한 경우 [Microsoft 365](fix-problems-with-directory-synchronization.md) 문서의 디렉터리 동기화 문제 해결을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="88140-106">If you need assistance with troubleshooting directory synchronization, see the [Fixing problems with directory synchronization for Microsoft 365](fix-problems-with-directory-synchronization.md) article.</span></span> 
  
<span data-ttu-id="88140-107">[필요한 경우](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) 비즈니스 제품에 대한 지원에 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="88140-107">[Contact support](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) for business products if needed.</span></span>
  
## <a name="turn-off-directory-synchronization"></a><span data-ttu-id="88140-108">디렉터리 동기화 끄기</span><span class="sxs-lookup"><span data-stu-id="88140-108">Turn off directory synchronization</span></span>  
<span data-ttu-id="88140-109">디렉터리 동기화를 끄기 위해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="88140-109">To turn off Directory synchronization:</span></span>
  
1. <span data-ttu-id="88140-110">먼저 필요한 소프트웨어를 설치하고 Microsoft 365 구독에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="88140-110">First, install the required software and connect to your Microsoft 365 subscription.</span></span> <span data-ttu-id="88140-111">자세한 내용은 Microsoft [Azure Active Directory 모듈을](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)사용하여 연결하여 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="88140-111">For instructions, see [Connect with the Microsoft Azure Active Directory Module for Windows PowerShell](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
    
2. <span data-ttu-id="88140-112">[Set-MsolDirSyncEnabled를](https://go.microsoft.com/fwlink/p/?LinkId=821939) 사용하여 디렉터리 동기화를 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88140-112">Use [Set-MsolDirSyncEnabled](https://go.microsoft.com/fwlink/p/?LinkId=821939) to disable directory synchronization:</span></span> 
    
  ```powershell
  Set-MsolDirSyncEnabled -EnableDirSync $false
  ```

>[!Note]
><span data-ttu-id="88140-113">이 명령을 사용하는 경우 디렉터리 동기화를 다시 켜기 전에 72시간을 기다려야 합니다.</span><span class="sxs-lookup"><span data-stu-id="88140-113">If you use this command, you must wait 72 hours before you can turn directory synchronization back on.</span></span>
>
 
