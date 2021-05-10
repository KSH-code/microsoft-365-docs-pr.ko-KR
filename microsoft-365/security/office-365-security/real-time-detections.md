---
title: Microsoft Defender for Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 05/05/2021
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 탐색기 또는 실시간 검색을 사용하여 위협을 효율적으로 조사하고 대응합니다.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7ab7b5731d121106d930868b03330d4ac7befd77
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300218"
---
# <a name="threat-explorer-and-real-time-detections-basics"></a><span data-ttu-id="e6a1d-103">위협 탐색기 및 실시간 검색 기본</span><span class="sxs-lookup"><span data-stu-id="e6a1d-103">Threat Explorer and Real-time detections basics</span></span>

<span data-ttu-id="e6a1d-104">이 문서의 내용</span><span class="sxs-lookup"><span data-stu-id="e6a1d-104">In this article:</span></span>

- [<span data-ttu-id="e6a1d-105">위협 탐색기 및 실시간 검색 간의 차이점</span><span class="sxs-lookup"><span data-stu-id="e6a1d-105">Differences between Threat Explorer and Real-time detections</span></span>](#differences-between-threat-explorer-and-real-time-detections)<br/>
- [<span data-ttu-id="e6a1d-106">필수 라이선스 및 사용 권한</span><span class="sxs-lookup"><span data-stu-id="e6a1d-106">Required licenses and permissions</span></span>](#required-licenses-and-permissions)

> [!NOTE]
> <span data-ttu-id="e6a1d-107">이 문서는 위협 탐색기(탐색기) **,** 전자 메일 보안 및 **탐색기** 및 실시간 검색 기본(예: 도구 간 차이점 및 작동에 필요한 사용 권한)에 대한 **3개** 문서 시리즈의 일부입니다. </span><span class="sxs-lookup"><span data-stu-id="e6a1d-107">This is part of a **3-article series** on **Threat Explorer (Explorer)**, **email security**, and **Explorer and Real-time detections basics** (such as differences between the tools, and permissions needed to operate them).</span></span> <span data-ttu-id="e6a1d-108">이 시리즈의 다른 두 문서는 위협 탐색기에서 위협 [헌팅](threat-hunting-in-threat-explorer.md) 및 위협 탐색기를 사용하는 전자 메일 [보안입니다.](email-security-in-microsoft-defender.md)</span><span class="sxs-lookup"><span data-stu-id="e6a1d-108">The other two articles in this series are [Threat hunting in Threat Explorer](threat-hunting-in-threat-explorer.md) and [Email security with Threat Explorer](email-security-in-microsoft-defender.md).</span></span>

<span data-ttu-id="e6a1d-109">이 문서에서는 위협 탐색과 실시간 검색 보고 간의 차이점과 필요한 라이선스 및 사용 권한에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a1d-109">This article explains the difference between threat exploration and real-time detections reporting, and the licenses and permissions that are required.</span></span>

<span data-ttu-id="e6a1d-110">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="e6a1d-110">**Applies to**</span></span>
- [<span data-ttu-id="e6a1d-111">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="e6a1d-111">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="e6a1d-112">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e6a1d-112">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="e6a1d-113">조직에 microsoft [Defender for Office 365](defender-for-office-365.md)권한이 있는 경우 [](#required-licenses-and-permissions)위협 탐색기(탐색기) 또는 실시간  검색을 사용하여 위협을 감지하고 치료할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="e6a1d-113">If your organization has [Microsoft Defender for Office 365](defender-for-office-365.md), and you have the [permissions](#required-licenses-and-permissions), you can use **Threat Explorer** (called **Explorer**) or **Real-time detections** to detect and remediate threats.</span></span>

<span data-ttu-id="e6a1d-114">보안 & 준수 센터에서 위협 **관리로** 이동한 다음   탐색기 또는 실시간 검색  **을 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="e6a1d-114">In the **Security & Compliance Center**, go to **Threat management**, and then choose **Explorer** _or_ **Real-time detections**.</span></span>

<br>

****

|<span data-ttu-id="e6a1d-115">Microsoft Defender for Office 365 요금제 2를 사용하면 다음을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6a1d-115">With Microsoft Defender for Office 365 Plan 2, you see:</span></span>|<span data-ttu-id="e6a1d-116">Microsoft Defender for Office 365 요금제 1을 사용하면 다음을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6a1d-116">With Microsoft Defender for Office 365 Plan 1, you see:</span></span>|
|---|---|
|![위협 탐색기](../../media/threatmgmt-explorer.png)|![실시간 탐지](../../media/threatmgmt-realtimedetections.png)|
|

<span data-ttu-id="e6a1d-119">다음 도구를 사용하여 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6a1d-119">With these tools, you can:</span></span>

- <span data-ttu-id="e6a1d-120">보안 기능에서 검색된 맬웨어를 Microsoft 365 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a1d-120">See malware detected by Microsoft 365 security features.</span></span>
- <span data-ttu-id="e6a1d-121">피싱 URL을 보고 판정 데이터를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a1d-121">View phishing URL and click verdict data.</span></span>
- <span data-ttu-id="e6a1d-122">탐색기 보기에서 자동화된 조사 및 응답 프로세스를 시작하십시오.</span><span class="sxs-lookup"><span data-stu-id="e6a1d-122">Start an automated investigation and response process from a view in Explorer.</span></span>
- <span data-ttu-id="e6a1d-123">악성 전자 메일 조사 등</span><span class="sxs-lookup"><span data-stu-id="e6a1d-123">Investigate malicious email, and more.</span></span>

<span data-ttu-id="e6a1d-124">자세한 내용은 [위협 탐색기를 사용하여 전자 메일 보안을 참조하세요.](email-security-in-microsoft-defender.md)</span><span class="sxs-lookup"><span data-stu-id="e6a1d-124">For more information, see [Email security with Threat Explorer](email-security-in-microsoft-defender.md).</span></span>

## <a name="differences-between-threat-explorer-and-real-time-detections"></a><span data-ttu-id="e6a1d-125">위협 탐색기 및 실시간 검색 간의 차이점</span><span class="sxs-lookup"><span data-stu-id="e6a1d-125">Differences between Threat Explorer and Real-time detections</span></span>

- <span data-ttu-id="e6a1d-126">*실시간 검색은* 계획 1에 대한 Defender에서 Office 365 보고 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a1d-126">*Real-time detections* is a reporting tool available in Defender for Office 365 Plan 1.</span></span> <span data-ttu-id="e6a1d-127">*위협 탐색기는* 계획 2용 Defender에서 사용할 수 있는 위협 Office 365 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a1d-127">*Threat Explorer* is a threat hunting and remediation tool available in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="e6a1d-128">실시간 검색 보고서를 사용하면 검색을 실시간으로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6a1d-128">The Real-time detections report allows you to view detections in real time.</span></span> <span data-ttu-id="e6a1d-129">위협 탐색기도 이 작업을 수행하지만 공격 캠페인 강조 표시와 같은 특정 공격에 대한 추가 세부 정보를 제공하며 보안 운영 팀에 위협을 수정하는 기능을 제공합니다(자동화된 조사 및 대응 조사 트리거 [포함).](automated-investigation-response-office.md)</span><span class="sxs-lookup"><span data-stu-id="e6a1d-129">Threat Explorer does this as well, but it provides additional details for a given attack, such as highlighting attack campaigns, and gives security operations teams the ability to remediate threats (including triggering an [Automated Investigation and Response investigation](automated-investigation-response-office.md)).</span></span>
- <span data-ttu-id="e6a1d-130">모든 *전자 메일* 보기는 위협 탐색기에서 사용할 수 있지만 실시간 검색 보고서에는 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e6a1d-130">An *All email* view is available in Threat Explorer, but not included in the Real-time detections report.</span></span>
- <span data-ttu-id="e6a1d-131">다양한 필터링 기능 및 수정 작업이 위협 탐색기에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6a1d-131">Rich filtering capabilities and remediation actions are included in Threat Explorer.</span></span> <span data-ttu-id="e6a1d-132">자세한 내용은 [Microsoft Defender for Office 365 Service Description: Feature availability across Defender for Office 365 참조하세요.](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)</span><span class="sxs-lookup"><span data-stu-id="e6a1d-132">For more information, see [Microsoft Defender for Office 365 Service Description: Feature availability across Defender for Office 365 plans](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="e6a1d-133">필수 라이선스 및 사용 권한</span><span class="sxs-lookup"><span data-stu-id="e6a1d-133">Required licenses and permissions</span></span>

<span data-ttu-id="e6a1d-134">탐색기 또는 실시간 Office 365 사용하려면 Microsoft [Defender가](defender-for-office-365.md) 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a1d-134">You must have [Microsoft Defender for Office 365](defender-for-office-365.md) to use either of Explorer or Real-time detections:</span></span>

- <span data-ttu-id="e6a1d-135">그러나 Explorer는 요금제 2용 Defender에만 Office 365 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6a1d-135">But Explorer is only included in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="e6a1d-136">실시간 검색 보고서는 Plan 1의 Defender에 Office 365 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6a1d-136">The Real-time detections report is included in Defender for Office 365 Plan 1.</span></span>

<span data-ttu-id="e6a1d-137">보안 운영 팀은 사용자에 대해 Defender를 통해 보호해야 하는 모든 사용자에 대해 Office 365 탐색기 및 실시간 검색에 사용이 허가된 사용자의 검색 데이터가 표시되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a1d-137">Security Operations teams need to assign licenses for all users who should be protected by Defender for Office 365 and be aware that Explorer and Real-time detections show detection data for licensed users.</span></span>

<span data-ttu-id="e6a1d-138">탐색기 또는  실시간 검색을 보고 사용하려면 다음이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a1d-138">To view and use Explorer *or* Real-time detections, you must have the following:</span></span>

- <span data-ttu-id="e6a1d-139">보안 및 준수 &:</span><span class="sxs-lookup"><span data-stu-id="e6a1d-139">For the Security & Compliance Center:</span></span>

  - <span data-ttu-id="e6a1d-140">조직 관리</span><span class="sxs-lookup"><span data-stu-id="e6a1d-140">Organization Management</span></span>
  - <span data-ttu-id="e6a1d-141">보안 관리자(Azure Active Directory 관리 센터에서 할당할 수 있습니다. <https://aad.portal.azure.com> )</span><span class="sxs-lookup"><span data-stu-id="e6a1d-141">Security Administrator (this can be assigned in the Azure Active Directory admin center (<https://aad.portal.azure.com>)</span></span>
  - <span data-ttu-id="e6a1d-142">보안 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="e6a1d-142">Security Reader</span></span>

- <span data-ttu-id="e6a1d-143">다음 Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="e6a1d-143">For Exchange Online:</span></span>

  - <span data-ttu-id="e6a1d-144">조직 관리</span><span class="sxs-lookup"><span data-stu-id="e6a1d-144">Organization Management</span></span>
  - <span data-ttu-id="e6a1d-145">보기 전용 조직 관리</span><span class="sxs-lookup"><span data-stu-id="e6a1d-145">View-Only Organization Management</span></span>
  - <span data-ttu-id="e6a1d-146">보기 전용 받는 사람</span><span class="sxs-lookup"><span data-stu-id="e6a1d-146">View-Only Recipients</span></span>
  - <span data-ttu-id="e6a1d-147">준수 관리</span><span class="sxs-lookup"><span data-stu-id="e6a1d-147">Compliance Management</span></span>

<span data-ttu-id="e6a1d-148">역할 및 사용 권한에 대한 자세한 내용은 다음 리소스를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a1d-148">To learn more about roles and permissions, see the following resources:</span></span>

- [<span data-ttu-id="e6a1d-149">보안 및 준수 센터의 사용 권한</span><span class="sxs-lookup"><span data-stu-id="e6a1d-149">Permissions in the Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
- [<span data-ttu-id="e6a1d-150">Exchange Online의 기능 사용 권한</span><span class="sxs-lookup"><span data-stu-id="e6a1d-150">Feature permissions in Exchange Online</span></span>](/exchange/permissions-exo/feature-permissions)
- [<span data-ttu-id="e6a1d-151">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="e6a1d-151">Exchange Online PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)

## <a name="more-information"></a><span data-ttu-id="e6a1d-152">추가 정보</span><span class="sxs-lookup"><span data-stu-id="e6a1d-152">More information</span></span>
- [<span data-ttu-id="e6a1d-153">위협 탐색기는 전자 메일 엔터티 페이지에서 전자 메일 세부 정보를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a1d-153">Threat Explorer collect email details on the email entity page</span></span>](mdo-email-entity-page.md)
- [<span data-ttu-id="e6a1d-154">배달된 악성 전자 메일 찾기 및 조사</span><span class="sxs-lookup"><span data-stu-id="e6a1d-154">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)
- [<span data-ttu-id="e6a1d-155">SharePoint Online, OneDrive 및 파일에서 검색된 악성 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e6a1d-155">View malicious files detected in SharePoint Online, OneDrive, and Microsoft Teams</span></span>](mdo-for-spo-odb-and-teams.md)
- [<span data-ttu-id="e6a1d-156">위협 방지 상태 보고서</span><span class="sxs-lookup"><span data-stu-id="e6a1d-156">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="e6a1d-157">Microsoft Threat Protection의 자동화된 조사 및 대응</span><span class="sxs-lookup"><span data-stu-id="e6a1d-157">Automated investigation and response in Microsoft Threat Protection</span></span>](automated-investigation-response-office.md)