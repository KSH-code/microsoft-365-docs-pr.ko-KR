---
title: Microsoft 365 Lighthouse 장치 준수 페이지 개요
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: 서비스 공급자를 사용하는 MSP(관리 Microsoft 365 Lighthouse)의 경우 장치 준수 페이지에 대해 자세히 알아보십시오.
ms.openlocfilehash: 3568f5b362df86955a1ea6ce15928658c854a584
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "53395227"
---
# <a name="microsoft-365-lighthouse-device-compliance-page-overview"></a><span data-ttu-id="906e6-103">Microsoft 365 Lighthouse 장치 준수 페이지 개요</span><span class="sxs-lookup"><span data-stu-id="906e6-103">Microsoft 365 Lighthouse Device compliance page overview</span></span>

> [!NOTE]
> <span data-ttu-id="906e6-104">이 문서에 설명된 기능은 미리 보기에 있으며, 변경될 수 있으며, 요구 사항을 충족하는 파트너만 사용할 수 [있습니다.](m365-lighthouse-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="906e6-104">The features described in this article are in Preview, are subject to change, and are only available to partners who meet the [requirements](m365-lighthouse-requirements.md).</span></span> <span data-ttu-id="906e6-105">조직에 등록이 Microsoft 365 Lighthouse 에 [등록을 Microsoft 365 Lighthouse.](m365-lighthouse-sign-up.md)</span><span class="sxs-lookup"><span data-stu-id="906e6-105">If your organization does not have Microsoft 365 Lighthouse, see [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).</span></span>

<span data-ttu-id="906e6-106">Microsoft 365 Lighthouse 탐색 창에서 장치를 선택하여 장치 준수 페이지를 열어 모든 테넌트에  대한 Intune 장치 준수와 관련된 인사이트 및 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="906e6-106">Microsoft 365 Lighthouse lets you view insights and information related to Intune device compliance for all your tenants by selecting **Devices** in the left navigation pane to open the Device compliance page.</span></span> <span data-ttu-id="906e6-107">이 페이지에서는 테넌트 전체의 규정 준수 상태에 대한 개요를 보고, 각 테넌트의 장치 목록을 보고, 준수 정책 및 설정에 대한 상태 보고서를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="906e6-107">From this page, you can get an overview of compliance status across tenants, view a list of devices for each tenant, and get status reports on compliance policies and settings.</span></span>

## <a name="overview-tab"></a><span data-ttu-id="906e6-108">개요 탭</span><span class="sxs-lookup"><span data-stu-id="906e6-108">Overview tab</span></span>  
  
<span data-ttu-id="906e6-109">개요 탭에서 테넌트 전체에서 장치 준수 상태를 보고, 월별 장치 준수 추세를 보고, 장치에 할당된 준수 정책이 있는지 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="906e6-109">On the Overview tab, you can view device compliance status across your tenants, see monthly device compliance trends, and track whether devices have compliance policies assigned to them.</span></span> <span data-ttu-id="906e6-110">조건부 액세스 정책에 따라 테넌트 장치 준수 작업 및 요구 사항에 대한 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="906e6-110">You can also view information on tenant device compliance actions and requirements based on Conditional Access policies.</span></span>

:::image type="content" source="../media/m365-lighthouse-device-compliance-page-overview/device-overview-tab.png" alt-text="개요 탭의 스크린샷.":::

## <a name="devices-tab"></a><span data-ttu-id="906e6-112">장치 탭</span><span class="sxs-lookup"><span data-stu-id="906e6-112">Devices tab</span></span>

<span data-ttu-id="906e6-113">장치 탭에서 모든 테넌트 장치 목록을 보고 준수 상태(호환, 비호준, 유예 기간 및 평가되지 않은 경우)에 따라 목록을 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="906e6-113">On the Devices tab, you can view a list of all tenant devices and filter the list based on the following compliance statuses: Compliant, Non-compliant, In Grace period, and Not evaluated.</span></span> <span data-ttu-id="906e6-114">다양한 준수 상태에 대한 자세한 내용은 Intune 장치 준수 정책 [모니터링을 참조하세요.](/mem/intune/protect/compliance-policy-monitor)</span><span class="sxs-lookup"><span data-stu-id="906e6-114">For more information about the different compliance statuses, see [Monitor Intune Device compliance policies](/mem/intune/protect/compliance-policy-monitor).</span></span>

<span data-ttu-id="906e6-115">장치를 선택하여 장치가 현재 규정 준수 상태인 이유에 대한 자세한 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="906e6-115">Select any device to view more information on why the device is in its current compliance state.</span></span> <span data-ttu-id="906e6-116">디바이스에서 조치를 취해야 하는 경우 장치에서 장치를 볼 수 Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="906e6-116">If you need to take action on the device, there's an option to view the device in Microsoft Endpoint Manager.</span></span>

:::image type="content" source="../media/m365-lighthouse-device-compliance-page-overview/devices-device-tab.png" alt-text="장치 탭의 스크린샷.":::

## <a name="policies-tab"></a><span data-ttu-id="906e6-118">정책 탭</span><span class="sxs-lookup"><span data-stu-id="906e6-118">Policies tab</span></span>

<span data-ttu-id="906e6-119">정책 탭에서는 도구 모음의 비교 기능을 사용하여 테넌트 전체에서 준수 정책을 보고 동일한 플랫폼 유형의 두 개 또는 세 개의 정책을 비교할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="906e6-119">On the Policies tab, you can view compliance policies across your tenants and compare two or three policies of the same platform type by using the Compare feature on the toolbar.</span></span> <span data-ttu-id="906e6-120">정책을 선택하여 자세한 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="906e6-120">You can also select any policy to view more information.</span></span>

:::image type="content" source="../media/m365-lighthouse-device-compliance-page-overview/devices-policies-tab.png" alt-text="정책 탭의 스크린샷.":::

## <a name="settings-tab"></a><span data-ttu-id="906e6-122">설정 탭</span><span class="sxs-lookup"><span data-stu-id="906e6-122">Settings tab</span></span>

<span data-ttu-id="906e6-123">설정 탭은 테넌트 장치 전반에 걸쳐 비호준 설정에 대한 집계 보고서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="906e6-123">The settings tab provides an aggregated report of non-compliant settings across tenant devices.</span></span> <span data-ttu-id="906e6-124">비규준 장치가 속한 테넌트 등 자세한 정보를 보시고 보고서 행을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="906e6-124">Select any of the report rows to view more information, including which tenants the non-compliant devices belong to.</span></span>

:::image type="content" source="../media/m365-lighthouse-device-compliance-page-overview/device-settings-tab.png" alt-text="Screenshot of the 설정 tab.":::

## <a name="related-content"></a><span data-ttu-id="906e6-126">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="906e6-126">Related content</span></span>

<span data-ttu-id="906e6-127">[Microsoft 365 Lighthouse 페이지](m365-lighthouse-users-page-overview.md) 개요(문서)</span><span class="sxs-lookup"><span data-stu-id="906e6-127">[Microsoft 365 Lighthouse Users page overview](m365-lighthouse-users-page-overview.md) (article)</span></span>\
<span data-ttu-id="906e6-128">[Microsoft 365 Lighthouse FAQ(문서)](m365-lighthouse-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="906e6-128">[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (article)</span></span>
