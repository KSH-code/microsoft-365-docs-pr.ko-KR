---
title: WMI를 통해 Microsoft Defender 바이러스 백신 구성
description: WMI 스크립트를 사용하여 끝점용 Microsoft Defender의 설정을 검색, 수정 및 업데이트하여 Microsoft Defender 바이러스 백신을 구성하고 관리하는 방법을 학습합니다.
keywords: wmi, 스크립트, Windows 관리 계측, 구성
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
audience: ITPro
ms.topic: how-to
ms.openlocfilehash: 25518383131e4f7ecb7451965ef7a42b1c6eee4b
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764066"
---
# <a name="use-windows-management-instrumentation-wmi-to-configure-and-manage-microsoft-defender-antivirus"></a><span data-ttu-id="5b6d6-104">WMI(Windows Management Instrumentation)를 사용하여 Microsoft Defender 바이러스 백신 구성 및 관리</span><span class="sxs-lookup"><span data-stu-id="5b6d6-104">Use Windows Management Instrumentation (WMI) to configure and manage Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="5b6d6-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="5b6d6-105">**Applies to:**</span></span>

- <span data-ttu-id="5b6d6-106">[엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/) </span><span class="sxs-lookup"><span data-stu-id="5b6d6-106">[Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)</span></span>

<span data-ttu-id="5b6d6-107">WMI(Windows Management Instrumentation)는 설정을 검색, 수정 및 업데이트할 수 있는 스크립팅 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="5b6d6-107">Windows Management Instrumentation (WMI) is a scripting interface that allows you to retrieve, modify, and update settings.</span></span>

<span data-ttu-id="5b6d6-108">WMI에 대한 자세한 내용은 시스템 Microsoft Developer Network [라이브러리를 읽어 보십시오.](/windows/win32/wmisdk/wmi-start-page)</span><span class="sxs-lookup"><span data-stu-id="5b6d6-108">Read more about WMI at the [Microsoft Developer Network System Administration library](/windows/win32/wmisdk/wmi-start-page).</span></span>

<span data-ttu-id="5b6d6-109">Microsoft Defender 바이러스 백신에는 그룹 정책 및 기타 관리 도구와 동일한 대부분의 기능을 수행하는 데 사용할 수 있는 다양한 특정 WMI 클래스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b6d6-109">Microsoft Defender Antivirus has a number of specific WMI classes that can be used to perform most of the same functions as Group Policy and other management tools.</span></span> <span data-ttu-id="5b6d6-110">대부분의 클래스는 [Defender PowerShell cmdlet과 유사합니다.](use-powershell-cmdlets-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="5b6d6-110">Many of the classes are analogous to [Defender PowerShell cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="5b6d6-111">[MSDN Windows Defender WMIv2 공급자](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) 참조 라이브러리에는 Microsoft Defender 바이러스 백신에 사용할 수 있는 WMI 클래스가 나열되어 있으며 예제 스크립트가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b6d6-111">The [MSDN Windows Defender WMIv2 Provider reference library](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) lists the available WMI classes for Microsoft Defender Antivirus, and includes example scripts.</span></span>

<span data-ttu-id="5b6d6-112">WMI를 사용하여 변경한 내용은 변경 내용이 배포되거나 적용된 끝점의 로컬 설정에 영향을 미치게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b6d6-112">Changes made with WMI will affect local settings on the endpoint where the changes are deployed or made.</span></span> <span data-ttu-id="5b6d6-113">즉, 그룹 정책, Microsoft Endpoint Configuration Manager 또는 Microsoft Intune을 사용하여 정책을 배포하면 WMI로 변경한 내용을 덮어 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b6d6-113">This means that deployments of policy with Group Policy, Microsoft Endpoint Configuration Manager, or Microsoft Intune can overwrite changes made with WMI.</span></span> 

<span data-ttu-id="5b6d6-114">로컬 정책 다시 설정으로 로컬로 다시 정할 수 있는 설정을 [구성할 수 있습니다.](configure-local-policy-overrides-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="5b6d6-114">You can [configure which settings can be overridden locally  with local policy overrides](configure-local-policy-overrides-microsoft-defender-antivirus.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="5b6d6-115">관련 항목</span><span class="sxs-lookup"><span data-stu-id="5b6d6-115">Related topics</span></span>

- [<span data-ttu-id="5b6d6-116">관리 및 구성 도구에 대한 참조 항목</span><span class="sxs-lookup"><span data-stu-id="5b6d6-116">Reference topics for management and configuration tools</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="5b6d6-117">Windows 10의 Microsoft Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="5b6d6-117">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)