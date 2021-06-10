---
title: 데이터 손실 방지 경고 대시보드 시작
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: 데이터 손실 방지 정책에 대한 경고 정의 및 관리부터 시작하십시오.
ms.openlocfilehash: ad117eb0c5460b90c92c664f0c233b81d1882327
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843869"
---
# <a name="get-started-with-the-data-loss-prevention-alert-dashboard"></a><span data-ttu-id="2a71e-103">데이터 손실 방지 경고 대시보드 시작</span><span class="sxs-lookup"><span data-stu-id="2a71e-103">Get started with the data loss prevention alert dashboard</span></span>

<span data-ttu-id="2a71e-104">DLP(데이터 손실 방지) 정책은 중요한 항목의 의도하지 않은 공유를 방지하기 위해 보호 조치를 취할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a71e-104">Data loss prevention (DLP) policies can take protective actions to prevent unintentional sharing of sensitive items.</span></span> <span data-ttu-id="2a71e-105">중요한 항목에 대해 작업을 수행하면 DLP에 대한 알림을 구성하여 알림을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a71e-105">When an action is taken on a sensitive item, you can be notified by configuring alerts for DLP.</span></span> <span data-ttu-id="2a71e-106">이 문서에서는 DLP(데이터 손실 방지) 정책에 연결된 다양한 경고 정책을 정의하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="2a71e-106">This article shows you how to define rich alert policies that are linked to your data loss prevention (DLP) policies.</span></span> <span data-ttu-id="2a71e-107">Microsoft 365 센터에서 DLP 경고 관리 대시보드를 사용하여 [DLP](https://compliance.microsoft.com/datalossprevention?viewid=dlpalerts) 정책 위반에 대한 [경고Microsoft 365](https://compliance.microsoft.com/) 이벤트 및 관련 메타데이터를 보는 방법을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a71e-107">You'll see how to use the [DLP alert management dashboard](https://compliance.microsoft.com/datalossprevention?viewid=dlpalerts) in the [Microsoft 365 compliance center](https://compliance.microsoft.com/) to view alerts, events, and associated metadata for DLP policy violations.</span></span>

<span data-ttu-id="2a71e-108">DLP 경고를 새로 사용하는 경우 데이터 손실 방지 경고에 대한 자세한 정보 대시보드를 [검토해야 합니다.](dlp-alerts-dashboard-learn.md)</span><span class="sxs-lookup"><span data-stu-id="2a71e-108">If you are new to DLP alerts, you should review [Learn about the data loss prevention alerts dashboard](dlp-alerts-dashboard-learn.md)</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="2a71e-109">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="2a71e-109">Before you begin</span></span>

<span data-ttu-id="2a71e-110">시작하기 전에 다음 필수 필수가 있는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="2a71e-110">Before you begin, make sure you have the necessary prerequisites:</span></span>

-   <span data-ttu-id="2a71e-111">DLP 경고 관리 대시보드에 대한 라이선스</span><span class="sxs-lookup"><span data-stu-id="2a71e-111">Licensing for the DLP alerts management dashboard</span></span>
-   <span data-ttu-id="2a71e-112">경고 구성 옵션에 대한 라이선싱</span><span class="sxs-lookup"><span data-stu-id="2a71e-112">Licensing for alert configuration options</span></span>
-   <span data-ttu-id="2a71e-113">역할</span><span class="sxs-lookup"><span data-stu-id="2a71e-113">Roles</span></span>

### <a name="licensing-for-the-dlp-alert-management-dashboard"></a><span data-ttu-id="2a71e-114">DLP 경고 관리 대시보드에 대한 라이선스</span><span class="sxs-lookup"><span data-stu-id="2a71e-114">Licensing for the DLP alert management dashboard</span></span>

<span data-ttu-id="2a71e-115">DLP의 모든 적합한 Office 365 DLP 경고 관리 대시보드에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a71e-115">All eligible tenants for Office 365 DLP can access the DLP alert management dashboard.</span></span> <span data-ttu-id="2a71e-116">시작을 위해 Office 365, SharePoint Online 및 Exchange Online DLP를 비즈니스용 OneDrive.</span><span class="sxs-lookup"><span data-stu-id="2a71e-116">To get started, you should be eligible for Office 365 DLP for Exchange Online, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="2a71e-117">Office 365 DLP의 라이선스 요구 사항에 대한 자세한 내용은 사용자에게 서비스를 혜택을 제공할 수 있는 권한을 제공하는 라이선스를 [참조하세요.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#which-licenses-provide-the-rights-for-a-user-to-benefit-from-the-service-16)</span><span class="sxs-lookup"><span data-stu-id="2a71e-117">For more information about the licensing requirements for Office 365 DLP, see [Which licenses provide the rights for a user to benefit from the service?](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#which-licenses-provide-the-rights-for-a-user-to-benefit-from-the-service-16).</span></span>

<span data-ttu-id="2a71e-118">Teams DLP를 사용할 수 있는 끝점 [DLP를](endpoint-dlp-learn-about.md) 사용하는 고객에게는 끝점 DLP 정책 경고 및 [DLP](dlp-microsoft-teams.md) Teams 관리 대시보드에서 DLP 정책 경고가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a71e-118">Customers who use [Endpoint DLP](endpoint-dlp-learn-about.md) who are eligible for [Teams DLP](dlp-microsoft-teams.md) will see their endpoint DLP policy alerts and Teams DLP policy alerts in the DLP alert management dashboard.</span></span>

<span data-ttu-id="2a71e-119">콘텐츠 **미리 보기 기능은** 다음 라이선스에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a71e-119">The **content preview** feature is available only for these licenses:</span></span>

- <span data-ttu-id="2a71e-120">Microsoft 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="2a71e-120">Microsoft 365 (E5)</span></span>
- <span data-ttu-id="2a71e-121">Office 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="2a71e-121">Office 365 (E5)</span></span>
- <span data-ttu-id="2a71e-122">E5(고급 규정 준수) 추가 기능</span><span class="sxs-lookup"><span data-stu-id="2a71e-122">Advanced Compliance (E5) add on</span></span>
- <span data-ttu-id="2a71e-123">Microsoft 365 E5/A5 정보 보호 및 거버넌스</span><span class="sxs-lookup"><span data-stu-id="2a71e-123">Microsoft 365 E5/A5 Information Protection and Governance</span></span>
- <span data-ttu-id="2a71e-124">마이크로소프트 365 E5/A5 규정 준수</span><span class="sxs-lookup"><span data-stu-id="2a71e-124">Microsft 365 E5/A5 Compliance</span></span>

### <a name="licensing-for-alert-configuration-options"></a><span data-ttu-id="2a71e-125">경고 구성 옵션에 대한 라이선싱</span><span class="sxs-lookup"><span data-stu-id="2a71e-125">Licensing for alert configuration options</span></span>

<span data-ttu-id="2a71e-126">**단일 이벤트** 경고 구성: E1, F1 또는 G1 구독이 있는 조직이나 E3 또는 G3 구독이 있는 조직은 활동이 발생할 때마다 경고가 트리거되는 경우만 경고 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a71e-126">**Single-event alert configuration**: Organizations that have an E1, F1, or G1 subscription or an E3 or G3 subscription can create alert policies only where an alert is triggered every time an activity occurs.</span></span>

<span data-ttu-id="2a71e-127">**집계된 경고 구성:** 임계값을 기반으로 집계 경고 정책을 구성하려면 다음 라이선스 구성 중 하나를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a71e-127">**Aggregated alert configuration**: To configure aggregate alert policies based on a threshold, you must one of these licensing configurations:</span></span>

- <span data-ttu-id="2a71e-128">E5 또는 G5 구독</span><span class="sxs-lookup"><span data-stu-id="2a71e-128">An E5 or G5 subscription</span></span>
- <span data-ttu-id="2a71e-129">E1, F1 또는 G1 구독 또는 다음 기능 중 하나를 포함하는 E3 또는 G3 구독</span><span class="sxs-lookup"><span data-stu-id="2a71e-129">An E1, F1, or G1 subscription or an E3 or G3 subscription that includes one of the following features:</span></span>
    - <span data-ttu-id="2a71e-130">Office 365 Advanced Threat Protection Plan 2</span><span class="sxs-lookup"><span data-stu-id="2a71e-130">Office 365 Advanced Threat Protection Plan 2</span></span>
    - <span data-ttu-id="2a71e-131">Microsoft 365 E5 Compliance</span><span class="sxs-lookup"><span data-stu-id="2a71e-131">Microsoft 365 E5 Compliance</span></span>
    - <span data-ttu-id="2a71e-132">Microsoft 365 및 추가 기능 라이선스 감사</span><span class="sxs-lookup"><span data-stu-id="2a71e-132">Microsoft 365 eDiscovery and Audit add-on license</span></span>

### <a name="roles"></a><span data-ttu-id="2a71e-133">역할</span><span class="sxs-lookup"><span data-stu-id="2a71e-133">Roles</span></span>


<span data-ttu-id="2a71e-134">DLP 경고 관리 대시보드를 보거나 DLP 정책에서 경고 구성 옵션을 편집하려면 다음 역할 그룹 중 하나의 구성원이 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a71e-134">If you want to view the DLP alert management dashboard or to edit the alert configuration options in a DLP policy, you must be a member of one of these role groups:</span></span>

- <span data-ttu-id="2a71e-135">준수 관리자</span><span class="sxs-lookup"><span data-stu-id="2a71e-135">Compliance Administrator</span></span>
- <span data-ttu-id="2a71e-136">준수 데이터 관리자</span><span class="sxs-lookup"><span data-stu-id="2a71e-136">Compliance Data Administrator</span></span>
- <span data-ttu-id="2a71e-137">보안 관리자</span><span class="sxs-lookup"><span data-stu-id="2a71e-137">Security Administrator</span></span>
- <span data-ttu-id="2a71e-138">보안 운영자</span><span class="sxs-lookup"><span data-stu-id="2a71e-138">Security Operator</span></span>
- <span data-ttu-id="2a71e-139">보안 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="2a71e-139">Security Reader</span></span>

<span data-ttu-id="2a71e-140">DLP 경고 관리 대시보드에 액세스하려면 다음이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2a71e-140">To access the DLP alert management dashboard, you need the:</span></span>

- <span data-ttu-id="2a71e-141">경고 관리</span><span class="sxs-lookup"><span data-stu-id="2a71e-141">Manage alerts</span></span>

<span data-ttu-id="2a71e-142">및 다음 두 역할 중 하나:</span><span class="sxs-lookup"><span data-stu-id="2a71e-142">and either of these two roles:</span></span>

- <span data-ttu-id="2a71e-143">DLP 규정 준수 관리</span><span class="sxs-lookup"><span data-stu-id="2a71e-143">DLP Compliance Management</span></span>
- <span data-ttu-id="2a71e-144">View-Only DLP 준수 관리</span><span class="sxs-lookup"><span data-stu-id="2a71e-144">View-Only DLP Compliance Management</span></span>

<span data-ttu-id="2a71e-145">콘텐츠 미리 보기 기능 및 일치하는 중요한 콘텐츠 및 컨텍스트 기능에 액세스하려면 다음의 구성원이 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a71e-145">To access the Content preview feature and the Matched sensitive content and context features you must be a member of:</span></span>

- <span data-ttu-id="2a71e-146">콘텐츠 탐색기 콘텐츠 뷰어 역할 그룹</span><span class="sxs-lookup"><span data-stu-id="2a71e-146">Content Explorer Content Viewer role group</span></span>

<span data-ttu-id="2a71e-147">데이터 분류 콘텐츠 뷰어 역할이 미리 할당되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a71e-147">which has the data classification content viewer role pre-assigned.</span></span>

## <a name="dlp-alert-configuration"></a><span data-ttu-id="2a71e-148">DLP 경고 구성</span><span class="sxs-lookup"><span data-stu-id="2a71e-148">DLP alert configuration</span></span>

<span data-ttu-id="2a71e-149">DLP 정책에서 경고를 구성하는 방법에 대한 자세한 내용은 데이터 손실 방지로 시작하는 [위치를 참조합니다.](create-test-tune-dlp-policy.md#where-to-start-with-data-loss-prevention)</span><span class="sxs-lookup"><span data-stu-id="2a71e-149">To learn how to configure an alert in your DLP policy, see [Where to start with data loss prevention](create-test-tune-dlp-policy.md#where-to-start-with-data-loss-prevention).</span></span>

### <a name="aggregate-event-alert-configuration"></a><span data-ttu-id="2a71e-150">집계 이벤트 경고 구성</span><span class="sxs-lookup"><span data-stu-id="2a71e-150">Aggregate event alert configuration</span></span>

<span data-ttu-id="2a71e-151">집계된 경고 구성 옵션에 대한 사용이 허가된 경우 DLP 정책을 만들거나 편집할 때 이러한 옵션이 표시됩니다. [](#licensing-for-alert-configuration-options)</span><span class="sxs-lookup"><span data-stu-id="2a71e-151">If your org is licensed for [aggregated alert configuration options](#licensing-for-alert-configuration-options), then you'll see these options when you create or edit a DLP policy.</span></span>

:::image type="content" source="../media/incident-reports-options-aggregated-alerts.png" alt-text="집계된 경고 구성 옵션을 사용할 수 있는 사용자에 대한 문제 보고서 옵션을 보여 주는 스크린샷." border="false":::

<span data-ttu-id="2a71e-153">이 구성을 사용하면 활동이 정책 조건과 일치하거나 활동 수 또는 유출된 데이터의 볼륨에 따라 특정 임계값을 초과할 때마다 경고를 생성하도록 정책을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a71e-153">This configuration allows you to set up a policy to generate an alert every time an activity matches the policy conditions or when a certain threshold is exceeded, based on the number of activities or based on the volume of exfiltrated data.</span></span>

### <a name="single-event-alert-configuration"></a><span data-ttu-id="2a71e-154">단일 이벤트 경고 구성</span><span class="sxs-lookup"><span data-stu-id="2a71e-154">Single event alert configuration</span></span>

<span data-ttu-id="2a71e-155">단일 이벤트 경고 구성 [](#licensing-for-alert-configuration-options)옵션에 대한 사용이 허가된 경우 DLP 정책을 만들거나 편집할 때 이러한 옵션이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a71e-155">If your org is licensed for [single-event alert configuration options](#licensing-for-alert-configuration-options), then you'll see these options when you create or edit a DLP policy.</span></span> <span data-ttu-id="2a71e-156">DLP 규칙 일치가 발생할 때마다 발생하는 경고를 만들 때 이 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2a71e-156">Use this option to create an alert that's raised every time a DLP rule match happens.</span></span>

:::image type="content" source="../media/incident-reports-options-single-event-alerts.png" alt-text="단일 이벤트 경고 구성 옵션을 사용할 수 있는 사용자에 대한 문제 보고서 옵션을 보여 주는 스크린샷." border="false":::

## <a name="investigate-a-dlp-alert"></a><span data-ttu-id="2a71e-158">DLP 경고 조사</span><span class="sxs-lookup"><span data-stu-id="2a71e-158">Investigate a DLP alert</span></span>

<span data-ttu-id="2a71e-159">DLP 경고 관리 대시보드에서 작업하는 경우:</span><span class="sxs-lookup"><span data-stu-id="2a71e-159">To work with the DLP alert management dashboard:</span></span>

1. <span data-ttu-id="2a71e-160">Microsoft 365 [센터에서](https://www.compliance.microsoft.com)데이터 손실 **방지로 이동하십시오.**</span><span class="sxs-lookup"><span data-stu-id="2a71e-160">In the [Microsoft 365 compliance center](https://www.compliance.microsoft.com), go to **Data Loss Prevention**.</span></span>
2. <span data-ttu-id="2a71e-161">경고 **탭을 선택하여** DLP 경고 대시보드를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a71e-161">Select the **Alerts** tab to view the DLP alerts dashboard.</span></span>
3. <span data-ttu-id="2a71e-162">경고를 선택하여 세부 정보를 봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a71e-162">Select an alert to see details:</span></span>

:::image type="content" source="../media/alert-details.png" alt-text="Screenshot showing alert details on the DLP alert management dashboard." border="false":::

4. <span data-ttu-id="2a71e-164">경고와  연결된 모든 이벤트를 표시하려면 이벤트 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2a71e-164">Select the **Events** tab to view all of the events associated with the alert.</span></span> <span data-ttu-id="2a71e-165">특정 이벤트를 선택하면 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a71e-165">You can choose a particular event to view its details.</span></span> <span data-ttu-id="2a71e-166">사용 가능한 이벤트 세부 정보의 목록은 데이터 손실 방지 경고 대시보드에 대한 자세한 [정보를 참조하세요.](dlp-alerts-dashboard-learn.md)</span><span class="sxs-lookup"><span data-stu-id="2a71e-166">For a list of some of the available event details, see, [Learn about the data loss prevention Alerts dashboard](dlp-alerts-dashboard-learn.md).</span></span>
5. <span data-ttu-id="2a71e-167">세부 **정보를 선택하여** 경고에 대한 **개요** 페이지를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a71e-167">Select **Details** to open the **Overview** page for the alert.</span></span> <span data-ttu-id="2a71e-168">개요 페이지에서는 다음과 같은 요약 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2a71e-168">The overview page provides a summary:</span></span>
    1. <span data-ttu-id="2a71e-169">발생된 일</span><span class="sxs-lookup"><span data-stu-id="2a71e-169">of what happened</span></span>
    1. <span data-ttu-id="2a71e-170">정책 일치를 유발한 작업을 수행한 사람</span><span class="sxs-lookup"><span data-stu-id="2a71e-170">who performed the actions that caused the policy match</span></span>
    1. <span data-ttu-id="2a71e-171">일치하는 정책에 대한 정보 등</span><span class="sxs-lookup"><span data-stu-id="2a71e-171">information about the matched policy, and more</span></span> 

6. <span data-ttu-id="2a71e-172">이벤트 **탭을 선택하고** 다음에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="2a71e-172">Choose the **Events** tab to access the:</span></span>
    1. <span data-ttu-id="2a71e-173">관련된 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="2a71e-173">content involved</span></span>
    1. <span data-ttu-id="2a71e-174">일치하는 중요한 정보 유형</span><span class="sxs-lookup"><span data-stu-id="2a71e-174">sensitive information types matched</span></span>
    1. <span data-ttu-id="2a71e-175">메타데이터</span><span class="sxs-lookup"><span data-stu-id="2a71e-175">metadata</span></span>

7. <span data-ttu-id="2a71e-176">중요한 정보 **유형 탭을 선택하여** 콘텐츠에서 검색된 중요한 정보 유형에 대한 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a71e-176">Select the **Sensitive Info Types** tab to view details about the sensitive information types detected in the content.</span></span> <span data-ttu-id="2a71e-177">세부 정보에는 신뢰도, 개수 및 중요한 정보 유형과 일치하는 콘텐츠가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a71e-177">Details include confidence, count, and the content that matches the sensitive information type.</span></span>

8. <span data-ttu-id="2a71e-178">경고를 조사한 후 개요  탭으로 돌아와서 경고의 경과를 관리하고 설명을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a71e-178">After you investigate the alert, return to the **Overview** tab where you can manage triage and manage the disposition of the alert and add comments.</span></span>

- <span data-ttu-id="2a71e-179">워크플로 관리 기록을 확인하려면 관리 로그 **를 선택하세요.**</span><span class="sxs-lookup"><span data-stu-id="2a71e-179">To see the history of workflow management, choose **Management log**.</span></span>
- <span data-ttu-id="2a71e-180">경고에 대해 필요한 작업을 수행한 후 경고 상태를 해결된 으로 **설정하십시오.**</span><span class="sxs-lookup"><span data-stu-id="2a71e-180">After you take the required action for the alert, set the status of the alert to **Resolved**.</span></span>

## <a name="see-also"></a><span data-ttu-id="2a71e-181">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2a71e-181">See also</span></span>

- [<span data-ttu-id="2a71e-182">데이터 손실 방지 경고 및 경고 대시보드에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="2a71e-182">Learn about data loss prevention alerts and the alerts dashboard</span></span>](dlp-alerts-dashboard-learn.md)
- [<span data-ttu-id="2a71e-183">DLP 정책 만들기, 테스트 및 조정</span><span class="sxs-lookup"><span data-stu-id="2a71e-183">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)