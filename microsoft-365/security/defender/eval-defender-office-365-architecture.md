---
title: Microsoft Defender의 아키텍처 요구 사항 및 계획 Office 365, 구성, 구축 및 디자인 프레임워크를 검토합니다.
description: Microsoft Defender for Office 365 Microsoft 365 Defender 다이어그램은 평가판 랩 또는 파일럿 환경을 구축하기 전에 Microsoft 365 ID를 이해하는 데 도움이 됩니다.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: 07/01/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 15c84921dcfb4644241cf83ce4ffb6403180b9d4
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458276"
---
# <a name="review-microsoft-defender-for-office-365-architecture-requirements-and-key-concepts"></a><span data-ttu-id="0105a-103">Microsoft Defender에서 아키텍처 요구 Office 365 주요 개념 검토</span><span class="sxs-lookup"><span data-stu-id="0105a-103">Review Microsoft Defender for Office 365 architecture requirements and key concepts</span></span>


<span data-ttu-id="0105a-104">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="0105a-104">**Applies to:**</span></span>
- <span data-ttu-id="0105a-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0105a-105">Microsoft 365 Defender</span></span>

<span data-ttu-id="0105a-106">이 문서는 Microsoft Defender의 평가 환경을 설정하는 프로세스의 [3단계](eval-defender-office-365-overview.md) 중 1단계입니다Office 365.</span><span class="sxs-lookup"><span data-stu-id="0105a-106">This article is [Step 1 of 3](eval-defender-office-365-overview.md) in the process of setting up the evaluation environment for Microsoft Defender for Office 365.</span></span> <span data-ttu-id="0105a-107">이 프로세스에 대한 자세한 내용은 개요 문서를 [참조하세요.](eval-defender-office-365-overview.md)</span><span class="sxs-lookup"><span data-stu-id="0105a-107">For more information about this process, see the [overview article](eval-defender-office-365-overview.md).</span></span>

<span data-ttu-id="0105a-108">사용자에 대해 Defender를 Office 365 아키텍처를 이해하고 요구 사항을 충족할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0105a-108">Before enabling Defender for Office 365, be sure you understand the architecture and can meet the requirements.</span></span> <span data-ttu-id="0105a-109">이 문서에서는 사용자 환경이 충족해야 하는 아키텍처, 주요 개념 및 Exchange Online 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0105a-109">This article describes the architecture, key concepts, and the prerequisites that your Exchange Online environment must meet.</span></span>

## <a name="understand-the-architecture"></a><span data-ttu-id="0105a-110">아키텍처 이해</span><span class="sxs-lookup"><span data-stu-id="0105a-110">Understand the architecture</span></span>

<span data-ttu-id="0105a-111">다음 다이어그램은 타사 SMTP 게이트웨이 또는 Office 통합을 포함할 수 있는 Microsoft Defender for Office 아키텍처를 보여 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0105a-111">The following diagram illustrates baseline architecture for Microsoft Defender for Office which can include a third-party SMTP gateway or on-premises integration.</span></span> <span data-ttu-id="0105a-112">하이브리드 동시 사용 시나리오(즉, 프로덕션 사서함은 모두 사내 사서함과 온라인 사서함)에는 더 복잡한 구성이 필요하며 이 문서 또는 평가 지침에서는 다루지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0105a-112">Hybrid coexistence scenarios (i.e. production mailboxes are both on-premise and online) require more complex configurations and are not covered in this article or evaluation guidance.</span></span>

![Microsoft Defender for Office 365](../../media/defender/m365-defender-office-architecture.png)

<span data-ttu-id="0105a-114">다음 표에서는 이 그림에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0105a-114">The following table describes this illustration.</span></span>

|<span data-ttu-id="0105a-115">Call-out</span><span class="sxs-lookup"><span data-stu-id="0105a-115">Call-out</span></span>  |<span data-ttu-id="0105a-116">설명</span><span class="sxs-lookup"><span data-stu-id="0105a-116">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="0105a-117">1</span><span class="sxs-lookup"><span data-stu-id="0105a-117">1</span></span>     | <span data-ttu-id="0105a-118">외부 보낸 사람에 대한 호스트 서버는 일반적으로 메시지를 릴레이할 대상 서버를 제공하는 MX 레코드에 대한 공용 DNS 쿼리를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="0105a-118">The host server for the external sender typically performs a public DNS lookup for an MX record which provides the target server to relay the message.</span></span>  <span data-ttu-id="0105a-119">이 참조는 EXO(Exchange Online)나 EXO에 대해 릴레이하도록 구성된 SMTP 게이트웨이일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0105a-119">This referral can either be Exchange Online (EXO) directly or an SMTP gateway that has been configured to relay against EXO.</span></span>  |
|<span data-ttu-id="0105a-120">2 </span><span class="sxs-lookup"><span data-stu-id="0105a-120">2</span></span>     | <span data-ttu-id="0105a-121">Exchange Online Protection 연결의 유효성을 검사하고 메시지 헤더 및 콘텐츠를 검사하여 필요한 추가 정책, 태그 지정 또는 처리를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0105a-121">Exchange Online Protection negotiates and validates the inbound connection and inspects the message headers and content to determine what additional policies, tagging, or processing is required.</span></span>  |
|<span data-ttu-id="0105a-122">3 </span><span class="sxs-lookup"><span data-stu-id="0105a-122">3</span></span>     | <span data-ttu-id="0105a-123">Exchange Online Microsoft Defender for Office 365 통합하여 보다 고급 위협 방지, 완화 및 수정을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0105a-123">Exchange Online integrates with Microsoft Defender for Office 365 to offer more advanced threat protection, mitigation, and remediation.</span></span> |
|<span data-ttu-id="0105a-124">4 </span><span class="sxs-lookup"><span data-stu-id="0105a-124">4</span></span>     | <span data-ttu-id="0105a-125">악의적, 차단 또는 격리되지 않은 메시지는 처리된 후 정크 메일, 사서함 규칙 또는 기타 설정과 관련된 사용자 기본 설정을 평가하고 트리거하는 EXO의 받는 사람에게 배달됩니다.</span><span class="sxs-lookup"><span data-stu-id="0105a-125">A message that is not malicious, blocked, or quarantined is processed and delivered to the recipient in EXO where user preferences related to junk mail, mailbox rules, or other settings are evaluated and triggered.</span></span> |
|<span data-ttu-id="0105a-126">5 </span><span class="sxs-lookup"><span data-stu-id="0105a-126">5</span></span>     | <span data-ttu-id="0105a-127">Azure AD 디렉토리를 사용하여 메일 사용이 가능한 개체 및 계정을 동기화하고 커넥트 Active Directory와의 통합을 Azure Active Directory 최종적으로 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="0105a-127">Integration with on-premises Active Directory can be enabled using Azure AD Connect to synchronize and provision mail-enabled objects and accounts to Azure Active Directory and ultimately Exchange Online.</span></span> |
|<span data-ttu-id="0105a-128">6 </span><span class="sxs-lookup"><span data-stu-id="0105a-128">6</span></span>     | <span data-ttu-id="0105a-129">사내 환경을 통합할 때 메일 관련 특성, 설정 및 구성의 지원되는 관리 및 관리에 Exchange 서버를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0105a-129">When integrating an on-premises environment, it is strongly encouraged to use an Exchange server for supported management and administration of mail related attributes, settings, and configurations</span></span> |
|<span data-ttu-id="0105a-130">7 </span><span class="sxs-lookup"><span data-stu-id="0105a-130">7</span></span>     | <span data-ttu-id="0105a-131">Microsoft Defender for Office 365 XDR(확장된 Microsoft 365 Defender 및 응답)에 대한 신호를 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="0105a-131">Microsoft Defender for Office 365 shares signals to Microsoft 365 Defender for extended detection and response (XDR).</span></span>|

<span data-ttu-id="0105a-132">사내 통합은 일반적이지만 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="0105a-132">On-premises integration is common but optional.</span></span> <span data-ttu-id="0105a-133">환경이 클라우드 전용인 경우 이 지침도 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0105a-133">If your environment is cloud-only this guidance will also work for you.</span></span>

## <a name="understand-key-concepts"></a><span data-ttu-id="0105a-134">주요 개념 이해</span><span class="sxs-lookup"><span data-stu-id="0105a-134">Understand key concepts</span></span>

<span data-ttu-id="0105a-135">다음 표에서는 MDO를 평가, 구성 및 배포할 때 이해해야 하는 주요 개념을 확인했습니다.</span><span class="sxs-lookup"><span data-stu-id="0105a-135">The following table identified key concepts that are important to understand when evaluating, configuring, and deploying MDO.</span></span>


|<span data-ttu-id="0105a-136">개념</span><span class="sxs-lookup"><span data-stu-id="0105a-136">Concept</span></span>  |<span data-ttu-id="0105a-137">설명</span><span class="sxs-lookup"><span data-stu-id="0105a-137">Description</span></span> |<span data-ttu-id="0105a-138">추가 정보</span><span class="sxs-lookup"><span data-stu-id="0105a-138">More information</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="0105a-139">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="0105a-139">Exchange Online Protection</span></span>      |    <span data-ttu-id="0105a-140">Exchange Online Protection(EOP)는 스팸 및 맬웨어 전자 메일로부터 조직을 보호하는 데 도움이 되는 클라우드 기반 필터링 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="0105a-140">Exchange Online Protection (EOP) is the cloud-based filtering service that helps protect your organization against spam and malware emails.</span></span> <span data-ttu-id="0105a-141">EOP는 EOP가 포함된 모든 Microsoft 365 라이선스에 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="0105a-141">EOP is included in all Microsoft 365 licenses which include Exchange Online.</span></span>     |   [<span data-ttu-id="0105a-142">Exchange Online Protection 개요</span><span class="sxs-lookup"><span data-stu-id="0105a-142">Exchange Online Protection overview</span></span>](../office-365-security/exchange-online-protection-overview.md)      |
|<span data-ttu-id="0105a-143">맬웨어 방지 보호 기능</span><span class="sxs-lookup"><span data-stu-id="0105a-143">Anti-malware protection</span></span>     |    <span data-ttu-id="0105a-144">EXO에 사서함이 있는 조직은 맬웨어로부터 자동으로 보호됩니다.</span><span class="sxs-lookup"><span data-stu-id="0105a-144">Organizations with mailboxes in EXO are automatically protected against malware.</span></span>     |  [<span data-ttu-id="0105a-145">EOP의 맬웨어 방지 보호 기능</span><span class="sxs-lookup"><span data-stu-id="0105a-145">Anti-malware protection in EOP</span></span>](../office-365-security/anti-malware-protection.md)       |
|<span data-ttu-id="0105a-146">스팸 방지 보호 기능</span><span class="sxs-lookup"><span data-stu-id="0105a-146">Anti-spam protection</span></span>     |   <span data-ttu-id="0105a-147">EXO에 사서함이 있는 조직은 정크 메일 및 스팸 정책으로부터 자동으로 보호됩니다.</span><span class="sxs-lookup"><span data-stu-id="0105a-147">Organizations with mailboxes in EXO are automatically protected against junk mail and spam policies.</span></span>      |  [<span data-ttu-id="0105a-148">EOP의 스팸 방지 보호 기능</span><span class="sxs-lookup"><span data-stu-id="0105a-148">Anti-spam protection in EOP</span></span>](../office-365-security/anti-spam-protection.md)       |
|<span data-ttu-id="0105a-149">피싱 방지 보호 기능</span><span class="sxs-lookup"><span data-stu-id="0105a-149">Anti-phishing protection</span></span> |  <span data-ttu-id="0105a-150">MDO는 스피어 피싱, 래싱, 랜섬웨어 및 기타 악의적인 활동과 관련된 고급 피싱 방지 보호 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0105a-150">MDO offers more advanced anti-phishing  protection related to spear phishing, whaling, ransomware, and other malicious activities.</span></span>   | [<span data-ttu-id="0105a-151">Office 365용 Microsoft Defender의 추가 피싱 방지 보호 기능</span><span class="sxs-lookup"><span data-stu-id="0105a-151">Additional anti-phishing protection in Microsoft Defender for Office 365</span></span>](../office-365-security/anti-phishing-protection.md)   |
|<span data-ttu-id="0105a-152">스푸핑 방지 보호 기능</span><span class="sxs-lookup"><span data-stu-id="0105a-152">Anti-spoofing protection</span></span>     |   <span data-ttu-id="0105a-153">EOP에는 스푸핑된(위조된) 보낸 사람으로부터 조직을 보호하는 데 도움이 되는 기능이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0105a-153">EOP includes features to help protect your organization from spoofed (forged) senders.</span></span>      |   [<span data-ttu-id="0105a-154">EOP의 스푸핑 방지 보호 기능</span><span class="sxs-lookup"><span data-stu-id="0105a-154">Anti-spoofing protection in EOP</span></span>](../office-365-security/anti-spoofing-protection.md)      |
|<span data-ttu-id="0105a-155">안전한 첨부 파일</span><span class="sxs-lookup"><span data-stu-id="0105a-155">Safe attachments</span></span>     |   <span data-ttu-id="0105a-156">금고 첨부 파일은 배달되기 전에 가상 환경을 사용하여 전자 메일 메시지의 첨부 파일을 확인하고 "확인"하여 추가 보호 계층을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0105a-156">Safe Attachments provides an additional layer of protection by using a virtual environment to check and "detonate" attachments in email messages before they are delivered.</span></span>      |   [<span data-ttu-id="0105a-157">금고 Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="0105a-157">Safe Attachments in Microsoft Defender for Office 365</span></span>](../office-365-security/safe-attachments.md)      |
|<span data-ttu-id="0105a-158">금고, SharePoint, OneDrive 및 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0105a-158">Safe attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>     |    <span data-ttu-id="0105a-159">또한 금고, SharePoint, OneDrive 및 Microsoft Teams 첨부 파일은 클라우드 저장소 저장소에 업로드된 파일에 대한 추가 보호 계층을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0105a-159">In addition, Safe Attachments for SharePoint, OneDrive, and Microsoft Teams offers an additional layer of protection for files that have been uploaded to cloud storage repositories.</span></span>     |  [<span data-ttu-id="0105a-160">SharePoint, OneDrive 및 Microsoft Teams용 안전한 첨부 파일</span><span class="sxs-lookup"><span data-stu-id="0105a-160">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>](../office-365-security/mdo-for-spo-odb-and-teams.md)       |
|<span data-ttu-id="0105a-161">안전한 링크</span><span class="sxs-lookup"><span data-stu-id="0105a-161">Safe Links</span></span>     | <span data-ttu-id="0105a-162">금고 링크는 인바운드 전자 메일 메시지 내에서 URL 검색 및 다시 를 제공하는 기능으로, 링크가 배달되거나 클릭되기 전에 해당 링크에 대한 확인을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0105a-162">Safe Links is a feature that provides URL scanning and rewriting within inbound email messages and offers verification of those links before they are delivered or clicked.</span></span>        |   [<span data-ttu-id="0105a-163">금고 Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="0105a-163">Safe Links in Microsoft Defender for Office 365</span></span>](../office-365-security/safe-links.md)      |
|    |         |         |

<span data-ttu-id="0105a-164">Microsoft Defender for Office 기능에 대한 자세한 내용은 microsoft [Defender for Office 365 참조하세요.](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)</span><span class="sxs-lookup"><span data-stu-id="0105a-164">For more detailed information about the capabilities included with Microsoft Defender for Office, see [Microsoft Defender for Office 365 service description](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

## <a name="review-architecture-requirements"></a><span data-ttu-id="0105a-165">아키텍처 요구 사항 검토</span><span class="sxs-lookup"><span data-stu-id="0105a-165">Review architecture requirements</span></span>
<span data-ttu-id="0105a-166">성공적인 MDO 평가 또는 프로덕션 파일럿에서는 다음과 같은 전제가 있는 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="0105a-166">A successful MDO evaluation or production pilot assumes the following pre-requisites:</span></span>
- <span data-ttu-id="0105a-167">모든 받는 사람 사서함이 현재 사서함에 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="0105a-167">All your recipient mailboxes are currently in Exchange Online.</span></span>
- <span data-ttu-id="0105a-168">공용 MX 레코드는 EOP 또는 타사 SMTP 게이트웨이로 직접 확인하여 인바운드 외부 전자 메일을 EOP에 직접 릴레이합니다.</span><span class="sxs-lookup"><span data-stu-id="0105a-168">Your public MX record resolves directly to EOP or a third-party SMTP gateway that then relays inbound external email directly to EOP.</span></span>
- <span data-ttu-id="0105a-169">기본 전자 메일 도메인은  기본 전자 메일 도메인에서 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="0105a-169">Your primary email domain is configured as *authoritative* in Exchange Online.</span></span>
- <span data-ttu-id="0105a-170">DBEB(디렉터리 기반 *Edge* 차단)를 적절하게 배포하고 구성했습니다.</span><span class="sxs-lookup"><span data-stu-id="0105a-170">You successfully deployed and configured *Directory Based Edge Blocking* (DBEB) as appropriate.</span></span> <span data-ttu-id="0105a-171">자세한 내용은 [디렉터리 기반 에지 차단을 사용하여 잘못된 받는 사람에게 전송된 메시지 거부](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0105a-171">For more information, see [Use Directory Based Edge Blocking to reject messages sent to invalid recipients](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0105a-172">이러한 요구 사항이 적용되지 않는 경우 또는 여전히 하이브리드 동시 사용 시나리오에 있는 경우 Office 365 평가용 Microsoft Defender 평가에는 이 지침에서 완전히 다루지 않는 더 복잡하거나 고급 구성이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0105a-172">If these requirements are not applicable or you are still in a hybrid coexistence scenario, then a Microsoft Defender for Office 365 evaluation can require more complex or advanced configurations which are not fully covered in this guidance.</span></span>

## <a name="siem-integration"></a><span data-ttu-id="0105a-173">SIEM 통합</span><span class="sxs-lookup"><span data-stu-id="0105a-173">SIEM integration</span></span>

<span data-ttu-id="0105a-174">Microsoft Defender for Office 365 Azure Sentinel과 통합하여 조직 전체의 보안 이벤트를 보다 포괄적으로 분석하고 효과적이고 즉각적인 응답을 위한 플레이북을 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0105a-174">You can integrate Microsoft Defender for Office 365 with Azure Sentinel to more comprehensively analyze security events across your organization and build playbooks for effective and immediate response.</span></span> <span data-ttu-id="0105a-175">자세한 내용은 커넥트 [Microsoft Defender에서](/azure/sentinel/connect-office-365-advanced-threat-protection)경고를 Office 365.</span><span class="sxs-lookup"><span data-stu-id="0105a-175">For more information, see [Connect alerts from Microsoft Defender for Office 365](/azure/sentinel/connect-office-365-advanced-threat-protection).</span></span>

<span data-ttu-id="0105a-176">Microsoft Defender for Office 365 Activity Management API를 사용하여 다른 SIEM(보안 정보 및 이벤트 관리) 솔루션에 Office 365 [수 있습니다.](/office/office-365-management-api/office-365-management-activity-api-reference)</span><span class="sxs-lookup"><span data-stu-id="0105a-176">Microsoft Defender for Office 365 can also be integrated into other Security Information and Event Management (SIEM) solutions using the [Office 365 Activity Management API](/office/office-365-management-api/office-365-management-activity-api-reference).</span></span>

## <a name="next-steps"></a><span data-ttu-id="0105a-177">다음 단계</span><span class="sxs-lookup"><span data-stu-id="0105a-177">Next steps</span></span>

<span data-ttu-id="0105a-178">3단계 중 2단계: Microsoft [Defender](eval-defender-office-365-enable-eval.md) for Office 365</span><span class="sxs-lookup"><span data-stu-id="0105a-178">Step 2 of 3: [Enable the evaluation environment Microsoft Defender for Office 365](eval-defender-office-365-enable-eval.md)</span></span>

<span data-ttu-id="0105a-179">Microsoft [Defender](eval-defender-office-365-overview.md) for Office 365</span><span class="sxs-lookup"><span data-stu-id="0105a-179">Return to the overview for [Evaluate Microsoft Defender for Office 365](eval-defender-office-365-overview.md)</span></span>

<span data-ttu-id="0105a-180">평가 및 파일럿 테스트 [개요로 Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="0105a-180">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span> 

