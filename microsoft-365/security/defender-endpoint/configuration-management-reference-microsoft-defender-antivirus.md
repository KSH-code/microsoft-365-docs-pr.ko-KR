---
title: 비즈니스 Windows Defender 관리
description: 그룹 정책, Configuration Manager, PowerShell, WMI, Intune 및 명령줄을 사용하여 Microsoft Defender AV를 관리하는 방법을 학습합니다.
keywords: 그룹 정책, gpo, 구성 관리자, sccm, scep, powershell, wmi, intune, defender, 바이러스 백신, 맬웨어 방지, 보안, 보호
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 12/16/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 6b9845812763f9e3f1fdecf5566824eb76971dad
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764870"
---
# <a name="manage-microsoft-defender-antivirus-in-your-business"></a><span data-ttu-id="d798a-104">비즈니스에서 Microsoft Defender 바이러스 백신 관리</span><span class="sxs-lookup"><span data-stu-id="d798a-104">Manage Microsoft Defender Antivirus in your business</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d798a-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="d798a-105">**Applies to:**</span></span>

- <span data-ttu-id="d798a-106">[엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/) </span><span class="sxs-lookup"><span data-stu-id="d798a-106">[Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)</span></span>

<span data-ttu-id="d798a-107">다음 도구를 사용하여 Microsoft Defender 바이러스 백신을 관리하고 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d798a-107">You can manage and configure Microsoft Defender Antivirus with the following tools:</span></span>

- <span data-ttu-id="d798a-108">[Microsoft Intune(현재](/mem/intune/protect/endpoint-security-antivirus-policy) Microsoft Endpoint Manager의 일부)</span><span class="sxs-lookup"><span data-stu-id="d798a-108">[Microsoft Intune](/mem/intune/protect/endpoint-security-antivirus-policy) (now part of Microsoft Endpoint Manager)</span></span>
- <span data-ttu-id="d798a-109">[Microsoft Endpoint Configuration Manager(현재](/mem/configmgr/protect/deploy-use/endpoint-protection-configure) Microsoft Endpoint Manager의 일부)</span><span class="sxs-lookup"><span data-stu-id="d798a-109">[Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection-configure) (now part of Microsoft Endpoint Manager)</span></span>
- [<span data-ttu-id="d798a-110">그룹 정책</span><span class="sxs-lookup"><span data-stu-id="d798a-110">Group Policy</span></span>](./use-group-policy-microsoft-defender-antivirus.md)
- [<span data-ttu-id="d798a-111">PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="d798a-111">PowerShell cmdlets</span></span>](./use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [<span data-ttu-id="d798a-112">WMI(Windows Management Instrumentation)</span><span class="sxs-lookup"><span data-stu-id="d798a-112">Windows Management Instrumentation (WMI)</span></span>](./use-wmi-microsoft-defender-antivirus.md)
- <span data-ttu-id="d798a-113">[Microsoft 맬웨어 보호 명령줄 유틸리티(mpcmdrun.exe](./command-line-arguments-microsoft-defender-antivirus.md) 유틸리티라고도 합니다. </span><span class="sxs-lookup"><span data-stu-id="d798a-113">The [Microsoft Malware Protection Command Line Utility](./command-line-arguments-microsoft-defender-antivirus.md) (referred to as the *mpcmdrun.exe* utility</span></span>

<span data-ttu-id="d798a-114">다음 문서에서는 이러한 도구를 사용하여 Microsoft Defender 바이러스 백신을 관리 및 구성하기 위한 추가 정보, 링크 및 리소스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d798a-114">The following articles provide further information, links, and resources for using these tools to manage and configure Microsoft Defender Antivirus.</span></span>

| <span data-ttu-id="d798a-115">문서</span><span class="sxs-lookup"><span data-stu-id="d798a-115">Article</span></span> | <span data-ttu-id="d798a-116">설명</span><span class="sxs-lookup"><span data-stu-id="d798a-116">Description</span></span> |
|:---|:---|
|[<span data-ttu-id="d798a-117">Microsoft Intune 및 Microsoft Endpoint Configuration Manager를 사용하여 Microsoft Defender 바이러스 백신 관리</span><span class="sxs-lookup"><span data-stu-id="d798a-117">Manage Microsoft Defender Antivirus with Microsoft Intune and Microsoft Endpoint Configuration Manager</span></span>](use-intune-config-manager-microsoft-defender-antivirus.md)|<span data-ttu-id="d798a-118">Intune 및 Configuration Manager를 사용하여 Microsoft Defender 바이러스 백신 배포, 관리, 보고 및 구성에 대한 정보</span><span class="sxs-lookup"><span data-stu-id="d798a-118">Information about using Intune and Configuration Manager to deploy, manage, report, and configure Microsoft Defender Antivirus</span></span> |
|[<span data-ttu-id="d798a-119">그룹 정책 설정을 사용하여 Microsoft Defender 바이러스 백신 관리</span><span class="sxs-lookup"><span data-stu-id="d798a-119">Manage Microsoft Defender Antivirus with Group Policy settings</span></span>](use-group-policy-microsoft-defender-antivirus.md)|<span data-ttu-id="d798a-120">ADMX 템플릿에 있는 모든 그룹 정책 설정 목록</span><span class="sxs-lookup"><span data-stu-id="d798a-120">List of all Group Policy settings located in ADMX templates</span></span> |
|[<span data-ttu-id="d798a-121">PowerShell cmdlet을 사용하여 Microsoft Defender 바이러스 백신 관리</span><span class="sxs-lookup"><span data-stu-id="d798a-121">Manage Microsoft Defender Antivirus with PowerShell cmdlets</span></span>](use-powershell-cmdlets-microsoft-defender-antivirus.md)|<span data-ttu-id="d798a-122">PowerShell cmdlet을 사용하여 Microsoft Defender 바이러스 백신을 관리하기 위한 지침과 모든 cmdlet 및 허용되는 매개 변수에 대한 설명서 링크</span><span class="sxs-lookup"><span data-stu-id="d798a-122">Instructions for using PowerShell cmdlets to manage Microsoft Defender Antivirus, plus links to documentation for all cmdlets and allowed parameters</span></span> |
|[<span data-ttu-id="d798a-123">WMI(Windows Management Instrumentation)를 사용하여 Microsoft Defender 바이러스 백신 관리</span><span class="sxs-lookup"><span data-stu-id="d798a-123">Manage Microsoft Defender Antivirus with Windows Management Instrumentation (WMI)</span></span>](use-wmi-microsoft-defender-antivirus.md)| <span data-ttu-id="d798a-124">WMI를 사용하여 Microsoft Defender 바이러스 백신을 관리하는 지침과 WMIv2 API에 대한 설명서 링크(모든 클래스, 메서드 및 속성 포함)</span><span class="sxs-lookup"><span data-stu-id="d798a-124">Instructions for using WMI to manage Microsoft Defender Antivirus, plus links to documentation for the WMIv2 APIs (including all classes, methods, and properties)</span></span> |
|[<span data-ttu-id="d798a-125">명령줄 도구를 사용하여 Microsoft Defender mpcmdrun.exe 관리</span><span class="sxs-lookup"><span data-stu-id="d798a-125">Manage Microsoft Defender Antivirus with the mpcmdrun.exe command-line tool</span></span>](command-line-arguments-microsoft-defender-antivirus.md)|<span data-ttu-id="d798a-126">전용 명령줄 도구를 사용하여 Microsoft Defender 바이러스 백신 관리 및 사용 지침</span><span class="sxs-lookup"><span data-stu-id="d798a-126">Instructions on using the dedicated command-line tool to manage and use Microsoft Defender Antivirus</span></span> |