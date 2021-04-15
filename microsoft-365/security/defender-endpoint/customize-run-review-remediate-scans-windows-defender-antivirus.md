---
title: 예약된 검사 및 필요에 따라 검사 실행 및 사용자 지정
description: 네트워크의 끝점에서 Microsoft Defender 바이러스 백신 검색을 사용자 지정하고 시작합니다.
keywords: 검사, 일정, 사용자 지정, 제외, 파일 제외, 수정, 검사 결과, 검지, 위협 제거, 빠른 검사, 전체 검사, Microsoft Defender 바이러스 백신
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: f3e0cc7ffccf02e24b9746d539a44d3a72810ead
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765674"
---
# <a name="customize-initiate-and-review-the-results-of-microsoft-defender-antivirus-scans--remediation"></a><span data-ttu-id="92e3e-104">Microsoft Defender 바이러스 백신 검사 사용자 지정, 시작 및 수정 & 검토</span><span class="sxs-lookup"><span data-stu-id="92e3e-104">Customize, initiate, and review the results of Microsoft Defender Antivirus scans & remediation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="92e3e-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="92e3e-105">**Applies to:**</span></span>

- <span data-ttu-id="92e3e-106">[엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/) </span><span class="sxs-lookup"><span data-stu-id="92e3e-106">[Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)</span></span>

<span data-ttu-id="92e3e-107">그룹 정책, PowerShell 및 WMI(Windows Management Instrumentation)를 사용하여 Microsoft Defender 바이러스 백신 검색을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92e3e-107">You can use Group Policy, PowerShell, and Windows Management Instrumentation (WMI) to configure Microsoft Defender Antivirus scans.</span></span> 

## <a name="in-this-section"></a><span data-ttu-id="92e3e-108">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="92e3e-108">In this section</span></span>

| <span data-ttu-id="92e3e-109">문서</span><span class="sxs-lookup"><span data-stu-id="92e3e-109">Article</span></span> | <span data-ttu-id="92e3e-110">설명</span><span class="sxs-lookup"><span data-stu-id="92e3e-110">Description</span></span> |
|:---|:---|
|[<span data-ttu-id="92e3e-111">Microsoft Defender 바이러스 백신 검사에서 파일, 폴더 및 프로세스에서 연 파일 제외 구성 및 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="92e3e-111">Configure and validate file, folder, and process-opened file exclusions in Microsoft Defender Antivirus scans</span></span>](configure-exclusions-microsoft-defender-antivirus.md) | <span data-ttu-id="92e3e-112">파일(지정된 프로세스에서 수정한 파일 포함) 및 폴더를 필요한 검사, 예약된 검사 및 항상 실시간 보호 모니터링 및 검사에서 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92e3e-112">You can exclude files (including files modified by specified processes) and folders from on-demand scans, scheduled scans, and always-on real-time protection monitoring and scanning</span></span> |
|[<span data-ttu-id="92e3e-113">Microsoft Defender 바이러스 백신 검사 옵션 구성</span><span class="sxs-lookup"><span data-stu-id="92e3e-113">Configure Microsoft Defender Antivirus scanning options</span></span>](configure-advanced-scan-types-microsoft-defender-antivirus.md) | <span data-ttu-id="92e3e-114">검사에 특정 유형의 전자 메일 저장소 파일, 백업 또는 재분석 지점, 보관된 파일(예: .zip 파일)을 포함하도록 Microsoft Defender 바이러스 백신을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92e3e-114">You can configure Microsoft Defender Antivirus to include certain types of email storage files, back-up or reparse points, and archived files (such as .zip files) in scans.</span></span> <span data-ttu-id="92e3e-115">네트워크 파일 검색을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92e3e-115">You can also enable network file scanning</span></span> |
|[<span data-ttu-id="92e3e-116">검사에 대한 수정 구성</span><span class="sxs-lookup"><span data-stu-id="92e3e-116">Configure remediation for scans</span></span>](configure-remediation-microsoft-defender-antivirus.md) | <span data-ttu-id="92e3e-117">위협을 감지할 때 Microsoft Defender 바이러스 백신이 어떤 작업을 해야 하는지, 그리고 분리된 파일을 검지 폴더에 보존해야 하는 기간 구성</span><span class="sxs-lookup"><span data-stu-id="92e3e-117">Configure what Microsoft Defender Antivirus should do when it detects a threat, and how long quarantined files should be retained in the quarantine folder</span></span> |
|[<span data-ttu-id="92e3e-118">예약된 검사 구성</span><span class="sxs-lookup"><span data-stu-id="92e3e-118">Configure scheduled scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md) | <span data-ttu-id="92e3e-119">실행해야 하는 시간 및 전체 검사 또는 빠른 검사로 실행 여부를 포함하여 재발(예약된) 검사 설정</span><span class="sxs-lookup"><span data-stu-id="92e3e-119">Set up recurring (scheduled) scans, including when they should run and whether they run as full or quick scans</span></span> |
|[<span data-ttu-id="92e3e-120">검사 구성 및 실행</span><span class="sxs-lookup"><span data-stu-id="92e3e-120">Configure and run scans</span></span>](run-scan-microsoft-defender-antivirus.md) | <span data-ttu-id="92e3e-121">PowerShell, Windows Management Instrumentation을 사용하여 또는 Windows 보안 앱을 사용하여 끝점에서 개별적으로 요구 시 검사 실행 및 구성</span><span class="sxs-lookup"><span data-stu-id="92e3e-121">Run and configure on-demand scans using PowerShell, Windows Management Instrumentation, or individually on endpoints with the Windows Security app</span></span> |
|[<span data-ttu-id="92e3e-122">검사 결과 검토</span><span class="sxs-lookup"><span data-stu-id="92e3e-122">Review scan results</span></span>](review-scan-results-microsoft-defender-antivirus.md) | <span data-ttu-id="92e3e-123">Microsoft Endpoint Configuration Manager, Microsoft Intune 또는 Windows 보안 앱을 사용하여 검사 결과 검토</span><span class="sxs-lookup"><span data-stu-id="92e3e-123">Review the results of scans using  Microsoft Endpoint Configuration Manager, Microsoft Intune, or the Windows Security app</span></span> |