---
title: Microsoft Defender for Office 365 평가
description: Defender for Office 365 for evaluation mode는 맬웨어 같은 verdicts를 기록 하지만 메시지에는 작동 하지 않는 Office 365 전자 메일 정책에 대 한 Defender를 만듭니다.
keywords: office 365, Microsoft Defender for Office 365, office 365 evaluation, office 365, Microsoft Defender, ATP 체험
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
ms.openlocfilehash: 12b6499822f8ed97ace8468054f219361d925332
ms.sourcegitcommit: a566ef236c85edfd566c8c3f859b80f9e5ce0473
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2020
ms.locfileid: "49562997"
---
# <a name="evaluate-microsoft-defender-for-office-365"></a><span data-ttu-id="731af-104">Microsoft Defender for Office 365 평가</span><span class="sxs-lookup"><span data-stu-id="731af-104">Evaluate Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

>[!IMPORTANT]
><span data-ttu-id="731af-105">Office 2013에 대 한 Microsoft Defender가 곧 공개 될 예정입니다. 365이 미리 보기 버전은 서비스 수준 계약 없이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="731af-105">Evaluate Microsoft Defender for Office 365 will soon be in public preview This preview version is provided without a service level agreement.</span></span> <span data-ttu-id="731af-106">특정 기능은 지원 되지 않거나 제한 된 기능을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="731af-106">Certain features might not be supported or might have constrained capabilities.</span></span>

<span data-ttu-id="731af-107">포괄적인 보안 제품 평가를 수행 하면 업그레이드 및 구매에 대 한 의사 결정을 내리는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="731af-107">Conducting a comprehensive security product evaluation can help give you informed decisions on upgrades and purchases.</span></span> <span data-ttu-id="731af-108">이를 통해 보안 제품의 기능을 사용해 일상적인 작업을 수행 하는 데 보안 운영 팀이 어떻게 도움이 되는지 평가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="731af-108">It helps to try out the security product’s capabilities to assess how it can help your security operations team in their daily tasks.</span></span>

<span data-ttu-id="731af-109">[Microsoft Defender For Office 365](office-365-atp.md) 평가 환경은 보안 솔루션의 기능 평가에 집중할 수 있도록 장치 및 환경 구성의 복잡성을 없애기 위해 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="731af-109">The [Microsoft Defender for Office 365](office-365-atp.md) evaluation experience is designed to eliminate the complexities of device and environment configuration so that you can focus on evaluating the capabilities of the security solution.</span></span> <span data-ttu-id="731af-110">SharePoint, Office 클라이언트 또는 팀이 아닌 전자 메일 보호에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="731af-110">It only applies to email protection and not SharePoint, Office Clients, or Teams.</span></span>

<span data-ttu-id="731af-111">Office 365 용 Microsoft Defender를 지 원하는 라이선스가 아직 없는 경우에는 [30 일 무료 평가판](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA) 을 시작 하 고 Office 365 보안 & 준수 센터 ()에서 기능을 테스트할 수 있습니다 https://protection.office.com/homepage) .</span><span class="sxs-lookup"><span data-stu-id="731af-111">If you don't already have a license that supports Microsoft Defender for Office 365, you can start a [free 30-day evaluation](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA) and test the capabilities in the Office 365 Security & Compliance center (https://protection.office.com/homepage).</span></span> <span data-ttu-id="731af-112">빠른 설정을 사용 하 고 필요한 경우 쉽게 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="731af-112">You'll enjoy the quick set-up and you can easily turn it off if necessary.</span></span>

## <a name="how-the-evaluation-works"></a><span data-ttu-id="731af-113">평가 작동 방식</span><span class="sxs-lookup"><span data-stu-id="731af-113">How the evaluation works</span></span>

<span data-ttu-id="731af-114">Defender for Office 365 for evaluation mode는 맬웨어 같은 verdicts를 기록 하지만 메시지에는 작동 하지 않는 Office 365 전자 메일 정책에 대 한 Defender를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="731af-114">Defender for Office 365 in evaluation mode creates Defender for Office 365 email policies that log verdicts, such as malware, but don’t act on messages.</span></span> <span data-ttu-id="731af-115">MX 레코드 구성을 변경할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="731af-115">You are not required to change your MX record configuration.</span></span>

<span data-ttu-id="731af-116">평가 모드, [안전한 첨부 파일](atp-safe-attachments.md), [안전한 링크](atp-safe-links.md)및 [피싱 방지 가장 정책이](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) 사용자 대신 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="731af-116">With evaluation mode, [Safe Attachments](atp-safe-attachments.md), [Safe Links](atp-safe-links.md), and [anti-phishing impersonation policies](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) are setup on your behalf.</span></span> <span data-ttu-id="731af-117">모든 Defender for Office 365 정책은 백그라운드에서 강요 되지 않음 모드로 만들어지고 사용자에 게 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="731af-117">All Defender for Office 365 policies are created in non-enforcement mode in the background and are not visible to you.</span></span>

<span data-ttu-id="731af-118">설치 과정의 일부로 평가 모드는 [커넥터에 대 한 향상 된 필터링](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)도 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="731af-118">As part of the setup, evaluation mode also configures [Enhanced Filtering for Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span> <span data-ttu-id="731af-119">Office 365의 Defender 앞에 있는 ESG (전자 메일 보안 게이트웨이)를 통해 메일이 전달 될 때 손실 되는 IP 주소 및 보낸 사람 정보를 유지 하 여 필터링 정확도를 향상 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="731af-119">It improves filtering accuracy by preserving IP address and sender information, which are otherwise lost when mail passes through an email security gateway (ESG) in front of Defender for Office 365.</span></span> <span data-ttu-id="731af-120">또한 EOP (Exchange Online Protection) 스팸 방지 및 피싱 방지 정책에 대 한 필터링 정확성이 향상 됩니다.</span><span class="sxs-lookup"><span data-stu-id="731af-120">This also improves the filtering accuracy for your Exchange Online Protection (EOP) anti-spam and anti-phishing policies.</span></span>

<span data-ttu-id="731af-121">일부 지원 되지 않는 시나리오에 대 한 잠재적 프로덕션 영향을 최소화 하기 위해 SCL (스팸 지 수)을-1로 설정 하는 전송 규칙을 만들어 모든 EOP 필터링을 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="731af-121">To minimize potential production impact on some unsupported scenarios, you can bypass all EOP filtering by creating a transport rule to set the Spam Confidence Level (SCL) to -1.</span></span> <span data-ttu-id="731af-122">자세한 내용은 [EAC를 사용 하 여 메시지의 SCL을 설정 하는 메일 흐름 규칙 만들기를](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message)참조 하십시오   .</span><span class="sxs-lookup"><span data-stu-id="731af-122">See [Use the EAC to create a mail flow rule that sets the SCL of a message](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) for details.</span></span>

<span data-ttu-id="731af-123">평가 모드를 설정 하면 매일 보고서가 업데이트 되 고 (예: 삭제, 정크로 보내기, 격리) 정책이 적용 되어 구현 된 것으로 차단 된 메시지를 수량화 하는 데이터를 최대 90 일까지 정량화 합니다.</span><span class="sxs-lookup"><span data-stu-id="731af-123">When the evaluation mode is set up, you will have a report updated daily with up to 90 days of data quantifying the messages that would have been blocked had the policies been made and implemented (for example, delete, send to junk, quarantine).</span></span> <span data-ttu-id="731af-124">모든 Defender for Office 365 및 EOP 검색에 대 한 보고서가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="731af-124">Reports are generated for all Defender for Office 365 and EOP detections.</span></span> <span data-ttu-id="731af-125">이러한 사용자는 검색 기술에 따라 집계 되며 (예: 가장) 시간 범위를 기준으로 필터링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="731af-125">They are aggregated per detection technology (for example, impersonation) and can be filtered by time range.</span></span> <span data-ttu-id="731af-126">또한 메시지 보고서를 주문형으로 만들어 사용자 지정 피벗을 만들거나 위협 탐색기를 사용 하 여 메시지를 자세히 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="731af-126">Additionally, message reports can be created on-demand to create custom pivots or to deep dive messages using Threat Explorer.</span></span>

<span data-ttu-id="731af-127">간단한 설정 환경에서는 다음에 집중할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="731af-127">With the simplified set-up experience, you can focus on:</span></span>

- <span data-ttu-id="731af-128">평가 실행</span><span class="sxs-lookup"><span data-stu-id="731af-128">Running the evaluation</span></span>
- <span data-ttu-id="731af-129">자세한 보고서 가져오기</span><span class="sxs-lookup"><span data-stu-id="731af-129">Getting a detailed report</span></span>
- <span data-ttu-id="731af-130">작업에 대 한 보고서 분석</span><span class="sxs-lookup"><span data-stu-id="731af-130">Analyzing the report for action</span></span>
- <span data-ttu-id="731af-131">평가 결과 발표</span><span class="sxs-lookup"><span data-stu-id="731af-131">Presenting the evaluation outcome</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="731af-132">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="731af-132">Before you begin</span></span>

### <a name="licensing"></a><span data-ttu-id="731af-133">라이선싱</span><span class="sxs-lookup"><span data-stu-id="731af-133">Licensing</span></span>

<span data-ttu-id="731af-134">평가에 액세스 하려면 라이선스 요구 사항을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="731af-134">To access the evaluation, you'll need to meet the licensing requirements.</span></span> <span data-ttu-id="731af-135">다음 라이선스 중 하나를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="731af-135">Any of the following licenses will work:</span></span>

- <span data-ttu-id="731af-136">Microsoft Defender for Office 365 계획 1</span><span class="sxs-lookup"><span data-stu-id="731af-136">Microsoft Defender for Office 365 Plan 1</span></span>
- <span data-ttu-id="731af-137">Microsoft Defender for Office 365 계획 2</span><span class="sxs-lookup"><span data-stu-id="731af-137">Microsoft Defender for Office 365 Plan 2</span></span>
- <span data-ttu-id="731af-138">Microsoft 365 E5, Microsoft 365 E5 보안</span><span class="sxs-lookup"><span data-stu-id="731af-138">Microsoft 365 E5, Microsoft 365 E5 Security</span></span>
- <span data-ttu-id="731af-139">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="731af-139">Office 365 E5</span></span>

<span data-ttu-id="731af-140">이러한 라이선스 중 하나가 없으면 평가판 라이선스를 취득 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="731af-140">If you don't have one of those licenses, then you'll need to obtain a trial license.</span></span>

#### <a name="trial"></a><span data-ttu-id="731af-141">평가판</span><span class="sxs-lookup"><span data-stu-id="731af-141">Trial</span></span>

<span data-ttu-id="731af-142">Microsoft Defender for Office 365에 대 한 평가판 라이선스를 취득 하려면 **청구 관리자 역할** 또는 **전역 관리자 역할이** 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="731af-142">To obtain a trial license for Microsoft Defender for Office 365, you need to have the **Billing admin role** or **Global admin role**.</span></span> <span data-ttu-id="731af-143">전역 관리자 역할이 있는 사용자의 권한을 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="731af-143">Request permission from someone that has the Global admin role.</span></span> [<span data-ttu-id="731af-144">구독 및 라이선스에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="731af-144">Learn about subscriptions and licenses</span></span>](https://docs.microsoft.com/microsoft-365/commerce/licenses/subscriptions-and-licenses)

<span data-ttu-id="731af-145">적절 한 역할을 수행한 후에는 Microsoft 365 관리 센터에서 Office 365 (요금제 2)에 대 한 Microsoft Defender에 대 한 평가판 라이선스를 취득 하는 것이 좋습니다 > Purchase service로 이동 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="731af-145">Once you have the proper role, the recommended path is to obtain a trial license for Microsoft Defender for Office 365 (Plan 2) in the Microsoft 365 admin center by going to Billing > Purchase services.</span></span> <span data-ttu-id="731af-146">평가판에는 25 개 라이선스에 대 한 30 일 무료 평가판이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="731af-146">The trial includes a 30-day free trial for 25 licenses.</span></span> <span data-ttu-id="731af-147">[Microsoft Defender For Office 365 (요금제 2)에 대 한 평가판을 받습니다](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA).</span><span class="sxs-lookup"><span data-stu-id="731af-147">[Get a trial for Microsoft Defender for Office 365 (Plan 2)](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA).</span></span> 

<span data-ttu-id="731af-148">최종 위협에 대 한 모니터링 및 보고를 위한 평가와 함께 30 일의 기간을 갖게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="731af-148">You'll have a 30-day window with the evaluation to monitor and report on advanced threats.</span></span> <span data-ttu-id="731af-149">또한 전체 Defender for Office 365 기능을 원하는 경우 유료 구독을 구입 하는 옵션도 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="731af-149">You'll also have the option to buy a paid subscription if you want the full Defender for Office 365 capabilities.</span></span>

### <a name="roles"></a><span data-ttu-id="731af-150">역할</span><span class="sxs-lookup"><span data-stu-id="731af-150">Roles</span></span>

<span data-ttu-id="731af-151">Exchange Online 역할은 평가 모드에서 Office 365 용 Defender를 설정 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="731af-151">Exchange Online roles are required to set up Defender for Office 365 in evaluation mode.</span></span> <span data-ttu-id="731af-152">필요한 역할은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="731af-152">The following roles are needed:</span></span>

|<span data-ttu-id="731af-153">작업</span><span class="sxs-lookup"><span data-stu-id="731af-153">Task</span></span> | <span data-ttu-id="731af-154">역할</span><span class="sxs-lookup"><span data-stu-id="731af-154">Role</span></span> |
|-----| -----|
| <span data-ttu-id="731af-155">무료 평가판 받기 또는 Office 365 용 Microsoft Defender 구매 (요금제 2)</span><span class="sxs-lookup"><span data-stu-id="731af-155">Get a free trial or buy Microsoft Defender for Office 365 (Plan 2)</span></span>| <span data-ttu-id="731af-156">청구 관리자 역할 또는 전역 관리자 역할</span><span class="sxs-lookup"><span data-stu-id="731af-156">Billing admin role OR Global admin role</span></span>|
| <span data-ttu-id="731af-157">평가 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="731af-157">Create evaluation policy</span></span>| <span data-ttu-id="731af-158">원격 및 허용 도메인 역할 보안 관리자 역할</span><span class="sxs-lookup"><span data-stu-id="731af-158">Remote and Accepted Domains role; Security admin role</span></span>|
| <span data-ttu-id="731af-159">평가 정책 편집</span><span class="sxs-lookup"><span data-stu-id="731af-159">Edit evaluation policy</span></span> | <span data-ttu-id="731af-160">원격 및 허용 도메인 역할 보안 관리자 역할</span><span class="sxs-lookup"><span data-stu-id="731af-160">Remote and Accepted Domains role; Security admin role</span></span> |
| <span data-ttu-id="731af-161">평가 정책 삭제</span><span class="sxs-lookup"><span data-stu-id="731af-161">Delete evaluation policy</span></span> | <span data-ttu-id="731af-162">원격 및 허용 도메인 역할 보안 관리자 역할</span><span class="sxs-lookup"><span data-stu-id="731af-162">Remote and Accepted Domains role; Security admin role</span></span> |
|<span data-ttu-id="731af-163">평가 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="731af-163">View evaluation report</span></span> | <span data-ttu-id="731af-164">보안 관리자 역할 또는 보안 독자 역할</span><span class="sxs-lookup"><span data-stu-id="731af-164">Security admin role OR Security reader role</span></span>|

### <a name="enhanced-filtering"></a><span data-ttu-id="731af-165">향상 된 필터링</span><span class="sxs-lookup"><span data-stu-id="731af-165">Enhanced filtering</span></span>

<span data-ttu-id="731af-166">대량 및 스팸 보호와 같은 Exchange Online 보호 정책이 동일 하 게 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="731af-166">Your Exchange Online Protection policies, such as bulk and spam protection, will remain the same.</span></span> <span data-ttu-id="731af-167">또한 메시지 배달은 동일 하 게 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="731af-167">Message delivery will also remain the same.</span></span> <span data-ttu-id="731af-168">그러나 계산을 통해 커넥터에 대 한 향상 된 필터링이 설정 되므로 무시 되지 않으면 메일 흐름 및 Exchange Online 보호 정책에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="731af-168">However, the evaluation turns on enhanced filtering for connectors, which will impact your mailflow and Exchange Online Protection policies unless bypassed.</span></span>

<span data-ttu-id="731af-169">커넥터에 대 한 향상 된 필터링을 통해 테 넌 트에서 스푸핑 방지 보호를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="731af-169">Enhanced filtering for connectors will allow tenants to use anti-spoofing protection.</span></span> <span data-ttu-id="731af-170">커넥터에 대 한 향상 된 필터링을 설정 하지 않고 ESG (전자 메일 보안 게이트웨이)를 사용 하는 경우에는 스푸핑 방지가 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="731af-170">Anti-spoofing is not supported if you’re using an email security gateway (ESG) without having turned on Enhanced filtering for connectors.</span></span>

### <a name="urls"></a><span data-ttu-id="731af-171">URL</span><span class="sxs-lookup"><span data-stu-id="731af-171">URLs</span></span>

<span data-ttu-id="731af-172">메일 흐름 중에 Url이 열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="731af-172">URLs will be detonated during mail flow.</span></span> <span data-ttu-id="731af-173">특정 Url을 열 않으려면 허용 되는 Url 목록을 적절 하 게 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="731af-173">If you don’t want specific URLs detonated, manage your list of allowed URLs appropriately.</span></span> <span data-ttu-id="731af-174">자세한 내용은 [테 넌 트 허용/차단 목록에서 Url 관리](tenant-allow-block-list.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="731af-174">See [Manage URLs in the Tenant Allow/Block List](tenant-allow-block-list.md) for details.</span></span>

<span data-ttu-id="731af-175">고객의 영향을 줄이기 위해 전자 메일 메시지 본문의 URL 링크가 래핑 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="731af-175">URL links in the email message bodies won't wrap, to lessen customer impact.</span></span>

### <a name="email-routing"></a><span data-ttu-id="731af-176">전자 메일 라우팅</span><span class="sxs-lookup"><span data-stu-id="731af-176">Email routing</span></span>

<span data-ttu-id="731af-177">메일을 라우팅하는 인바운드 커넥터의 이름을 비롯 하 여 전자 메일이 현재 라우팅되는 방법을 설정 하는 데 필요한 세부 정보를 준비 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="731af-177">You need to prepare the corresponding details that you will need to set up how your email is currently routed, including the name of the inbound connector that routes your mail.</span></span> <span data-ttu-id="731af-178">Exchange Online Protection을 사용 하는 경우에는 커넥터가 없는 것입니다.  [메일 흐름 및 전자 메일 라우팅에 대 한 자세한](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/mail-flow) 정보</span><span class="sxs-lookup"><span data-stu-id="731af-178">If you are just using Exchange Online Protection, you won’t have a connector. [Learn about mail flow and email routing](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/mail-flow)</span></span>

<span data-ttu-id="731af-179">지원 되는 전자 메일 라우팅 시나리오는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="731af-179">Supported email routing scenarios include:</span></span>

- <span data-ttu-id="731af-180">타사 **파트너 및/또는 온-프레미스 서비스 공급자**: 평가 하려는 인바운드 커넥터는 타사 공급자를 사용 하거나 전자 메일 보안에 온-프레미스 솔루션을 사용 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="731af-180">**Third-party partner and/or on-premises service provider**: The inbound connector that you want to evaluate uses a third-party provider and/or you’re using a solution for email security on-premises.</span></span>  
- <span data-ttu-id="731af-181">**Microsoft Exchange Online Protection 전용**: 평가 하려는 테 넌 트는 전자 메일 보안에 Office 365을 사용 하 고 MX (메일 교환) 레코드는 Microsoft를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="731af-181">**Microsoft Exchange Online Protection only**: The tenant that you want to evaluate uses Office 365 for email security and the Mail Exchange (MX) record points to Microsoft.</span></span>

### <a name="email-security-gateway"></a><span data-ttu-id="731af-182">전자 메일 보안 게이트웨이</span><span class="sxs-lookup"><span data-stu-id="731af-182">Email security gateway</span></span>

<span data-ttu-id="731af-183">타사 전자 메일 보안 게이트웨이 (ESG)를 사용 하는 경우 공급자의 이름을 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="731af-183">If you’re using a third-party email security gateway (ESG), you’ll need to know the provider’s name.</span></span> <span data-ttu-id="731af-184">ESG 온-프레미스 또는 지원 되지 않는 공급 업체를 사용 하는 경우에는 장치에 대 한 공용 IP 주소를 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="731af-184">If you’re using an ESG on-premises or non-supported vendors, you’ll need to know the public IP address(es) for the devices.</span></span>

<span data-ttu-id="731af-185">지원 되는 타사 파트너는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="731af-185">Supported third-party partners include:</span></span>

- <span data-ttu-id="731af-186">Barracuda</span><span class="sxs-lookup"><span data-stu-id="731af-186">Barracuda</span></span>
- <span data-ttu-id="731af-187">Ironpor</span><span class="sxs-lookup"><span data-stu-id="731af-187">IronPort</span></span>
- <span data-ttu-id="731af-188">Mimecast</span><span class="sxs-lookup"><span data-stu-id="731af-188">Mimecast</span></span>
- <span data-ttu-id="731af-189">Proofpoint</span><span class="sxs-lookup"><span data-stu-id="731af-189">Proofpoint</span></span>
- <span data-ttu-id="731af-190">Sophos</span><span class="sxs-lookup"><span data-stu-id="731af-190">Sophos</span></span>
- <span data-ttu-id="731af-191">Symantec</span><span class="sxs-lookup"><span data-stu-id="731af-191">Symantec</span></span>
- <span data-ttu-id="731af-192">경향 마이크로</span><span class="sxs-lookup"><span data-stu-id="731af-192">Trend Micro</span></span>

### <a name="scoping"></a><span data-ttu-id="731af-193">범위</span><span class="sxs-lookup"><span data-stu-id="731af-193">Scoping</span></span>

<span data-ttu-id="731af-194">인바운드 커넥터에 대 한 평가 범위를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="731af-194">You will be able to scope the evaluation to an inbound connector.</span></span> <span data-ttu-id="731af-195">커넥터를 구성 하지 않은 경우에는 평가 범위를 사용 하 여 관리자가 테 넌 트의 모든 사용자 로부터 데이터를 수집 하 여 Defender for Office 365을 평가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="731af-195">If there's no connector configured, then the evaluation scope will allow admins to gather data from any user in your tenant to evaluate Defender for Office 365.</span></span>

## <a name="get-started-with-the-evaluation"></a><span data-ttu-id="731af-196">평가 시작</span><span class="sxs-lookup"><span data-stu-id="731af-196">Get started with the evaluation</span></span>

<span data-ttu-id="731af-197"> https://protection.office.com/homepage)다음 3 개의 액세스 포인트에서 office 365 Security & 준수 센터의 office 365 평가용 설정 카드를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="731af-197">Find the Microsoft Defender for Office 365 evaluation set-up card in the Office 365 Security & Compliance center (https://protection.office.com/homepage) from three access points:</span></span>

- <span data-ttu-id="731af-198">위협 관리 > 대시보드</span><span class="sxs-lookup"><span data-stu-id="731af-198">Threat management > Dashboard</span></span>
- <span data-ttu-id="731af-199">위협 관리 > 정책</span><span class="sxs-lookup"><span data-stu-id="731af-199">Threat management > Policy</span></span>
- <span data-ttu-id="731af-200">보고서 > 대시보드</span><span class="sxs-lookup"><span data-stu-id="731af-200">Reports > Dashboard</span></span>

## <a name="setting-up-the-evaluation"></a><span data-ttu-id="731af-201">평가 설정</span><span class="sxs-lookup"><span data-stu-id="731af-201">Setting up the evaluation</span></span>

<span data-ttu-id="731af-202">평가를 위해 설정 흐름을 시작 하면 두 개의 라우팅 옵션이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="731af-202">Once you start the set-up flow for your evaluation, you'll be given two routing options.</span></span> <span data-ttu-id="731af-203">조직의 메일 라우팅 설정 및 평가 요구 사항에 따라 타사 및/또는 Microsoft Exchange Online만 사용 하 고 있는지 여부를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="731af-203">Depending on your organization’s mail routing setup and evaluation needs, you can select whether you are using a third-party and/or on-premises service provider or only Microsoft Exchange Online.</span></span>

- <span data-ttu-id="731af-204">타사 파트너 및/또는 온-프레미스 서비스 공급자를 사용 하는 경우에는 드롭다운 메뉴에서 공급 업체의 이름을 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="731af-204">If you are using a third-party partner and/or on-premises service provider, you'll need to select the name of the vendor from the drop-down menu.</span></span> <span data-ttu-id="731af-205">다른 커넥터 관련 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="731af-205">Provide the other connector-related details.</span></span>

- <span data-ttu-id="731af-206">MX 레코드가 Microsoft를 가리키고 Exchange Online 사서함이 있는 경우 Microsoft Exchange Online을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="731af-206">Select Microsoft Exchange Online if the MX record points to Microsoft and you have an Exchange Online mailbox.</span></span>

<span data-ttu-id="731af-207">설정을 검토 하 고 필요한 경우 편집 합니다.</span><span class="sxs-lookup"><span data-stu-id="731af-207">Review your settings and edit them if necessary.</span></span> <span data-ttu-id="731af-208">그런 다음 **평가 만들기** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="731af-208">Then, select **Create evaluation**.</span></span> <span data-ttu-id="731af-209">설정이 완료 되었음을 나타내는 확인 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="731af-209">You should get a confirmation message to indicate that your set-up is complete.</span></span>

<span data-ttu-id="731af-210">Microsoft Defender for Office 365 평가 보고서는 하루에 한 번 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="731af-210">Your Microsoft Defender for Office 365 evaluation report is generated once per day.</span></span> <span data-ttu-id="731af-211">데이터가 채워 차지 하는 데 최대 24 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="731af-211">It may take up to 24 hours for the data to populate.</span></span>

### <a name="exchange-rules-optional"></a><span data-ttu-id="731af-212">Exchange 규칙 (선택 사항)</span><span class="sxs-lookup"><span data-stu-id="731af-212">Exchange rules (optional)</span></span>

<span data-ttu-id="731af-213">기존 게이트웨이가 있는 경우에는 커넥터에 대 한 향상 된 필터링을 활성화 하 고 들어오는 보낸 사람 IP 주소를 변경 하기 때문에 필터링을 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="731af-213">If you have an existing gateway, you might want to bypass filtering because it will activate enhanced filtering for connectors and alter the incoming sender IP address.</span></span> <span data-ttu-id="731af-214">무시 하려면 Exchange 관리 센터로 이동 하 여 SCL-1 정책 (아직 없는 경우)을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="731af-214">To bypass, navigate to the Exchange admin center and create a policy of SCL -1 (if you don’t already have one).</span></span> <span data-ttu-id="731af-215">규칙 구성 요소 및 해당 작동 방식에 대 한 자세한 내용은 Exchange Online의 메일 흐름 규칙 (전송 규칙)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="731af-215">For details on the rule components and how they work, see Mail flow rules (transport rules) in Exchange Online.</span></span>

## <a name="evaluate-capabilities"></a><span data-ttu-id="731af-216">기능 평가</span><span class="sxs-lookup"><span data-stu-id="731af-216">Evaluate capabilities</span></span>

<span data-ttu-id="731af-217">평가 보고서가 생성 된 후 조직의 전자 메일 및 공동 작업 영역에서 식별 된 advanced threat links, advanced threat attachments 및 잠재 impersonations의 수를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="731af-217">After the evaluation report has been generated, see how many advanced threat links, advanced threat attachments, and potential impersonations were identified in the emails and collaboration workspaces in your organization.</span></span>  

<span data-ttu-id="731af-218">평가판이 만료 되 면 계속 해 서 90 일 동안 보고서에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="731af-218">Once the trial has expired, you can continue to access the report for 90 days.</span></span> <span data-ttu-id="731af-219">그러나 더 이상 정보를 수집 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="731af-219">However, it won’t collect any more information.</span></span> <span data-ttu-id="731af-220">평가판이 만료 된 후에 Microsoft Defender for Office 365을 계속 사용 하려면 [Microsoft defender For office 365 (요금제 2)에 대해 유료 구독을 구입](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="731af-220">If you want to continue using Microsoft Defender for Office 365 after your trial has expired, make sure you [buy a paid subscription for Microsoft Defender for Office 365 (Plan 2)](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA).</span></span>

<span data-ttu-id="731af-221">**설정** 으로 이동 하 여 라우팅을 업데이트 하거나 언제 든 지 평가를 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="731af-221">You can go to **Settings** to update your routing or turn off your evaluation at any time.</span></span> <span data-ttu-id="731af-222">그러나 종료 후에도 평가를 계속 하기로 결정 했을 때와 동일한 설정 프로세스를 다시 진행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="731af-222">However, you need to go through the same set-up process again should you decide to continue your evaluation after having turned it off.</span></span>

## <a name="provide-feedback"></a><span data-ttu-id="731af-223">피드백 제공</span><span class="sxs-lookup"><span data-stu-id="731af-223">Provide feedback</span></span>

<span data-ttu-id="731af-224">사용자 의견을 활용 하면 고급 공격 으로부터 환경을 보호 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="731af-224">Your feedback helps us get better at protecting your environment from advanced attacks.</span></span> <span data-ttu-id="731af-225">사용자 환경 및 제품 기능 및 평가 결과의 상대를 공유 합니다.</span><span class="sxs-lookup"><span data-stu-id="731af-225">Share your experience and impressions of product capabilities and evaluation results.</span></span>

<span data-ttu-id="731af-226">**의견 제공** 을 선택 하 여 생각 하는 사항을 알려주세요.</span><span class="sxs-lookup"><span data-stu-id="731af-226">Select **Give feedback** to let us know what you think.</span></span>
