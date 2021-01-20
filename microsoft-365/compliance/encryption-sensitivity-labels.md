---
title: 민감도 레이블을 사용하여 암호화를 적용하여 콘텐츠 액세스 제한하기
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 액세스 및 사용을 제한하여 데이터를 보호하는 암호화를 위한 민감도 레이블을 구성합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 83ed515d5ac6ea853c3e6a822fae0a03f73fc37c
ms.sourcegitcommit: 9e4b3df05eff94fe1be4ef8618a7ce6f2fca3658
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2021
ms.locfileid: "49904033"
---
# <a name="restrict-access-to-content-by-using-sensitivity-labels-to-apply-encryption"></a><span data-ttu-id="7aa6b-103">민감도 레이블을 사용하여 암호화를 적용하여 콘텐츠 액세스 제한</span><span class="sxs-lookup"><span data-stu-id="7aa6b-103">Restrict access to content by using sensitivity labels to apply encryption</span></span>

><span data-ttu-id="7aa6b-104">*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD)*</span><span class="sxs-lookup"><span data-stu-id="7aa6b-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="7aa6b-p101">민감한 레이블을 만들면 레이블이 적용되는 콘텐츠에 대한 액세스를 제한할 수 있습니다. 예를 들어 민감도 레이블의 암호화 설정으로 다음과 같이 콘텐츠를 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-p101">When you create a sensitivity label, you can restrict access to content that the label will be applied to. For example, with the encryption settings for a sensitivity label, you can protect content so that:</span></span>

- <span data-ttu-id="7aa6b-107">조직 내의 사용자만 기밀 문서나 전자 메일을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-107">Only users within your organization can open a confidential document or email.</span></span>
- <span data-ttu-id="7aa6b-108">마케팅 부서의 사용자만 프로모션 공지 사항 문서 또는 전자 메일을 편집하고 인쇄할 수 있으며 조직의 다른 모든 사용자는 이를 읽는 것만 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-108">Only users in the marketing department can edit and print the promotion announcement document or email, while all other users in your organization can only read it.</span></span>
- <span data-ttu-id="7aa6b-109">사용자는 내부 재구성에 대한 소식이 포함된 전자 메일을 전달하거나 정보를 복사할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-109">Users cannot forward an email or copy information from it that contains news about an internal reorganization.</span></span>
- <span data-ttu-id="7aa6b-110">비즈니스 파트너에게 전송되는 현재 가격 목록은 특정 날짜 이후에 열 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-110">The current price list that is sent to business partners cannot be opened after a specified date.</span></span>

<span data-ttu-id="7aa6b-111">문서 또는 전자 메일이 암호화되면 콘텐츠에 대한 액세스가 다음과 같이 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-111">When a document or email is encrypted, access to the content is restricted, so that it:</span></span>

- <span data-ttu-id="7aa6b-112">레이블의 암호화 설정에 따라 권한이 있는 사용자만 암호를 해독할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-112">Can be decrypted only by users authorized by the label's encryption settings.</span></span>
- <span data-ttu-id="7aa6b-113">파일의 이름이 바뀌더라도 조직의 내부 또는 외부에 관계 없이 암호화된 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-113">Remains encrypted no matter where it resides, inside or outside your organization, even if the file's renamed.</span></span>
- <span data-ttu-id="7aa6b-114">작동 중단 시(예: OneDrive 계정에서) 및 전송 중(예: 전자 메일이 인터넷을 트래버스할 때)에 모두 암호화됩니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-114">Is encrypted both at rest (for example, in a OneDrive account) and in transit (for example, email as it traverses the internet).</span></span>

<span data-ttu-id="7aa6b-115">마지막으로, 관리자가 암호화 적용을 위해 민감도 레이블을 구성할 때 다음 중 하나를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-115">Finally, as an admin, when you configure a sensitivity label to apply encryption, you can choose either to:</span></span>

- <span data-ttu-id="7aa6b-116">어떤 사용자에게 해당 레이블이 있는 콘텐츠에 어떤 권한을 부여할 것인지 정확하게 결정하도록 **지금 권한을 할당** 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-116">**Assign permissions now**, so that you determine exactly which users get which permissions to content with that label.</span></span>
- <span data-ttu-id="7aa6b-117">사용자가 콘텐츠에 레이블을 적용하는 경우 **사용자가 권한을 할당하도록** 허용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-117">**Let users assign permissions** when they apply the label to content.</span></span> <span data-ttu-id="7aa6b-118">이렇게 하면 조직의 사용자가 공동 작업과 작업 수행을 유연하게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-118">This way, you can allow people in your organization some flexibility that they might need to collaborate and get their work done.</span></span>

<span data-ttu-id="7aa6b-119">암호화 설정은 Microsoft 365 규정 준수 센터, Microsoft 365 보안 센터 또는 보안 및 규정 준수 센터에서 [민감도 레이블 만들기](create-sensitivity-labels.md)를 할 때 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-119">The encryption settings are available when you [create a sensitivity label](create-sensitivity-labels.md) in the Microsoft 365 compliance center, Microsoft 365 security center, or the Security & Compliance Center.</span></span>

## <a name="understand-how-the-encryption-works"></a><span data-ttu-id="7aa6b-120">암호화 작동 방식 이해</span><span class="sxs-lookup"><span data-stu-id="7aa6b-120">Understand how the encryption works</span></span>

<span data-ttu-id="7aa6b-121">암호화는 Azure Information Protection의 Azure RMS(Azure 권한 관리 서비스)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-121">Encryption uses the Azure Rights Management service (Azure RMS) from Azure Information Protection.</span></span> <span data-ttu-id="7aa6b-122">이 보호 솔루션은 암호화, ID 및 권한 부여 정책을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-122">This protection solution uses encryption, identity, and authorization policies.</span></span> <span data-ttu-id="7aa6b-123">자세한 내용은 Azure Information Protection 문서에서 [Azure 권한 관리란?](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-123">To learn more, see [What is Azure Rights Management?](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms) from the Azure Information Protection documentation.</span></span> 

<span data-ttu-id="7aa6b-124">이 암호화 솔루션을 사용하는 경우 **수퍼 사용자** 기능은 권한있는 사용자 및 서비스에서 조직에 대해 암호화된 데이터를 언제든지 읽고 검사 할 수 있도록 해줍니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-124">When you use this encryption solution, the **super user** feature ensures that authorized people and services can always read and inspect the data that has been encrypted for your organization.</span></span> <span data-ttu-id="7aa6b-125">필요한 경우 암호화를 제거하거나 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-125">If necessary, the encryption can then be removed or changed.</span></span> <span data-ttu-id="7aa6b-126">자세한 내용은 [Azure Information Protection 및 검색 서비스 또는 데이터 복구에 대한 수퍼 사용자 구성](https://docs.microsoft.com/azure/information-protection/configure-super-users)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-126">For more information, see [Configuring super users for Azure Information Protection and discovery services or data recovery](https://docs.microsoft.com/azure/information-protection/configure-super-users).</span></span>

## <a name="how-to-configure-a-label-for-encryption"></a><span data-ttu-id="7aa6b-127">암호화 레이블을 구성하는 방법</span><span class="sxs-lookup"><span data-stu-id="7aa6b-127">How to configure a label for encryption</span></span>

1. <span data-ttu-id="7aa6b-128">일반 지침에 따라 [민감도 레이블을 만들거나 편집](create-sensitivity-labels.md#create-and-configure-sensitivity-labels)하고 반드시 레이블 범위에 대해 **파일 및 전자 메일** 이 선택되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-128">Follow the general instructions to [create or edit a sensitivity label](create-sensitivity-labels.md#create-and-configure-sensitivity-labels) and make sure **Files & emails** is selected for the label's scope:</span></span> 
    
    ![파일 및 전자 메일에 대한 민감도 레이블 범위 옵션](../media/filesandemails-scope-options-sensitivity-label.png)

2. <span data-ttu-id="7aa6b-130">그런 다음 **파일 및 전자 메일에 대한 보호 설정 선택** 페이지에서 반드시 **파일 및 전자 메일 암호화** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-130">Then, on the **Choose protection settings for files and emails** page, make sure you select **Encrypt files and emails**</span></span>
    
    ![파일 및 전자 메일에 대한 민감도 레이블 보호 옵션](../media/protection-options-sensitivity-label.png)

4.  <span data-ttu-id="7aa6b-132">마법사의 **암호화** 페이지에서 다음 옵션 중 하나를 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-132">On the **Encryption** page of the wizard, select one of the following options:</span></span>
    
    - <span data-ttu-id="7aa6b-133">**파일이 암호화 된 경우 암호화 제거**: 이 시나리오에 대한 자세한 내용은 [레이블이 적용되는 경우 기존 암호화에 발생하는 영향](#what-happens-to-existing-encryption-when-a-labels-applied) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-133">**Remove encryption if the file is encrypted**: For more information about this scenario, see the [What happens to existing encryption when a label's applied](#what-happens-to-existing-encryption-when-a-labels-applied) section.</span></span> <span data-ttu-id="7aa6b-134">이 설정을 사용하면 사용자에게 충분한 권한이 없는 경우, 적용하지 못할 수 있는 민감도 레이블이 있다는 것을 이해하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-134">It's important to understand that this setting can result in a sensitivity label that users might not be able to apply when they don't have sufficient permissions.</span></span>
    
    - <span data-ttu-id="7aa6b-135">**암호화 설정 구성**: 암호화를 켜고 암호화 설정을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-135">**Configure encryption settings**: Turns on encryption and makes the encryption settings visible:</span></span>
        
        ![암호화에 대한 민감도 레이블 옵션](../media/encrytion-options-sensitivity-label.png)
        
        <span data-ttu-id="7aa6b-137">해당 설정에 대한 지침은 다음 [암호화 설정 구성](#configure-encryption-settings) 섹션에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-137">Instructions for these settings are in the following [Configure encryption settings](#configure-encryption-settings) section.</span></span>

### <a name="what-happens-to-existing-encryption-when-a-labels-applied"></a><span data-ttu-id="7aa6b-138">레이블이 적용되면 기존 암호화는 어떻게 되나요?</span><span class="sxs-lookup"><span data-stu-id="7aa6b-138">What happens to existing encryption when a label's applied</span></span>

<span data-ttu-id="7aa6b-139">암호화되지 않은 컨텐츠에 민감도 레이블이 적용된 경우 선택할 수 있는 암호화 옵션의 결과는 자명합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-139">If a sensitivity label is applied to unencrypted content, the outcome of the encryption options you can select is self-explanatory.</span></span> <span data-ttu-id="7aa6b-140">예를 들어 **암호화 파일 및 전자 메일** 을 선택하지 않은 경우 콘텐츠는 암호화되지 않은 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-140">For example, if you didn't select **Encrypt files and emails**, the content remains unencrypted.</span></span>

<span data-ttu-id="7aa6b-141">그러나 콘텐츠가 이미 암호화되었을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-141">However, the content might be already encrypted.</span></span> <span data-ttu-id="7aa6b-142">예를 들어 다른 사용자가 다음을 적용했을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-142">For example, another user might have applied:</span></span>

- <span data-ttu-id="7aa6b-143">레이블에 의해 프롬프트될 때 사용자 정의 권한, Azure Information Protection 클라이언트의 사용자 지정 권한 및 Office 앱 내에서 **제한된 액세스** 문서 보호가 포함된 자체 권한</span><span class="sxs-lookup"><span data-stu-id="7aa6b-143">Their own permissions, which include user-defined permissions when prompted by a label, custom permissions by the Azure Information Protection client, and the **Restricted Access** document protection from within an Office app.</span></span>
- <span data-ttu-id="7aa6b-144">레이블과 독립적으로 콘텐츠를 암호화하는 Azure 권한 관리 보호 서식 파일.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-144">An Azure Rights Management protection template that encrypts the content independently from a label.</span></span> <span data-ttu-id="7aa6b-145">이 범주에는 권한 보호를 사용하여 암호화를 적용하는 메일 흐름 규칙이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-145">This category includes mail flow rules that apply encryption by using rights protection.</span></span>
- <span data-ttu-id="7aa6b-146">관리자가 할당한 권한으로 암호화를 적용하는 레이블입니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-146">A label that applies encryption with permissions assigned by the administrator.</span></span>

<span data-ttu-id="7aa6b-147">다음 테이블에서는 민감도 레이블이 해당 콘텐츠에 적용되는 경우 기존 암호화가 어떻게 되는지에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-147">The following table identifies what happens to existing encryption when a sensitivity label is applied to that content:</span></span>

| | <span data-ttu-id="7aa6b-148">암호화: 선택되지 않음</span><span class="sxs-lookup"><span data-stu-id="7aa6b-148">Encryption: Not selected</span></span> | <span data-ttu-id="7aa6b-149">암호화: 구성됨</span><span class="sxs-lookup"><span data-stu-id="7aa6b-149">Encryption: Configured</span></span> | <span data-ttu-id="7aa6b-150">암호화: 제거</span><span class="sxs-lookup"><span data-stu-id="7aa6b-150">Encryption: Remove</span></span> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7aa6b-151">**사용자가 지정하는 사용 권한**</span><span class="sxs-lookup"><span data-stu-id="7aa6b-151">**Permissions specified by a user**</span></span>|<span data-ttu-id="7aa6b-152">원래 암호화가 유지됨</span><span class="sxs-lookup"><span data-stu-id="7aa6b-152">Original encryption is preserved</span></span>|<span data-ttu-id="7aa6b-153">새 레이블 암호화가 적용됨</span><span class="sxs-lookup"><span data-stu-id="7aa6b-153">New label encryption is applied</span></span>|<span data-ttu-id="7aa6b-154">원래 암호화가 제거됨</span><span class="sxs-lookup"><span data-stu-id="7aa6b-154">Original encryption is removed</span></span>|
|<span data-ttu-id="7aa6b-155">**보호 서식 파일**</span><span class="sxs-lookup"><span data-stu-id="7aa6b-155">**Protection template**</span></span>|<span data-ttu-id="7aa6b-156">원래 암호화가 유지됨</span><span class="sxs-lookup"><span data-stu-id="7aa6b-156">Original encryption is preserved</span></span>|<span data-ttu-id="7aa6b-157">새 레이블 암호화가 적용됨</span><span class="sxs-lookup"><span data-stu-id="7aa6b-157">New label encryption is applied</span></span>|<span data-ttu-id="7aa6b-158">원래 암호화가 제거됨</span><span class="sxs-lookup"><span data-stu-id="7aa6b-158">Original encryption is removed</span></span>|
|<span data-ttu-id="7aa6b-159">**관리자 정의 권한이 있는 레이블**</span><span class="sxs-lookup"><span data-stu-id="7aa6b-159">**Label with administator-defined permissions**</span></span>|<span data-ttu-id="7aa6b-160">원래 암호화가 제거됨</span><span class="sxs-lookup"><span data-stu-id="7aa6b-160">Original encryption is removed</span></span>|<span data-ttu-id="7aa6b-161">새 레이블 암호화가 적용됨</span><span class="sxs-lookup"><span data-stu-id="7aa6b-161">New label encryption is applied</span></span>|<span data-ttu-id="7aa6b-162">원래 암호화가 제거됨</span><span class="sxs-lookup"><span data-stu-id="7aa6b-162">Original encryption is removed</span></span>|

<span data-ttu-id="7aa6b-163">새 레이블 암호화가 적용되거나 원래 암호화가 제거된 경우, 레이블을 적용하는 사용자에게 이 작업을 지원하는 사용 권한 또는 역할이 있는 경우에만 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-163">Note that in the cases where the new label encryption is applied or the original encryption is removed, this happens only if the user applying the label has a usage right or role that supports this action:</span></span>

- <span data-ttu-id="7aa6b-164">[사용 권한](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions) 내보내기 또는 모든 권한.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-164">The [usage right](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions) Export or Full Control.</span></span>
- <span data-ttu-id="7aa6b-165">[권한 관리 발급자 또는 권한 관리 소유자](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#rights-management-issuer-and-rights-management-owner) 또는 [수퍼 사용자](https://docs.microsoft.com/azure/information-protection/configure-super-users)의 역할</span><span class="sxs-lookup"><span data-stu-id="7aa6b-165">The role of [Rights Management issuer or Rights Management owner](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#rights-management-issuer-and-rights-management-owner), or [super user](https://docs.microsoft.com/azure/information-protection/configure-super-users).</span></span>

<span data-ttu-id="7aa6b-166">사용자에게 이러한 권한이나 역할이 없는 경우에는 레이블을 적용할 수 없으므로 원래 암호화가 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-166">If the user doesn't have one of these rights or roles, the label can't be applied and so the original encryption is preserved.</span></span> <span data-ttu-id="7aa6b-167">사용자에게 다음 메시지가 표시됩니다. **민감도 레이블을 변경할 권한이 없습니다. 콘텐츠 소유자에게 문의하세요.**</span><span class="sxs-lookup"><span data-stu-id="7aa6b-167">The user sees the following message: **You don't have permission to make this change to the sensitivity label. Please contact the content owner.**</span></span>

<span data-ttu-id="7aa6b-168">예를 들어 전자 메일 메시지에 전달 안 함을 적용한 사람은 전자 메일의 권한 관리 소유자이므로 스레드의 레이블을 다시 지정하여 암호화를 대체하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-168">For example, the person who applies Do Not Forward to an email message can relabel the thread to replace the encryption or remove it, because they are the Rights Management owner for the email.</span></span> <span data-ttu-id="7aa6b-169">그러나 수퍼 사용자를 제외하고 이 전자 메일 수신자는 요구되는 사용 권한이 없기 때문에 레이블을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-169">But with the exception of super users, recipients of this email can't relabel it because they don't have the required usage rights.</span></span>

#### <a name="email-attachments-for-encrypted-email-messages"></a><span data-ttu-id="7aa6b-170">암호화된 전자 메일 메시지에 대한 전자 메일 첨부 파일</span><span class="sxs-lookup"><span data-stu-id="7aa6b-170">Email attachments for encrypted email messages</span></span>

<span data-ttu-id="7aa6b-171">어떤 방법으로든 전자 메일 메시지를 암호화하면 전자 메일에 첨부된 암호화되지 않은 Office 문서는 자동으로 동일한 암호화 설정을 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-171">When an email message is encrypted by any method, any unencrypted Office documents that are attached to the email automatically inherit the same encryption settings.</span></span>

<span data-ttu-id="7aa6b-172">이미 암호화된 후 첨부 파일로 추가된 문서는 항상 원래 암호화를 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-172">Documents that are already encrypted and then added as attachments always preserve their original encryption.</span></span>

## <a name="configure-encryption-settings"></a><span data-ttu-id="7aa6b-173">암호화 설정 구성</span><span class="sxs-lookup"><span data-stu-id="7aa6b-173">Configure encryption settings</span></span>

<span data-ttu-id="7aa6b-174">민감도 레이블을 만들거나 편집하기 위해 마법사의 **암호화** 페이지에서 **암호화 설정 구성** 을 선택하는 경우, 다음 옵션 중 하나를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-174">When you select **Configure encryption settings** on the **Encryption** page of the wizard to create or edit a sensitivity label, choose one of the following options:</span></span>

- <span data-ttu-id="7aa6b-175">레이블을 적용한 콘텐츠에 대해 어떤 사용자에게 어떤 권한을 부여할 것인지 정확하게 결정할 수 있도록 **지금 권한을 할당** 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-175">**Assign permissions now**, so that you can determine exactly which users get which permissions to content that has the label applied.</span></span> <span data-ttu-id="7aa6b-176">자세한 내용은 다음 섹션 [지금 권한 할당](#assign-permissions-now)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-176">For more information, see the next section [Assign permissions now](#assign-permissions-now).</span></span>
- <span data-ttu-id="7aa6b-177">사용자가 콘텐츠에 레이블을 적용하는 경우 **사용자가 권한을 할당하도록 허용** 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-177">**Let users assign permissions** when your users apply the label to content.</span></span> <span data-ttu-id="7aa6b-178">이 옵션을 사용하면 조직의 사용자가 공동 작업과 작업 수행을 유연하게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-178">With this option, you can allow people in your organization some flexibility that they might need to collaborate and get their work done.</span></span> <span data-ttu-id="7aa6b-179">자세한 내용은이 페이지에서 [권한을 할당할 수 있도록 허용](#let-users-assign-permissions) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-179">For more information, see the [Let users assign permissions](#let-users-assign-permissions) section on this page.</span></span>

<span data-ttu-id="7aa6b-180">예를 들어, 가장 중요한 콘텐츠에 적용되는 **극비** 라는 민감도 레이블을 사용하는 경우 해당 콘텐츠의 사용 권한 유형을 받을 사용자를 결정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-180">For example, if you have a sensitivity label named **Highly Confidential** that will be applied to your most sensitive content, you might want to decide now who gets what type of permissions to that content.</span></span>

<span data-ttu-id="7aa6b-181">또는 **비즈니스 계약서** 라는 민감도 레이블을 사용하고, 사용자 조직의 워크플로에 따라 사용자가 임시로 다른 사용자와 이 콘텐츠에 대해 공동 작업해야 하는 경우, 사용자가 레이블을 지정할 때 권한을 받을 사용자를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-181">Alternatively, if you have a sensitivity label named **Business Contracts**, and your organization's workflow requires that your people collaborate on this content with different people on an ad hoc basis, you might want to allow your users to decide who gets permissions when they assign the label.</span></span> <span data-ttu-id="7aa6b-182">이와 같은 유연성을 갖추어 사용자의 생산성은 향상되고 관리자가 특정 시나리오를 해결하기 위해 새 민감도 레이블을 업데이트하거나 만들어야 하는 요청은 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-182">This flexibility both helps your users' productivity and reduces the requests for your admins to update or create new sensitivity labels to address specific scenarios.</span></span>

<span data-ttu-id="7aa6b-183">지금 권한을 할당할지 사용자가 권한을 할당하도록 허용할지 선택:</span><span class="sxs-lookup"><span data-stu-id="7aa6b-183">Choosing whether to assign permissions now or let users assign permissions:</span></span>

![사용자 또는 관리자가 정의한 권한 추가 옵션](../media/sensitivity-label-user-or-admin-defined-permissions.png)

## <a name="assign-permissions-now"></a><span data-ttu-id="7aa6b-185">지금 권한 할당</span><span class="sxs-lookup"><span data-stu-id="7aa6b-185">Assign permissions now</span></span>

<span data-ttu-id="7aa6b-186">다음 옵션을 사용하여 이 레이블이 적용되는 전자 메일 또는 문서에 액세스할 수 있는 사용자를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-186">Use the following options to control who can access email or documents to which this label is applied.</span></span> <span data-ttu-id="7aa6b-187">다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-187">You can:</span></span>

- <span data-ttu-id="7aa6b-p115">특정 날짜 또는 레이블을 지정한 후 특정 일수가 지나면 **레이블을 지정한 콘텐츠에 대한 액세스가 만료** 되도록 합니다. 이 기간 이후 사용자는 레이블을 지정한 항목을 열 수 없습니다. 날짜를 지정하는 경우 표준 시간대의 해당 날짜 자정에 적용됩니다. 일부 전자 메일 클라이언트의 경우 캐싱 메커니즘으로 인해 만료 기능이 적용되지 않을 수 있으며 만료 날짜가 지난 전자 메일이 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-p115">**Allow access to labeled content to expire**, either on a specific date or after a specific number of days after the label is applied. After this time, users won't be able to open the labeled item. If you specify a date, it is effective midnight on that date in your current time zone. (Note that some email clients might not enforce expiration and show emails past their expiration date, due to their caching mechanisms.)</span></span>

- <span data-ttu-id="7aa6b-p116">**오프라인 액세스 허용** 을 허용 안 함, 항상 허용 또는 레이블을 적용한 후 특정 일수 동안 허용합니다. 오프라인 액세스를 허용 안 함 또는 며칠로 제한하는 경우 임계값에 도달하면 사용자를 다시 인증해야 하고 액세스 권한이 기록됩니다. 자세한 내용은 권한 관리 사용 라이선스에 대한 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-p116">**Allow offline access** never, always, or for a specific number of days after the label is applied. If you restrict offline access to never or a number of days, when that threshold is reached, users must be reauthenticated and their access is logged. For more information, see the next section on the Rights Management use license.</span></span>

<span data-ttu-id="7aa6b-195">암호화된 콘텐츠의 액세스 제어 설정:</span><span class="sxs-lookup"><span data-stu-id="7aa6b-195">Settings for access control for encrypted content:</span></span>

![관리자가 정의한 권한에 대한 설정](../media/sensitivity-encryption-settings-for-admin-defined-permissions.png)

### <a name="rights-management-use-license-for-offline-access"></a><span data-ttu-id="7aa6b-197">오프라인 액세스에 대한 권한 관리 사용 라이선스</span><span class="sxs-lookup"><span data-stu-id="7aa6b-197">Rights Management use license for offline access</span></span>

<span data-ttu-id="7aa6b-198">사용자가 Azure 권한 관리 서비스의 암호화로 보호된 문서 또는 전자 메일을 열면 해당 콘텐츠에 대한 Azure 권한 관리 사용 라이선스가 사용자에게 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-198">When a user opens a document or email that's been protected by encryption from the Azure Rights Management service, an Azure Rights Management use license for that content is granted to the user.</span></span> <span data-ttu-id="7aa6b-199">이 사용 라이선스는 문서 또는 전자 메일에 대한 사용자의 사용 권한 및 콘텐츠를 암호화하는 데 사용된 암호화 키를 포함하는 인증서입니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-199">This use license is a certificate that contains the user's usage rights for the document or email, and the encryption key that was used to encrypt the content.</span></span> <span data-ttu-id="7aa6b-200">사용 라이센스는 만료 날짜(설정된 경우)와 사용 라이선스 유효 기간도 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-200">The use license also contains an expiration date if this has been set, and how long the use license is valid.</span></span>

<span data-ttu-id="7aa6b-p118">만료 날짜가 설정된 경우 테넌트에 대한 기본 사용 라이선스의 유효 기간은 30일입니다. 사용 라이센스 동안 콘텐츠에 대해 다시 인증받지 않습니다. 이 프로세스를 통해 인터넷에 연결하지 않고도 보호된 문서 또는 전자 메일을 계속 열 수 있습니다. 사용 라이선스 유효 기간이 만료되면 다음에 사용자가 보호된 문서 또는 전자 메일에 액세스할 때 다시 인증받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-p118">If no expiration date has been set, the default use license validity period for a tenant is 30 days. For the duration of the use license, the user is not reauthenticated or reauthorized for the content. This process lets the user continue to open the protected document or email without an internet connection. When the use license validity period expires, the next time the user accesses the protected document or email, the user must be reauthenticated and reauthorized.</span></span>

<span data-ttu-id="7aa6b-205">재인증 외에도 정책 및 사용자 그룹 구성원 자격이 다시 평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-205">In addition to reauthentication, the encryption settings and user group membership is reevaluated.</span></span> <span data-ttu-id="7aa6b-206">즉, 사용자가 마지막으로 콘텐츠에 액세스한 시점에서 암호화 설정이나 그룹 구성원에 변경된 사항이 있는 경우 사용자에게 동일한 문서 또는 전자 메일에 대해 다른 액세스 결과를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-206">This means that users could experience different access results for the same document or email if there are changes in the encryption settings or group membership from when they last accessed the content.</span></span>

<span data-ttu-id="7aa6b-207">기본값 30일 설정을 변경하는 방법을 알아보려면 [권한 관리 사용 라이선스](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#rights-management-use-license)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-207">To learn how to change the default 30-day setting, see [Rights Management use license](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#rights-management-use-license).</span></span>

### <a name="assign-permissions-to-specific-users-or-groups"></a><span data-ttu-id="7aa6b-208">특정 사용자 또는 그룹에 사용 권한 할당</span><span class="sxs-lookup"><span data-stu-id="7aa6b-208">Assign permissions to specific users or groups</span></span>

<span data-ttu-id="7aa6b-209">특정 사용자만 레이블이 지정된 콘텐츠와 상호 작용할 수 있도록 다음과 같이 사용 권한을 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-209">You can grant permissions to specific people so that only they can interact with the labeled content:</span></span>

1. <span data-ttu-id="7aa6b-210">먼저 사용 권한을 할당할 사용자 또는 그룹을 레이블이 지정된 콘텐츠에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-210">First, add users or groups that will be assigned permissions to the labeled content.</span></span>

2. <span data-ttu-id="7aa6b-211">그런 다음 레이블이 지정된 컨텐츠에 대해 해당 사용자에게 어떤 권한이 있는지 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-211">Then, choose which permissions those users should have for the labeled content.</span></span>

<span data-ttu-id="7aa6b-212">사용 권한 할당:</span><span class="sxs-lookup"><span data-stu-id="7aa6b-212">Assigning permissions:</span></span>

![사용자에게 사용 권한을 할당하는 옵션](../media/Sensitivity-Assign-permissions-settings.png)

#### <a name="add-users-or-groups"></a><span data-ttu-id="7aa6b-214">사용자 또는 그룹 추가</span><span class="sxs-lookup"><span data-stu-id="7aa6b-214">Add users or groups</span></span>

<span data-ttu-id="7aa6b-215">권한을 할당할 때 다음을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-215">When you assign permissions, you can choose:</span></span>

- <span data-ttu-id="7aa6b-p120">조직의 모든 사용자(모든 테넌트 구성원). 이 설정에서는 게스트 계정이 제외됩니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-p120">Everyone in your organization (all tenant members). This setting excludes guest accounts.</span></span>

- <span data-ttu-id="7aa6b-218">인증된 모든 사용자.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-218">Any authenticated users.</span></span> <span data-ttu-id="7aa6b-219">이 설정을 선택하기 전에 이 설정의 [요구 사항과 제한 사항](#requirements-and-limitations-for-add-any-authenticated-users)을 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-219">Make sure you understand the [requirements and limitations](#requirements-and-limitations-for-add-any-authenticated-users) of this setting before selecting it.</span></span>

- <span data-ttu-id="7aa6b-220">모든 특정 사용자 또는 전자 메일 사용이 가능한 보안 그룹, 분배 그룹 또는 Azure AD의 Microsoft 365 그룹([이전 Office 365 그룹](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)).</span><span class="sxs-lookup"><span data-stu-id="7aa6b-220">Any specific user or email-enabled security group, distribution group, or Microsoft 365 group ([formerly Office 365 group](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) in Azure AD.</span></span> <span data-ttu-id="7aa6b-221">Microsoft 365 그룹에는 정적 또는 [동적 구성원](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-221">The Microsoft 365 group can have static or [dynamic membership](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule).</span></span> <span data-ttu-id="7aa6b-222">이 그룹 유형은 Azure AD와 동기화되지 않으며 전자 메일을 사용할 수없는 보안 그룹을 사용할 수 없으므로 [Exchange에서 동적 메일 그룹](https://docs.microsoft.com/Exchange/recipients/dynamic-distribution-groups/dynamic-distribution-groups)을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-222">Note that you can't use a [dynamic distribution group from Exchange](https://docs.microsoft.com/Exchange/recipients/dynamic-distribution-groups/dynamic-distribution-groups) because this group type isn't synchronized to Azure AD, and you can't use a security group that isn't email-enabled.</span></span>

- <span data-ttu-id="7aa6b-223">모든 전자 메일 주소 또는 도메인.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-223">Any email address or domain.</span></span> <span data-ttu-id="7aa6b-224">해당 조직에서 도메인 이름을 입력하여 Azure AD를 사용하는 다른 조직의 모든 사용자를 지정하려면 이 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-224">Use this option to specify all users in another organization who uses Azure AD, by entering any domain name from that organization.</span></span> <span data-ttu-id="7aa6b-225">소셜 공급자의 도메인 이름(예: **gmail.com**, **hotmail.com** 또는 **outlook.com**)을 입력하여 소셜 공급자에 이 옵션을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-225">You can also use this option for social providers, by entering their domain name such as **gmail.com**, **hotmail.com**, or **outlook.com**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7aa6b-226">Azure AD를 사용하는 조직에서 도메인을 지정할 경우 해당 특정 도메인에 대한 액세스를 제한할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-226">If you specify a domain from an organization that uses Azure AD, you can't restrict access to that specific domain.</span></span> <span data-ttu-id="7aa6b-227">대신에 Azure AD에서 확인된 모든 도메인은 사용자가 지정한 도메인 이름을 소유하는 테넌트에 자동으로 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-227">Instead, all verified domains in Azure AD are automatically included for the tenant that owns the domain name you specify.</span></span>

<span data-ttu-id="7aa6b-228">조직 혹은 브라우저 디렉토리에 모든 사용자 및 그룹을 선택하면 사용자 혹은 그룹에 전자 메일 주소가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-228">When you choose all users and groups in your organization or browse the directory, the users or groups must have an email address.</span></span>

<span data-ttu-id="7aa6b-p125">모범 사례로 사용자 대신 그룹을 사용할 수 있습니다. 이 전략으로 더 간단하게 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-p125">As a best practice, use groups rather than users. This strategy keeps your configuration simpler.</span></span>

##### <a name="requirements-and-limitations-for-add-any-authenticated-users"></a><span data-ttu-id="7aa6b-231">“인증된 사용자 추가”에 대한 요구 사항 및 제한 사항</span><span class="sxs-lookup"><span data-stu-id="7aa6b-231">Requirements and limitations for "Add any authenticated users"</span></span>

<span data-ttu-id="7aa6b-232">이 설정은 레이블이 암호화하는 컨텐츠에 액세스할 수 있는 사람을 제한하지 않고 컨텐츠를 계속 암호화하고 컨텐츠 사용 방법(권한) 및 액세스 방법(만료 및 오프라인 액세스)을 제한하는 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-232">This setting doesn't restrict who can access the content that the label encrypts, while still encrypting the content and providing you with options to restrict how the content can be used (permissions), and accessed (expiry and offline access).</span></span> <span data-ttu-id="7aa6b-233">그러나 암호화된 콘텐츠를 여는 응용 프로그램은 사용되는 인증을 지원할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-233">However, the application opening the encrypted content must be able to support the authentication being used.</span></span> <span data-ttu-id="7aa6b-234">이러한 이유로 Google과 같은 페더레이션된 소셜 공급자 및 일회용 암호 인증은 Exchange Online을 사용할 때에 한해 전자 메일에 대해서만 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-234">For this reason, federated social providers such as Google, and onetime passcode authentication work for email only, and only when you use Exchange Online.</span></span> <span data-ttu-id="7aa6b-235">Microsoft 계정은 Office 365 앱 및 [Azure Information Protection 뷰어](https://portal.azurerms.com/#/download)와 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-235">Microsoft accounts can be used with Office 365 apps and the [Azure Information Protection viewer](https://portal.azurerms.com/#/download).</span></span>

> [!NOTE]
> <span data-ttu-id="7aa6b-236">[SharePoint 및 OneDrive Office 파일에 대해 민감도 레이블을 사용](sensitivity-labels-sharepoint-onedrive-files.md)하는 경우 [Azure AD B2B와 SharePoint 및 OneDrive 통합](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)으로 이 설정을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-236">Consider using this setting with [SharePoint and OneDrive integration with Azure AD B2B](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview) when sensitivity labels are [enabled for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

<span data-ttu-id="7aa6b-237">인증된 사용자 설정에 대한 일반적인 시나리오는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-237">Some typical scenarios for any authenticated users setting:</span></span>

- <span data-ttu-id="7aa6b-238">누가 컨텐츠를 보는지는 신경 쓰지 않지만 컨텐츠 사용 방법을 제한하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-238">You don't mind who views the content, but you want to restrict how it is used.</span></span> <span data-ttu-id="7aa6b-239">예를 들어 내용의 편집, 복사 또는 인쇄를 원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-239">For example, you don't want the content to be edited, copied, or printed.</span></span>
- <span data-ttu-id="7aa6b-240">컨텐츠에 액세스하는 사람을 제한할 필요는 없지만 누가 컨텐츠를 여는지 확인하고 싶을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-240">You don't need to restrict who accesses the content, but you want to be able to confirm who opens it.</span></span>
- <span data-ttu-id="7aa6b-241">콘텐츠는 저장 및 전송시 암호화되어야 하지만 액세스 제어는 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-241">You have a requirement that the content must be encrypted at rest and in transit, but it doesn't require access controls.</span></span>

#### <a name="choose-permissions"></a><span data-ttu-id="7aa6b-242">사용 권한 선택</span><span class="sxs-lookup"><span data-stu-id="7aa6b-242">Choose permissions</span></span>

<span data-ttu-id="7aa6b-243">해당 사용자 또는 그룹에 허용할 사용 권한을 선택하면 다음 중 하나를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-243">When you choose which permissions to allow for those users or groups, you can select either:</span></span>

- <span data-ttu-id="7aa6b-244">미리 설정된 권한 그룹(예: 공동 작성 또는 검토자)이 있는 [미리 정의된 권한 수준](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#rights-included-in-permissions-levels).</span><span class="sxs-lookup"><span data-stu-id="7aa6b-244">A [predefined permissions level](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#rights-included-in-permissions-levels) with a preset group of rights, such as Co-Author or Reviewer.</span></span>
- <span data-ttu-id="7aa6b-245">하나 이상의 사용 권한을 선택하는 경우 권한 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="7aa6b-245">Custom permissions, where you choose one or more usage rights.</span></span>

<span data-ttu-id="7aa6b-246">적절한 사용 권한을 선택하는 데 도움이 되는 자세한 내용은 [사용 권한 및 설명](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-246">For more information to help you select the appropriate permissions, see [Usage rights and descriptions](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions).</span></span>  

![미리 설정된 옵션 또는 사용자 지정 사용 권한](../media/Sensitivity-Choose-permissions-settings.png)

<span data-ttu-id="7aa6b-p128">동일한 레이블로 다른 사용자에게 다른 권한을 부여할 수 있습니다. 예를 들어 아래에 있는 스크린샷과 같이 단일 레이블에서 일부 사용자를 검토자로 할당하고 다른 사용자를 공동 작성자로 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-p128">Note that the same label can grant different permissions to different users. For example, a single label can assign some users as Reviewer and a different user as Co-author, as shown in the following screenshot.</span></span>

<span data-ttu-id="7aa6b-p129">이를 위해서는 사용자 또는 그룹을 추가하고 사용 권한을 할당하고 해당 설정을 저장합니다. 그런 다음 매번 이 단계를 반복하여 사용자를 추가하고 권한을 할당하고 설정을 저장합니다. 이 구성을 필요한 만큼 수행하여 여러 사용자에게 서로 다른 권한을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-p129">To do this, add users or groups, assign them permissions, and save those settings. Then repeat these steps, adding users and assigning them permissions, saving the settings each time. You can repeat this configuration as often as necessary, to define different permissions for different users.</span></span>

![다른 사용 권한을 가진 다른 사용자](../media/Sensitivity-Multiple-users-permissions.png)

#### <a name="rights-management-issuer-user-applying-the-sensitivity-label-always-has-full-control"></a><span data-ttu-id="7aa6b-254">권한 관리 발급자(민감도 레이블을 적용한 사용자)는 항상 모든 권한을 갖습니다</span><span class="sxs-lookup"><span data-stu-id="7aa6b-254">Rights Management issuer (user applying the sensitivity label) always has Full Control</span></span>

<span data-ttu-id="7aa6b-255">민감도 레이블의 암호화는 Azure Information Protection의 Azure 권한 관리 서비스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-255">Encryption for a sensitivity label uses the Azure Rights Management service from Azure Information Protection.</span></span> <span data-ttu-id="7aa6b-256">사용자가 암호화를 사용하여 문서 또는 전자 메일을 보호하기 위해 중요도 레이블을 적용하면 해당 사용자는 해당 내용에 대한 권한 관리 발급자가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-256">When a user applies a sensitivity label to protect a document or email by using encryption, that user becomes the Rights Management issuer for that content.</span></span>

<span data-ttu-id="7aa6b-257">권한 관리 발급자는 문서 또는 전자 메일에 대한 모든 권한을 항상 부여받으며, 또한 다음과 같은 권한을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-257">The Rights Management issuer is always granted Full Control permissions for the document or email, and in addition:</span></span>

- <span data-ttu-id="7aa6b-258">암호화 설정에 만료 날짜가 포함된 경우 권한 관리 발급자는 해당 날짜 이후에도 여전히 문서 또는 전자 메일을 열고 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-258">If the encryption settings include an expiration date, the Rights Management issuer can still open and edit the document or email after that date.</span></span>
- <span data-ttu-id="7aa6b-259">권한 관리 발급자는 문서 또는 전자 메일을 언제든지 오프라인으로 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-259">The Rights Management issuer can always access the document or email offline.</span></span>
- <span data-ttu-id="7aa6b-260">권한 관리 발급자는 권한이 해지된 후에도 문서를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-260">The Rights Management issuer can still open a document after it is revoked.</span></span>

<span data-ttu-id="7aa6b-261">자세한 내용은 [권한 관리 발급자 및 권한 관리 소유자](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#rights-management-issuer-and-rights-management-owner)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-261">For more information, see [Rights Management issuer and Rights Management owner](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#rights-management-issuer-and-rights-management-owner).</span></span>

### <a name="double-key-encryption"></a><span data-ttu-id="7aa6b-262">이중 키 암호화</span><span class="sxs-lookup"><span data-stu-id="7aa6b-262">Double Key Encryption</span></span>

> [!NOTE]
> <span data-ttu-id="7aa6b-263">이 기능은 현재 Azure Information Protection 통합 라벨링 클라이언트에서만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-263">This feature is currently supported only by the Azure Information Protection unified labeling client.</span></span>

<span data-ttu-id="7aa6b-264">이중 키 암호화 서비스를 구성한 후 이 레이블이 적용되는 파일에 대해 해당 이중 키 암호화를 사용해야 하는 경우에만 이 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-264">Select this option only after you have configured the Double Key Encryption service and you need to use this double key encryption for files that will have this label applied.</span></span>

<span data-ttu-id="7aa6b-265">자세한 내용, 전제 조건 및 구성 지침을 보려면 [DKE(Double Key Encryption)를](double-key-encryption.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-265">For more information, prerequisites, and configuration instructions, see [Double Key Encryption (DKE)](double-key-encryption.md).</span></span>

## <a name="let-users-assign-permissions"></a><span data-ttu-id="7aa6b-266">사용자가 권한을 할당하도록 허용</span><span class="sxs-lookup"><span data-stu-id="7aa6b-266">Let users assign permissions</span></span>

<span data-ttu-id="7aa6b-267">다음 옵션을 사용하여 사용자가 민감도 레이블을 콘텐츠에 수동으로 추가할 때 사용자가 권한을 할당하도록 허용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-267">You can use these options to let users assign permissions when they manually apply a sensitivity label to content:</span></span>

- <span data-ttu-id="7aa6b-268">Outlook의 경우 사용자는 선택된 수신자에 대해 [전달 안 함](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#do-not-forward-option-for-emails) 옵션에 해당하는 제한을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-268">In Outlook, a user can select restrictions equivalent to the [Do Not Forward](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#do-not-forward-option-for-emails) option for their chosen recipients.</span></span>

- <span data-ttu-id="7aa6b-269">Word, PowerPoint 및 Excel의 경우 사용자에게 특정 사용자, 그룹 또는 조직에 대한 고유 권한을 선택하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-269">In Word, PowerPoint, and Excel, a user is prompted to select their own permissions for specific users, groups, or organizations.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7aa6b-270">Word, PowerPoint 및 Excel에 대한 이 옵션은 Azure Information Protection 통합 레이블 클라이언트에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-270">This option for Word, PowerPoint, and Excel is supported by the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="7aa6b-271">기본 제공 되는 레이블을 사용하는 앱의 경우에는 [어떤 앱이 지원하는지 확인하세요](sensitivity-labels-office-apps.md#sensitivity-label-capabilities-in-word-excel-and-powerpoint).</span><span class="sxs-lookup"><span data-stu-id="7aa6b-271">For apps that use built-in labeling, [check which apps support it](sensitivity-labels-office-apps.md#sensitivity-label-capabilities-in-word-excel-and-powerpoint).</span></span>
    >
    > <span data-ttu-id="7aa6b-272">이 옵션이 선택되었지만 사용자의 앱에서 지원되지 않는 경우, 해당 레이블은 사용자에게 표시되지 않거나 레이블이 일관성을 위해 표시되지만 설명 메시지와 함께 적용될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-272">If this option is selected but isn't supported for a user's app, either that label doesn't display to the user, or the label displays for consistency, but it can't be applied with an explanation message to users.</span></span>

<span data-ttu-id="7aa6b-273">옵션이 지원되면 다음 표를 사용하여 사용자에게 민감도 레이블이 표시되는 시기를 식별하세요.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-273">When the options are supported, use the following table to identify when users see the sensitivity label:</span></span>

|<span data-ttu-id="7aa6b-274">설정</span><span class="sxs-lookup"><span data-stu-id="7aa6b-274">Setting</span></span> |<span data-ttu-id="7aa6b-275">Outlook에 표시되는 레이블</span><span class="sxs-lookup"><span data-stu-id="7aa6b-275">Label visible in Outlook</span></span>|<span data-ttu-id="7aa6b-276">Word, Excel, PowerPoint에서 표시되는 레이블</span><span class="sxs-lookup"><span data-stu-id="7aa6b-276">Label visible in Word, Excel, PowerPoint</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7aa6b-277">**Outlook에서 전달 안 함 옵션에 해당하는 제한 사항을 적용합니다.**</span><span class="sxs-lookup"><span data-stu-id="7aa6b-277">**In Outlook, enforce restrictions equivalent to the Do Not Forward option**</span></span>|<span data-ttu-id="7aa6b-278">예</span><span class="sxs-lookup"><span data-stu-id="7aa6b-278">Yes</span></span> |<span data-ttu-id="7aa6b-279">아니요</span><span class="sxs-lookup"><span data-stu-id="7aa6b-279">No</span></span> |
|<span data-ttu-id="7aa6b-280">**Word, PowerPoint 및 Excel에서 사용자에게 사용 권한을 지정하라는 메시지가 표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="7aa6b-280">**In Word, PowerPoint, and Excel, prompt users to specify permissions**</span></span>|<span data-ttu-id="7aa6b-281">아니요</span><span class="sxs-lookup"><span data-stu-id="7aa6b-281">No</span></span> |<span data-ttu-id="7aa6b-282">예</span><span class="sxs-lookup"><span data-stu-id="7aa6b-282">Yes</span></span>|

<span data-ttu-id="7aa6b-283">두 설정을 모두 선택하면 레이블은 Outlook과 Word, Excel 및 PowerPoint 모두에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-283">When both settings are selected, the label is therefore visible in both Outlook and in Word, Excel, and PowerPoint.</span></span>

<span data-ttu-id="7aa6b-284">사용자가 권한을 할당할 수 있도록 허용하는 민감도 레이블은 사용자가 수동으로만 콘텐츠에 적용할 수 있으므로, 이를 추천 레이블로 자동 적용 또는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-284">A sensitivity label that lets users assign permissions can be applied to content only manually by users; it can't be auto-applied or used as a recommended label.</span></span>

<span data-ttu-id="7aa6b-285">사용자 할당 권한 구성:</span><span class="sxs-lookup"><span data-stu-id="7aa6b-285">Configuring the user-assigned permissions:</span></span>

![사용자 정의 권한에 대한 암호화 설정](../media/sensitivity-encryption-settings-for-user-defined-permissions.png)

### <a name="outlook-restrictions"></a><span data-ttu-id="7aa6b-287">Outlook 제한 사항</span><span class="sxs-lookup"><span data-stu-id="7aa6b-287">Outlook restrictions</span></span>

<span data-ttu-id="7aa6b-288">Outlook에서, 사용자가 메시지에 권한을 할당하도록 허용하는 민감도 레이블을 적용하는 경우 이 제한 사항은 전달 금지 옵션과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-288">In Outlook, when a user applies a sensitivity label that lets them assign permissions to a message, the restrictions are the same as the Do Not Forward option.</span></span> <span data-ttu-id="7aa6b-289">사용자에게 메시지 맨 위에 레이블 이름과 설명이 표시됩니다. 이는 콘텐츠가 보호되고 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-289">The user will see the label name and description at the top of the message, which indicates the content's being protected.</span></span> <span data-ttu-id="7aa6b-290">Word, PowerPoint 및 Excel([다음 섹션](#word-powerpoint-and-excel-permissions) 참조)과 달리, 사용자에게 특정 권한을 선택 하라는 메시지가 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-290">Unlike Word, PowerPoint, and Excel (see the [next section](#word-powerpoint-and-excel-permissions)), users aren't prompted to select specific permissions.</span></span>

![Outlook의 메시지에 적용된 민감도 레이블](../media/sensitivity-label-outlook-protection-applied.png)

<span data-ttu-id="7aa6b-292">전달 금지 옵션이 전자 메일에 적용되는 경우, 전자 메일이 암호화되므로 받는 사람을 인증해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-292">When the Do Not Forward option is applied to an email, the email is encrypted and recipients must be authenticated.</span></span> <span data-ttu-id="7aa6b-293">그런 다음, 받는 사람이 이를 전달하거나, 인쇄하거나, 복사할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-293">Then, the recipients cannot forward it, print it, or copy from it.</span></span> <span data-ttu-id="7aa6b-294">예를 들어, Outlook 클라이언트에서 전달 단추를 사용할 수 없고, 다른 이름으로 저장 및 인쇄 메뉴 옵션도 사용할 수 없으며, 받는 사람, 참조 또는 숨은 참조 상자에서 받는 사람을 추가하거나 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-294">For example, in the Outlook client, the Forward button is not available, the Save As and Print menu options are not available, and you cannot add or change recipients in the To, Cc, or Bcc boxes.</span></span>

<span data-ttu-id="7aa6b-295">전자 메일에 첨부된 암호화되지 않은 Office 문서는 자동으로 동일한 제한 사항을 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-295">Unencrypted Office documents that are attached to the email automatically inherit the same restrictions.</span></span> <span data-ttu-id="7aa6b-296">이 문서에 적용되는 사용 권한은 콘텐츠 편집, 편집, 저장, 보기, 열기, 읽기, 모든 매크로입니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-296">The usage rights applied to these documents are Edit Content, Edit; Save; View, Open, Read; and Allow Macros.</span></span> <span data-ttu-id="7aa6b-297">사용자가 첨부 파일에 대해 다른 권한을 요구하는 경우 또는 첨부 파일이 상속된 보호를 지원하는 Office 문서가 아닌 경우, 사용자가 파일을 전자 메일에 첨부하기 전에 파일을 보호해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-297">If the user wants different usage rights for an attachment, or the attachment is not an Office document that supports this inherited protection, the user needs to protect the file before attaching it to the email.</span></span>

### <a name="word-powerpoint-and-excel-permissions"></a><span data-ttu-id="7aa6b-298">Word, PowerPoint 및 Excel 권한</span><span class="sxs-lookup"><span data-stu-id="7aa6b-298">Word, PowerPoint, and Excel permissions</span></span>

<span data-ttu-id="7aa6b-299">Word, PowerPoint 및 Excel에서 사용자가 문서에 사용 권한을 할당할 수 있는 민감도 레이블을 적용하면 암호화 적용시 사용자와 사용 권한을 선택하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-299">In Word, PowerPoint, and Excel, when a user applies a sensitivity label that lets them assign permissions to a document, they are prompted to specify their choice of users and permissions when the encryption is applied.</span></span>

<span data-ttu-id="7aa6b-300">예를 들어 Azure Information Protection 통합 레이블 클라이언트를 사용하면 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-300">For example, with the Azure Information Protection unified labeling client, users can:</span></span>

- <span data-ttu-id="7aa6b-301">뷰어(보기 전용 권한 할당) 또는 공동 작성자(보기, 편집, 복사 및 인쇄 권한 할당)와 같은 권한 수준을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-301">Select a permission level, such as Viewer (which assigns View Only permission) or Co-Author (which assigns View, Edit, Copy, and Print permissions).</span></span>
- <span data-ttu-id="7aa6b-302">사용자, 그룹 또는 조직을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-302">Select users, groups, or organizations.</span></span> <span data-ttu-id="7aa6b-303">여기에는 조직의 내부 또는 외부 사용자가 모두 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-303">This can include people both inside or outside your organizations.</span></span>
- <span data-ttu-id="7aa6b-304">선택한 사용자가 콘텐츠에 액세스할 수 없는 만료 날짜를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-304">Set an expiration date, after which the selected users cannot access the content.</span></span> <span data-ttu-id="7aa6b-305">자세한 내용은 위에 있는 섹션 [오프라인 액세스용 권한 관리 사용자 라이선스](#rights-management-use-license-for-offline-access)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-305">For more information, see the above section [Rights Management use license for offline access](#rights-management-use-license-for-offline-access).</span></span>

![사용자 지정 권한을 사용하여 보호하기 위한 옵션](../media/sensitivity-aip-custom-permissions-dialog.png)

<span data-ttu-id="7aa6b-307">내장 레이블의 경우 유저가 다음을 선택할 경우 동일한 대화 상자가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-307">For built-in labeling, users see the same dialog box if they select the following:</span></span>

- <span data-ttu-id="7aa6b-308">Windows: **파일** 탭 > **정보** > **문서 보호** > **액세스 제한** > **제한된 액세스**</span><span class="sxs-lookup"><span data-stu-id="7aa6b-308">Windows: **File** tab > **Info** > **Protect Document** > **Restrict Access** > **Restricted Access**</span></span>

- <span data-ttu-id="7aa6b-309">MacOS: **검토** 탭 > **보호** > **사용 권한** > **제한된 액세스**</span><span class="sxs-lookup"><span data-stu-id="7aa6b-309">macOS: **Review** tab > **Protection** > **Permissions** > **Restricted Access**</span></span>

## <a name="example-configurations-for-the-encryption-settings"></a><span data-ttu-id="7aa6b-310">암호화 설정의 예제 구성</span><span class="sxs-lookup"><span data-stu-id="7aa6b-310">Example configurations for the encryption settings</span></span>

<span data-ttu-id="7aa6b-311">아래에 나오는 각 예제에 대해 **암호화 설정 구성** 을 선택하는 경우, 마법사의 **암호화** 페이지에서 구성을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-311">For each example that follows, do the configuration from the **Encryption** page of the wizard when **Configure encryption settings** is selected:</span></span>

![민감도 레이블 마법사의 암호화 옵션 적용](../media/apply-encryption-option.png)

### <a name="example-1-label-that-applies-do-not-forward-to-send-an-encrypted-email-to-a-gmail-account"></a><span data-ttu-id="7aa6b-313">예제 1: 적용되는 레이블 암호화된 전자 메일을 Gmail 계정으로 보내기 위해 전달하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-313">Example 1: Label that applies Do Not Forward to send an encrypted email to a Gmail account</span></span>

<span data-ttu-id="7aa6b-314">이 레이블은 Outlook 및 웹에서의 Outlook에서만 사용할 수 있으며 Exchange Online을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-314">This label displays only in Outlook and Outlook on the web, and you must use Exchange Online.</span></span> <span data-ttu-id="7aa6b-315">사용자가 Gmail 계정(또는 조직 외부의 다른 전자 메일 계정)을 사용하는 사용자에게 암호화된 전자 메일을 보내야 하는 경우 이 레이블을 선택하도록 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-315">Instruct users to select this label when they need to send an encrypted email to people using a Gmail account (or any other email account outside your organization).</span></span>

<span data-ttu-id="7aa6b-316">사용자는 **받는 사람** 상자에 Gmail 전자 메일 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-316">Your users type the Gmail email address in the **To** box.</span></span>  <span data-ttu-id="7aa6b-317">그런 다음 레이블을 선택하면 전달 금지 옵션이 전자 메일에 자동으로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-317">Then, they select the label and the Do Not Forward option is automatically added to the email.</span></span> <span data-ttu-id="7aa6b-318">그 결과 받는 사람이 **다른 이름으로 저장** 옵션을 사용하여 전자 메일을 전달, 인쇄, 복사하거나 혹은 사서함 외부에 해당 전자 메일을 저장하는 것을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-318">The result is that recipients cannot forward the email, or print it, copy from it, or save the email outside their mailbox by using the **Save As** option.</span></span>

1. <span data-ttu-id="7aa6b-319">**암호화** 페이지에서 다음을 수행합니다. **사용 권한을 지금 할당 혹은 사용자가 결정하도록 하기** 에서 **사용자가 레이블을 적용할 때 사용 권한을 할당하도록 하기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-319">On the **Encryption** page: For **Assign permissions now or let users decide?** select **Let users assign permissions when they apply the label**.</span></span>

2. <span data-ttu-id="7aa6b-320">확인란 선택: **Outlook에서 전달 금지 옵션에 해당하는 제한 사항을 적용합니다**.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-320">Select the checkbox: **In Outlook, enforce restrictions equivalent to the Do Not Forward option**.</span></span>

3. <span data-ttu-id="7aa6b-321">선택된 경우 확인란의 선택을 취소합니다. **Word, PowerPoint 및 Excel에서 사용자에게 사용 권한을 지정하라는 메시지를 표시합니다**.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-321">If selected, clear the checkbox: **In Word, PowerPoint, and Excel, prompt users to specify permissions**.</span></span>

4. <span data-ttu-id="7aa6b-322">**다음** 을 선택하고 마법사를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-322">Select **Next** and complete the wizard.</span></span>

### <a name="example-2-label-that-restricts-read-only-permission-to-all-users-in-another-organization"></a><span data-ttu-id="7aa6b-323">예제 2: 다른 조직의 모든 사용자에게 읽기 전용 권한을 제한하는 레이블</span><span class="sxs-lookup"><span data-stu-id="7aa6b-323">Example 2: Label that restricts read-only permission to all users in another organization</span></span>

<span data-ttu-id="7aa6b-324">이 레이블은 매우 중요한 문서를 읽기 전용으로 공유하는 데 적합하며, 이러한 문서를 보려면 항상 인터넷 연결이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-324">This label is suitable for sharing very sensitive documents as read-only, and the documents always require an internet connection to view them.</span></span>

<span data-ttu-id="7aa6b-325">이 레이블은 전자 메일에 적합하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-325">This label is not suitable for emails.</span></span>

1. <span data-ttu-id="7aa6b-326">**암호화** 페이지에서 다음을 수행합니다. **사용 권한을 지금 할당 혹은 사용자가 결정하도록 하기** 에서 **지금 사용 권한을 할당** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-326">On the **Encryption** page: For **Assign permissions now or let users decide?** select **Assign permissions now**.</span></span>

2. <span data-ttu-id="7aa6b-327">**오프라인 액세스를 허용** 은 **절대 불허** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-327">For **Allow offline access**, select **Never**.</span></span>

3. <span data-ttu-id="7aa6b-328">**사용 권한 할당** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-328">Select **Assign permissions**.</span></span>

4. <span data-ttu-id="7aa6b-329">**사용 권한 할당** 창에서 **특정 전자 메일 주소 또는 도메인 추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-329">On the **Assign permissions** pane, select **Add specific email addresses or domains**.</span></span>

5. <span data-ttu-id="7aa6b-330">텍스트 상자에 다른 조직의 도메인 이름을 입력 합니다(예:**fabrikam.com**).</span><span class="sxs-lookup"><span data-stu-id="7aa6b-330">In the text box, enter the name of a domain from the other organization, for example, **fabrikam.com**.</span></span> <span data-ttu-id="7aa6b-331">그런 다음 **추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-331">Then select **Add**.</span></span>

6. <span data-ttu-id="7aa6b-332">**사용 권한 선택** 선택</span><span class="sxs-lookup"><span data-stu-id="7aa6b-332">Select **Choose permissions**.</span></span>

7. <span data-ttu-id="7aa6b-333">**사용 권한 선택** 창에서 드롭다운 상자를 선택하고 **뷰어** 를 선택 한 다음 **저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-333">On the **Choose permissions** pane, select the dropdown box, select **Viewer**, and then select **Save**.</span></span>

8. <span data-ttu-id="7aa6b-334">**사용 권한 할당** 창으로 돌아가서 **저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-334">Back on the **Assign Permissions** pane, select **Save**.</span></span>

9. <span data-ttu-id="7aa6b-335">**암호화** 페이지에서 **다음** 을 선택하고 마법사를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-335">On the **Encryption** page, select **Next** and complete the wizard.</span></span>

### <a name="example-3-add-external-users-to-an-existing-label-that-encrypts-content"></a><span data-ttu-id="7aa6b-336">예제 3: 콘텐츠를 암호화하는 기존 레이블에 외부 사용자 추가</span><span class="sxs-lookup"><span data-stu-id="7aa6b-336">Example 3: Add external users to an existing label that encrypts content</span></span>

<span data-ttu-id="7aa6b-337">추가하는 새 사용자는 이 레이블로 이미 보호된 문서 및 전자 메일을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-337">The new users that you add will be able open documents and emails that have already been protected with this label.</span></span> <span data-ttu-id="7aa6b-338">이러한 사용자에게 부여하는 사용 권한은 기존 사용자의 사용 권한과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-338">The permissions that you grant these users can be different from the permissions that the existing users have.</span></span>

1. <span data-ttu-id="7aa6b-339">**암호화** 페이지에서 다음을 수행합니다. **사용 권한을 지금 할당 혹은 사용자가 결정하도록 하기** 에서 반드시 **지금 사용 권한을 할당** 이 선택되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-339">On the **Encryption** page: For **Assign permissions now or let users decide?** make sure **Assign permissions now** is selected.</span></span>

2. <span data-ttu-id="7aa6b-340">**사용 권한 할당** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-340">Select **Assign permissions**.</span></span>

3. <span data-ttu-id="7aa6b-341">**사용 권한 할당** 창에서 **특정 전자 메일 주소 또는 도메인 추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-341">On the **Assign permissions** pane, select **Add specific email addresses or domains**.</span></span>

4. <span data-ttu-id="7aa6b-342">텍스트 상자에 추가할 첫 번째 사용자(또는 그룹)의 전자 메일 주소를 입력한 다음 **추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-342">In the text box, enter the email address of the first user (or group) to add, and then select **Add**.</span></span>

5. <span data-ttu-id="7aa6b-343">**사용 권한 선택** 선택</span><span class="sxs-lookup"><span data-stu-id="7aa6b-343">Select **Choose permissions**.</span></span>

6. <span data-ttu-id="7aa6b-344">**사용 권한 선택** 창에서 이 사용자(또는 그룹)에 대한 사용 권한을 선택하고 **저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-344">On the **Choose permissions** pane, select the permissions for this user (or group), and then select **Save**.</span></span>

7. <span data-ttu-id="7aa6b-345">**사용 권한 할당** 창으로 돌아가서 이 레이블에 추가하려는 각 사용자(또는 그룹)에 대해 3 ~ 6단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-345">Back on the **Assign Permissions** pane, repeat steps 3 through 6 for each user (or group) that you want to add to this label.</span></span> <span data-ttu-id="7aa6b-346">그런 다음 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-346">Then click **Save**.</span></span>

8. <span data-ttu-id="7aa6b-347">**암호화** 페이지에서 **다음** 을 선택하고 마법사를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-347">On the **Encryption** page, select **Next** and complete the wizard.</span></span>

### <a name="example-4-label-that-encrypts-content-but-doesnt-restrict-who-can-access-it"></a><span data-ttu-id="7aa6b-348">예제 4: 콘텐츠를 암호화하지만 액세스할 수 있는 사용자를 제한하지 않는 레이블</span><span class="sxs-lookup"><span data-stu-id="7aa6b-348">Example 4: Label that encrypts content but doesn't restrict who can access it</span></span>

<span data-ttu-id="7aa6b-349">이 구성은 전자 메일이나 문서를 암호화하는 데 사용자, 그룹 또는 도메인을 지정할 필요가 없다는 장점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-349">This configuration has the advantage that you don't need to specify users, groups, or domains to encrypt an email or document.</span></span> <span data-ttu-id="7aa6b-350">콘텐츠는 계속 암호화되므로 사용 권한, 만료 날짜 및 오프라인 액세스를 계속 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-350">The content will still be encrypted and you can still specify usage rights, an expiry date, and offline access.</span></span>

<span data-ttu-id="7aa6b-351">보호되는 문서 또는 전자 메일을 열 수 있는 사용자를 제한할 필요가 없는 경우에만 이 구성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-351">Use this configuration only when you do not need to restrict who can open the protected document or email.</span></span> [<span data-ttu-id="7aa6b-352">이 설정에 대한 자세한 내용</span><span class="sxs-lookup"><span data-stu-id="7aa6b-352">More information about this setting</span></span>](#requirements-and-limitations-for-add-any-authenticated-users)

1. <span data-ttu-id="7aa6b-353">**암호화** 페이지에서 다음을 수행합니다. **사용 권한을 지금 할당 혹은 사용자가 결정하도록 하기** 에서 반드시 **지금 사용 권한을 할당** 이 선택되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-353">On the **Encryption** page: For **Assign permissions now or let users decide?** make sure **Assign permissions now** is selected.</span></span>

2. <span data-ttu-id="7aa6b-354">필요한 경우 **콘텐츠에 대한 사용자 액세스 만료** 및 **오프라인 액세스 허용** 에 대한 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-354">Configure settings for **User access to content expires** and **Allow offline access** as required.</span></span>

3. <span data-ttu-id="7aa6b-355">**사용 권한 할당** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-355">Select **Assign permissions**.</span></span>

4. <span data-ttu-id="7aa6b-356">**사용 권한 할당** 창에서 **인증된 사용자 추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-356">On the **Assign permissions** pane, select **Add any authenticated users**.</span></span>

    <span data-ttu-id="7aa6b-357">**사용자 및 그룹** 의 경우 **인증된 사용자** 가 자동으로 추가되는 것을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-357">For **Users and groups**, you see **Authenticated users** automatically added.</span></span> <span data-ttu-id="7aa6b-358">이 값은 변경할 수 없고 삭제만 가능하며 삭제 시 **인증된 사용자 추가** 선택이 취소됩니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-358">You can't change this value, only delete it, which cancels the **Add any authenticated users** selection.</span></span>

5. <span data-ttu-id="7aa6b-359">**사용 권한 선택** 선택</span><span class="sxs-lookup"><span data-stu-id="7aa6b-359">Select **Choose permissions**.</span></span>

6. <span data-ttu-id="7aa6b-360">**사용 권한 선택** 창에서 드롭다운 상자를 선택하고 원하는 사용 권한을 선택한 다음 **저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-360">On the **Choose permissions** pane, select the dropdown box, select the permissions you want, and then select **Save**.</span></span>

7. <span data-ttu-id="7aa6b-361">**사용 권한 할당** 창으로 돌아가서 **저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-361">Back on the **Assign Permissions** pane, select **Save**.</span></span>

8. <span data-ttu-id="7aa6b-362">**암호화** 페이지에서 **다음** 을 선택하고 마법사를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-362">On the **Encryption** page, select **Next** and complete the wizard.</span></span>

## <a name="considerations-for-encrypted-content"></a><span data-ttu-id="7aa6b-363">암호화된 콘텐츠의 고려 사항</span><span class="sxs-lookup"><span data-stu-id="7aa6b-363">Considerations for encrypted content</span></span>

<span data-ttu-id="7aa6b-364">가장 중요한 문서와 전자 메일을 암호화하면 권한있는 사용자만 이 데이터에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-364">Encrypting your most sensitive documents and emails helps to ensure that only authorized people can access this data.</span></span> <span data-ttu-id="7aa6b-365">그러나 다음과 같은 몇 가지 고려해야 할 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-365">However, there are some considerations to take into account:</span></span>

- <span data-ttu-id="7aa6b-366">조직이 [SharePoint 및 OneDrive에서 Office 파일에 대한 민감도 레이블을 활성화](sensitivity-labels-sharepoint-onedrive-files.md)하지 않은 경우, 다음과 같이 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-366">If your organization hasn't [enabled sensitivity labels for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md):</span></span>

  - <span data-ttu-id="7aa6b-367">암호화된 파일에는 검색, eDiscovery 및 Delve가 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-367">Search, eDiscovery, and Delve will not work for encrypted files.</span></span>
  - <span data-ttu-id="7aa6b-368">DLP 정책은 이러한 암호화된 파일의 메타 데이터(보존 레이블 정보 포함)에 대해서는 작동하지만 파일의 내용(예: 파일 내의 신용 카드 번호)에는 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-368">DLP policies work for the metadata of these encrypted files (including retention label information) but not the content of these files (such as credit card numbers within files).</span></span>
  - <span data-ttu-id="7aa6b-369">사용자는 웹에서 Office를 사용하여 암호화된 파일을 열 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-369">Users can't open encrypted files using Office on the web.</span></span> <span data-ttu-id="7aa6b-370">SharePoint 및 OneDrive에서 Office 파일에 대한 민감도 레이블을 사용하도록 설정하면 사용자는 웹에서 Office를 사용하여 암호화된 파일을 열 수 있습니다. 이 경우에는 온-프레미스 키("자체 키 보유" 또는 HYOK)를 사용하여 적용된 암호화, [이중 키 암호화](#double-key-encryption)와 민감도 레이블과 독립적으로 적용된 암호화를 포함하는 몇 가지 [제한 사항](sensitivity-labels-sharepoint-onedrive-files.md#limitations)이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-370">When sensitivity labels for Office files in SharePoint and OneDrive are enabled, users can use Office on the web to open encrypted files, with some [limitations](sensitivity-labels-sharepoint-onedrive-files.md#limitations) that include encryption that has been applied with an on-premises key (known as "hold your own key", or HYOK), [double key encryption](#double-key-encryption), and encryption that has been applied independently from a sensitivity label.</span></span>

- <span data-ttu-id="7aa6b-371">여러 사용자가 동시에 암호화된 파일을 편집하려면 모두 웹용 Office를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-371">For multiple users to edit an encrypted file at the same time, they must all be using Office for the web.</span></span> <span data-ttu-id="7aa6b-372">그와 같은 상황이 아니고 파일이 이미 열려있는 경우:</span><span class="sxs-lookup"><span data-stu-id="7aa6b-372">If this isn't the case, and the file is already open:</span></span>

  - <span data-ttu-id="7aa6b-373">Office 앱(Windows, Mac, Android 및 iOS)에서, 사용자에게는 파일을 체크아웃한 사용자의 이름과 함께 **사용 중인 파일** 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-373">In Office apps (Windows, Mac, Android, and iOS), users see a **File In Use** message with the name of the person who has checked out the file.</span></span> <span data-ttu-id="7aa6b-374">그런 다음 읽기 전용 사본을 보거나 파일 사본을 저장 및 편집하고, 파일을 사용할 수 있을 때 알림을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-374">They can then view a read-only copy or save and edit a copy of the file, and receive notification when the file is available.</span></span>
  - <span data-ttu-id="7aa6b-375">웹용 Office에서, 사용자에게는 다른 사람과 함께 문서를 편집할 수 없다는 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-375">In Office for the web, users see an error message that they can't edit the document with other people.</span></span> <span data-ttu-id="7aa6b-376">그런 다음 **읽기용 보기에서 열기** 를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-376">They can then select **Open in Reading View**.</span></span>

- <span data-ttu-id="7aa6b-377">암호화된 파일에 대해서는 Office 앱(Windows, Mac, Android 및 iOS)의 [자동 저장](https://support.office.com/article/what-is-autosave-6d6bd723-ebfd-4e40-b5f6-ae6e8088f7a5) 기능이 비활성화되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-377">The [AutoSave](https://support.office.com/article/what-is-autosave-6d6bd723-ebfd-4e40-b5f6-ae6e8088f7a5) functionality in Office apps (Windows, Mac, Android, and iOS) is disabled for encrypted files.</span></span> <span data-ttu-id="7aa6b-378">사용자에게는 자동 저장을 설정하기 전에 사용 권한의 제한을 해제해야 한다는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-378">Users see a message that the file has restricted permissions that must be removed before AutoSave can be turned on.</span></span>

- <span data-ttu-id="7aa6b-379">암호화된 파일은 Office 앱(Windows, Mac, Android 및 iOS)에서 여는 데 시간이 더 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-379">Encrypted files might take longer to open in Office apps (Windows, Mac, Android, and iOS).</span></span>

- <span data-ttu-id="7aa6b-380">문서가 [SharePoint에서 체크아웃](https://support.microsoft.com/office/check-out-check-in-or-discard-changes-to-files-in-a-library-7e2c12a9-a874-4393-9511-1378a700f6de)될 때 Office 앱을 사용하여 암호화를 적용하는 레이블이 추가된 다음 사용자가 체크아웃을 무시해도 문서는 레이블과 암호화된 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-380">If a label that applies encryption is added by using an Office app when the document is [checked out in SharePoint](https://support.microsoft.com/office/check-out-check-in-or-discard-changes-to-files-in-a-library-7e2c12a9-a874-4393-9511-1378a700f6de), and the user then discards the checkout, the document remains labeled and encrypted.</span></span>

- <span data-ttu-id="7aa6b-381">암호화된 파일에 대한 다음 작업은 Office 앱(Windows, Mac, Android 및 iOS)에서 지원되지 않으며 사용자에게 문제가 있다는 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-381">The following actions for encrypted files aren't supported from Office apps (Windows, Mac, Android, and iOS), and users see an error message that something went wrong.</span></span> <span data-ttu-id="7aa6b-382">그러나 SharePoint 기능을 대안으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-382">However, SharePoint functionality can be used as an alternative:</span></span>

  - <span data-ttu-id="7aa6b-383">이전 버전의 사본 보기, 복원 및 저장.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-383">View, restore, and save copies of previous versions.</span></span> <span data-ttu-id="7aa6b-384">대안으로, 사용자는 [목록 또는 라이브러리에 대한 버전 관리를 활성화하고 구성할 때](https://support.office.com/article/enable-and-configure-versioning-for-a-list-or-library-1555d642-23ee-446a-990a-bcab618c7a37) 웹에서 Office를 사용하여 이러한 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-384">As an alternative, users can do these actions using Office on the web when you [enable and configure versioning for a list or library](https://support.office.com/article/enable-and-configure-versioning-for-a-list-or-library-1555d642-23ee-446a-990a-bcab618c7a37).</span></span>
  - <span data-ttu-id="7aa6b-385">파일 이름 또는 위치 변경.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-385">Change the name or location of files.</span></span> <span data-ttu-id="7aa6b-386">대안으로, 사용자는 SharePoint에서 [문서 라이브러리에서 파일, 폴더 또는 링크 이름 바꾸기](https://support.microsoft.com/office/rename-a-file-folder-or-link-in-a-document-library-bc493c1a-921f-4bc1-a7f6-985ce11bb185)를 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-386">As an alternative, users can [rename a file, folder, or link in a document library](https://support.microsoft.com/office/rename-a-file-folder-or-link-in-a-document-library-bc493c1a-921f-4bc1-a7f6-985ce11bb185) in SharePoint.</span></span>

<span data-ttu-id="7aa6b-387">민감도 레이블로 암호화된 파일에 대한 최상의 공동 작업 환경을 위해서는 웹용 Office와 [SharePoint 및 OneDrive의 Office 파일에 대해 민감도 레이블을 사용](sensitivity-labels-sharepoint-onedrive-files.md)하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-387">For the best collaboration experience for files that are encrypted by a sensitivity label, we recommend you use [sensitivity labels for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md) and Office for the web.</span></span>

## <a name="important-prerequisites"></a><span data-ttu-id="7aa6b-388">중요한 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="7aa6b-388">Important prerequisites</span></span>

<span data-ttu-id="7aa6b-389">암호화를 사용하려면 먼저 몇 가지 구성 작업을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-389">Before you can use encryption, you might need to do some configuration tasks.</span></span>

- <span data-ttu-id="7aa6b-390">Azure Information Protection에서 보호 활성화</span><span class="sxs-lookup"><span data-stu-id="7aa6b-390">Activate protection from Azure Information Protection</span></span>
    
    <span data-ttu-id="7aa6b-391">민감도 레이블이 암호화를 적용하려면 테넌트에 대해 Azure Information Protection의 보호 서비스(Azure 권한 관리)가 활성화되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-391">For sensitivity labels to apply encryption, the protection service (Azure Rights Management) from Azure Information Protection must be activated for your tenant.</span></span> <span data-ttu-id="7aa6b-392">새 테넌트에서는 이것이 기본 설정이지만 서비스를 수동으로 활성화해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-392">In newer tenants, this is the default setting, but you might need to manually activate the service.</span></span> <span data-ttu-id="7aa6b-393">자세한 내용은 [Azure Information Protection에서 보호 서비스 활성화](https://docs.microsoft.com/azure/information-protection/activate-service)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-393">For more information, see [Activating the protection service from Azure Information Protection](https://docs.microsoft.com/azure/information-protection/activate-service).</span></span>

- <span data-ttu-id="7aa6b-394">Azure Information Protection에 대한 Exchange 구성</span><span class="sxs-lookup"><span data-stu-id="7aa6b-394">Configure Exchange for Azure Information Protection</span></span>
    
    <span data-ttu-id="7aa6b-395">사용자가 Outlook에서 전자 메일을 암호화하기 위해 레이블을 적용하기 전에 Azure Information Protection을 위해 Exchange를 구성할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-395">Exchange does not have to be configured for Azure Information Protection before users can apply labels in Outlook to encrypt their emails.</span></span> <span data-ttu-id="7aa6b-396">그러나 Exchange에 Azure Information Protection을 구성하기 전에는 Exchange에서 Azure 권한 관리 보호 사용의 모든 기능을 이용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-396">However, until Exchange is configured for Azure Information Protection, you do not get the full functionality of using Azure Rights Management protection with Exchange.</span></span>
    
    <span data-ttu-id="7aa6b-397">예를 들어 사용자는 휴대폰 또는 웹에서의 Outlook으로 암호화된 전자 메일을 볼 수 없으며 검색 시 암호화된 전자 메일이 인덱싱되지 않으며 권한 관리 보호를 위한 Exchange Online DLP를 구성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-397">For example, users cannot view encrypted emails on mobile phones or with Outlook on the web, encrypted emails cannot be indexed for search, and you cannot configure Exchange Online DLP for Rights Management protection.</span></span> 
    
    <span data-ttu-id="7aa6b-398">Exchange에서 이러한 추가 시나리오를 지원할 수 있는지 확인하려면 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-398">To ensure that Exchange can support these additional scenarios, see the following:</span></span>
    
    - <span data-ttu-id="7aa6b-399">Exchange Online의 경우 [Exchange Online: IRM 구성](https://docs.microsoft.com/azure/information-protection/configure-office365#exchangeonline-irm-configuration)에 대한 설명서를 참고하세요.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-399">For Exchange Online, see the instructions for [Exchange Online: IRM Configuration](https://docs.microsoft.com/azure/information-protection/configure-office365#exchangeonline-irm-configuration).</span></span>
    - <span data-ttu-id="7aa6b-400">Exchange 온-프레미스의 경우 [RMS 커넥터를 배포하고 Exchange 서버를 구성](https://docs.microsoft.com/azure/information-protection/deploy-rms-connector)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-400">For Exchange on-premises, you must deploy the [RMS connector and configure your Exchange servers](https://docs.microsoft.com/azure/information-protection/deploy-rms-connector).</span></span> 

## <a name="next-steps"></a><span data-ttu-id="7aa6b-401">다음 단계</span><span class="sxs-lookup"><span data-stu-id="7aa6b-401">Next steps</span></span>

<span data-ttu-id="7aa6b-402">레이블이 지정되고 암호화된 문서를 조직 외부의 사용자와 공유해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="7aa6b-402">Need to share your labeled and encrypted documents with people outside your organization?</span></span>  <span data-ttu-id="7aa6b-403">[암호화된 문서 외부 사용자와 공유](sensitivity-labels-office-apps.md#sharing-encrypted-documents-with-external-users)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7aa6b-403">See [Sharing encrypted documents with external users](sensitivity-labels-office-apps.md#sharing-encrypted-documents-with-external-users).</span></span>