---
title: Microsoft Threat Protection 서비스 문제 트러블슈팅
description: 기존 Microsoft Threat Protection 문제 해결 및 해결 방법
keywords: Microsoft Threat Protection, 문제 해결, Azure ATP, 문제, 추가 기능, 설정 페이지 문제 해결
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
ms.openlocfilehash: bbc7d5d434765b94b0b2707605be2edfbbc8e423
ms.sourcegitcommit: 2913fd74ad5086c7cac6388447285be9aa5a8e44
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/01/2020
ms.locfileid: "41661984"
---
# <a name="troubleshoot-microsoft-threat-protection-service-issues"></a><span data-ttu-id="6e02e-104">Microsoft Threat Protection 서비스 문제 트러블슈팅</span><span class="sxs-lookup"><span data-stu-id="6e02e-104">Troubleshoot Microsoft Threat Protection service issues</span></span>

<span data-ttu-id="6e02e-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="6e02e-105">**Applies to:**</span></span>
- <span data-ttu-id="6e02e-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="6e02e-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="6e02e-107">이 섹션에서는 Microsoft Threat Protection 서비스를 사용 하는 경우 발생할 수 있는 문제를 해결 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e02e-107">This section addresses issues that might arise as you use the Microsoft Threat Protection service.</span></span>


## <a name="i-dont-see-microsoft-threat-protection-content"></a><span data-ttu-id="6e02e-108">Microsoft Threat Protection 콘텐츠가 표시 되지 않음</span><span class="sxs-lookup"><span data-stu-id="6e02e-108">I don't see Microsoft Threat Protection content</span></span>
<span data-ttu-id="6e02e-109">포털의 인시던트, 작업 센터 또는 검색 등의 기능이 탐색 창에 표시 되지 않는 경우에는 테 넌 트에 적절 한 라이선스가 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e02e-109">If you don't see capabilities on the navigation pane such as the Incidents, Action Center, or Hunting in your portal, you'll need to verify that your tenant has the appropriate licenses.</span></span> 

<span data-ttu-id="6e02e-110">자세한 내용은 [전제 조건](prerequisites.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6e02e-110">For more information, see [Prerequisites](prerequisites.md).</span></span>

## <a name="azure-atp-alerts-are-not-showing-up-in-the-microsoft-threat-protection-incidents"></a><span data-ttu-id="6e02e-111">Microsoft Threat Protection 사고에 Azure ATP 알림이 표시 되지 않음</span><span class="sxs-lookup"><span data-stu-id="6e02e-111">Azure ATP alerts are not showing up in the Microsoft Threat Protection incidents</span></span>
<span data-ttu-id="6e02e-112">환경에서 Azure ATP가 배포 되었지만 Microsoft Threat Protection 사건에서 Azure ATP 알림이 표시되지 않는 경우 Microsoft Cloud App Security 및 Azure ATP 통합 사용 설정이 허용되었는지 확인 합니다. </span><span class="sxs-lookup"><span data-stu-id="6e02e-112">If you have Azure ATP deployed in your environment but you're not seeing Azure ATP alerts as part of Microsoft Threat Protection incidents, you'll need to ensure that the Microsoft Cloud App Security and Azure ATP integration is enabled.</span></span> 

<span data-ttu-id="6e02e-113">자세한 내용은 [Azure ATP integration](https://docs.microsoft.com/cloud-app-security/aatp-integration)을 확인하세요. </span><span class="sxs-lookup"><span data-stu-id="6e02e-113">For more information, see [Azure ATP integration](https://docs.microsoft.com/cloud-app-security/aatp-integration).</span></span>

## <a name="is-microsoft-threat-protection-available-for-us-government-community-cloud-gcc-or-gcc-high"></a><span data-ttu-id="6e02e-114">GCC(미국 정부 커뮤니티 클라우드)나 GCC High에서 Microsoft Threat Protection을 사용할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="6e02e-114">Is Microsoft Threat Protection available for US Government Community Cloud (GCC) or GCC High?</span></span>
<span data-ttu-id="6e02e-115">현재는 사용불가합니다. </span><span class="sxs-lookup"><span data-stu-id="6e02e-115">At the moment, it is not available.</span></span>

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a><span data-ttu-id="6e02e-116">서비스를 켜는 설정 페이지는 어디에 있나요?</span><span class="sxs-lookup"><span data-stu-id="6e02e-116">Where is the settings page for turning the service on?</span></span>
<span data-ttu-id="6e02e-117">Microsoft Threat Protection을 설정 하려면 Microsoft 365 보안 센터의 탐색 창에서 **설정** 에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e02e-117">To turn on Microsoft Threat Protection, access **Settings** from the navigation pane in the Microsoft 365 security center.</span></span> <span data-ttu-id="6e02e-118">이 탐색 항목은 [필수 사용 권한 및 라이선스가](mtp-enable.md#check-license-eligibility-and-required-permissions)있는 경우에만 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e02e-118">This navigation item is visible only if you have the [prerequisite permissions and licenses](mtp-enable.md#check-license-eligibility-and-required-permissions).</span></span>

## <a name="can-i-use-an-add-on-instead-of-the-required-e5-licenses"></a><span data-ttu-id="6e02e-119">필수 E5 라이선스 대신 추가 기능을 사용할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="6e02e-119">Can I use an add-on instead of the required E5 licenses?</span></span>
<span data-ttu-id="6e02e-120">현재 Microsoft Threat Protection에 대 한 추가 기능은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6e02e-120">There are currently no add-ons for Microsoft Threat Protection.</span></span> [<span data-ttu-id="6e02e-121">라이선스 요구 사항 참조</span><span class="sxs-lookup"><span data-stu-id="6e02e-121">See licensing requirements</span></span>](prerequisites.md) 

