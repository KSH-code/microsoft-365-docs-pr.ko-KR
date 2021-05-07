---
title: Microsoft 365에서 콘텐츠에 민감도 레이블을 자동 적용
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
description: 민감도 레이블을 만들 때 파일 또는 전자 메일에 레이블을 자동으로 적용하거나 사용자에게 권장 레이블을 선택하라는 메시지를 표시할 수 있습니다.
ms.openlocfilehash: 23320d962b52e1a443d459cb6b57d444fca91592
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939312"
---
# <a name="apply-a-sensitivity-label-to-content-automatically"></a><span data-ttu-id="c0557-103">콘텐츠에 민감도 레이블을 자동으로 적용</span><span class="sxs-lookup"><span data-stu-id="c0557-103">Apply a sensitivity label to content automatically</span></span>

><span data-ttu-id="c0557-104">*[보안 및 규정 준수에 대한 Microsoft 365 라이선싱 지침](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span><span class="sxs-lookup"><span data-stu-id="c0557-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

> [!NOTE]
> <span data-ttu-id="c0557-105">현재 Azure Purview(미리 보기)에서 레이블 자동 적용에 대한 자세한 내용은 [Azure Purview에서 콘텐츠에 레이블 자동 적용](/azure/purview/create-sensitivity-label)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c0557-105">For information about automatically applying a sensitivity label in Azure Purview (preview), see [Automatically label your content in Azure Purview](/azure/purview/create-sensitivity-label).</span></span>

<span data-ttu-id="c0557-106">민감도 레이블을 만들 때 사용자가 지정한 조건과 일치하는 경우 해당 레이블을 파일 및 전자 메일에 자동으로 붙일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-106">When you create a sensitivity label, you can automatically assign that label to files and emails when it matches conditions that you specify.</span></span>

<span data-ttu-id="c0557-107">콘텐츠에 자동으로 민감도 레이블을 적용하는 기능은 다음과 같은 이유로 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-107">This ability to apply sensitivity labels to content automatically is important because:</span></span>

- <span data-ttu-id="c0557-108">사용자에게 각 분류를 언제 사용할지 교육할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-108">You don't need to train your users when to use each of your classifications.</span></span>

- <span data-ttu-id="c0557-109">모든 콘텐츠를 올바르게 분류하기 위해 사용자에게 의존할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-109">You don't need to rely on users to classify all content correctly.</span></span>

- <span data-ttu-id="c0557-110">사용자가 더 이상 정책을 알 필요가 없으며, 대신 업무에 집중할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-110">Users no longer need to know about your policies—they can instead focus on their work.</span></span>

<span data-ttu-id="c0557-111">콘텐츠에 수동으로 레이블을 지정한 경우 해당 레이블은 자동 레이블로 대체되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-111">When content has been manually labeled, that label will never be replaced by automatic labeling.</span></span> <span data-ttu-id="c0557-112">그러나 자동으로 적용된 [우선 순위 낮은 레이블](sensitivity-labels.md#label-priority-order-matters)이 자동 레이블 적용 기능에 의해 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-112">However, automatic labeling can replace a [lower priority label](sensitivity-labels.md#label-priority-order-matters) that was automatically applied.</span></span>

<span data-ttu-id="c0557-113">Microsoft 365에서 콘텐츠에 민감도 레이블을 자동으로 적용하는 방법에는 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-113">There are two different methods for automatically applying a sensitivity label to content in Microsoft 365:</span></span>

- <span data-ttu-id="c0557-114">**사용자가 문서를 편집하거나 전자 메일을 작성(답장 또는 전달) 시 클라이언트 쪽 레이블 지정**: 파일 및 전자 메일(Word, Excel, PowerPoint 및 Outlook 포함)에 자동 레이블을 지정하기 위해 구성된 레이블을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-114">**Client-side labeling when users edit documents or compose (also reply or forward) emails**: Use a label that's configured for auto-labeling for files and emails (includes Word, Excel, PowerPoint, and Outlook).</span></span> 
    
    <span data-ttu-id="c0557-115">이 방법은 자동 레이블 적용 뿐만 아니라 사용자에게 레이블 권장을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-115">This method supports recommending a label to users, as well as automatically applying a label.</span></span> <span data-ttu-id="c0557-116">그러나 두 경우 모두 사용자가 레이블을 수락할지 또는 거부할지 결정하여 내용에 올바른 레이블을 지정할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-116">But in both cases, the user decides whether to accept or reject the label, to help ensure the correct labeling of content.</span></span> <span data-ttu-id="c0557-117">이 클라이언트 쪽 레이블에는 문서가 저장되기 전에 레이블을 지정할 수 있으므로 문서에 대한 지연 시간이 최소화됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-117">This client-side labeling has minimal delay for documents because the label can be applied even before the document is saved.</span></span> <span data-ttu-id="c0557-118">그러나 일부 클라이언트 앱에서는 자동 레이블 지정을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-118">However, not all client apps support auto-labeling.</span></span> <span data-ttu-id="c0557-119">이 기능은 Azure Information Protection 통합 레이블 지정 클라이언트 및 [일부 버전의 Office](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-119">This capability is supported by the Azure Information Protection unified labeling client, and [some versions of Office](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps).</span></span> 
    
    <span data-ttu-id="c0557-120">구성 방법에 대한 자세한 내용은 이 페이지에서 [Office 앱에 대한 자동 레이블 지정 구성 방법](#how-to-configure-auto-labeling-for-office-apps)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c0557-120">For configuration instructions, see [How to configure auto-labeling for Office apps](#how-to-configure-auto-labeling-for-office-apps) on this page.</span></span>

- <span data-ttu-id="c0557-121">**콘텐츠가 이미 저장되었거나(SharePoint 또는 OneDrive) 전자 메일로 전송(Exchange Online에서 처리됨)된 경우 서비스쪽 레이블 지정**: 자동 레이블 지정 정책을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-121">**Service-side labeling when content is already saved (in SharePoint or OneDrive) or emailed (processed by Exchange Online)**: Use an auto-labeling policy.</span></span> 
    
    <span data-ttu-id="c0557-p103">이 메서드는 미사용 데이터(SharePoint 및 OneDrive의 문서) 및 전송 중인 데이터(Exchange에서 보내거나 받은 전자 메일)에 대한 자동 레이블 지정이라고 불리기도 합니다. Exchange의 경우에는 미사용 전자 메일(사서함)을 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-p103">You might also hear this method referred to as auto-labeling for data at rest (documents in SharePoint and OneDrive) and data in transit (email that is sent or received by Exchange). For Exchange, it doesn't include emails at rest (mailboxes).</span></span>
    
    <span data-ttu-id="c0557-124">이 레이블 지정은 응용 프로그램이 아닌 서비스에서 적용되므로 사용자에게 어떤 버전의 앱이 있는지 걱정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-124">Because this labeling is applied by services rather than by applications, you don't need to worry about what apps users have and what version.</span></span> <span data-ttu-id="c0557-125">따라서 이 기능은 조직 전체에서 즉시 사용할 수 있으며 대규모로 레이블을 지정하는 데 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-125">As a result, this capability is immediately available throughout your organization and suitable for labeling at scale.</span></span> <span data-ttu-id="c0557-126">자동 레이블 지정 정책은 사용자가 레이블 지정 프로세스와 상호 작용하지 않기 때문에 권장되는 레이블 지정을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-126">Auto-labeling policies don't support recommended labeling because the user doesn't interact with the labeling process.</span></span> <span data-ttu-id="c0557-127">대신 관리자가 시뮬레이션 모드에서 정책을 실행하여 실제로 레이블을 적용하기 전에 콘텐츠의 올바른 레이블을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-127">Instead, the administrator runs the policies in simulation mode to help ensure the correct labeling of content before actually applying the label.</span></span>
    
    <span data-ttu-id="c0557-128">구성 지침은 이 페이지에서 [SharePoint, OneDrive 및 Exchange에 대한 자동 레이블 지정 정책을 구성하는 방법](#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c0557-128">For configuration instructions, see [How to configure auto-labeling policies for SharePoint, OneDrive, and Exchange](#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange) on this page.</span></span>
    
    <span data-ttu-id="c0557-129">SharePoint 및 OneDrive에 대한 자동 레이블 지정에만 해당:</span><span class="sxs-lookup"><span data-stu-id="c0557-129">Specific to auto-labeling for SharePoint and OneDrive:</span></span>
    - <span data-ttu-id="c0557-p105">Word, PowerPoint, Excel Office 파일은 지원됩니다. Open XML 형식(예: .docx, .xlsx)은 지원되지만, Microsoft Office 97~2003 형식(예: .doc, .xls)은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-p105">Office files for Word, PowerPoint, and Excel are supported. Open XML format is supported (such as .docx and .xlsx) but not Microsoft Office 97-2003 format (such as .doc and .xls).</span></span>
        - <span data-ttu-id="c0557-132">이러한 파일은 자동 레이블 지정 정책이 작성되기 전이나 만들어진 후에 유휴 상태로 자동 레이블링될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-132">These files can be auto-labeled at rest before or after the auto-labeling policies are created.</span></span> <span data-ttu-id="c0557-133">파일이 열려 있는 세션(파일이 열려 있는 경우)의 일부인 경우 자동 레이블을 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-133">Note that files cannot be auto-labeled if they are part of an open session (the file is open).</span></span>
    - <span data-ttu-id="c0557-134">테넌트에서 하루 최대 25,000개의 자동 레이블 지정 파일 수.</span><span class="sxs-lookup"><span data-stu-id="c0557-134">Maximum of 25,000 automatically labeled files in your tenant per day.</span></span>
    - <span data-ttu-id="c0557-135">최대 10개의 사이트 (SharePoint 또는 OneDrive)를 대상으로 하는 테넌트당 최대 10개의 자동 레이블 정책.</span><span class="sxs-lookup"><span data-stu-id="c0557-135">Maximum of 10 auto-labeling policies per tenant, each targeting up to 10 sites (SharePoint or OneDrive).</span></span>
    - <span data-ttu-id="c0557-136">시뮬레이션 모드 및 레이블 적용 시 둘 다의 경우 자동 레이블링 정책의 결과로 수정됨, 수정자 및 날짜에 대한 기존 값은 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-136">Existing values for modified, modified by, and the date are not changed as a result of auto-labeling policies—for both simulation mode and when labels are applied.</span></span>
    - <span data-ttu-id="c0557-137">레이블이 암호화를 적용하는 경우 [권한 관리 발행자 및 권한 관리 소유자](/azure/information-protection/configure-usage-rights#rights-management-issuer-and-rights-management-owner)는 파일을 마지막으로 수정한 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-137">When the label applies encryption, the [Rights Management issuer and Rights Management owner](/azure/information-protection/configure-usage-rights#rights-management-issuer-and-rights-management-owner) is the account that last modified the file.</span></span>

    <span data-ttu-id="c0557-138">Exchange 자동 레이블 지정에만 해당:</span><span class="sxs-lookup"><span data-stu-id="c0557-138">Specific to auto-labeling for Exchange:</span></span>
    - <span data-ttu-id="c0557-p107">Office 앱을 사용하는 수동 레이블 지정 또는 자동 레이블 기능과는 달리, Office 첨부 파일(Word, Excel, PowerPoint 파일)과 PDF 첨부 파일에도 자동 레이블 지정 정책에서 지정한 조건에 대한 검사가 실시됩니다. 일치하는 경우 전자 메일에는 레이블이 지정되지만 첨부 파일에는 지정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-p107">Unlike manual labeling or auto-labeling with Office apps, Office attachments (Word, Excel, and PowerPoint files) and PDF attachments are also scanned for the conditions you specify in your auto-labeling policy. When there is a match, the email is labeled but not the attachment.</span></span>
        - <span data-ttu-id="c0557-141">Office 파일의 경우, Open XML 형식(예: .docx 및 .xlsx)은 지원되지만, Microsoft Office 97~2003 형식(예: .doc 및 .xls)은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-141">For these Office files, Open XML format is supported (such as .docx and .xlsx) but not Microsoft Office 97-2003 format (such as .doc and .xls).</span></span>
    - <span data-ttu-id="c0557-142">IRM 암호화를 적용하는 Exchange 메일 흐름 규칙 또는 DLP(데이터 손실 방지) 정책이 있는 경우: 이러한 규칙 또는 정책과 자동 레이블 지정 정책으로 콘텐츠를 식별하면 레이블이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-142">If you have Exchange mail flow rules or data loss prevention (DLP) policies that apply IRM encryption: When content is identified by these rules or policies and an auto-labeling policy, the label is applied.</span></span> <span data-ttu-id="c0557-143">해당 레이블이 암호화를 적용하면 Exchange 메일 흐름 규칙 또는 DLP 정책의 IRM 설정이 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-143">If that label applies encryption, the IRM settings from the Exchange mail flow rules or DLP policies are ignored.</span></span> <span data-ttu-id="c0557-144">그러나 해당 레이블에 암호화가 적용되지 않으면 레이블과 더불어 메일 흐름 규칙 또는 DLP 정책의 IRM 설정이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-144">However, if that label doesn't apply encryption, the IRM settings from the mail flow rules or DLP policies are applied in addition to the label.</span></span>
    - <span data-ttu-id="c0557-145">레이블이 없는 IRM 암호화를 포함하는 전자 메일은 자동 레이블 지정을 사용하여 일치하는 항목이 있는 경우 모든 암호화 설정이 있는 레이블로 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-145">Email that has IRM encryption with no label will be replaced by a label with any encryption settings when there is a match by using auto-labeling.</span></span>
    - <span data-ttu-id="c0557-146">자동 레이블 지정 조건과 일치하는 경우 수신 전자 메일에 레이블이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-146">Incoming email is labeled when there is a match with your auto-labeling conditions:</span></span>
        - <span data-ttu-id="c0557-147">[암호화](encryption-sensitivity-labels.md)를 위해 레이블을 구성하는 경우 해당 암호화는 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-147">If the label is configured for [encryption](encryption-sensitivity-labels.md), that encryption isn't applied.</span></span>
        - <span data-ttu-id="c0557-148">[동적 표시](sensitivity-labels-office-apps.md#dynamic-markings-with-variables)를 적용하기 위해 레이블을 구성하는 경우, 결과에 조직 외부 사용자의 이름이 표시될 수 있다는 사실을 명심하세요.</span><span class="sxs-lookup"><span data-stu-id="c0557-148">If the label is configured to apply [dynamic markings](sensitivity-labels-office-apps.md#dynamic-markings-with-variables), be aware that this can result in the names of people outside your organization.</span></span>
    - <span data-ttu-id="c0557-149">레이블이 암호화를 적용하는 경우 [권한 관리 발행자 및 권한 관리 소유자](/azure/information-protection/configure-usage-rights#rights-management-issuer-and-rights-management-owner)는 전자 메일을 보낸 사람입니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-149">When the label applies encryption, the [Rights Management issuer and Rights Management owner](/azure/information-protection/configure-usage-rights#rights-management-issuer-and-rights-management-owner) is the person who sends the email.</span></span>
    

## <a name="compare-auto-labeling-for-office-apps-with-auto-labeling-policies"></a><span data-ttu-id="c0557-150">자동 레이블 지정 정책과 Office 앱에 대한 자동 레이블 지정 비교</span><span class="sxs-lookup"><span data-stu-id="c0557-150">Compare auto-labeling for Office apps with auto-labeling policies</span></span>

<span data-ttu-id="c0557-151">다음 표를 사용하면 두 가지 보완적인 자동 레이블 지정 방법의 동작이 어떻게 차이나는지 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-151">Use the following table to help you identify the differences in behavior for the two complementary automatic labeling methods:</span></span>

|<span data-ttu-id="c0557-152">기능 또는 동작</span><span class="sxs-lookup"><span data-stu-id="c0557-152">Feature or behavior</span></span>|<span data-ttu-id="c0557-153">레이블 설정: 파일 및 전자 메일에 자동 레이블 지정</span><span class="sxs-lookup"><span data-stu-id="c0557-153">Label setting: Auto-labeling for files and emails</span></span>  |<span data-ttu-id="c0557-154">정책: 자동 레이블 지정</span><span class="sxs-lookup"><span data-stu-id="c0557-154">Policy: Auto-labeling</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c0557-155">앱 종속성</span><span class="sxs-lookup"><span data-stu-id="c0557-155">App dependency</span></span>|[<span data-ttu-id="c0557-156">예</span><span class="sxs-lookup"><span data-stu-id="c0557-156">Yes</span></span>](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps) |<span data-ttu-id="c0557-157">아니요\*</span><span class="sxs-lookup"><span data-stu-id="c0557-157">No \*</span></span> |
|<span data-ttu-id="c0557-158">위치별 제한</span><span class="sxs-lookup"><span data-stu-id="c0557-158">Restrict by location</span></span>|<span data-ttu-id="c0557-159">아니오</span><span class="sxs-lookup"><span data-stu-id="c0557-159">No</span></span> |<span data-ttu-id="c0557-160">예</span><span class="sxs-lookup"><span data-stu-id="c0557-160">Yes</span></span> |
|<span data-ttu-id="c0557-161">조건: 훈련 가능한 분류자</span><span class="sxs-lookup"><span data-stu-id="c0557-161">Conditions: Trainable classifiers</span></span>|<span data-ttu-id="c0557-162">예</span><span class="sxs-lookup"><span data-stu-id="c0557-162">Yes</span></span> |<span data-ttu-id="c0557-163">아니요</span><span class="sxs-lookup"><span data-stu-id="c0557-163">No</span></span> |
|<span data-ttu-id="c0557-164">조건: 전자 메일 공유 옵션 및 추가 옵션</span><span class="sxs-lookup"><span data-stu-id="c0557-164">Conditions: Sharing options and additional options for email</span></span>|<span data-ttu-id="c0557-165">아니요</span><span class="sxs-lookup"><span data-stu-id="c0557-165">No</span></span> |<span data-ttu-id="c0557-166">예</span><span class="sxs-lookup"><span data-stu-id="c0557-166">Yes</span></span> |
|<span data-ttu-id="c0557-167">권장 사항, 정책 도구 설명 및 사용자 재정의</span><span class="sxs-lookup"><span data-stu-id="c0557-167">Recommendations, policy tooltip, and user overrides</span></span>|<span data-ttu-id="c0557-168">예</span><span class="sxs-lookup"><span data-stu-id="c0557-168">Yes</span></span> |<span data-ttu-id="c0557-169">아니요</span><span class="sxs-lookup"><span data-stu-id="c0557-169">No</span></span> |
|<span data-ttu-id="c0557-170">시뮬레이션 모드</span><span class="sxs-lookup"><span data-stu-id="c0557-170">Simulation mode</span></span>|<span data-ttu-id="c0557-171">아니요</span><span class="sxs-lookup"><span data-stu-id="c0557-171">No</span></span> |<span data-ttu-id="c0557-172">예</span><span class="sxs-lookup"><span data-stu-id="c0557-172">Yes</span></span> |
|<span data-ttu-id="c0557-173">조건이 확인된 Exchange 첨부 파일</span><span class="sxs-lookup"><span data-stu-id="c0557-173">Exchange attachments checked for conditions</span></span>|<span data-ttu-id="c0557-174">아니요</span><span class="sxs-lookup"><span data-stu-id="c0557-174">No</span></span> | <span data-ttu-id="c0557-175">예</span><span class="sxs-lookup"><span data-stu-id="c0557-175">Yes</span></span>|
|<span data-ttu-id="c0557-176">시각적 표시 적용</span><span class="sxs-lookup"><span data-stu-id="c0557-176">Apply visual markings</span></span> |<span data-ttu-id="c0557-177">예</span><span class="sxs-lookup"><span data-stu-id="c0557-177">Yes</span></span> |<span data-ttu-id="c0557-178">예(전자 메일만 해당)</span><span class="sxs-lookup"><span data-stu-id="c0557-178">Yes (email only)</span></span> |
|<span data-ttu-id="c0557-179">레이블 없이 적용된 IRM 암호화 재정의</span><span class="sxs-lookup"><span data-stu-id="c0557-179">Override IRM encryption applied without a label</span></span>|<span data-ttu-id="c0557-180">예(사용자에게 내보내기의 최소 사용 권한이 있는 경우)</span><span class="sxs-lookup"><span data-stu-id="c0557-180">Yes if the user has the minimum usage right of Export</span></span> |<span data-ttu-id="c0557-181">예(전자 메일만 해당)</span><span class="sxs-lookup"><span data-stu-id="c0557-181">Yes (email only)</span></span> |
|<span data-ttu-id="c0557-182">받는 전자 메일에 레이블 지정</span><span class="sxs-lookup"><span data-stu-id="c0557-182">Label incoming email</span></span>|<span data-ttu-id="c0557-183">아니요</span><span class="sxs-lookup"><span data-stu-id="c0557-183">No</span></span> |<span data-ttu-id="c0557-184">예(암호화가 적용되지 않음)</span><span class="sxs-lookup"><span data-stu-id="c0557-184">Yes (encryption not applied)</span></span> |

<span data-ttu-id="c0557-185">\* 현재 모든 지역에서 자동 레이블을 사용할 수 있는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-185">\* Auto-labeling isn't currently available in all regions.</span></span> <span data-ttu-id="c0557-186">테넌트가 이 기능을 지원할 수 없는 경우 자동 레이블 지정 탭은 관리 레이블 센터에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-186">If your tenant can't support this functionality, the Auto-labeling tab isn't visible in the admin labeling center.</span></span>

## <a name="how-multiple-conditions-are-evaluated-when-they-apply-to-more-than-one-label"></a><span data-ttu-id="c0557-187">여러 조건에 두 개 이상의 레이블을 적용했을 때 평가 방식</span><span class="sxs-lookup"><span data-stu-id="c0557-187">How multiple conditions are evaluated when they apply to more than one label</span></span>

<span data-ttu-id="c0557-p110">레이블은 정책에서 지정한 위치에 따라 평가되도록 정렬됩니다. 먼저 배치된 레이블은 가장 낮은 위치에 있고(가장 민감하지 않음) 마지막에 위치한 레이블은 가장 높은 위치에 배치됩니다(가장 민감합니다). 우선 순위에 대한 자세한 내용은 [레이블 우선 순위 (순서 관련 문제)](sensitivity-labels.md#label-priority-order-matters)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c0557-p110">The labels are ordered for evaluation according to their position that you specify in the policy: The label positioned first has the lowest position (least sensitive) and the label positioned last has the highest position (most sensitive). For more information on priority, see [Label priority (order matters)](sensitivity-labels.md#label-priority-order-matters).</span></span>

## <a name="dont-configure-a-parent-label-to-be-applied-automatically-or-recommended"></a><span data-ttu-id="c0557-190">상위 레이블이 자동으로 적용되거나 권장되도록 구성하지 않음</span><span class="sxs-lookup"><span data-stu-id="c0557-190">Don't configure a parent label to be applied automatically or recommended</span></span>

<span data-ttu-id="c0557-191">상위 레이블(하위 레이블이 있는 레이블)은 콘텐츠에 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-191">Remember, you can't apply a parent label (a label with sublabels) to content.</span></span> <span data-ttu-id="c0557-192">Office 앱에서 상위 레이블을 자동으로 적용하거나 권장하도록 구성하지 않았는지 확인하고 자동 레이블 정책에 대한 상위 레이블을 선택하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="c0557-192">Make sure that you don't configure a parent label to be auto-applied or recommended in Office apps, and don't select a parent label for an auto-labeling policy.</span></span> <span data-ttu-id="c0557-193">이렇게 하면 상위 레이블이 콘텐츠에 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-193">If you do, the parent label won't be applied to content.</span></span>

<span data-ttu-id="c0557-194">하위 레이블과 함께 자동 레이블을 사용하려면 상위 레이블과 하위 레이블을 모두 게시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-194">To use automatic labeling with sublabels, make sure you publish both the parent label and the sublabel.</span></span>

<span data-ttu-id="c0557-195">상위 레이블 및 하위 레이블에 대한 자세한 내용은 [하위 레이블(레이블 그룹화)](sensitivity-labels.md#sublabels-grouping-labels)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c0557-195">For more information on parent labels and sublabels, see [Sublabels (grouping labels)](sensitivity-labels.md#sublabels-grouping-labels).</span></span>

## <a name="how-to-configure-auto-labeling-for-office-apps"></a><span data-ttu-id="c0557-196">Office 앱에 대한 자동 레이블 지정을 구성하는 방법</span><span class="sxs-lookup"><span data-stu-id="c0557-196">How to configure auto-labeling for Office apps</span></span>

<span data-ttu-id="c0557-197">Windows용 Office 앱의 자동 레이블 지정은 Azure Information Protection 통합 레이블 클라이언트에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-197">Automatic labeling in Office apps for Windows is supported by the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="c0557-198">Office 앱에서 기본 제공되는 레이블 지정은 [앱마다 사용 가능 단계가 다릅니다](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps).</span><span class="sxs-lookup"><span data-stu-id="c0557-198">For built-in labeling in Office apps, this capability is in [different stages of availability for different apps](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps).</span></span>

<span data-ttu-id="c0557-199">[민감도 레이블을 만들거나 편집](create-sensitivity-labels.md)하는 경우, Office 앱에 대한 자동 레이블 지정 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-199">The auto-labeling settings for Office apps are available when you [create or edit a sensitivity label](create-sensitivity-labels.md).</span></span> <span data-ttu-id="c0557-200">**파일 및 전자 메일** 이 레이블 범위에서 선택되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-200">Make sure **Files & emails** is selected for the label's scope:</span></span> 

![파일 및 전자 메일의 민감도 레이블 범위 옵션](../media/filesandemails-scope-options-sensitivity-label.png)

<span data-ttu-id="c0557-202">마법사를 거쳐 이동하면서 중요한 정보 유형 또는 교육 가능한 분류자 목록에서 사용자가 선택할 수 있는 **파일 및 전자 메일의 자동 레이블 지정** 페이지를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-202">As you move through the wizard, you see the **Auto-labeling for files and emails** page where you can choose from a list of sensitive info types or trainable classifiers:</span></span>

![Office 앱에서 자동 레이블 지정에 대한 레이블 조건](../media/sensitivity-labels-conditions.png)

<span data-ttu-id="c0557-p114">이 민감도 레이블이 자동으로 적용되면 사용자는 Office 앱에서 알림을 보게 됩니다. 다음은 그 예시입니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-p114">When this sensitivity label is automatically applied, the user sees a notification in their Office app. For example:</span></span>

![문서에 레이블이 자동 적용되었다는 알림](../media/sensitivity-labels-msg-doc-was-auto-labeled.PNG)

### <a name="configuring-sensitive-info-types-for-a-label"></a><span data-ttu-id="c0557-207">레이블에 대한 중요한 정보 유형 구성</span><span class="sxs-lookup"><span data-stu-id="c0557-207">Configuring sensitive info types for a label</span></span>

<span data-ttu-id="c0557-208">**중요한 정보 유형** 옵션을 선택하면 DLP(데이터 손실 방지) 정책을 만들 때 같은 중요한 정보 유형 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-208">When you select the **Sensitive info types** option, you see the same list of sensitive information types as when you create a data loss prevention (DLP) policy.</span></span> <span data-ttu-id="c0557-209">예를 들어 신용카드 번호, 주민등록번호 또는 여권 번호와 같은 고객의 개인 정보를 포함하는 모든 콘텐츠에 자동으로 기밀 유지 레이블을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-209">So you can, for example, automatically apply a Highly Confidential label to any content that contains customers' personal information, such as credit card numbers, social security numbers, or passport numbers:</span></span>

![Office 앱에서 자동 레이블 지정을 위한 중요한 정보 유형](../media/sensitivity-labels-sensitive-info-types.png)

<span data-ttu-id="c0557-p116">DLP 정책을 구성할 때와 마찬가지로 인스턴스 수와 일치 정확성을 변경하여 조건을 구체화할 수 있습니다. 다음은 그 예시입니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-p116">Similarly to when you configure DLP policies, you can then refine your condition by changing the instance count and match accuracy. For example:</span></span>

![일치 정확도 및 인스턴스 수 옵션](../media/sensitivity-labels-instance-count-match-accuracy.png)

<span data-ttu-id="c0557-214">이러한 구성 옵션에 대한 자세한 내용은 DLP 설명서 [일치하기 더욱 쉽게 혹은 어렵게 만드는 튜닝 규칙](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c0557-214">You can learn more about these configuration options from the DLP documentation: [Tuning rules to make them easier or harder to match](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span></span>

<span data-ttu-id="c0557-215">또한 DLP 정책 구성과 마찬가지로 조건이 모든 중요한 정보 유형을 탐지해야 하는지 또는 이러한 정보 유형 중 하나만 탐지해야 하는지 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-215">Also similarly to DLP policy configuration, you can choose whether a condition must detect all sensitive information types, or just one of them.</span></span> <span data-ttu-id="c0557-216">또한 조건을 더 유연하고 복잡하게 만들기 위해 [그룹을 추가하고 그룹 간에 논리 연산자를 사용](data-loss-prevention-policies.md#grouping-and-logical-operators)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-216">And to make your conditions more flexible or complex, you can add [groups and use logical operators between the groups](data-loss-prevention-policies.md#grouping-and-logical-operators).</span></span>

### <a name="configuring-trainable-classifiers-for-a-label"></a><span data-ttu-id="c0557-217">레이블에 교육 가능한 분류자 구성하기</span><span class="sxs-lookup"><span data-stu-id="c0557-217">Configuring trainable classifiers for a label</span></span>

<span data-ttu-id="c0557-218">이 옵션은 현재 미리 보기로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-218">This option is currently in preview.</span></span> <span data-ttu-id="c0557-219">이 옵션을 사용하는 경우 자동 레이블 지정과 [중요한 정보 유형 옵션](#configuring-sensitive-info-types-for-a-label)에 구성된 하나 이상의 다른 민감도 레이블을 테넌트에 게시했는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="c0557-219">If you use this option, make sure you have published in your tenant at least one other sensitivity label that's configured for auto-labeling and the [sensitive info types option](#configuring-sensitive-info-types-for-a-label).</span></span>

<span data-ttu-id="c0557-220">**교육 가능한 분류자** 옵션을 선택하는 경우, Microsoft의 기본 제공 교육 가능 분류자를 하나 이상 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-220">When you select the **Trainable classifiers** option, select one or more of the built-in trainable classifiers from Microsoft.</span></span> <span data-ttu-id="c0557-221">사용자 지정 교육 가능 분류자를 만든 경우, 다음의 사항 또한 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-221">If you've created your own custom trainable classifiers, these are also available to select:</span></span>

![교육 가능한 분류자 및 민감도 레이블에 대한 옵션](../media/sensitivity-labels-classifers.png)

> [!CAUTION]
> <span data-ttu-id="c0557-223">당사는 **비속어** 기본 제공 분류자가 많은 수의 가양성을 생성하였기 에 그 사용을 중단하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-223">We are deprecating the **Offensive Language** built-in classifier because it has been producing a high number of false positives.</span></span> <span data-ttu-id="c0557-224">이러한 기본 제공 분류자를 사용하지 않도록 하고 현재 사용하고 있는 경우에는 비즈니스 프로세스를 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-224">Don't use this built-in classifier and if you are currently using it, you should move your business processes off it.</span></span> <span data-ttu-id="c0557-225">대신에 **대상 지정 괴롭힘**,**모독** 그리고 **위협** 기본 제공 분류자를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-225">We recommend using the **Targeted Harassment**, **Profanity**, and **Threat** built-in classifiers instead.</span></span>

<span data-ttu-id="c0557-226">해당 분류자에 대한 자세한 내용은 [학습 가능한 분류자에 대한 자세한 정보](classifier-learn-about.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c0557-226">For more information about these classifiers, see [Learn about trainable classifiers](classifier-learn-about.md).</span></span>

<span data-ttu-id="c0557-227">이 옵션의 미리 보기 기간 동안 다음 앱이 민감도 레이블에 대한 교육 가능한 분류자를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-227">During the preview period for this option, the following apps support trainable classifiers for sensitivity labels:</span></span>

- <span data-ttu-id="c0557-228">Windows 엔터프라이즈용 Microsoft 365 앱([구 Office 365 ProPlus](/deployoffice/name-change))가 버전 2006 이후에서 [현재 채널](/deployoffice/overview-update-channels#current-channel-overview)로 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-228">Microsoft 365 Apps for enterprise ([formerly Office 365 ProPlus](/deployoffice/name-change)) for Windows, now rolling out to the [Current Channel](/deployoffice/overview-update-channels#current-channel-overview) in version 2006 and later:</span></span>
    - <span data-ttu-id="c0557-229">Word</span><span class="sxs-lookup"><span data-stu-id="c0557-229">Word</span></span>
    - <span data-ttu-id="c0557-230">Excel</span><span class="sxs-lookup"><span data-stu-id="c0557-230">Excel</span></span>
    - <span data-ttu-id="c0557-231">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="c0557-231">PowerPoint</span></span>

- <span data-ttu-id="c0557-232">[SharePoint 및 OneDrive에서 Office 파일에 대한 민감도 레이블을 사용하도록 설정](sensitivity-labels-sharepoint-onedrive-files.md)한 경우, 웹 앱용 Office:</span><span class="sxs-lookup"><span data-stu-id="c0557-232">Office for the web apps, when you have [enabled sensitivity labels for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md):</span></span>
    - <span data-ttu-id="c0557-233">Word</span><span class="sxs-lookup"><span data-stu-id="c0557-233">Word</span></span>
    - <span data-ttu-id="c0557-234">Excel</span><span class="sxs-lookup"><span data-stu-id="c0557-234">Excel</span></span>
    - <span data-ttu-id="c0557-235">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="c0557-235">PowerPoint</span></span>
    - <span data-ttu-id="c0557-236">Outlook</span><span class="sxs-lookup"><span data-stu-id="c0557-236">Outlook</span></span>

### <a name="recommend-that-the-user-applies-a-sensitivity-label"></a><span data-ttu-id="c0557-237">사용자가 민감도 레이블을 적용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-237">Recommend that the user applies a sensitivity label</span></span>

<span data-ttu-id="c0557-p121">원한다면 사용자에게 레이블을 적용하도록 권장할 수 있습니다. 이 옵션을 사용하면 사용자가 분류와 모든 관련 보호를 수락할 수 있으며, 사용자 콘텐츠에 레이블이 적합하지 않다면 권장 사항을 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-p121">If you prefer, you can recommend to your users that they apply the label. With this option, your users can accept the classification and any associated protection, or dismiss the recommendation if the label isn't suitable for their content.</span></span>

![사용자에게 민감도 레이블을 권장하기 위한 옵션](../media/Sensitivity-labels-Recommended-label-option.png)

<span data-ttu-id="c0557-p122">다음은 사용자 지정 정책 팁을 사용하여 레이블을 권장 작업으로 적용하도록 조건을 구성할 때 Azure Information Protection 통합 레이블 지정 클라이언트에서 표시되는 메시지의 예입니다. 정책 팁에 표시될 텍스트를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-p122">Here's an example of a prompt from the Azure Information Protection unified labeling client when you configure a condition to apply a label as a recommended action, with a custom policy tip. You can choose what text is displayed in the policy tip.</span></span>

![권장된 레이블을 적용하라는 메시지 표시](../media/Sensitivity-label-Prompt-for-required-label.png)

### <a name="when-automatic-or-recommended-labels-are-applied"></a><span data-ttu-id="c0557-244">자동 또는 권장 레이블이 적용되는 경우</span><span class="sxs-lookup"><span data-stu-id="c0557-244">When automatic or recommended labels are applied</span></span>

<span data-ttu-id="c0557-p123">Office 앱의 자동 및 권장 레이블 지정 구현은 Office 기본 제공 레이블을 사용할지, Azure Information Protection 통합 레이블 지정 클라이언트를 사용할지에 따라 달라집니다. 하지만 다음은 두 경우에 모두 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-p123">The implementation of automatic and recommended labeling in Office apps depend on whether you're using labeling that's built into Office, or the Azure Information Protection unified labeling client. In both cases, however:</span></span>

- <span data-ttu-id="c0557-p124">이전에 수동으로 레이블이 지정되었거나, 더 높은 수준의 민감성으로 자동으로 레이블이 지정된 적이 있는 문서나 전자 메일에 대해서는 자동 레이블 지정을 사용할 수 없습니다. 문서나 전자 메일에는 하나의 보존 레이블과 하나의 민감도 레이블만 적용할 수 있다는 사실을 기억하세요.</span><span class="sxs-lookup"><span data-stu-id="c0557-p124">You can't use automatic labeling for documents and emails that were previously manually labeled, or previously automatically labeled with a higher sensitivity. Remember, you can only apply a single sensitivity label to a document or email (in addition to a single retention label).</span></span>

- <span data-ttu-id="c0557-p125">이전에 더 높은 민감성으로 레이블이 지정된 적이 있는 문서나 전자 메일에 대해서는 권장 레이블 지정을 사용할 수 없습니다. 콘텐츠가 이미 더 높은 민감도로 레이블 지정되었다면 사용자에게는 권장 사항과 정책 팁이 담긴 메시지가 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-p125">You can't use recommended labeling for documents or emails that were previously labeled with a higher sensitivity. When the content's already labeled with a higher sensitivity, the user won't see the prompt with the recommendation and policy tip.</span></span>

<span data-ttu-id="c0557-251">기본 제공 레이블 지정과 관련된 내용:</span><span class="sxs-lookup"><span data-stu-id="c0557-251">Specific to built-in labeling:</span></span>

- <span data-ttu-id="c0557-252">모든 Office 앱이 자동(및 권장) 레이블 지정을 지원하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-252">Not all Office apps support automatic (and recommended) labeling.</span></span> <span data-ttu-id="c0557-253">자세한 내용은 [앱에서의 민감도 레이블 기능에 대한 지원](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c0557-253">For more information, see [Support for sensitivity label capabilities in apps](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps).</span></span>

- <span data-ttu-id="c0557-254">데스크톱 버전의 Word에서 권장되는 레이블의 경우 사용자가 권장되는 민감도 레이블을 적용하는 대신, 중요한 콘텐츠를 검토하고 제거할 수 있도록 권장 사항을 트리거한 중요한 콘텐츠에 플래그가 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-254">For recommended labels in the desktop versions of Word, the sensitive content that triggered the recommendation is flagged so that users can review and remove the sensitive content instead of applying the recommended sensitivity label.</span></span>

- <span data-ttu-id="c0557-255">Office 앱에서 이러한 레이블을 적용하는 방법에 대한 자세한 내용과 예제 스크린샷 및 중요한 정보를 검색하는 방법에 대한 자세한 내용은 [Office에서 파일 및 전자 메일에 자동으로 민감도 레이블 적용 또는 추천](https://support.office.com/ko-KR/article/automatically-apply-or-recommend-sensitivity-labels-to-your-files-and-emails-in-office-622e0d9c-f38c-470a-bcdb-9e90b24d71a1)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c0557-255">For details about how these labels are applied in Office apps, example screenshots, and how sensitive information is detected, see [Automatically apply or recommend sensitivity labels to your files and emails in Office](https://support.office.com/ko-KR/article/automatically-apply-or-recommend-sensitivity-labels-to-your-files-and-emails-in-office-622e0d9c-f38c-470a-bcdb-9e90b24d71a1).</span></span>

<span data-ttu-id="c0557-256">Azure Information Protection 통합 레이블 지정 클라이언트와 관련된 내용:</span><span class="sxs-lookup"><span data-stu-id="c0557-256">Specific to the Azure Information Protection unified labeling client:</span></span>

-  <span data-ttu-id="c0557-257">자동 및 권장되는 레이블은 문서를 저장할 때는 Word, Excel 및 PowerPoint에 적용되고, 전자 메일을 보낼 때는 Outlook에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-257">Automatic and recommended labeling applies to Word, Excel, and PowerPoint when you save a document, and to Outlook when you send an email.</span></span>

- <span data-ttu-id="c0557-258">Outlook에서 권장되는 레이블 지정을 지원하려면 먼저 [고급 정책 설정](/azure/information-protection/rms-client/clientv2-admin-guide-customizations#enable-recommended-classification-in-outlook)을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-258">For Outlook to support recommended labeling, you must first configure an [advanced policy setting](/azure/information-protection/rms-client/clientv2-admin-guide-customizations#enable-recommended-classification-in-outlook).</span></span>

- <span data-ttu-id="c0557-259">문서 및 전자 메일의 본문 텍스트와 머리글 및 바닥글에서는 중요한 정보를 검색할 수 있지만, 전자 메일의 제목 줄이나 첨부 파일에서는 중요한 정보를 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-259">Sensitive information can be detected in the body text in documents and emails, and to headers and footers—but not in the subject line or attachments of email.</span></span>

## <a name="how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange"></a><span data-ttu-id="c0557-260">SharePoint, OneDrive 및 Exchange에 대한 자동 레이블 지정 정책을 구성하는 방법</span><span class="sxs-lookup"><span data-stu-id="c0557-260">How to configure auto-labeling policies for SharePoint, OneDrive, and Exchange</span></span>

<span data-ttu-id="c0557-261">반드시 자동 레이블 정책을 구성하기 전에 먼저 필수 조건을 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-261">Make sure you're aware of the prerequisites before you configure auto-labeling policies.</span></span> 

### <a name="prerequisites-for-auto-labeling-policies"></a><span data-ttu-id="c0557-262">자동 레이블 지정 정책에 대한 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="c0557-262">Prerequisites for auto-labeling policies</span></span>

- <span data-ttu-id="c0557-263">시뮬레이션 모드:</span><span class="sxs-lookup"><span data-stu-id="c0557-263">Simulation mode:</span></span>
    - <span data-ttu-id="c0557-264">Microsoft 365에 대한 감사가 설정되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-264">Auditing for Microsoft 365 must be turned on.</span></span> <span data-ttu-id="c0557-265">감사를 설정해야 하거나 감사가 이미 설정되어 있는지 확실하지 않은 경우에는 [감사 로그 검색 켜기 또는 끄기](turn-audit-log-search-on-or-off.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c0557-265">If you need to turn on auditing or you're not sure whether auditing is already on, see [Turn audit log search on or off](turn-audit-log-search-on-or-off.md).</span></span>
    - <span data-ttu-id="c0557-266">원본 보기에서 파일 또는 전자 메일 콘텐츠를 보려면 **콘텐츠 탐색기 콘텐츠 뷰어** 역할을 보유하고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-266">To view file or email contents in the source view, you must have the **Content Explorer Content Viewer** role.</span></span> <span data-ttu-id="c0557-267">전역 관리자에게는 기본적으로 해당 역할이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-267">Global admins don't have this role by default.</span></span> <span data-ttu-id="c0557-268">이 권한이 없는 경우 **일치하는 항목** 탭에서 항목을 선택할 때 미리 보기 창이 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-268">If you don't have this permission, you don't see the preview pane when you select an item from the **Matched Items** tab.</span></span>

- <span data-ttu-id="c0557-269">SharePoint 및 OneDrive에서 파일에 자동 레이블을 지정하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-269">To auto-label files in SharePoint and OneDrive:</span></span>
    - <span data-ttu-id="c0557-270">[SharePoint 및 OneDrive에서 Office 파일에 대한 민감도 레이블을 사용하도록 설정](sensitivity-labels-sharepoint-onedrive-files.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-270">You have [enabled sensitivity labels for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>
    - <span data-ttu-id="c0557-271">자동 레이블 지정 정책이 실행될 때 다른 프로세스나 사용자가 파일을 열면 안됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-271">At the time the auto-labeling policy runs, the file mustn't be open by another process or user.</span></span> <span data-ttu-id="c0557-272">편집을 위해 체크 아웃된 파일은 이 범주로 분류됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-272">A file that's checked out for editing falls into this category.</span></span>

- <span data-ttu-id="c0557-273">기본 제공 민감도 유형이 아닌 [사용자 지정 민감도 정보 유형](sensitive-information-type-learn-about.md)을 사용하려는 경우:</span><span class="sxs-lookup"><span data-stu-id="c0557-273">If you plan to use [custom sensitive information types](sensitive-information-type-learn-about.md) rather than the built-in sensitivity types:</span></span> 
    - <span data-ttu-id="c0557-274">사용자 지정 민감도 정보 유형은 사용자 지정 민감도 정보 유형을 저장한 후 SharePoint 또는 OneDrive에 추가되는 콘텐츠에 대해 평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-274">Custom sensitivity information types are evaluated for content that is added to SharePoint or OneDrive after the custom sensitivity information types are saved.</span></span> 
    - <span data-ttu-id="c0557-275">새로운 사용자 지정 민감도 정보 유형을 테스트하려면 자동 레이블 지정 정책을 만들기 전에 해당 유형을 만든 다음 테스트용 샘플 데이터가 포함된 새 문서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-275">To test new custom sensitive information types, create them before you create your auto-labeling policy, and then create new documents with sample data for testing.</span></span>

- <span data-ttu-id="c0557-276">자동 레이블 지정 정책에 대해 선택할 수 있는 하나 이상의 민감도 레이블이 [생성 및 게시](create-sensitivity-labels.md)(적어도 한 명의 사용자에게) 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-276">One or more sensitivity labels [created and published](create-sensitivity-labels.md) (to at least one user) that you can select for your auto-labeling policies.</span></span> <span data-ttu-id="c0557-277">이러한 레이블의 경우:</span><span class="sxs-lookup"><span data-stu-id="c0557-277">For these labels:</span></span>
    - <span data-ttu-id="c0557-278">소개에 설명된 대로 레이블 설정은 자동 레이블 지정 정책을 보완하기 때문에 Office 앱 레이블 설정의 자동 레이블 지정 설정이 켜져 있는지 여부는 중요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-278">It doesn't matter if the auto-labeling in Office apps label setting is turned on or off, because that label setting supplements auto-labeling policies, as explained in the introduction.</span></span>
    - <span data-ttu-id="c0557-279">자동 레이블에 사용하려는 레이블이 시각적 표시(머리글, 바닥글, 워터 마크)를 사용하도록 구성된 경우 문서에는 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-279">If the labels you want to use for auto-labeling are configured to use visual markings (headers, footers, watermarks), note that these are not applied to documents.</span></span>
    - <span data-ttu-id="c0557-280">레이블이 [암호화](encryption-sensitivity-labels.md)를 적용하는 경우 **지금 권한 할당** 설정에 대해 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-280">If the labels apply [encryption](encryption-sensitivity-labels.md), they must be configured for the **Assign permissions now** setting.</span></span>

### <a name="learn-about-simulation-mode"></a><span data-ttu-id="c0557-281">시뮬레이션 모드에 대해 알아보기</span><span class="sxs-lookup"><span data-stu-id="c0557-281">Learn about simulation mode</span></span>

<span data-ttu-id="c0557-282">시뮬레이션 모드는 자동 레이블 지정 정책에 고유하며 워크플로에 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-282">Simulation mode is unique to auto-labeling policies and woven into the workflow.</span></span> <span data-ttu-id="c0557-283">정책에서 적어도 한 번의 시뮬레이션이 실행될 때까지 문서 및 전자 메일에 자동으로 레이블을 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-283">You can't automatically label documents and emails until your policy has run at least one simulation.</span></span>

<span data-ttu-id="c0557-284">자동 레이블 지정 정책의 워크플로:</span><span class="sxs-lookup"><span data-stu-id="c0557-284">Workflow for an auto-labeling policy:</span></span>

1. <span data-ttu-id="c0557-285">자동 레이블 정책 만들기 및 구성</span><span class="sxs-lookup"><span data-stu-id="c0557-285">Create and configure an auto-labeling policy.</span></span>

2. <span data-ttu-id="c0557-286">시뮬레이션 모드에서 정책을 실행하며 완료하는 데 48시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-286">Run the policy in simulation mode, which can take 48 hours to complete.</span></span>

3. <span data-ttu-id="c0557-287">결과를 검토하고 필요한 경우 정책을 구체화합니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-287">Review the results, and if necessary, refine your policy.</span></span> <span data-ttu-id="c0557-288">응답 모드를 다시 실행하고 다시 완료될 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-288">Rerun simulation mode and wait for it to complete again.</span></span>

4. <span data-ttu-id="c0557-289">필요한 경우 3단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-289">Repeat step 3 as needed.</span></span>

5. <span data-ttu-id="c0557-290">프로덕션에서 배포.</span><span class="sxs-lookup"><span data-stu-id="c0557-290">Deploy in production.</span></span>

<span data-ttu-id="c0557-291">시뮬레이션된 배포는 PowerShell의 WhatIf 매개 변수처럼 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-291">The simulated deployment runs like the WhatIf parameter for PowerShell.</span></span> <span data-ttu-id="c0557-292">사용자가 정의한 규칙을 사용하여 자동 레이블 지정 정책이 선택한 레이블을 적용한 것처럼 보고된 결과를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-292">You see results reported as if the auto-labeling policy had applied your selected label, using the rules that you defined.</span></span> <span data-ttu-id="c0557-293">그런 다음 필요한 경우 규칙을 조정하고 시뮬레이션을 다시 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-293">You can then refine your rules for accuracy if needed, and rerun the simulation.</span></span> <span data-ttu-id="c0557-294">그러나 Exchange용 자동 레이블 지정은 사서함에 저장된 전자 메일이 아닌 보내고 받는 전자 메일에 적용되기 때문에, 정확히 같은 전자 메일 메시지를 보내고 받을 수 없는 한 시뮬레이션의 전자 메일에 대한 결과가 일관되길 기대하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-294">However, because auto-labeling for Exchange applies to emails that are sent and received, rather than emails stored in mailboxes, don't expect results for email in a simulation to be consistent unless you're able to send and receive the exact same email messages.</span></span>

<span data-ttu-id="c0557-295">또한 시뮬레이션 모드를 사용하면 배포 전에 자동 레이블 지정 정책의 범위를 단계적으로 늘릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-295">Simulation mode also lets you gradually increase the scope of your auto-labeling policy before deployment.</span></span> <span data-ttu-id="c0557-296">예를 들어 단일 문서 라이브러리를 사용하여 SharePoint 사이트와 같은 단일 위치에서 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-296">For example, you might start with a single location, such as a SharePoint site, with a single document library.</span></span> <span data-ttu-id="c0557-297">그런 다음 반복적인 변경으로 범위를 여러 사이트로 늘리고 OneDrive와 같은 다른 위치로 범위를 늘립니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-297">Then, with iterative changes, increase the scope to multiple sites, and then to another location, such as OneDrive.</span></span>

<span data-ttu-id="c0557-298">마지막으로 시뮬레이션 모드를 사용하여 자동 레이블 지정 정책을 실행하는 데 필요한 시간을 대략적으로 제공하여 시뮬레이션 모드없이 실행할 시기를 계획하고 예약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-298">Finally, you can use simulation mode to provide an approximation of the time needed to run your auto-labeling policy, to help you plan and schedule when to run it without simulation mode.</span></span>

### <a name="creating-an-auto-labeling-policy"></a><span data-ttu-id="c0557-299">자동 레이블 지정 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="c0557-299">Creating an auto-labeling policy</span></span>

1. <span data-ttu-id="c0557-300">[Microsoft 365 규정 준수 센터](https://compliance.microsoft.com/)에서 민감도 레이블로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-300">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to sensitivity labels:</span></span>
    
    - <span data-ttu-id="c0557-301">**솔루션** > **정보 보호**</span><span class="sxs-lookup"><span data-stu-id="c0557-301">**Solutions** > **Information protection**</span></span>
    
    <span data-ttu-id="c0557-302">이 옵션이 바로 보이지 않는 경우에는 먼저 **모두 표시** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-302">If you don't immediately see this option, first select **Show all**.</span></span>

2. <span data-ttu-id="c0557-303">**자동 레이블 지정** 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-303">Select the **Auto-labeling** tab:</span></span>
    
    ![자동 레이블 지정 탭](../media/auto-labeling-tab.png)
    
    > [!NOTE]
    > <span data-ttu-id="c0557-305">**자동 레이블** 탭이 보이지 않으면 현재 해당 지역에서 이 기능을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-305">If you don't see the **Auto-labeling** tab, this functionality isn't currently available in your region.</span></span>

3. <span data-ttu-id="c0557-306">**+ 자동 레이블 지정 정책 만들기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-306">Select **+ Create auto-labeling policy**.</span></span> <span data-ttu-id="c0557-307">이를 통해 새 정책 마법사가 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-307">This starts the New policy wizard:</span></span>
    
    ![<span data-ttu-id="c0557-308">자동 레이블 지정에 대한 새 정책 마법사</span><span class="sxs-lookup"><span data-stu-id="c0557-308">New policy wizard for auto-labeling</span></span> ](../media/auto-labeling-wizard.png)

4. <span data-ttu-id="c0557-309">**이 레이블을 적용할 정보 선택** 페이지에서 **재무** 또는 **개인 정보 보호** 와 같은 템플릿 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-309">For the page **Choose info you want this label applied to**: Select one of the templates, such as **Financial** or **Privacy**.</span></span> <span data-ttu-id="c0557-310">**표시 옵션** 드롭 다운을 사용하여 검색을 구체화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-310">You can refine your search by using the **Show options for** dropdown.</span></span> <span data-ttu-id="c0557-311">또는 템플릿이 요구 사항을 충족하지 않으면 **사용자 지정 정책** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-311">Or, select **Custom policy** if the templates don't meet your requirements.</span></span> <span data-ttu-id="c0557-312">**다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-312">Select **Next**.</span></span>

5. <span data-ttu-id="c0557-313">**자동 레이블 지정 정책 이름 지정** 페이지에서 고유한 이름을 입력하고, 필요에 따라 레이블을 지정할 콘텐츠를 식별하는 자동으로 적용되는 레이블, 위치 및 조건을 식별하는 데 도움이 되는 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-313">For the page **Name your auto-labeling policy**: Provide a unique name, and optionally a description to help identify the automatically applied label, locations, and conditions that identify the content to label.</span></span>

6. <span data-ttu-id="c0557-314">**레이블을 적용할 위치 선택** 페이지에서 Exchange, SharePoint 사이트 및 OneDrive의 위치를 선택하고 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-314">For the page **Choose locations where you want to apply the label**: Select and specify locations for Exchange, SharePoint sites, and OneDrive.</span></span> <span data-ttu-id="c0557-315">그런 후 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-315">Then select **Next**.</span></span>
    
    ![<span data-ttu-id="c0557-316">위치 선택 페이지 자동 레이블 지정 마법사</span><span class="sxs-lookup"><span data-stu-id="c0557-316">Choose locations page auto-labelingwizard</span></span> ](../media/locations-auto-labeling-wizard.png)
    
    <span data-ttu-id="c0557-317">개별 SharePoint 사이트 및 OneDrive 계정을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-317">You must specify individual SharePoint sites and OneDrive accounts.</span></span> <span data-ttu-id="c0557-318">OneDrive의 경우, 사용자의 OneDrive에 대한 URL은 다음과 같은 형식입니다. `https://<tenant name>-my.sharepoint.com/personal/<user_name>_<tenant name>_com`</span><span class="sxs-lookup"><span data-stu-id="c0557-318">For OneDrive, the URL for a user's OneDrive account is in the following format: `https://<tenant name>-my.sharepoint.com/personal/<user_name>_<tenant name>_com`</span></span>
    
    <span data-ttu-id="c0557-319">예를 들어, "rsimone"라는 사용자 이름을 보유한 Contoso 테넌트에 있는 사용자의 경우: `https://contoso-my.sharepoint.com/personal/rsimone_contoso_onmicrosoft_com`</span><span class="sxs-lookup"><span data-stu-id="c0557-319">For example, for a user in the contoso tenant that has a user name of "rsimone": `https://contoso-my.sharepoint.com/personal/rsimone_contoso_onmicrosoft_com`</span></span>
    
    <span data-ttu-id="c0557-320">테넌트의 구문을 확인하고 사용자 URL을 확인하려면, [조직에 있는 모든 사용자 OneDrive URL 목록 가져오기](/onedrive/list-onedrive-urls)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c0557-320">To verify the syntax for your tenant and identify URLs for users, see [Get a list of all user OneDrive URLs in your organization](/onedrive/list-onedrive-urls).</span></span>

7. <span data-ttu-id="c0557-321">**일반 또는 고급 규칙 설정** 페이지의 경우: 선택한 모든 위치에서 레이블을 지정할 콘텐츠를 식별하는 규칙을 정의하기 위해 **일반 규칙** 의 기본값을 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-321">For the **Set up common or advanced rules** page: Keep the default of **Common rules** to define rules that identify content to label across all your selected locations.</span></span> <span data-ttu-id="c0557-322">위치마다 다른 규칙이 필요한 경우 **고급 규칙** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-322">If you need different rules per location, select **Advanced rules**.</span></span> <span data-ttu-id="c0557-323">그런 후 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-323">Then select **Next**.</span></span>
    
    <span data-ttu-id="c0557-324">이 규칙은 민감한 정보 유형 및 공유 옵션이 포함된 조건을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-324">The rules use conditions that include sensitive information types and sharing options:</span></span>
    - <span data-ttu-id="c0557-325">민감한 정보 유형의 경우 기본 제공 정보 유형과 사용자 지정 민감한 정보 유형을 모두 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-325">For sensitive information types, you can select both built-in and custom sensitive information types.</span></span>
    - <span data-ttu-id="c0557-326">공유 옵션의 경우 **조직 내부의 사용자만** 또는 **조직 외부의 사용자** 를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-326">For the shared options, you can choose **only with people inside my organization** or **with people outside my organization**.</span></span>
    
    <span data-ttu-id="c0557-327">유일한 위치가 **Exchange** 이거나 **고급 규칙** 을 선택한 경우 다음과 같은 추가 조건을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-327">If your only location is **Exchange**, or if you select **Advanced rules**, there are additional conditions that you can select:</span></span>
    - <span data-ttu-id="c0557-328">보낸 사람 IP 주소는</span><span class="sxs-lookup"><span data-stu-id="c0557-328">Sender IP address is</span></span>
    - <span data-ttu-id="c0557-329">받는 사람 도메인은</span><span class="sxs-lookup"><span data-stu-id="c0557-329">Recipient domain is</span></span>
    - <span data-ttu-id="c0557-330">받는 사람은</span><span class="sxs-lookup"><span data-stu-id="c0557-330">Recipient is</span></span>
    - <span data-ttu-id="c0557-331">첨부 파일 확장명은</span><span class="sxs-lookup"><span data-stu-id="c0557-331">Attachment's file extension is</span></span>
    - <span data-ttu-id="c0557-332">첨부 파일이 암호로 보호됨</span><span class="sxs-lookup"><span data-stu-id="c0557-332">Attachment is password protected</span></span>
    - <span data-ttu-id="c0557-333">전자 메일 첨부 파일의 콘텐츠를 검사할 수 없음</span><span class="sxs-lookup"><span data-stu-id="c0557-333">Any email attachment's content could not be scanned</span></span>
    - <span data-ttu-id="c0557-334">전자 메일 첨부 파일 내용의 검사가 완료되지 않음</span><span class="sxs-lookup"><span data-stu-id="c0557-334">Any email attachment's content didn't complete scanning</span></span>

8. <span data-ttu-id="c0557-335">이제 이전 선택에 따라 조건 및 예외를 사용하여 새 규칙을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-335">Depending on your previous choices, you'll now have an opportunity to create new rules by using conditions and exceptions.</span></span>
    
    <span data-ttu-id="c0557-336">민감한 정보 유형의 구성 옵션은 Office 앱에 대한 자동 레이블 지정에 대해 선택한 것과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-336">The configuration options for sensitive information types are the same as those you select for auto-labeling for Office apps.</span></span> <span data-ttu-id="c0557-337">자세한 정보가 필요한 경우 [레이블에 민감한 정보 유형 구성](#configuring-sensitive-info-types-for-a-label)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c0557-337">If you need more information, see [Configuring sensitive info types for a label](#configuring-sensitive-info-types-for-a-label).</span></span>
    
    <span data-ttu-id="c0557-338">필요한 모든 규칙을 정의하고 해당 상태가 켜져 있음을 확인한 후 **다음** 을 선택하여 자동 적용을 위해 레이블 선택으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-338">When you have defined all the rules you need, and confirmed their status is on, select **Next** to move on to choosing a label to auto-apply.</span></span>

11. <span data-ttu-id="c0557-339">**자동 적용할 레이블 선택** 페이지에서 **+ 레이블 선택** 을 선택하고, **민감도 레이블 선택** 창에서 레이블을 선택한 후 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-339">For the **Choose a label to auto-apply** page: Select **+ Choose a label**, select a label from the **Choose a sensitivity label** pane, and then select **Next**.</span></span>

12. <span data-ttu-id="c0557-340">**정책을 지금 또는 나중에 테스트할지 결정** 페이지의 경우: 지금 자동 레이블 지정 정책을 실행할 준비가 되었으면 **시뮬레이션 모드에서 정책 실행** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-340">For the **Decide if you want to test out the policy now or later** page: Select **Run policy in simulation mode** if you're ready to run the auto-labeling policy now, in simulation mode.</span></span> <span data-ttu-id="c0557-341">그렇지 않으면 **정책을 해제로 두기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-341">Otherwise, select **Leave policy turned off**.</span></span> <span data-ttu-id="c0557-342">**다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-342">Select **Next**:</span></span> 
    
    ![정책 자동 레이블 지정 마법사 테스트](../media/simulation-mode-auto-labeling-wizard.png)

13. <span data-ttu-id="c0557-344">**요약** 페이지에서 자동 레이블 지정 정책의 구성을 검토하고 필요한 사항을 변경한 후 마법사를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-344">For the **Summary** page: Review the configuration of your auto-labeling policy and make any changes that needed, and complete the wizard.</span></span>

<span data-ttu-id="c0557-345">이제 **정보 보호** > **자동 레이블 지정** 페이지에서 **시뮬레이션** 혹은 **끄기** 구역에 시뮬레이션 모드에서 실행할지의 선택 여부에 따라 자동 레이블 지정 정책이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-345">Now on the **Information protection** > **Auto-labeling** page, you see your auto-labeling policy in the **Simulation** or **Off** section, depending on whether you chose to run it in simulation mode or not.</span></span> <span data-ttu-id="c0557-346">구성 및 상태에 대한 세부 사항을 보려면 정책을 선택합니다(예: **정책 시뮬레이션을 아직 실행 중**).</span><span class="sxs-lookup"><span data-stu-id="c0557-346">Select your policy to see the details of the configuration and status (for example, **Policy simulation is still running**).</span></span> <span data-ttu-id="c0557-347">시뮬레이션 모드에서의 정책의 경우 **일치 항목** 탭을 선택하여 지정한 규칙과 일치하는 전자 메일 또는 문서를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-347">For policies in simulation mode, select the **Matched items** tab to see which emails or documents matched the rules that you specified.</span></span>

<span data-ttu-id="c0557-348">다음의 인터페이스에서 직접 정책을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-348">You can modify your policy directly from this interface:</span></span>

- <span data-ttu-id="c0557-349">**끄기** 구역에 있는 정책의 경우 **정책 편집** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-349">For a policy in the **Off** section, select the **Edit policy** button.</span></span>

- <span data-ttu-id="c0557-350">**시뮬레이션** 구역에 있는 정책의 경우 페이지 맨 위의 다음과 같은 탭에서 **편집** 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-350">For policy in the **Simulation** section, select the **Edit policy** option at the top of the page, from either tab:</span></span>
    
    ![자동 레이블 지정 정책 옵션 편집](../media/auto-labeling-edit.png)
    
    <span data-ttu-id="c0557-352">시뮬레이션없이 정책을 실행할 준비가 되면 **정책 켜기** 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-352">When you're ready to run the policy without simulation, select the **Turn on policy** option.</span></span>

<span data-ttu-id="c0557-353">자동 정책은 삭제될 때까지 계속 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-353">Your auto-policies run continuously until they are deleted.</span></span> <span data-ttu-id="c0557-354">예를 들어 새 문서와 수정된 문서는 현재 정책 설정에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-354">For example, new and modified documents will be included with the current policy settings.</span></span>

<span data-ttu-id="c0557-355">적절한 [권한](data-classification-content-explorer.md#permissions)이 있는 경우 [콘텐츠 탐색기](data-classification-content-explorer.md)를 사용하여 자동 레이블 지정 정책의 결과를 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-355">You can also see the results of your auto-labeling policy by using [content explorer](data-classification-content-explorer.md) when you have the appropriate [permissions](data-classification-content-explorer.md#permissions):</span></span>
- <span data-ttu-id="c0557-356">**콘텐츠 탐색기 목록 뷰어** 를 사용하면 파일 내용이 아닌 파일의 레이블을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-356">**Content Explorer List Viewer** lets you see a file's label but not the file's contents.</span></span>
- <span data-ttu-id="c0557-357">**콘텐츠 탐색기 콘텐츠 뷰어** 를 사용하면 파일 내용을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-357">**Content Explorer Content Viewer** lets you see the file's contents.</span></span>

> [!TIP]
> <span data-ttu-id="c0557-358">또한 콘텐츠 탐색기를 사용하여 민감한 정보가 포함된 문서가 있지만 레이블이 지정되지 않은 위치를 식별할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-358">You can also use content explorer to identify locations that have documents with sensitive information, but are unlabeled.</span></span> <span data-ttu-id="c0557-359">이 정보를 사용하여 이러한 위치를 자동 레이블 지정 정책에 추가하고 식별된 민감한 정보 유형을 규칙으로 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-359">Using this information, consider adding these locations to your auto-labeling policy, and include the identified sensitive information types as rules.</span></span>

### <a name="use-powershell-for-auto-labeling-policies"></a><span data-ttu-id="c0557-360">자동 레이블 지정 정책을 위한 PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="c0557-360">Use PowerShell for auto-labeling policies</span></span>

<span data-ttu-id="c0557-361">[보안 및 준수 센터 PowerShell](/powershell/exchange/scc-powershell)을 사용하여 자동 레이블 지정 정책을 만들고 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-361">You can use [Security & Compliance Center PowerShell](/powershell/exchange/scc-powershell) to create and configure auto-labeling policies.</span></span> <span data-ttu-id="c0557-362">즉, 자동 레이블 지정 정책의 생성 및 유지 관리를 완전히 스크립팅할 수 있으며 OneDrive 및 SharePoint 위치에 대해 여러 URL을 지정하는 보다 효율적인 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-362">This means you can fully script the creation and maintenance of your auto-labeling policies, which also provides a more efficient method of specifying multiple URLs for OneDrive and SharePoint locations.</span></span>

<span data-ttu-id="c0557-363">PowerShell에서 명령을 실행하기 전에 먼저 [보안 및 준수 센터 PowerShell에 연결](/powershell/exchange/connect-to-scc-powershell)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-363">Before you run the commands in PowerShell, you must first [connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

<span data-ttu-id="c0557-364">새 자동 레이블 지정 정책을 생성하려면 다음을 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="c0557-364">To create a new auto-labeling policy:</span></span> 

```powershell
New-AutoSensitivityLabelPolicy -Name <AutoLabelingPolicyName> -SharePointLocation "<SharePointSiteLocation>" -ApplySensitivityLabel <Label> -Mode TestWithoutNotifications
```
<span data-ttu-id="c0557-365">이 명령은 지정한 SharePoint 사이트에 대한 자동 레이블 지정 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-365">This command creates an auto-labeling policy for a SharePoint site that you specify.</span></span> <span data-ttu-id="c0557-366">OneDrive 위치의 경우 *OneDriveLocation* 매개 변수를 대신 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="c0557-366">For a OneDrive location, use the *OneDriveLocation* parameter, instead.</span></span> 

<span data-ttu-id="c0557-367">기존 자동 레이블 지정 정책에 사이트를 추가하려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="c0557-367">To add additional sites to an existing auto-labeling policy:</span></span>

```powershell
$spoLocations = @("<SharePointSiteLocation1>","<SharePointSiteLocation2>")
Set-AutoSensitivityLabelPolicy -Identity <AutoLabelingPolicyName> -AddSharePointLocation $spoLocations -ApplySensitivityLabel <Label> -Mode TestWithoutNotifications
```

<span data-ttu-id="c0557-368">이 명령은 기존 자동 레이블 지정 정책에 추가되는 변수의 추가 SharePoint URL을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-368">This command specifies the additional SharePoint URLs in a variable that is then added to an existing auto-labeling policy.</span></span> <span data-ttu-id="c0557-369">OneDrive 위치를 대신 추가하려면 *$OneDriveLocations* 와 같은 다른 변수와 함께 *AddOneDriveLocation* 매개 변수를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="c0557-369">To add OneDrive locations instead, use the *AddOneDriveLocation* parameter with a different variable, such as *$OneDriveLocations*.</span></span>

<span data-ttu-id="c0557-370">새로운 자동 레이블 지정 정책 규칙을 만들려면 다음을 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="c0557-370">To create a new auto-labeling policy rule:</span></span>

```powershell
New-AutoSensitivityLabelRule -Policy <AutoLabelingPolicyName> -Name <AutoLabelingRuleName> -ContentContainsSensitiveInformation @{"name"= "a44669fe-0d48-453d-a9b1-2cc83f2cba77"; "mincount" = "2"} -Workload SharePoint
```

<span data-ttu-id="c0557-371">기존 자동 레이블 지정 정책의 경우, 이 명령은 엔터티 ID가 a44669fe-0d48-453d-a9b1-2cc83f2cba77인 **미국 사회 보장 번호(SSN)** 의 중요한 정보 유형을 감지하는 새 정책 규칙을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c0557-371">For an existing auto-labeling policy, this command creates a new policy rule to detect the sensitive information type of **U.S. social security number (SSN)**, which has an entity ID of a44669fe-0d48-453d-a9b1-2cc83f2cba77.</span></span> <span data-ttu-id="c0557-372">다른 중요한 정보 유형의 엔티티 ID를 찾으려면 [중요한 정보 유형 엔터티 정의](sensitive-information-type-entity-definitions.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c0557-372">To find the entity IDs for other sensitive information types, refer to [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md).</span></span>

<span data-ttu-id="c0557-373">자동 레이블 지정 정책을 지원하는 PowerShell cmdlet, 사용 가능한 매개 변수 및 몇 가지 예에 대한 자세한 내용은 다음 cmdlet 도움말을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c0557-373">For more information about the PowerShell cmdlets that support auto-labeling policies, their available parameters and some examples, see the following cmdlet help:</span></span>

- [<span data-ttu-id="c0557-374">Get-AutoSensitivityLabelPolicy</span><span class="sxs-lookup"><span data-stu-id="c0557-374">Get-AutoSensitivityLabelPolicy</span></span>](/powershell/module/exchange/get-autosensitivitylabelpolicy)
- [<span data-ttu-id="c0557-375">New-AutoSensitivityLabelPolicy</span><span class="sxs-lookup"><span data-stu-id="c0557-375">New-AutoSensitivityLabelPolicy</span></span>](/powershell/module/exchange/new-autosensitivitylabelpolicy)
- [<span data-ttu-id="c0557-376">New-AutoSensitivityLabelRule</span><span class="sxs-lookup"><span data-stu-id="c0557-376">New-AutoSensitivityLabelRule</span></span>](/powershell/module/exchange/new-autosensitivitylabelrule)
- [<span data-ttu-id="c0557-377">Remove-AutoSensitivityLabelPolicy</span><span class="sxs-lookup"><span data-stu-id="c0557-377">Remove-AutoSensitivityLabelPolicy</span></span>](/powershell/module/exchange/remove-autosensitivitylabelpolicy)
- [<span data-ttu-id="c0557-378">Remove-AutoSensitivityLabelRule</span><span class="sxs-lookup"><span data-stu-id="c0557-378">Remove-AutoSensitivityLabelRule</span></span>](/powershell/module/exchange/remove-autosensitivitylabelrule)
- [<span data-ttu-id="c0557-379">Set-AutoSensitivityLabelPolicy</span><span class="sxs-lookup"><span data-stu-id="c0557-379">Set-AutoSensitivityLabelPolicy</span></span>](/powershell/module/exchange/set-autosensitivitylabelpolicy)
- [<span data-ttu-id="c0557-380">Set-AutoSensitivityLabelRule</span><span class="sxs-lookup"><span data-stu-id="c0557-380">Set-AutoSensitivityLabelRule</span></span>](/powershell/module/exchange/set-autosensitivitylabelrule)