---
title: 새로운 Office 365 메시지 암호화 기능 설정
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/30/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 7ff0c040-b25c-4378-9904-b1b50210d00e
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 새 Office 365 메시지 암호화 기능은 Azure Information Protection을 바탕으로 하여 구현되었고, 이 기능을 사용하면 조직 내부나 조직 외부의 사람과 보호된 전자 메일을 사용하여 통신할 수 있습니다. 새 OME 기능은 다른 Office 365 조직, Outlook.com, Gmail 및 기타 전자 메일 서비스와 함께 동작합니다.
ms.openlocfilehash: c772151250d30e62a3f2689df5cd853536af3ede
ms.sourcegitcommit: 1c962bd0d51dc12419c4e6e393bb734c972b7e38
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "39218737"
---
# <a name="set-up-new-office-365-message-encryption-capabilities"></a><span data-ttu-id="c7045-104">새로운 Office 365 메시지 암호화 기능 설정</span><span class="sxs-lookup"><span data-stu-id="c7045-104">Set up new Office 365 Message Encryption capabilities</span></span>

<span data-ttu-id="c7045-105">새 Office 365 메시지 암호화(OME) 기능을 사용하면 조직은 모든 장치에 있는 모든 사용자와 보호된 전자 메일을 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7045-105">The new Office 365 Message Encryption (OME) capabilities allow organizations to share protected email with anyone on any device.</span></span> <span data-ttu-id="c7045-106">사용자는 다른 Office 365 조직은 물론, Outlook.com, Gmail 및 기타 전자 메일 서비스를 사용하지만 Office 365 고객이 아닌 사용자와도 보호된 메시지를 주고받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7045-106">Users can exchange protected messages with other Office 365 organizations, as well as non-Office 365 customers using Outlook.com, Gmail, and other email services.</span></span>

<span data-ttu-id="c7045-107">Office 365 조직에서 새 OME 기능을 사용할 수 있는지 여부는 아래 단계를 실시하여 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="c7045-107">Follow the steps below to ensure that the new OME capabilities are available in your Office 365 organization.</span></span>

## <a name="verify-that-azure-rights-management-is-active"></a><span data-ttu-id="c7045-108">Azure 권한 관리의 활성화 여부 확인</span><span class="sxs-lookup"><span data-stu-id="c7045-108">Verify that Azure Rights Management is active</span></span>

<span data-ttu-id="c7045-109">새 OME 기능은 암호화 및 액세스 제어를 통한 전자 메일 및 문서 보호를 위해 [Azure Information Protection](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms)이 사용하는 기술인 [Azure 권한 관리 서비스(Azure RMS)](https://docs.microsoft.com/azure/information-protection/what-is-information-protection)에 있는 보호 기능을 활용합니다.</span><span class="sxs-lookup"><span data-stu-id="c7045-109">The new OME capabilities leverage the protection features in [Azure Rights Management Services (Azure RMS)](https://docs.microsoft.com/azure/information-protection/what-is-information-protection), the technology used by [Azure Information Protection](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms) to protect emails and documents via encryption and access controls.</span></span>

<span data-ttu-id="c7045-110">새 OME 기능을 사용하기 위해서는 조직의 테넌트에서 [Azure 권한 관리](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms)가 활성화되어 있기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7045-110">The only prerequisite for using the new OME capabilities is that [Azure Rights Management](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms) must be activated in your organization's tenant.</span></span> <span data-ttu-id="c7045-111">활성화된 경우에는 Office 365가 새 OME 기능을 자동으로 활성화하므로 다른 작업이 필요 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c7045-111">If it is, Office 365 activates the new OME capabilities automatically and you don't need to do anything.</span></span>

<span data-ttu-id="c7045-112">대부분의 사용 가능한 플랜에서 Azure RMS가 자동으로 활성화되기 때문에, 여기에서도 보통의 경우 다른 추가 작업이 필요없습니다.</span><span class="sxs-lookup"><span data-stu-id="c7045-112">Azure RMS is also activated automatically for most eligible plans, so you probably don't have to do anything in this regard either.</span></span> <span data-ttu-id="c7045-113">자세한 내용은 [Azure 권한 관리 활성화](https://docs.microsoft.com/azure/information-protection/activate-service)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c7045-113">See [Activating Azure Rights Management](https://docs.microsoft.com/azure/information-protection/activate-service) for more information.</span></span>

>[!IMPORTANT]
><span data-ttu-id="c7045-114">Exchange Online과 함께 Active Directory Rights Management Service(AD RMS)를 사용하는 경우에 새 OME 기능을 사용하려면, 먼저 [Azure Information Protection 마이그레이션](https://docs.microsoft.com/azure/information-protection/migrate-from-ad-rms-to-azure-rms)을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7045-114">If you use Active Directory Rights Management service (AD RMS) with Exchange Online, you need to [migrate to Azure Information Protection](https://docs.microsoft.com/azure/information-protection/migrate-from-ad-rms-to-azure-rms) before you can use the new OME capabilities.</span></span> <span data-ttu-id="c7045-115">OME는 AD RMS와 호환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c7045-115">OME is not compatible with AD RMS.</span></span>  

<span data-ttu-id="c7045-116">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c7045-116">For more information, see:</span></span>

- <span data-ttu-id="c7045-117">현재의 구독에 Azure Information Protection이 포함되었는지 여부를 확인하려면 [새 OME 기능을 사용하기 위해서는 어떤 구독이 필요한가요?](ome-faq.md#what-subscriptions-do-i-need-to-use-the-new-ome-capabilities)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c7045-117">[What subscriptions do I need to use the new OME capabilities?](ome-faq.md#what-subscriptions-do-i-need-to-use-the-new-ome-capabilities) to check whether your subscription plan includes Azure Information Protection (which includes Azure RMS functionality).</span></span>
- <span data-ttu-id="c7045-118">적절한 구독을 구입하기 위해서는 [Azure Information Protection](https://azure.microsoft.com/services/information-protection/)에서 자세한 내용을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c7045-118">[Azure Information Protection](https://azure.microsoft.com/services/information-protection/) for information about purchasing an eligible subscription.</span></span>  

### <a name="manually-activating-azure-rights-management"></a><span data-ttu-id="c7045-119">Azure AD Rights Management 수동 활성화</span><span class="sxs-lookup"><span data-stu-id="c7045-119">Manually activating Azure Rights Management</span></span>

<span data-ttu-id="c7045-120">Azure RMS를 비활성화로 설정한 경우나, 어떤 이유에서 자동으로 활성화되지 못한 경우에는 수동으로 활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7045-120">If you disabled Azure RMS, or if it was not automatically activated for any reason, you can activate it manually in the:</span></span>

- <span data-ttu-id="c7045-121">**Microsoft 365 관리 센터**: [관리 센터에서 Azure 권한 관리 활성화 방법](https://docs.microsoft.com/azure/information-protection/activate-office365)을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="c7045-121">**Microsoft 365 admin center**: See [How to activate Azure Rights Management from the admin center](https://docs.microsoft.com/azure/information-protection/activate-office365) for instructions.</span></span>
- <span data-ttu-id="c7045-122">**Azure Portal**: [Azure Portal에서 Azure 권한 관리 활성화 방법](https://docs.microsoft.com/azure/information-protection/activate-azure)을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="c7045-122">**Azure portal**: See [How to activate Azure Rights Management from the Azure portal](https://docs.microsoft.com/azure/information-protection/activate-azure) for instructions.</span></span>

## <a name="configure-management-of-your-azure-information-protection-tenant-key"></a><span data-ttu-id="c7045-123">Azure Information Protection 테넌트 키 관리 구성</span><span class="sxs-lookup"><span data-stu-id="c7045-123">Configure management of your Azure Information Protection tenant key</span></span>

<span data-ttu-id="c7045-124">이 단계는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="c7045-124">This is an optional step.</span></span> <span data-ttu-id="c7045-125">기본 설정은 Azure Information Protection용 루트 키를 Microsoft가 관리하도록 구성하는 것이고, 대부분의 Office 365 테넌트에 대해서 가장 권장하는 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="c7045-125">Allowing Microsoft to manage the root key for Azure Information Protection is the default setting and recommended best practice for most Office 365 tenants.</span></span> <span data-ttu-id="c7045-126">이렇게 설정된 경우에는 별도의 작업이 필요 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c7045-126">If this is the case, you don't need to do anything.</span></span>

<span data-ttu-id="c7045-127">여러 가지 이유에서 직접 사용자 고유 루트 키(BYOK(Bring Your Own Key)라고도 함)를 생성하고 관리해야 할 필요가 있는 경우가 있습니다. 예를 들면, 규정 준수 요구 사항을 충족하기 위한 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="c7045-127">There are many reasons, for example compliance requirements, that may necessitate you generating and managing your own root key (also known as bring your own key (BYOK)).</span></span> <span data-ttu-id="c7045-128">이러한 경우에는 새 OME 기능을 설정하기 전에 필수 단계를 먼저 완료하는 것을 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="c7045-128">If this is the case, we recommend that you complete the required steps before setting up the new OME capabilities.</span></span> <span data-ttu-id="c7045-129">자세한 내용은 [Azure Information Protection 테넌트 키 계획 및 구현](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c7045-129">See [Planning and implementing your Azure Information Protection tenant key](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key) for more.</span></span>

## <a name="verify-new-ome-configuration-in-exchange-online-powershell"></a><span data-ttu-id="c7045-130">Exchange Online PowerShell에서 새 OME 구성 확인</span><span class="sxs-lookup"><span data-stu-id="c7045-130">Verify new OME configuration in Exchange Online PowerShell</span></span>

<span data-ttu-id="c7045-131">[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)에서 새 OME 기능을 사용할 수 있도록 Office 365 테넌트가 올바르게 구성되었는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7045-131">You can verify that your Office 365 tenant is properly configured to use the new OME capabilities in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps).</span></span>
  
1. <span data-ttu-id="c7045-132">Office 365 테넌트에서 전역 관리자 권한을 사용하여 [Exchange Online PowerShell 연결](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)을 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7045-132">[Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) using an account with global administrator permissions in your Office 365 tenant.</span></span>

2. <span data-ttu-id="c7045-133">Get-IRMConfiguration cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c7045-133">Run the Get-IRMConfiguration cmdlet.</span></span>

     <span data-ttu-id="c7045-134">AzureRMSLicensingEnabled 매개 변수의 값이 $True인지 확인합니다. 이 값은 테넌트에서 OME가 구성되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c7045-134">You should see a value of $True for the AzureRMSLicensingEnabled parameter, which indicates that OME is configured in your tenant.</span></span> <span data-ttu-id="c7045-135">그렇지 않은 경우에는 AzureRMSLicensingEnabled의 값을 $True으로 설정하여 OME을 사용할 수 있도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c7045-135">If it is not, use Set-IRMConfiguration to set the value of AzureRMSLicensingEnabled to $True to enable OME.</span></span>

3. <span data-ttu-id="c7045-136">다음 구문을 사용하여 Test-IRMConfiguration cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c7045-136">Run the script by using the following syntax:</span></span>

     ```powershell
     Test-IRMConfiguration [-Sender <email address >]
     ```  

   <span data-ttu-id="c7045-137">**예제**:</span><span class="sxs-lookup"><span data-stu-id="c7045-137">**Example**:</span></span>

     ```powershell
     Test-IRMConfiguration -Sender securityadmin@contoso.com
     ```

     - <span data-ttu-id="c7045-138">보낸 사람 전자 메일을 제공하는 것은 선택 사항이지만, 시스템이 추가 검사를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7045-138">Providing a sender email is optional, but forces the system to perform additional checks.</span></span> <span data-ttu-id="c7045-139">Office 365 테넌트 사용자의 전자 메일 주소를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c7045-139">Use the email address of any user in your Office 365 tenant.</span></span>

     <span data-ttu-id="c7045-140">결과는 다음과 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7045-140">Your results should be similar to:</span></span>

     ```text
    Results : Acquiring RMS Templates ...
                - PASS: RMS Templates acquired.  Templates available: Contoso  - Confidential View Only, Contoso  - Confidential, Do Not
            Forward.
            Verifying encryption ...
                - PASS: Encryption verified successfully.
            Verifying decryption ...
                - PASS: Decryption verified successfully.
            Verifying IRM is enabled ...
                - PASS: IRM verified successfully.

            OVERALL RESULT: PASS
    ```

   - <span data-ttu-id="c7045-141">*Contoso* 자리에 Office 365 조직 이름이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7045-141">Your Office 365 organization name will replace *Contoso*.</span></span>

   - <span data-ttu-id="c7045-142">기본 템플릿 이름은 위에 표시된 이름과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7045-142">The default template names may be different from those displayed above.</span></span> <span data-ttu-id="c7045-143">자세한 내용은 [Azure Information Protection의 템플릿 구성 및 관리](https://docs.microsoft.com/azure/information-protection/configure-policy-templates)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c7045-143">See [Configuring and managing templates for Azure Information Protection](https://docs.microsoft.com/azure/information-protection/configure-policy-templates) for more.</span></span>

4. <span data-ttu-id="c7045-144">Remove-PSSession cmdle을 실행하여 권한 관리 서비스와의 연결을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="c7045-144">Run the Remove-PSSession cmdlet to disconnect from the Rights Management service.</span></span>

     ```powershell
     Remove-PSSession $session
     ```

## <a name="next-steps-define-mail-flow-rules-to-use-new-ome-capabilities"></a><span data-ttu-id="c7045-145">다음 단계: 새 OME 기능을 사용하기 위한 메일 흐름 규칙 정의</span><span class="sxs-lookup"><span data-stu-id="c7045-145">Next steps: Define mail flow rules to use new OME capabilities</span></span>

<span data-ttu-id="c7045-146">Office 365 조직에서 전자 메일을 암호화하기 위한 사전 구성 메일 흐름 규칙이 있는 경우는 새 OME 기능을 사용할 수 있도록 기존 규칙을 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7045-146">If there are previously configured mail flow rules to encrypt email in your Office 365 organization, you need to update the existing rules to use the new OME capabilities.</span></span> <span data-ttu-id="c7045-147">새 배포의 경우에는 새 메일 흐름 규칙을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7045-147">For new deployments, you need to create new mail flow rules.</span></span>

>[!IMPORTANT]
><span data-ttu-id="c7045-148">기존의 메일 흐름 규칙을 업데이트하지 않으면 사용자는 계속해서 새 OME 환경이 아닌 이전의 HTML 첨부 파일 형식의 암호화된 메일을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7045-148">If you do not update existing mail flow rules, your users will continue to receive encrypted mail that uses the previous HTML attachment format, instead of the new seamless OME experience.</span></span>

<span data-ttu-id="c7045-149">메일 흐름 규칙은 어떤 전자 메일을 암호화하고, 어떤 메시지의 암호화를 제거할지에 대한 조건을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="c7045-149">Mail flow rules determine under what conditions email messages should be encrypted, as well as conditions for removing that encryption.</span></span> <span data-ttu-id="c7045-150">규칙에 대한 동작을 설정하면 규칙 조건에 일치하는 모든 메시지가 전송 시에 암호화됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7045-150">When you set an action for a rule, any messages that match the rule conditions are encrypted when they're sent.</span></span>
  
<span data-ttu-id="c7045-151">OME에 대한 메일 흐름 규칙을 만드는 단계에 대한 내용은 [Office 365에서 전자 메일 메시지를 암호화하기 위한 메일 흐름 규칙 정의](define-mail-flow-rules-to-encrypt-email.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c7045-151">For steps on creating mail flow rules for OME, see [Define mail flow rules to encrypt email messages in Office 365](define-mail-flow-rules-to-encrypt-email.md).</span></span>

<span data-ttu-id="c7045-152">기존 규칙을 업데이트하여 새 OME 기능을 사용하려면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c7045-152">To update existing rules to use the new OME capabilities:</span></span>

1. <span data-ttu-id="c7045-153">Microsoft 365 관리 센터에서 **관리 센터 > Exchange**로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c7045-153">In the Office 365 admin center, navigate to Admin centers  Exchange.</span></span>
2. <span data-ttu-id="c7045-154">Exchange 관리 센터에서 **메일 흐름 > 규칙**으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c7045-154">In the Exchange admin center (EAC), go to **Mail flow > Rules**.</span></span>
3. <span data-ttu-id="c7045-155">각 규칙에 대해 **다음**을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c7045-155">For each rule, in **Do the following**:</span></span>
    - <span data-ttu-id="c7045-156">**메시지 보안 수정**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c7045-156">Select **Modify the message security**.</span></span>
    - <span data-ttu-id="c7045-157">**365 메시지 암호화 및 권한 보호 적용**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c7045-157">Select **Apply Office 365 Message Encryption and rights protection**.</span></span>
    - <span data-ttu-id="c7045-158">목록에서 RMS 템플릿을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c7045-158">Select an RMS template from the list.</span></span>
    - <span data-ttu-id="c7045-159">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c7045-159">Select **Save**.</span></span>
    - <span data-ttu-id="c7045-160">**확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c7045-160">Select **OK**.</span></span>
