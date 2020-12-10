---
title: Office 365용 Microsoft Defender 평가
description: 평가 모드에서 Office 365용 Defender는 맬웨어와 같은 판정을 기록하지만 메시지에 대해 활동하지 않는 Office 365 전자 메일 정책에 대한 Defender를 만듭니다.
keywords: Office 365, Office 365용 Microsoft Defender 평가, Office 365 평가, Office 365, Microsoft Defender, ATP 평가
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b5b095a1d75ead0f963a71d816e7d879b7cd3697
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49614801"
---
# <a name="evaluate-microsoft-defender-for-office-365"></a><span data-ttu-id="928c0-104">Office 365용 Microsoft Defender 평가</span><span class="sxs-lookup"><span data-stu-id="928c0-104">Evaluate Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> <span data-ttu-id="928c0-105">Office 365용 Microsoft Defender 평가는 곧 공개 미리 보기로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-105">Evaluate Microsoft Defender for Office 365 will soon be in public preview.</span></span> <span data-ttu-id="928c0-106">이 미리 보기 버전은 서비스 수준 계약 없이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-106">This preview version is provided without a service level agreement.</span></span> <span data-ttu-id="928c0-107">일부 기능은 지원되지 않을 수도, 기능이 제한될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-107">Certain features might not be supported or might have constrained capabilities.</span></span>

<span data-ttu-id="928c0-108">포괄적인 보안 제품 평가를 수행하면 업그레이드 및 구매에 대한 정보를 제공한 결정을 내리는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-108">Conducting a comprehensive security product evaluation can help give you informed decisions on upgrades and purchases.</span></span> <span data-ttu-id="928c0-109">보안 제품의 기능을 사용하여 보안 운영 팀이 일상적인 작업에서 어떻게 도움이 될 수 있는지 평가하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-109">It helps to try out the security product’s capabilities to assess how it can help your security operations team in their daily tasks.</span></span>

<span data-ttu-id="928c0-110">[Office 365용 Microsoft Defender](office-365-atp.md) 평가 환경은 보안 솔루션의 기능을 평가하는 데 집중할 수 있도록 장치 및 환경 구성의 복잡한 문제를 제거하도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-110">The [Microsoft Defender for Office 365](office-365-atp.md) evaluation experience is designed to eliminate the complexities of device and environment configuration so that you can focus on evaluating the capabilities of the security solution.</span></span> <span data-ttu-id="928c0-111">SharePoint, Office 클라이언트 또는 Teams가 아닌 전자 메일 보호에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-111">It only applies to email protection and not SharePoint, Office Clients, or Teams.</span></span>

<span data-ttu-id="928c0-112">Office 365용 Microsoft Defender를 지원하는 라이선스가 아직 없는 경우 [무료 30일](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA) 평가를 시작하고 Office 365 보안 및 준수 센터에서 기능을 & 수 있습니다. https://protection.office.com/homepage)</span><span class="sxs-lookup"><span data-stu-id="928c0-112">If you don't already have a license that supports Microsoft Defender for Office 365, you can start a [free 30-day evaluation](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA) and test the capabilities in the Office 365 Security & Compliance center (https://protection.office.com/homepage).</span></span> <span data-ttu-id="928c0-113">빠른 설치를 즐길 수 있으며 필요한 경우 쉽게 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-113">You'll enjoy the quick set-up and you can easily turn it off if necessary.</span></span>

## <a name="how-the-evaluation-works"></a><span data-ttu-id="928c0-114">평가 작동 방식</span><span class="sxs-lookup"><span data-stu-id="928c0-114">How the evaluation works</span></span>

<span data-ttu-id="928c0-115">평가 모드에서 Office 365용 Defender는 맬웨어와 같은 판정을 기록하지만 메시지에 대해 활동하지 않는 Office 365 전자 메일 정책에 대한 Defender를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-115">Defender for Office 365 in evaluation mode creates Defender for Office 365 email policies that log verdicts, such as malware, but don’t act on messages.</span></span> <span data-ttu-id="928c0-116">MX 레코드 구성을 변경할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-116">You are not required to change your MX record configuration.</span></span>

<span data-ttu-id="928c0-117">평가 모드에서는 [안전](atp-safe-attachments.md)첨부 파일, [](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)  [안전한](atp-safe-links.md)링크 및 피싱 방지 가장 정책이 사용자 대신 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-117">With evaluation mode, [Safe Attachments](atp-safe-attachments.md), [Safe Links](atp-safe-links.md), and [anti-phishing impersonation policies](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) are setup on your behalf.</span></span> <span data-ttu-id="928c0-118">Office 365용 모든 Defender 정책은 백그라운드에서 적용되지 않은 모드로 만들어지며 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-118">All Defender for Office 365 policies are created in non-enforcement mode in the background and are not visible to you.</span></span>

<span data-ttu-id="928c0-119">또한 설치의 일부로 평가 모드는 커넥터에 대한 향상된 [필터링을 구성합니다.](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)</span><span class="sxs-lookup"><span data-stu-id="928c0-119">As part of the setup, evaluation mode also configures [Enhanced Filtering for Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span> <span data-ttu-id="928c0-120">IP 주소 및 보낸 사람 정보를 보존하여 필터링 정확도를 향상시킵니다. 이 정보는 메일이 Office 365용 Defender 앞에 있는 ESG(전자 메일 보안 게이트웨이)를 통과할 때 손실됩니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-120">It improves filtering accuracy by preserving IP address and sender information, which are otherwise lost when mail passes through an email security gateway (ESG) in front of Defender for Office 365.</span></span> <span data-ttu-id="928c0-121">또한 EOP(Exchange Online Protection) 스팸 방지 및 피싱 방지 정책에 대한 필터링 정확도도 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-121">This also improves the filtering accuracy for your Exchange Online Protection (EOP) anti-spam and anti-phishing policies.</span></span>

<span data-ttu-id="928c0-122">일부 미지원 시나리오에 대한 잠재적인 프로덕션 영향을 최소화하기 위해 SCL(스팸 지수)을 -1로 설정하는 전송 규칙을 만들어 모든 EOP 필터링을 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-122">To minimize potential production impact on some unsupported scenarios, you can bypass all EOP filtering by creating a transport rule to set the Spam Confidence Level (SCL) to -1.</span></span> <span data-ttu-id="928c0-123">자세한 [내용은 EAC를 사용하여 메시지의 SCL을](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message)설정하는 메일 흐름   규칙을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-123">See [Use the EAC to create a mail flow rule that sets the SCL of a message](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) for details.</span></span>

<span data-ttu-id="928c0-124">평가 모드를 설정하면 매일 최대 90일간의 데이터가 업데이트되어 정책이 만들어지고 구현된 경우 차단될 메시지를 수량화하는 보고서가 업데이트됩니다(예: 삭제, 정크 메일 보내기, 정크 메일로 보내기, 정크 메일 보내기).</span><span class="sxs-lookup"><span data-stu-id="928c0-124">When the evaluation mode is set up, you will have a report updated daily with up to 90 days of data quantifying the messages that would have been blocked had the policies been made and implemented (for example, delete, send to junk, quarantine).</span></span> <span data-ttu-id="928c0-125">Office 365 및 EOP 검색에 대한 모든 Defender에 대한 보고서가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-125">Reports are generated for all Defender for Office 365 and EOP detections.</span></span> <span data-ttu-id="928c0-126">검색 기술(예: 가장)별로 집계되어 시간 범위별로 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-126">They are aggregated per detection technology (for example, impersonation) and can be filtered by time range.</span></span> <span data-ttu-id="928c0-127">또한 요구 시 메시지 보고서를 만들어 사용자 지정 피벗을 만들거나 위협 탐색기를 사용하여 심층 분석 메시지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-127">Additionally, message reports can be created on-demand to create custom pivots or to deep dive messages using Threat Explorer.</span></span>

<span data-ttu-id="928c0-128">간소화된 설정 환경을 통해 다음에 집중할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-128">With the simplified set-up experience, you can focus on:</span></span>

- <span data-ttu-id="928c0-129">평가 실행</span><span class="sxs-lookup"><span data-stu-id="928c0-129">Running the evaluation</span></span>
- <span data-ttu-id="928c0-130">자세한 보고서 확인</span><span class="sxs-lookup"><span data-stu-id="928c0-130">Getting a detailed report</span></span>
- <span data-ttu-id="928c0-131">보고서에서 작업 분석</span><span class="sxs-lookup"><span data-stu-id="928c0-131">Analyzing the report for action</span></span>
- <span data-ttu-id="928c0-132">평가 결과 발표</span><span class="sxs-lookup"><span data-stu-id="928c0-132">Presenting the evaluation outcome</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="928c0-133">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="928c0-133">Before you begin</span></span>

### <a name="licensing"></a><span data-ttu-id="928c0-134">라이선싱</span><span class="sxs-lookup"><span data-stu-id="928c0-134">Licensing</span></span>

<span data-ttu-id="928c0-135">평가에 액세스하려면 라이선스 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-135">To access the evaluation, you'll need to meet the licensing requirements.</span></span> <span data-ttu-id="928c0-136">다음 라이선스 중 한 개가 작동됩니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-136">Any of the following licenses will work:</span></span>

- <span data-ttu-id="928c0-137">Microsoft Defender for Office 365 요금제 1</span><span class="sxs-lookup"><span data-stu-id="928c0-137">Microsoft Defender for Office 365 Plan 1</span></span>
- <span data-ttu-id="928c0-138">Microsoft Defender for Office 365 요금제 2</span><span class="sxs-lookup"><span data-stu-id="928c0-138">Microsoft Defender for Office 365 Plan 2</span></span>
- <span data-ttu-id="928c0-139">Microsoft 365 E5, Microsoft 365 E5 보안</span><span class="sxs-lookup"><span data-stu-id="928c0-139">Microsoft 365 E5, Microsoft 365 E5 Security</span></span>
- <span data-ttu-id="928c0-140">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="928c0-140">Office 365 E5</span></span>

<span data-ttu-id="928c0-141">이러한 라이선스 중 하나만 있는 경우 평가판 라이선스를 얻어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-141">If you don't have one of those licenses, then you'll need to obtain a trial license.</span></span>

#### <a name="trial"></a><span data-ttu-id="928c0-142">평가판</span><span class="sxs-lookup"><span data-stu-id="928c0-142">Trial</span></span>

<span data-ttu-id="928c0-143">Office 365용 Microsoft Defender에 대한 평가판 라이선스를  얻하려면 대금 청구 관리자 역할 또는 전역 관리자 **역할이 필요합니다.**</span><span class="sxs-lookup"><span data-stu-id="928c0-143">To obtain a trial license for Microsoft Defender for Office 365, you need to have the **Billing admin role** or **Global admin role**.</span></span> <span data-ttu-id="928c0-144">전역 관리자 역할이 있는 사용자로부터 사용 권한을 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-144">Request permission from someone that has the Global admin role.</span></span> [<span data-ttu-id="928c0-145">구독 및 라이선스에 대해 자세히</span><span class="sxs-lookup"><span data-stu-id="928c0-145">Learn about subscriptions and licenses</span></span>](https://docs.microsoft.com/microsoft-365/commerce/licenses/subscriptions-and-licenses)

<span data-ttu-id="928c0-146">적절한 역할이 있는 경우 Microsoft 365 관리 센터에서 청구 서비스 구매 서비스로 > Microsoft Defender for Office 365(계획 2)에 대한 평가판 라이선스를 얻는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-146">Once you have the proper role, the recommended path is to obtain a trial license for Microsoft Defender for Office 365 (Plan 2) in the Microsoft 365 admin center by going to Billing > Purchase services.</span></span> <span data-ttu-id="928c0-147">평가판에는 25개 라이선스에 대한 30일 무료 평가판이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-147">The trial includes a 30-day free trial for 25 licenses.</span></span> <span data-ttu-id="928c0-148">[Office 365용 Microsoft Defender 평가판(계획 2)을 다운로드합니다.](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)</span><span class="sxs-lookup"><span data-stu-id="928c0-148">[Get a trial for Microsoft Defender for Office 365 (Plan 2)](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA).</span></span>

<span data-ttu-id="928c0-149">고급 위협을 모니터링하고 보고하는 평가가 있는 30일 기간이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-149">You'll have a 30-day window with the evaluation to monitor and report on advanced threats.</span></span> <span data-ttu-id="928c0-150">Office 365의 전체 Defender 기능을 원하는 경우 유료 구독을 구입할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-150">You'll also have the option to buy a paid subscription if you want the full Defender for Office 365 capabilities.</span></span>

### <a name="roles"></a><span data-ttu-id="928c0-151">역할</span><span class="sxs-lookup"><span data-stu-id="928c0-151">Roles</span></span>

<span data-ttu-id="928c0-152">평가 모드에서 Office 365용 Defender를 설정하려면 Exchange Online 역할이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-152">Exchange Online roles are required to set up Defender for Office 365 in evaluation mode.</span></span> <span data-ttu-id="928c0-153">다음 역할이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-153">The following roles are needed:</span></span>

|<span data-ttu-id="928c0-154">작업</span><span class="sxs-lookup"><span data-stu-id="928c0-154">Task</span></span>|<span data-ttu-id="928c0-155">역할</span><span class="sxs-lookup"><span data-stu-id="928c0-155">Role</span></span>|
|---|---|
|<span data-ttu-id="928c0-156">무료 평가판 다운로드 또는 Office 365용 Microsoft Defender 구입(계획 2)</span><span class="sxs-lookup"><span data-stu-id="928c0-156">Get a free trial or buy Microsoft Defender for Office 365 (Plan 2)</span></span>|<span data-ttu-id="928c0-157">청구 관리자 역할 또는 전역 관리자 역할</span><span class="sxs-lookup"><span data-stu-id="928c0-157">Billing admin role OR Global admin role</span></span>|
|<span data-ttu-id="928c0-158">평가 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="928c0-158">Create evaluation policy</span></span>|<span data-ttu-id="928c0-159">원격 및 허용 도메인 역할 보안 관리자 역할</span><span class="sxs-lookup"><span data-stu-id="928c0-159">Remote and Accepted Domains role; Security admin role</span></span>|
|<span data-ttu-id="928c0-160">평가 정책 편집</span><span class="sxs-lookup"><span data-stu-id="928c0-160">Edit evaluation policy</span></span>|<span data-ttu-id="928c0-161">원격 및 허용 도메인 역할 보안 관리자 역할</span><span class="sxs-lookup"><span data-stu-id="928c0-161">Remote and Accepted Domains role; Security admin role</span></span>|
|<span data-ttu-id="928c0-162">평가 정책 삭제</span><span class="sxs-lookup"><span data-stu-id="928c0-162">Delete evaluation policy</span></span>|<span data-ttu-id="928c0-163">원격 및 허용 도메인 역할 보안 관리자 역할</span><span class="sxs-lookup"><span data-stu-id="928c0-163">Remote and Accepted Domains role; Security admin role</span></span> |
|<span data-ttu-id="928c0-164">평가 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="928c0-164">View evaluation report</span></span>|<span data-ttu-id="928c0-165">보안 관리자 역할 또는 보안 읽기 관리자 역할</span><span class="sxs-lookup"><span data-stu-id="928c0-165">Security admin role OR Security reader role</span></span>|
|

### <a name="enhanced-filtering"></a><span data-ttu-id="928c0-166">향상된 필터링</span><span class="sxs-lookup"><span data-stu-id="928c0-166">Enhanced filtering</span></span>

<span data-ttu-id="928c0-167">대량 및 스팸 방지와 같은 Exchange Online Protection 정책은 동일하게 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-167">Your Exchange Online Protection policies, such as bulk and spam protection, will remain the same.</span></span> <span data-ttu-id="928c0-168">메시지 배달도 동일하게 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-168">Message delivery will also remain the same.</span></span> <span data-ttu-id="928c0-169">그러나 이 평가에서는 커넥터에 대한 향상된 필터링이 설정되어 우회하지 않는 한 메일 흐름 및 Exchange Online Protection 정책에 영향을 미치게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-169">However, the evaluation turns on enhanced filtering for connectors, which will impact your mailflow and Exchange Online Protection policies unless bypassed.</span></span>

<span data-ttu-id="928c0-170">커넥터에 대한 향상된 필터링을 통해 테넌트는 스푸핑 방지 보호를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-170">Enhanced filtering for connectors will allow tenants to use anti-spoofing protection.</span></span> <span data-ttu-id="928c0-171">커넥터에 대한 향상된 필터링을 설정하지 않고도 ESG(전자 메일 보안 게이트웨이)를 사용하는 경우 스푸핑 방지가 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-171">Anti-spoofing is not supported if you’re using an email security gateway (ESG) without having turned on Enhanced filtering for connectors.</span></span>

### <a name="urls"></a><span data-ttu-id="928c0-172">URL</span><span class="sxs-lookup"><span data-stu-id="928c0-172">URLs</span></span>

<span data-ttu-id="928c0-173">메일 흐름 중에 URL이 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-173">URLs will be detonated during mail flow.</span></span> <span data-ttu-id="928c0-174">특정 URL을 검색하지 못하도록 하려는 경우 허용된 URL 목록을 적절하게 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-174">If you don’t want specific URLs detonated, manage your list of allowed URLs appropriately.</span></span> <span data-ttu-id="928c0-175">자세한 [내용은 테넌트 허용/차단](tenant-allow-block-list.md) 목록에서 URL 관리를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="928c0-175">See [Manage URLs in the Tenant Allow/Block List](tenant-allow-block-list.md) for details.</span></span>

<span data-ttu-id="928c0-176">전자 메일 메시지 본문의 URL 링크는 줄 바꿈되지 않습니다. 이를 통해 고객 영향이 줄 바꿈되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-176">URL links in the email message bodies won't wrap, to lessen customer impact.</span></span>

### <a name="email-routing"></a><span data-ttu-id="928c0-177">전자 메일 라우팅</span><span class="sxs-lookup"><span data-stu-id="928c0-177">Email routing</span></span>

<span data-ttu-id="928c0-178">메일을 라우팅하는 인바운드 커넥터의 이름을 포함하여 전자 메일이 현재 라우팅되는 방법을 설정하는 데 필요한 해당 세부 정보를 준비해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-178">You need to prepare the corresponding details that you will need to set up how your email is currently routed, including the name of the inbound connector that routes your mail.</span></span> <span data-ttu-id="928c0-179">Exchange Online Protection만 사용하는 경우 커넥터가 없습니다.  [메일 흐름 및 전자 메일 라우팅에 대해 자세히](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/mail-flow)</span><span class="sxs-lookup"><span data-stu-id="928c0-179">If you are just using Exchange Online Protection, you won’t have a connector. [Learn about mail flow and email routing](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/mail-flow)</span></span>

<span data-ttu-id="928c0-180">지원되는 전자 메일 라우팅 시나리오는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-180">Supported email routing scenarios include:</span></span>

- <span data-ttu-id="928c0-181">타사 파트너 **및/또는** 프레미스 서비스 공급자: 평가하려는 인바운드 커넥터는 타사 공급자를 사용하고/ 또는 전자 메일 보안에 대한 솔루션을 사용 중입니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-181">**Third-party partner and/or on-premises service provider**: The inbound connector that you want to evaluate uses a third-party provider and/or you’re using a solution for email security on-premises.</span></span>
- <span data-ttu-id="928c0-182">**Microsoft Exchange Online 보호만:** 평가하려는 테넌트는 전자 메일 보안에 Office 365를 사용하며 MX(메일 교환) 레코드는 Microsoft를 지날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-182">**Microsoft Exchange Online Protection only**: The tenant that you want to evaluate uses Office 365 for email security and the Mail Exchange (MX) record points to Microsoft.</span></span>

### <a name="email-security-gateway"></a><span data-ttu-id="928c0-183">전자 메일 보안 게이트웨이</span><span class="sxs-lookup"><span data-stu-id="928c0-183">Email security gateway</span></span>

<span data-ttu-id="928c0-184">타사 ESG(전자 메일 보안 게이트웨이)를 사용하는 경우 공급자의 이름을 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-184">If you’re using a third-party email security gateway (ESG), you’ll need to know the provider’s name.</span></span> <span data-ttu-id="928c0-185">ESG를 사용하는 경우 장치용 공용 IP 주소(예: ES)를 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-185">If you’re using an ESG on-premises or non-supported vendors, you’ll need to know the public IP address(es) for the devices.</span></span>

<span data-ttu-id="928c0-186">지원되는 타사 파트너는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-186">Supported third-party partners include:</span></span>

- <span data-ttu-id="928c0-187">Barracuda</span><span class="sxs-lookup"><span data-stu-id="928c0-187">Barracuda</span></span>
- <span data-ttu-id="928c0-188">IronPort</span><span class="sxs-lookup"><span data-stu-id="928c0-188">IronPort</span></span>
- <span data-ttu-id="928c0-189">Mimecast</span><span class="sxs-lookup"><span data-stu-id="928c0-189">Mimecast</span></span>
- <span data-ttu-id="928c0-190">Proofpoint</span><span class="sxs-lookup"><span data-stu-id="928c0-190">Proofpoint</span></span>
- <span data-ttu-id="928c0-191">소포스</span><span class="sxs-lookup"><span data-stu-id="928c0-191">Sophos</span></span>
- <span data-ttu-id="928c0-192">Symantec</span><span class="sxs-lookup"><span data-stu-id="928c0-192">Symantec</span></span>
- <span data-ttu-id="928c0-193">경향 마이크로</span><span class="sxs-lookup"><span data-stu-id="928c0-193">Trend Micro</span></span>

### <a name="scoping"></a><span data-ttu-id="928c0-194">겹치기</span><span class="sxs-lookup"><span data-stu-id="928c0-194">Scoping</span></span>

<span data-ttu-id="928c0-195">평가 범위를 인바운드 커넥터로 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-195">You will be able to scope the evaluation to an inbound connector.</span></span> <span data-ttu-id="928c0-196">커넥터가 구성되지 않은 경우 관리자는 평가 범위를 통해 테넌트의 모든 사용자로부터 데이터를 수집하여 Office 365용 Defender를 평가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-196">If there's no connector configured, then the evaluation scope will allow admins to gather data from any user in your tenant to evaluate Defender for Office 365.</span></span>

## <a name="get-started-with-the-evaluation"></a><span data-ttu-id="928c0-197">평가 시작</span><span class="sxs-lookup"><span data-stu-id="928c0-197">Get started with the evaluation</span></span>

<span data-ttu-id="928c0-198">Office 365 보안 및 준수 센터에서 Office 365용 Microsoft Defender 평가판 & 카드(다음 세 가지 액세스 https://protection.office.com/homepage) 지점에서)를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-198">Find the Microsoft Defender for Office 365 evaluation set-up card in the Office 365 Security & Compliance center (https://protection.office.com/homepage) from three access points:</span></span>

- <span data-ttu-id="928c0-199">위협 관리 > 대시보드</span><span class="sxs-lookup"><span data-stu-id="928c0-199">Threat management > Dashboard</span></span>
- <span data-ttu-id="928c0-200">위협 관리 > 정책</span><span class="sxs-lookup"><span data-stu-id="928c0-200">Threat management > Policy</span></span>
- <span data-ttu-id="928c0-201">보고서 > 대시보드</span><span class="sxs-lookup"><span data-stu-id="928c0-201">Reports > Dashboard</span></span>

## <a name="setting-up-the-evaluation"></a><span data-ttu-id="928c0-202">평가 설정</span><span class="sxs-lookup"><span data-stu-id="928c0-202">Setting up the evaluation</span></span>

<span data-ttu-id="928c0-203">평가를 위한 설정 흐름을 시작하면 두 가지 라우팅 옵션이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-203">Once you start the set-up flow for your evaluation, you'll be given two routing options.</span></span> <span data-ttu-id="928c0-204">조직의 메일 라우팅 설정 및 평가 요구에 따라 타사 및/또는 프레미스 서비스 공급자를 사용할지 아니면 서비스 공급자만 사용하고 있는지를 선택할 수 Microsoft Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="928c0-204">Depending on your organization’s mail routing setup and evaluation needs, you can select whether you are using a third-party and/or on-premises service provider or only Microsoft Exchange Online.</span></span>

- <span data-ttu-id="928c0-205">타사 파트너 및/또는 프레미스 서비스 공급자를 사용하는 경우 드롭다운 메뉴에서 공급업체의 이름을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-205">If you are using a third-party partner and/or on-premises service provider, you'll need to select the name of the vendor from the drop-down menu.</span></span> <span data-ttu-id="928c0-206">다른 커넥터 관련 세부 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-206">Provide the other connector-related details.</span></span>

- <span data-ttu-id="928c0-207">MX 레코드가 Microsoft를 Microsoft Exchange Online Exchange Online 사서함이 있는 경우 이 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-207">Select Microsoft Exchange Online if the MX record points to Microsoft and you have an Exchange Online mailbox.</span></span>

<span data-ttu-id="928c0-208">설정을 검토하고 필요한 경우 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-208">Review your settings and edit them if necessary.</span></span> <span data-ttu-id="928c0-209">그런 다음 평가 **만들기를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="928c0-209">Then, select **Create evaluation**.</span></span> <span data-ttu-id="928c0-210">설정이 완료된 것을 나타내는 확인 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-210">You should get a confirmation message to indicate that your set-up is complete.</span></span>

<span data-ttu-id="928c0-211">Office 365용 Microsoft Defender 평가 보고서는 매일 한 번 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-211">Your Microsoft Defender for Office 365 evaluation report is generated once per day.</span></span> <span data-ttu-id="928c0-212">데이터를 채우는 데 최대 24시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-212">It may take up to 24 hours for the data to populate.</span></span>

### <a name="exchange-rules-optional"></a><span data-ttu-id="928c0-213">Exchange 규칙(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="928c0-213">Exchange rules (optional)</span></span>

<span data-ttu-id="928c0-214">기존 게이트웨이가 있는 경우 커넥터에 대한 향상된 필터링을 활성화하고 들어오는 보낸 사람 IP 주소를 변경하기 때문에 필터링을 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-214">If you have an existing gateway, you might want to bypass filtering because it will activate enhanced filtering for connectors and alter the incoming sender IP address.</span></span> <span data-ttu-id="928c0-215">우회하려면 Exchange 관리 센터로 이동하여 SCL -1의 정책을 생성합니다(아직 SCL이 없는 경우).</span><span class="sxs-lookup"><span data-stu-id="928c0-215">To bypass, navigate to the Exchange admin center and create a policy of SCL -1 (if you don’t already have one).</span></span> <span data-ttu-id="928c0-216">규칙 구성 요소 및 규칙의 작동 방식에 대한 자세한 내용은 Exchange Online의 메일 흐름 규칙(전송 규칙)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="928c0-216">For details on the rule components and how they work, see Mail flow rules (transport rules) in Exchange Online.</span></span>

## <a name="evaluate-capabilities"></a><span data-ttu-id="928c0-217">기능 평가</span><span class="sxs-lookup"><span data-stu-id="928c0-217">Evaluate capabilities</span></span>

<span data-ttu-id="928c0-218">평가 보고서가 생성된 후 조직의 전자 메일 및 공동 작업 작업 공간에서 식별된 고급 위협 링크, 고급 위협 첨부 파일 및 잠재적인 가장 수를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="928c0-218">After the evaluation report has been generated, see how many advanced threat links, advanced threat attachments, and potential impersonations were identified in the emails and collaboration workspaces in your organization.</span></span>

<span data-ttu-id="928c0-219">평가판이 만료되면 90일 동안 보고서에 계속 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-219">Once the trial has expired, you can continue to access the report for 90 days.</span></span> <span data-ttu-id="928c0-220">그러나 더 이상 정보를 수집하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-220">However, it won’t collect any more information.</span></span> <span data-ttu-id="928c0-221">평가판이 만료된 후 Office 365용 Microsoft Defender를 계속 사용하려면 [Office 365용 Microsoft Defender](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)유료 구독(계획 2)을 구입해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-221">If you want to continue using Microsoft Defender for Office 365 after your trial has expired, make sure you [buy a paid subscription for Microsoft Defender for Office 365 (Plan 2)](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA).</span></span>

<span data-ttu-id="928c0-222">설정으로 **이동하여** 라우팅을 업데이트하거나 평가를 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-222">You can go to **Settings** to update your routing or turn off your evaluation at any time.</span></span> <span data-ttu-id="928c0-223">그러나 해제한 후 평가를 계속하기로 결정한 경우 동일한 설정 프로세스를 다시 진행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-223">However, you need to go through the same set-up process again should you decide to continue your evaluation after having turned it off.</span></span>

## <a name="provide-feedback"></a><span data-ttu-id="928c0-224">피드백 제공</span><span class="sxs-lookup"><span data-stu-id="928c0-224">Provide feedback</span></span>

<span data-ttu-id="928c0-225">사용자 의견은 고급 공격으로부터 환경을 보호하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-225">Your feedback helps us get better at protecting your environment from advanced attacks.</span></span> <span data-ttu-id="928c0-226">제품 기능 및 평가 결과에 대한 경험과 노출을 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="928c0-226">Share your experience and impressions of product capabilities and evaluation results.</span></span>

<span data-ttu-id="928c0-227">의견 **제공을** 선택하여 의견을 보내주세요.</span><span class="sxs-lookup"><span data-stu-id="928c0-227">Select **Give feedback** to let us know what you think.</span></span>
