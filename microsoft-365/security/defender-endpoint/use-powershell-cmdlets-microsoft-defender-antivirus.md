---
title: PowerShell cmdlet을 사용하여 Microsoft Defender AV 구성 및 실행
description: Windows 10에서는 PowerShell cmdlet을 사용하여 검색을 실행하고, 보안 인텔리전스를 업데이트하고, Microsoft Defender 바이러스 백신의 설정을 변경할 수 있습니다.
keywords: 검사, 명령줄, mpcmdrun, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 07/23/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.openlocfilehash: d6fb8dc510e004fa88bf99583cc2cc33ae8c63bb
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765302"
---
# <a name="use-powershell-cmdlets-to-configure-and-manage-microsoft-defender-antivirus"></a><span data-ttu-id="af967-104">PowerShell cmdlet을 사용하여 Microsoft Defender 바이러스 백신 구성 및 관리</span><span class="sxs-lookup"><span data-stu-id="af967-104">Use PowerShell cmdlets to configure and manage Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="af967-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="af967-105">**Applies to:**</span></span>

- <span data-ttu-id="af967-106">[엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/) </span><span class="sxs-lookup"><span data-stu-id="af967-106">[Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)</span></span>

<span data-ttu-id="af967-107">PowerShell을 사용하여 여러 기능을 수행할 수 Windows Defender.</span><span class="sxs-lookup"><span data-stu-id="af967-107">You can use PowerShell to perform various functions in Windows Defender.</span></span> <span data-ttu-id="af967-108">명령 프롬프트 또는 명령줄과 마찬가지로 PowerShell은 특히 시스템 관리용으로 설계된 작업 기반 명령줄 셸 및 스크립팅 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="af967-108">Similar to the command prompt or command line, PowerShell is a task-based command-line shell and scripting language designed especially for system administration.</span></span> <span data-ttu-id="af967-109">자세한 내용은 [MSDN의 PowerShell 허브에서 읽어 볼 수 있습니다.](/previous-versions/msdn10/mt173057(v=msdn.10))</span><span class="sxs-lookup"><span data-stu-id="af967-109">You can read more about it at the [PowerShell hub on MSDN](/previous-versions/msdn10/mt173057(v=msdn.10)).</span></span>

<span data-ttu-id="af967-110">cmdlet 및 해당 기능 및 사용 가능한 매개 변수 목록은 [Defender cmdlets 항목을 참조하세요.](/powershell/module/defender)</span><span class="sxs-lookup"><span data-stu-id="af967-110">For a list of the cmdlets and their functions and available parameters, see the [Defender cmdlets](/powershell/module/defender) topic.</span></span>

<span data-ttu-id="af967-111">PowerShell cmdlet은 GUI(그래픽 사용자 인터페이스)를 사용하여 소프트웨어를 구성하지 않는 Windows Server 환경에서 가장 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="af967-111">PowerShell cmdlets are most useful in Windows Server environments that don't rely on a graphical user interface (GUI) to configure software.</span></span>

> [!NOTE]
> <span data-ttu-id="af967-112">PowerShell cmdlet은 [Microsoft Endpoint Configuration Manager,](/configmgr)그룹 정책 관리 콘솔 또는 Microsoft [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))Defender 바이러스 백신 그룹 정책 [ADMX](https://www.microsoft.com/download/101445)템플릿과 같은 전체 네트워크 정책 관리 인프라를 대체하는 것으로 사용되어선 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af967-112">PowerShell cmdlets should not be used as a replacement for a full network policy management infrastructure, such as [Microsoft Endpoint Configuration Manager](/configmgr), [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), or [Microsoft Defender Antivirus Group Policy ADMX templates](https://www.microsoft.com/download/101445).</span></span>

<span data-ttu-id="af967-113">PowerShell을 사용하여 변경한 내용은 변경 내용이 배포되거나 적용된 끝점의 로컬 설정에 영향을 미치게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af967-113">Changes made with PowerShell will affect local settings on the endpoint where the changes are deployed or made.</span></span> <span data-ttu-id="af967-114">즉, 그룹 정책, Microsoft Endpoint Configuration Manager 또는 Microsoft Intune을 사용하여 정책을 배포하면 PowerShell을 사용하여 변경한 내용을 덮어 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af967-114">This means that deployments of policy with Group Policy, Microsoft Endpoint Configuration Manager, or Microsoft Intune can overwrite changes made with PowerShell.</span></span>

<span data-ttu-id="af967-115">로컬 정책 다시 설정으로 로컬로 다시 정할 수 있는 설정을 [구성할 수 있습니다.](configure-local-policy-overrides-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="af967-115">You can [configure which settings can be overridden locally with local policy overrides](configure-local-policy-overrides-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="af967-116">PowerShell은 일반적으로 폴더 아래에 `%SystemRoot%\system32\WindowsPowerShell` 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="af967-116">PowerShell is typically installed under the folder `%SystemRoot%\system32\WindowsPowerShell`.</span></span>

## <a name="use-microsoft-defender-antivirus-powershell-cmdlets"></a><span data-ttu-id="af967-117">Microsoft Defender 바이러스 백신 PowerShell cmdlet 사용</span><span class="sxs-lookup"><span data-stu-id="af967-117">Use Microsoft Defender Antivirus PowerShell cmdlets</span></span>

1. <span data-ttu-id="af967-118">Windows 검색 창에 **powershell 을 입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="af967-118">In the Windows search bar, type **powershell**.</span></span>
2. <span data-ttu-id="af967-119">결과에서 **Windows PowerShell** 선택하여 인터페이스를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af967-119">Select **Windows PowerShell** from the results to open the interface.</span></span>
3. <span data-ttu-id="af967-120">PowerShell 명령과 매개 변수를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="af967-120">Enter the PowerShell command and any parameters.</span></span>

> [!NOTE]
> <span data-ttu-id="af967-121">관리자 모드에서 PowerShell을 열 필요가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af967-121">You may need to open PowerShell in administrator mode.</span></span> <span data-ttu-id="af967-122">시작 메뉴에서 항목을 마우스 오른쪽  단추로 클릭하고 관리자 권한으로 실행을 클릭한 다음 사용 권한 프롬프트에서 **예를** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="af967-122">Right-click the item in the Start menu, click **Run as administrator** and click **Yes** at the permissions prompt.</span></span>

<span data-ttu-id="af967-123">cmdlet에 대한 온라인 도움말을 열기 위해 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="af967-123">To open online help for any of the cmdlets type the following:</span></span>

```PowerShell
Get-Help <cmdlet> -Online
```

<span data-ttu-id="af967-124">로컬로 `-online` 캐시된 도움말을 얻기 위해 매개 변수를 생략합니다.</span><span class="sxs-lookup"><span data-stu-id="af967-124">Omit the `-online` parameter to get locally cached help.</span></span>

## <a name="related-topics"></a><span data-ttu-id="af967-125">관련 항목</span><span class="sxs-lookup"><span data-stu-id="af967-125">Related topics</span></span>

- [<span data-ttu-id="af967-126">관리 및 구성 도구에 대한 참조 항목</span><span class="sxs-lookup"><span data-stu-id="af967-126">Reference topics for management and configuration tools</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="af967-127">Windows 10의 Microsoft Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="af967-127">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="af967-128">Microsoft Defender 바이러스 백신 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="af967-128">Microsoft Defender Antivirus Cmdlets</span></span>](/powershell/module/defender)