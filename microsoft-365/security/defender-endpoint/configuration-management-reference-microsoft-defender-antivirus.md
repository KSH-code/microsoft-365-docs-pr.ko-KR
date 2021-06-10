---
title: 비즈니스 Windows Defender 관리
description: 그룹 정책, Configuration Manager, PowerShell, WMI, Intune 및 명령줄을 사용하여 Microsoft Defender AV를 관리하는 방법을 학습합니다.
keywords: 그룹 정책, gpo, 구성 관리자, sccm, scep, powershell, wmi, intune, defender, 바이러스 백신, 맬웨어 방지, 보안, 보호
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/06/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 2265f3680e425ade062d444685fbd8873eaa02ca
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274979"
---
# <a name="manage-microsoft-defender-antivirus-in-your-business"></a><span data-ttu-id="1883c-104">비즈니스 Microsoft Defender 바이러스 백신 관리</span><span class="sxs-lookup"><span data-stu-id="1883c-104">Manage Microsoft Defender Antivirus in your business</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="1883c-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="1883c-105">**Applies to:**</span></span>

- [<span data-ttu-id="1883c-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="1883c-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="1883c-107">다음 도구를 사용하여 Microsoft Defender 바이러스 백신 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1883c-107">You can manage and configure Microsoft Defender Antivirus with the following tools:</span></span>

- <span data-ttu-id="1883c-108">[Microsoft Intune(현재](/mem/intune/protect/endpoint-security-antivirus-policy) Microsoft Endpoint Manager)</span><span class="sxs-lookup"><span data-stu-id="1883c-108">[Microsoft Intune](/mem/intune/protect/endpoint-security-antivirus-policy) (now part of Microsoft Endpoint Manager)</span></span>
- <span data-ttu-id="1883c-109">[Microsoft Endpoint Configuration Manager(현재](/mem/configmgr/protect/deploy-use/endpoint-protection-configure) Microsoft Endpoint Manager)</span><span class="sxs-lookup"><span data-stu-id="1883c-109">[Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection-configure) (now part of Microsoft Endpoint Manager)</span></span>
- [<span data-ttu-id="1883c-110">그룹 정책</span><span class="sxs-lookup"><span data-stu-id="1883c-110">Group Policy</span></span>](./use-group-policy-microsoft-defender-antivirus.md)
- [<span data-ttu-id="1883c-111">PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="1883c-111">PowerShell cmdlets</span></span>](./use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [<span data-ttu-id="1883c-112">WMI(Windows Management Instrumentation)</span><span class="sxs-lookup"><span data-stu-id="1883c-112">Windows Management Instrumentation (WMI)</span></span>](./use-wmi-microsoft-defender-antivirus.md)
- <span data-ttu-id="1883c-113">[Microsoft 맬웨어 보호 명령줄 유틸리티(mpcmdrun.exe](./command-line-arguments-microsoft-defender-antivirus.md) 유틸리티라고도 합니다. </span><span class="sxs-lookup"><span data-stu-id="1883c-113">The [Microsoft Malware Protection Command Line Utility](./command-line-arguments-microsoft-defender-antivirus.md) (referred to as the *mpcmdrun.exe* utility</span></span>

<span data-ttu-id="1883c-114">다음 문서에서는 이러한 도구를 사용하여 이러한 도구를 관리하고 구성하기 위한 추가 정보, 링크 및 리소스를 Microsoft Defender 바이러스 백신.</span><span class="sxs-lookup"><span data-stu-id="1883c-114">The following articles provide further information, links, and resources for using these tools to manage and configure Microsoft Defender Antivirus.</span></span>

| <span data-ttu-id="1883c-115">문서</span><span class="sxs-lookup"><span data-stu-id="1883c-115">Article</span></span> | <span data-ttu-id="1883c-116">설명</span><span class="sxs-lookup"><span data-stu-id="1883c-116">Description</span></span> |
|:---|:---|
|[<span data-ttu-id="1883c-117">사용자 Microsoft Defender 바이러스 백신 사용하여 Microsoft Intune 관리 Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="1883c-117">Manage Microsoft Defender Antivirus with Microsoft Intune and Microsoft Endpoint Configuration Manager</span></span>](use-intune-config-manager-microsoft-defender-antivirus.md)|<span data-ttu-id="1883c-118">Intune 및 Configuration Manager를 사용하여 데이터를 배포, 관리, 보고 및 구성하는 Microsoft Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="1883c-118">Information about using Intune and Configuration Manager to deploy, manage, report, and configure Microsoft Defender Antivirus</span></span> |
|[<span data-ttu-id="1883c-119">그룹 Microsoft Defender 바이러스 백신 설정으로 관리</span><span class="sxs-lookup"><span data-stu-id="1883c-119">Manage Microsoft Defender Antivirus with Group Policy settings</span></span>](use-group-policy-microsoft-defender-antivirus.md)|<span data-ttu-id="1883c-120">ADMX 템플릿에 있는 모든 그룹 정책 설정 목록</span><span class="sxs-lookup"><span data-stu-id="1883c-120">List of all Group Policy settings located in ADMX templates</span></span> |
|[<span data-ttu-id="1883c-121">PowerShell cmdlet을 사용하여 Microsoft Defender 바이러스 백신 관리</span><span class="sxs-lookup"><span data-stu-id="1883c-121">Manage Microsoft Defender Antivirus with PowerShell cmdlets</span></span>](use-powershell-cmdlets-microsoft-defender-antivirus.md)|<span data-ttu-id="1883c-122">PowerShell cmdlet을 사용하여 Microsoft Defender 바이러스 백신 및 모든 cmdlet 및 허용되는 매개 변수에 대한 설명서에 대한 링크</span><span class="sxs-lookup"><span data-stu-id="1883c-122">Instructions for using PowerShell cmdlets to manage Microsoft Defender Antivirus, plus links to documentation for all cmdlets and allowed parameters</span></span> |
|[<span data-ttu-id="1883c-123">WMI(Microsoft Defender 바이러스 백신 Management Instrumentation)Windows 관리</span><span class="sxs-lookup"><span data-stu-id="1883c-123">Manage Microsoft Defender Antivirus with Windows Management Instrumentation (WMI)</span></span>](use-wmi-microsoft-defender-antivirus.md)| <span data-ttu-id="1883c-124">WMI를 사용하여 관리하기 위한 지침Microsoft Defender 바이러스 백신 WMIv2 API에 대한 설명서 링크(모든 클래스, 메서드 및 속성 포함)</span><span class="sxs-lookup"><span data-stu-id="1883c-124">Instructions for using WMI to manage Microsoft Defender Antivirus, plus links to documentation for the WMIv2 APIs (including all classes, methods, and properties)</span></span> |
|[<span data-ttu-id="1883c-125">명령줄 Microsoft Defender 바이러스 백신 사용하여 mpcmdrun.exe 관리</span><span class="sxs-lookup"><span data-stu-id="1883c-125">Manage Microsoft Defender Antivirus with the mpcmdrun.exe command-line tool</span></span>](command-line-arguments-microsoft-defender-antivirus.md)|<span data-ttu-id="1883c-126">전용 명령줄 도구를 사용하여 명령줄 도구를 관리하고 사용하는 방법에 대한 Microsoft Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="1883c-126">Instructions on using the dedicated command-line tool to manage and use Microsoft Defender Antivirus</span></span> |