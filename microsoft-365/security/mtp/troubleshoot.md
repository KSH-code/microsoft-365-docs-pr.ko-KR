---
title: Microsoft Threat Protection 서비스 문제 트러블슈팅
description: 기존 Microsoft Threat Protection 문제 해결 및 해결 방법
keywords: 트러블슈팅 Microsoft Threat Protection, 트러블슈팅, 문제
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 2f7faec3223ca707e166c229b48093193be09d1e
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599975"
---
# <a name="troubleshoot-microsoft-threat-protection-service-issues"></a><span data-ttu-id="571b1-104">Microsoft Threat Protection 서비스 문제 트러블슈팅</span><span class="sxs-lookup"><span data-stu-id="571b1-104">Troubleshoot Microsoft Threat Protection service issues</span></span>

<span data-ttu-id="571b1-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="571b1-105">**Applies to:**</span></span>
- <span data-ttu-id="571b1-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="571b1-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="571b1-107">이 섹션에서는 Microsoft Threat Protection 서비스를 사용 하는 경우 발생할 수 있는 문제를 해결 합니다.</span><span class="sxs-lookup"><span data-stu-id="571b1-107">This section addresses issues that might arise as you use the Microsoft Threat Protection service.</span></span>


## <a name="not-seeing-microsoft-threat-protection-content"></a><span data-ttu-id="571b1-108">Microsoft Threat Protection 콘텐츠를 볼 수 없음</span><span class="sxs-lookup"><span data-stu-id="571b1-108">Not seeing Microsoft Threat Protection content</span></span>
<span data-ttu-id="571b1-109">포털에서 사고, 활동 센터, 검색 등의 탐색 페이지 기능이 보이지 않으면 테넌트가 적정한 라이선스를 보유하고 있는지 확인해야 합니다. </span><span class="sxs-lookup"><span data-stu-id="571b1-109">If you don't see capabilities on the navigation page such as the Incidents, Action Center, or Hunting in your portal you'll need to verify that your tenant has the appropriate license.</span></span> 

<span data-ttu-id="571b1-110">자세한 내용은 [전제 조건](prerequisites.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="571b1-110">For more information, see [Prerequisites](prerequisites.md).</span></span>

## <a name="azure-atp-alerts-are-not-showing-up-in-the-microsoft-threat-protection-incidents"></a><span data-ttu-id="571b1-111">Microsoft Threat Protection 사고에 Azure ATP 알림이 표시 되지 않음</span><span class="sxs-lookup"><span data-stu-id="571b1-111">Azure ATP alerts are not showing up in the Microsoft Threat Protection incidents</span></span>
<span data-ttu-id="571b1-112">환경에서 Azure ATP가 배포 되었지만 Microsoft Threat Protection 사건에서 Azure ATP 알림이 표시되지 않는 경우 Microsoft Cloud App Security 및 Azure ATP 통합 사용 설정이 허용되었는지 확인 합니다. </span><span class="sxs-lookup"><span data-stu-id="571b1-112">If you have Azure ATP deployed in your environment but you're not seeing Azure ATP alerts as part of Microsoft Threat Protection incidents, you'll need to ensure that the Microsoft Cloud App Security and Azure ATP integration is enabled.</span></span> 

<span data-ttu-id="571b1-113">자세한 내용은 [Azure ATP integration](https://docs.microsoft.com/cloud-app-security/aatp-integration)을 확인하세요. </span><span class="sxs-lookup"><span data-stu-id="571b1-113">For more information, see [Azure ATP integration](https://docs.microsoft.com/cloud-app-security/aatp-integration).</span></span>

## <a name="is-microsoft-threat-protection-available-for-us-government-community-cloud-gcc-or-gcc-high"></a><span data-ttu-id="571b1-114">GCC(미국 정부 커뮤니티 클라우드)나 GCC High에서 Microsoft Threat Protection을 사용할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="571b1-114">Is Microsoft Threat Protection available for US Government Community Cloud (GCC) or GCC High?</span></span>
<span data-ttu-id="571b1-115">현재는 사용불가합니다. </span><span class="sxs-lookup"><span data-stu-id="571b1-115">At the moment, it is not available.</span></span> 


