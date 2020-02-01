---
title: Office 365에서 전자 메일 메시지를 암호화하기 위한 메일의 흐름 규정을 정의
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 9b7daf19-d5f2-415b-bc43-a0f5f4a585e8
ms.collection:
- M365-security-compliance
description: 관리자는 Office 365 메시지 암호화를 사용 하 여 메시지를 암호화 하 고 암호를 해독 하는 메일 흐름 규칙 (전송 규칙)을 만드는 방법을 알 수 있습니다.
ms.openlocfilehash: a2f37bff8fa3fd45999a44341cfdb077b4f43e62
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595343"
---
# <a name="define-mail-flow-rules-to-encrypt-email-messages-in-office-365"></a><span data-ttu-id="58968-103">Office 365에서 전자 메일 메시지를 암호화하기 위한 메일의 흐름 규정을 정의</span><span class="sxs-lookup"><span data-stu-id="58968-103">Define mail flow rules to encrypt email messages in Office 365</span></span>

<span data-ttu-id="58968-104">Office 365 전역 관리자는 보내는 전자 메일 메시지를 보호 하는 데 도움이 되는 메일 흐름 규칙 (전송 규칙이 라고도 함)을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58968-104">As an Office 365 global administrator, you can create mail flow rules (also known as transport rules) to help protect email messages you send and receive.</span></span> <span data-ttu-id="58968-105">규칙을 설정 하 여 보내는 전자 메일 메시지를 암호화 하 고 조직 내부에서 전송 되는 암호화 된 메시지에서 또는 조직이 보낸 암호화 된 메시지에 대 한 암호화를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58968-105">You can set up rules to encrypt any outgoing email messages and remove encryption from encrypted messages coming from inside your organization or from replies to encrypted messages sent from your organization.</span></span> <span data-ttu-id="58968-106">EAC (Exchange 관리 센터) 또는 Exchange Online PowerShell을 사용 하 여 이러한 규칙을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58968-106">You can use the Exchange admin center (EAC) or Exchange Online PowerShell to create these rules.</span></span> <span data-ttu-id="58968-107">전체 암호화 규칙 외에도 최종 사용자에 대한 개별 메시지 암호화 옵션을 사용할지 여부를 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58968-107">In addition to overall encryption rules, you can also choose to enable or disable individual message encryption options for end-users.</span></span>

<span data-ttu-id="58968-108">조직 외부의 보낸 사람 으로부터 인바운드 메일을 암호화할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="58968-108">You can't encrypt inbound mail from senders outside of your organization.</span></span>

<span data-ttu-id="58968-109">최근에 AD RMS에서 Azure Information Protection으로 마이그레이션한 경우 기존 메일 흐름 규칙을 검토 하 여 새 환경에서 계속 작동 하는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58968-109">If you recently migrated from AD RMS to Azure Information Protection, you'll need to review your existing mail flow rules to ensure that they continue to work in your new environment.</span></span> <span data-ttu-id="58968-110">또한 Azure Information Protection을 통해 새 Office 365 메시지 암호화 (OME) 기능을 활용 하려는 경우 기존 메일 흐름 규칙을 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58968-110">Additionally, if you want to take advantage of the new Office 365 Message Encryption (OME) capabilities available to you through Azure Information Protection, you need to update your existing mail flow rules.</span></span> <span data-ttu-id="58968-111">그렇지 않으면 사용자는 새로운 OME 환경이 아닌 이전 HTML 첨부 파일 형식을 사용 하는 암호화 된 메일을 계속 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="58968-111">Otherwise, your users will continue to receive encrypted mail that uses the previous HTML attachment format instead of the new, seamless OME experience.</span></span> <span data-ttu-id="58968-112">아직 OME을 설정 하지 않은 경우 정보를 보려면 [새 Office 365 메시지 암호화 기능 설정을](set-up-new-message-encryption-capabilities.md) 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="58968-112">If you haven't set up OME yet, see [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md) for information.</span></span>

<span data-ttu-id="58968-113">메일 흐름 규칙을 만드는 구성 요소와 메일 흐름 규칙의 작동 방식에 대 한 자세한 내용은 [메일 흐름 규칙 (전송 규칙)에서 Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="58968-113">For information about the components that make up mail flow rules and how mail flow rules work, see [Mail flow rules (transport rules) in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span> <span data-ttu-id="58968-114">메일 흐름 규칙이 Azure Information Protection과 함께 작동 하는 방식에 대 한 자세한 내용은 [Azure Information protection 레이블에 대 한 Exchange Online 메일 흐름 규칙 구성을](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-exo-rules)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="58968-114">For additional information about how mail flow rules work with Azure Information Protection, see [Configuring Exchange Online mail flow rules for Azure Information Protection labels](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-exo-rules).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="58968-115">하이브리드 Exchange 환경에서는 온-프레미스 사용자가 Exchange Online을 통해 전자 메일을 라우팅하는 경우에만 OME를 사용 하 여 암호화 된 메일을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58968-115">For hybrid Exchange environments, on-premises users can send encrypted mail using OME only if email is routed through Exchange Online.</span></span> <span data-ttu-id="58968-116">하이브리드 Exchange 환경에서 OME을 구성 하려면 먼저 [하이브리드 구성 마법사를 사용 하 여 하이브리드를 구성한](https://docs.microsoft.com/Exchange/exchange-hybrid) 다음 [전자 메일 서버에서 Office 365로 메일이 전송 되도록 구성](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58968-116">To configure OME in a hybrid Exchange environment, you need to first [configure hybrid using the Hybrid Configuration wizard](https://docs.microsoft.com/Exchange/exchange-hybrid) and then [configure mail to flow from your email server to Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365).</span></span> <span data-ttu-id="58968-117">Office 365를 통해 메일이 전송 되도록 구성한 후에는이 지침을 사용 하 여 OME에 대 한 메일 흐름 규칙을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58968-117">Once you've configured mail to flow through Office 365, then you can configure mail flow rules for OME by using this guidance.</span></span>

## <a name="create-mail-flow-rules-to-encrypt-email-messages-with-the-new-ome-capabilities"></a><span data-ttu-id="58968-118">새 OME 기능을 사용 하 여 전자 메일 메시지를 암호화 하는 메일 흐름 규칙 만들기</span><span class="sxs-lookup"><span data-stu-id="58968-118">Create mail flow rules to encrypt email messages with the new OME capabilities</span></span>

<span data-ttu-id="58968-119">EAC를 사용 하 여 새 OME 기능으로 메시지 암호화를 트리거하는 메일 흐름 규칙을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58968-119">You can define mail flow rules for triggering message encryption with the new OME capabilities by using the EAC.</span></span>

### <a name="use-the-eac-to-create-a-rule-for-encrypting-email-messages-with-the-new-ome-capabilities"></a><span data-ttu-id="58968-120">EAC를 사용 하 여 새 OME 기능을 사용 하 여 전자 메일 메시지를 암호화 하는 규칙 만들기</span><span class="sxs-lookup"><span data-stu-id="58968-120">Use the EAC to create a rule for encrypting email messages with the new OME capabilities</span></span>

1. <span data-ttu-id="58968-121">웹 브라우저에서 전역 관리자 권한이 부여 된 회사 또는 학교 계정을 사용 하 여 [Office 365에 로그인](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)합니다.</span><span class="sxs-lookup"><span data-stu-id="58968-121">In a web browser, using a work or school account that has been granted global administrator permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>

2. <span data-ttu-id="58968-122">**관리** 타일을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="58968-122">Choose the **Admin** tile.</span></span>

3. <span data-ttu-id="58968-123">Microsoft 365 관리 센터에서 **관리 센터** \> **Exchange**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="58968-123">In the Microsoft 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>

4. <span data-ttu-id="58968-124">EAC에서 **메일 흐름** \> **규칙** 으로 이동 하 **고 새로** ![만들기 아이콘](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> 을 선택 하 여 **새 규칙을 만듭니다**.</span><span class="sxs-lookup"><span data-stu-id="58968-124">In the EAC, go to **Mail flow** \> **Rules** and select **New** ![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **Create a new rule**.</span></span> <span data-ttu-id="58968-125">EAC를 사용 하는 방법에 대 한 자세한 내용은 exchange [Online의 exchange 관리 센터](https://docs.microsoft.com/exchange/exchange-admin-center)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="58968-125">For more information about using the EAC, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>

5. <span data-ttu-id="58968-126">**이름**에 DrToniRamos@hotmail.com에 대 한 메일 암호화와 같은 규칙의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="58968-126">In **Name**, type a name for the rule, such as Encrypt mail for DrToniRamos@hotmail.com.</span></span>

6. <span data-ttu-id="58968-p106">**다음의 경우 이 규칙 적용**에서 조건을 선택하고 필요한 경우 값을 입력합니다. 예를 들어 DrToniRamos@hotmail.com에 보내는 메시지를 암호화하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="58968-p106">In **Apply this rule if** select a condition, and enter a value if necessary. For example, to encrypt messages going to DrToniRamos@hotmail.com:</span></span>

   1. <span data-ttu-id="58968-129">**다음의 경우 이 규칙 적용**에서 **받는 사람이 다음과 같음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="58968-129">In **Apply this rule if**, select **the recipient is**.</span></span>

   2. <span data-ttu-id="58968-130">연락처 목록에서 기존 이름을 선택하거나 **이름 확인** 상자에 새 전자 메일 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="58968-130">Select an existing name from the contact list or type a new email address in the **check names** box.</span></span>

      - <span data-ttu-id="58968-131">기존 이름을 선택하려면 목록에서 이름을 선택한 다음 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="58968-131">To select an existing name, select it from the list and then click **OK**.</span></span>

      - <span data-ttu-id="58968-132">새 이름을 입력 하려면 **이름 확인** 상자에 전자 메일 주소를 입력 하 고 **이름** \> 확인 **을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="58968-132">To enter a new name, type an email address in the **check names** box and then select **check names** \> **OK**.</span></span>

7. <span data-ttu-id="58968-133">조건을 더 추가 하려면 **기타 옵션** 을 선택한 다음 **조건 추가** 를 선택 하 고 목록에서를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="58968-133">To add more conditions, choose **More options** and then choose **add condition** and select from the list.</span></span>

   <span data-ttu-id="58968-134">예를 들어 받는 사람이 조직 외부에 있는 경우에만이 규칙을 적용 하려면 **조건 추가** 를 선택한 다음 받는 사람이 \> **조직** \> 외부에 있는 **외부/내부에** **있습니다 .를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="58968-134">For example, to apply the rule only if the recipient is outside your organization, select **add condition** and then select **The recipient is external/internal** \> **Outside the organization** \> **OK**.</span></span>

8. <span data-ttu-id="58968-135">새 OME 기능을 사용 하 여 암호화를 사용 하도록 설정 하려면 **다음 작업을 수행**하 고 **메시지 보안 수정을** 선택한 다음 **Office 365 메시지 암호화 및 권한 보호 적용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="58968-135">To enable encryption using the new OME capabilities, from **Do the following**, select **Modify the message security** and then choose **Apply Office 365 Message Encryption and rights protection**.</span></span> <span data-ttu-id="58968-136">목록에서 RMS 템플릿을 선택 하 고 **저장**을 선택한 다음 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="58968-136">Select an RMS template from the list, choose **Save**, and then choose **OK**.</span></span>
  
  <span data-ttu-id="58968-137">서식 파일 목록에는 모든 기본 서식 파일 및 옵션 뿐 아니라 Office 365에서 사용 하기 위해 만든 사용자 지정 서식 파일도 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="58968-137">The list of templates includes all default templates and options as well as any custom templates you've created for use by Office 365.</span></span> <span data-ttu-id="58968-138">목록이 비어 있으면 [새 office 365 메시지 암호화 기능 설정](set-up-new-message-encryption-capabilities.md)에 설명 된 대로 Office 365 메시지 암호화를 새로운 기능으로 설정 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="58968-138">If the list is empty, ensure that you have set up Office 365 Message Encryption with the new capabilities as described in [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).</span></span> <span data-ttu-id="58968-139">기본 서식 파일에 대 한 자세한 내용은 [Azure Information Protection의 템플릿 구성 및 관리](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="58968-139">For information about the default templates, see [Configuring and managing templates for Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates).</span></span> <span data-ttu-id="58968-140">**전달 하지** 않음 옵션에 대 한 자세한 내용은 [전자 메일에 대 한 전달 옵션 안 함](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="58968-140">For information about the **Do Not Forward** option, see [Do Not Forward option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails).</span></span> <span data-ttu-id="58968-141">**암호화 전용** 옵션에 대 한 자세한 내용은 [전자 메일에 대 한 암호화 옵션](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="58968-141">For information about the **encrypt only** option, see [Encrypt Only option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).</span></span>

  <span data-ttu-id="58968-142">다른 작업을 지정 하려는 경우 **작업 추가** 를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58968-142">You can choose **add action** if you want to specify another action.</span></span>

### <a name="use-the-eac-to-update-an-existing-mail-flow-rule-to-use-the-new-ome-capabilities"></a><span data-ttu-id="58968-143">EAC를 사용 하 여 새 OME 기능을 사용 하도록 기존 메일 흐름 규칙 업데이트</span><span class="sxs-lookup"><span data-stu-id="58968-143">Use the EAC to update an existing mail flow rule to use the new OME capabilities</span></span>

1. <span data-ttu-id="58968-144">웹 브라우저에서 전역 관리자 권한이 부여 된 회사 또는 학교 계정을 사용 하 여 [Office 365에 로그인](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)합니다.</span><span class="sxs-lookup"><span data-stu-id="58968-144">In a web browser, using a work or school account that has been granted global administrator permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>

2. <span data-ttu-id="58968-145">**관리** 타일을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="58968-145">Choose the **Admin** tile.</span></span>

3. <span data-ttu-id="58968-146">Microsoft 365 관리 센터에서 **관리 센터** \> **Exchange**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="58968-146">In the Microsoft 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>

4. <span data-ttu-id="58968-147">EAC에서 **메일 흐름** \> **규칙**으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="58968-147">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

5. <span data-ttu-id="58968-148">메일 흐름 규칙 목록에서 새 OME 기능을 사용 하도록 수정할 규칙을 선택 하 고 편집 아이콘](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) **편집** ![을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="58968-148">In the list of mail flow rules, select the rule you want to modify to use the new OME capabilities and then choose **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>

6. <span data-ttu-id="58968-149">새 OME 기능을 사용 하 여 암호화를 사용 하도록 설정 하려면 **다음 작업을 수행**하 고 **메시지 보안 수정을** 선택한 다음 **Office 365 메시지 암호화 및 권한 보호 적용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="58968-149">To enable encryption using the new OME capabilities, from **Do the following**, choose **Modify the message security** and then choose **Apply Office 365 Message Encryption and rights protection**.</span></span> <span data-ttu-id="58968-150">목록에서 RMS 템플릿을 선택 하 고 **저장** 을 선택한 다음 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="58968-150">Select an RMS template from the list, choose **Save** and then choose **OK**.</span></span>

   <span data-ttu-id="58968-151">서식 파일 목록에는 모든 기본 서식 파일 및 옵션 뿐 아니라 Office 365에서 사용 하기 위해 만든 사용자 지정 서식 파일도 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="58968-151">The list of templates includes all default templates and options as well as any custom templates you've created for use by Office 365.</span></span> <span data-ttu-id="58968-152">목록이 비어 있으면 Office 365 메시지 암호화가 [Azure Information Protection의 새로운 office 365 메시지 암호화 기능 설정](set-up-new-message-encryption-capabilities.md)에 설명 된 대로 새로운 기능을 사용 하 여 설정 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="58968-152">If the list is empty, ensure that you have set up Office 365 Message Encryption with the new capabilities as described in [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection](set-up-new-message-encryption-capabilities.md).</span></span> <span data-ttu-id="58968-153">기본 서식 파일에 대 한 자세한 내용은 [Azure Information Protection의 템플릿 구성 및 관리](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="58968-153">For information about the default templates, see [Configuring and managing templates for Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates).</span></span> <span data-ttu-id="58968-154">**전달 하지** 않음 옵션에 대 한 자세한 내용은 [전자 메일에 대 한 전달 옵션 안 함](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="58968-154">For information about the **Do Not Forward** option, see [Do Not Forward option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails).</span></span> <span data-ttu-id="58968-155">**암호화 전용** 옵션에 대 한 자세한 내용은 [전자 메일에 대 한 암호화 옵션](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="58968-155">For information about the **encrypt only** option, see [Encrypt Only option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).</span></span>

   <span data-ttu-id="58968-156">다른 작업을 지정 하려는 경우 **작업 추가** 를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58968-156">You can choose **add action** if you want to specify another action.</span></span>

7. <span data-ttu-id="58968-157">다음 작업 **수행** 목록에서 **메시지 보안** \> 을 수정 하도록 할당 된 모든 작업을 제거 하 **여 이전 버전의 OME을 적용**합니다.</span><span class="sxs-lookup"><span data-stu-id="58968-157">From the **Do the following** list, remove any actions that are assigned to **Modify the message security** \> **Apply the previous version of OME**.</span></span>

8. <span data-ttu-id="58968-158">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="58968-158">Choose **Save**.</span></span>

## <a name="create-mail-flow-rules-for-office-365-message-encryption-without-the-new-capabilities"></a><span data-ttu-id="58968-159">새 기능 없이 Office 365 메시지 암호화에 대 한 메일 흐름 규칙 만들기</span><span class="sxs-lookup"><span data-stu-id="58968-159">Create mail flow rules for Office 365 Message Encryption without the new capabilities</span></span>

<span data-ttu-id="58968-160">아직 Office 365 조 직을 새 OME 기능으로 이동 하지 않은 경우 다음 작업을 사용 하 여 조직에 대 한 메시지를 암호화 하는 메일 흐름 규칙을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="58968-160">If you haven't yet moved your Office 365 organization to the new OME capabilities, use these tasks to define mail flow rules to encrypt messages for your organization.</span></span> <span data-ttu-id="58968-161">조직에 적합 한 시기에 새 OME 기능으로 바로 이동 하는 계획을 수립 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="58968-161">Microsoft recommends that you make a plan to move to the new OME capabilities as soon as it is reasonable for your organization.</span></span> <span data-ttu-id="58968-162">자세한 내용은 [Azure Information Protection 기반으로 구축 된 새 Office 365 메시지 암호화 기능 설치](set-up-new-message-encryption-capabilities.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="58968-162">For instructions, see [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection](set-up-new-message-encryption-capabilities.md).</span></span>

### <a name="use-the-eac-to-create-a-mail-flow-rule-for-encrypting-email-messages-without-the-new-ome-capabilities"></a><span data-ttu-id="58968-163">EAC를 사용 하 여 새 OME 기능 없이 전자 메일 메시지를 암호화 하기 위한 메일 흐름 규칙 만들기</span><span class="sxs-lookup"><span data-stu-id="58968-163">Use the EAC to create a mail flow rule for encrypting email messages without the new OME capabilities</span></span>

1. <span data-ttu-id="58968-164">웹 브라우저에서 전역 관리자 권한이 부여 된 회사 또는 학교 계정을 사용 하 여 [Office 365에 로그인](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)합니다.</span><span class="sxs-lookup"><span data-stu-id="58968-164">In a web browser, using a work or school account that has been granted global administrator permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>

2. <span data-ttu-id="58968-165">**관리** 타일을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="58968-165">Choose the **Admin** tile.</span></span>

3. <span data-ttu-id="58968-166">Microsoft 365 관리 센터에서 **관리 센터** \> **Exchange**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="58968-166">In the Microsoft 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>

4. <span data-ttu-id="58968-167">EAC에서 **메일 흐름** \> **규칙** 으로 이동 하 **고 새로** ![만들기 아이콘](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> 을 선택 하 여 **새 규칙을 만듭니다**.</span><span class="sxs-lookup"><span data-stu-id="58968-167">In the EAC, go to **Mail flow** \> **Rules** and select **New** ![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **Create a new rule**.</span></span> <span data-ttu-id="58968-168">EAC를 사용 하는 방법에 대 한 자세한 내용은 exchange [Online의 exchange 관리 센터](https://docs.microsoft.com/exchange/exchange-admin-center)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="58968-168">For more information about using the EAC, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>

5. <span data-ttu-id="58968-169">**이름**에 DrToniRamos@hotmail.com에 대 한 메일 암호화와 같은 규칙의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="58968-169">In **Name**, type a name for the rule, such as Encrypt mail for DrToniRamos@hotmail.com.</span></span>

6. <span data-ttu-id="58968-p113">**다음의 경우 이 규칙 적용**에서 조건을 선택하고 필요한 경우 값을 입력합니다. 예를 들어 DrToniRamos@hotmail.com에 보내는 메시지를 암호화하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="58968-p113">In **Apply this rule if** select a condition, and enter a value if necessary. For example, to encrypt messages going to DrToniRamos@hotmail.com:</span></span>

   1. <span data-ttu-id="58968-172">**다음의 경우 이 규칙 적용**에서 **받는 사람이 다음과 같음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="58968-172">In **Apply this rule if**, select **the recipient is**.</span></span>

   2. <span data-ttu-id="58968-173">연락처 목록에서 기존 이름을 선택하거나 **이름 확인** 상자에 새 전자 메일 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="58968-173">Select an existing name from the contact list or type a new email address in the **check names** box.</span></span>

      - <span data-ttu-id="58968-174">기존 이름을 선택하려면 목록에서 이름을 선택한 다음 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="58968-174">To select an existing name, select it from the list and then click **OK**.</span></span>

      - <span data-ttu-id="58968-175">새 이름을 입력 하려면 **이름 확인** 상자에 전자 메일 주소를 입력 하 고 **이름** \> 확인 **을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="58968-175">To enter a new name, type an email address in the **check names** box and then select **check names** \> **OK**.</span></span>

7. <span data-ttu-id="58968-176">조건을 더 추가 하려면 **기타 옵션** 을 선택한 다음 **조건 추가** 를 선택 하 고 목록에서를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="58968-176">To add more conditions, choose **More options** and then select **add condition** and select from the list.</span></span>

   <span data-ttu-id="58968-177">예를 들어 받는 사람이 조직 외부에 있는 경우에만이 규칙을 적용 하려면 **조건 추가** 를 선택한 다음 받는 사람이 \> **조직** \> 외부에 있는 **외부/내부에** **있습니다 .를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="58968-177">For example, to apply the rule only if the recipient is outside your organization, select **add condition** and then select **The recipient is external/internal** \> **Outside the organization** \> **OK**.</span></span>

8. <span data-ttu-id="58968-178">새 OME 기능을 사용 하지 않고 암호화를 사용 하도록 설정 하려면 **다음 작업**에서 **메시지 보안** \> 수정을 선택 하 여 **이전 버전의 OME를 적용**한 다음 **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="58968-178">To enable encryption without using the new OME capabilities, in **Do the following**, select **Modify the message security** \> **Apply the previous version of OME**, and then choose **Save**.</span></span>

  <span data-ttu-id="58968-179">IRM 라이선싱을 사용할 수 없다는 오류가 표시 되는 경우에는 조직에 대 한 OME를 아직 설정 하지 않은 것입니다.</span><span class="sxs-lookup"><span data-stu-id="58968-179">If you receive an error that IRM licensing isn't enabled, then you haven't set up OME for your organization yet.</span></span> <span data-ttu-id="58968-180">지금 OME을 설정 하려면 새 OME 기능을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58968-180">If you'd like to set up OME now, you must set it up to use the new OME capabilities.</span></span> <span data-ttu-id="58968-181">자세한 내용은 [Azure Information Protection 기반으로 구축 된 새 Office 365 메시지 암호화 기능](set-up-new-message-encryption-capabilities.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="58968-181">For information, see [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection](set-up-new-message-encryption-capabilities.md).</span></span> <span data-ttu-id="58968-182">Microsoft에서는 새 기능 없이는 OME의 새 배포를 설정 하는 것이 더 이상 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="58968-182">Microsoft no longer supports setting up new deployments of OME without the new capabilities.</span></span>

  <span data-ttu-id="58968-183">다른 작업을 지정 하려는 경우 **작업 추가** 를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58968-183">You can choose **add action** if you want to specify another action.</span></span>

### <a name="use-exchange-online-powershell-to-create-a-mail-flow-rule-for-encrypting-email-messages-without-the-new-ome-capabilities"></a><span data-ttu-id="58968-184">Exchange Online PowerShell을 사용 하 여 새 OME 기능 없이 전자 메일 메시지를 암호화 하기 위한 메일 흐름 규칙 만들기</span><span class="sxs-lookup"><span data-stu-id="58968-184">Use Exchange Online PowerShell to create a mail flow rule for encrypting email messages without the new OME capabilities</span></span>

1. <span data-ttu-id="58968-185">Exchange Online PowerShell에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="58968-185">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="58968-186">자세한 내용은 [원격 PowerShell을 사용하여 Exchange Online에 연결](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="58968-186">For more information, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="58968-187">**New-transportrule** cmdlet을 사용 하 여 규칙을 만들고 _ApplyOME_ 매개 변수를로 `$true`설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="58968-187">Create a rule by using the **New-TransportRule** cmdlet and set the _ApplyOME_ parameter to `$true`.</span></span>

   <span data-ttu-id="58968-188">이 예에서는 DrToniRamos@hotmail.com으로 전송 되는 모든 전자 메일 메시지를 암호화 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58968-188">This example requires that all email messages sent to DrToniRamos@hotmail.com must be encrypted.</span></span>

   ```powershell
   New-TransportRule -Name "Encrypt rule for Dr Toni Ramos" -SentTo "DrToniRamos@hotmail.com" -SentToScope "NotinOrganization" -ApplyOME $true
   ```

   <span data-ttu-id="58968-189">**참고**:</span><span class="sxs-lookup"><span data-stu-id="58968-189">**Notes**:</span></span>

   - <span data-ttu-id="58968-190">새 규칙의 고유한 이름은 "Dr Toni에 대 한 암호화 규칙"입니다.</span><span class="sxs-lookup"><span data-stu-id="58968-190">The unique name of the new rule is "Encrypt rule for Dr Toni Ramos".</span></span>

   - <span data-ttu-id="58968-191">_SentTo_ 매개 변수는 메시지 받는 사람 (이름, 전자 메일 주소, 고유 이름 등으로 식별 됨)을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="58968-191">The _SentTo_ parameter specifies the message recipients (identified by name, email address, distinguished name, etc.).</span></span> <span data-ttu-id="58968-192">이 예에서는 받는 사람이 전자 메일 주소 "DrToniRamos@hotmail.com"로 식별 됩니다.</span><span class="sxs-lookup"><span data-stu-id="58968-192">In this example, the recipient is identified by the email address "DrToniRamos@hotmail.com".</span></span>

   - <span data-ttu-id="58968-193">_SentToScope_ 매개 변수는 메시지 받는 사람의 위치를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="58968-193">The _SentToScope_ parameter specifies the location of the message recipients.</span></span> <span data-ttu-id="58968-194">이 예에서는 받는 사람의 사서함이 hotmail에 있고 Office 365 조직의 일부가 아니므로 값 `NotInOrganization` 이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="58968-194">In this example, the recipient's mailbox is in hotmail and is not part of the Office 365 organization, so the value `NotInOrganization` is used.</span></span>

   <span data-ttu-id="58968-195">구문과 매개 변수에 대한 자세한 내용은 [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/New-TransportRule)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="58968-195">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/New-TransportRule).</span></span>

### <a name="remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a><span data-ttu-id="58968-196">새 OME 기능을 사용 하지 않고 암호화 된 전자 메일 회신에서 암호화 제거</span><span class="sxs-lookup"><span data-stu-id="58968-196">Remove encryption from email replies encrypted without the new OME capabilities</span></span>

<span data-ttu-id="58968-197">전자 메일 사용자가 암호화된 메시지를 보내면 해당 메시지의 받는 사람은 암호화된 회신을 통해 응답을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58968-197">When your email users send encrypted messages, recipients of those messages can respond with encrypted replies.</span></span> <span data-ttu-id="58968-198">메일 흐름 규칙을 만들면 조직의 전자 메일 사용자가 암호화 포털에 로그인 하 여 메시지를 볼 필요가 없도록 자동으로 회신에서 암호화를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58968-198">You can create mail flow rules to automatically remove encryption from replies so email users in your organization don't have to sign in to the encryption portal to view them.</span></span> <span data-ttu-id="58968-199">EAC 또는 Windows PowerShell cmdlet을 사용 하 여 이러한 규칙을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58968-199">You can use the EAC or Windows PowerShell cmdlets to define these rules.</span></span> <span data-ttu-id="58968-200">아직 새 OME 기능을 사용 하지 않는 경우 조직 내에서 전송 되거나 조직 내에서 전송 된 메시지에 회신 하는 메시지의 암호를 해독 하는 것만 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="58968-200">If you are not yet using the new OME capabilities, you can only decrypt messages that are either sent from within your organization or messages that are replies to messages sent from within your organization.</span></span> <span data-ttu-id="58968-201">조직 외부에서 보낸 암호화 된 메시지의 암호를 해독할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="58968-201">You cannot decrypt encrypted messages originating from outside of your organization.</span></span>

#### <a name="use-the-eac-to-create-a-rule-for-removing-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a><span data-ttu-id="58968-202">EAC를 사용 하 여 새 OME 기능 없이 암호화 된 전자 메일 응답에서 암호화를 제거 하는 규칙 만들기</span><span class="sxs-lookup"><span data-stu-id="58968-202">Use the EAC to create a rule for removing encryption from email replies encrypted without the new OME capabilities</span></span>

1. <span data-ttu-id="58968-203">웹 브라우저에서 관리자 권한이 부여 된 회사 또는 학교 계정을 사용 하 여 [Office 365에 로그인](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)합니다.</span><span class="sxs-lookup"><span data-stu-id="58968-203">In a web browser, using a work or school account that has been granted admin permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>

2. <span data-ttu-id="58968-204">**관리** 타일을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="58968-204">Choose the **Admin** tile.</span></span>

3. <span data-ttu-id="58968-205">Microsoft 365 관리 센터에서 **관리 센터** \> **Exchange**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="58968-205">In the Microsoft 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>

4. <span data-ttu-id="58968-206">EAC에서 **메일 흐름** \> **규칙** 으로 이동 하 **고 새로** ![만들기 아이콘](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> 을 선택 하 여 **새 규칙을 만듭니다**.</span><span class="sxs-lookup"><span data-stu-id="58968-206">In the EAC, go to **Mail flow** \> **Rules** and select **New** ![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **Create a new rule**.</span></span> <span data-ttu-id="58968-207">EAC를 사용 하는 방법에 대 한 자세한 내용은 exchange [Online의 exchange 관리 센터](https://docs.microsoft.com/exchange/exchange-admin-center)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="58968-207">For more information about using the EAC, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>

5. <span data-ttu-id="58968-208">**이름**에 규칙의 이름을 입력 합니다 (예: 받는 메일에서 암호화 제거).</span><span class="sxs-lookup"><span data-stu-id="58968-208">In **Name**, type a name for the rule, such as Remove encryption from incoming mail.</span></span>

6. <span data-ttu-id="58968-209">**다음의 경우이 규칙 적용** 에서 **받는 사람이** \> **조직 내부**에 있는 것과 같이 메시지에서 암호화를 제거 해야 하는 조건을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="58968-209">In **Apply this rule if** select the conditions where encryption should be removed from messages, such as **The recipient is located** \> **Inside the organization**.</span></span>

7. <span data-ttu-id="58968-210">**다음 작업 실행**에서 **메시지 보안** \> 수정을 선택 하 여 **이전 버전의 OME을 제거**합니다.</span><span class="sxs-lookup"><span data-stu-id="58968-210">In **Do the following**, select **Modify the message security** \> **Remove the previous version of OME**.</span></span>

8. <span data-ttu-id="58968-211">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="58968-211">Select **Save**.</span></span>

#### <a name="use-exchange-online-powershell-to-create-a-rule-to-remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a><span data-ttu-id="58968-212">Exchange Online PowerShell을 사용 하 여 새 OME 기능 없이 암호화 된 전자 메일 응답에서 암호화를 제거 하는 규칙 만들기</span><span class="sxs-lookup"><span data-stu-id="58968-212">Use Exchange Online PowerShell to create a rule to remove encryption from email replies encrypted without the new OME capabilities</span></span>

1. <span data-ttu-id="58968-213">Exchange Online PowerShell에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="58968-213">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="58968-214">자세한 내용은 [원격 PowerShell을 사용하여 Exchange Online에 연결](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="58968-214">For more information, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="58968-215">**New-transportrule** cmdlet을 사용 하 여 규칙을 만들고 _RemoveOME_ 매개 변수를로 `$true`설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="58968-215">Create a rule by using the **New-TransportRule** cmdlet and set the _RemoveOME_ parameter to `$true`.</span></span>

   <span data-ttu-id="58968-216">이 예에서는 Office 365 조직의 받는 사람에 게 전송 되는 모든 메일에서 암호화를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="58968-216">This example removes the encryption from all mail sent to recipients in the Office 365 organization.</span></span>

   ```powershell
   New-TransportRule -Name "Remove encryption from incoming mail" -SentToScope "InOrganization" -RemoveOME $true
   ```

   <span data-ttu-id="58968-217">**참고**:</span><span class="sxs-lookup"><span data-stu-id="58968-217">**Notes**:</span></span>

   - <span data-ttu-id="58968-218">새 규칙의 고유한 이름은 "받는 메일에서 암호화 제거"입니다.</span><span class="sxs-lookup"><span data-stu-id="58968-218">The unique name of the new rule is "Remove encryption from incoming mail".</span></span>

   - <span data-ttu-id="58968-219">_SentToScope_ 매개 변수는 메시지 받는 사람의 위치를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="58968-219">The _SentToScope_ parameter specifies the location of the message recipients.</span></span> <span data-ttu-id="58968-220">이 예제에서는 다음을 나타내는 `InOrganization` 값 값을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="58968-220">In this example, the value `InOrganization` value is used, which indicates:</span></span>

     - <span data-ttu-id="58968-221">받는 사람이 조직의 사서함, 메일 사용자, 그룹 또는 메일 사용이 가능한 공용 폴더인 경우</span><span class="sxs-lookup"><span data-stu-id="58968-221">The recipient is a mailbox, mail user, group, or mail-enabled public folder in your organization.</span></span>

       <span data-ttu-id="58968-222">또는</span><span class="sxs-lookup"><span data-stu-id="58968-222">or</span></span>

     - <span data-ttu-id="58968-223">받는 사람의 전자 메일 주소가 신뢰할 수 있는 도메인 이나 조직의 내부 릴레이 도메인으로 구성 된 허용 도메인에 _있으며_ , 인증 된 연결을 통해 메시지를 보내거나 받은 경우</span><span class="sxs-lookup"><span data-stu-id="58968-223">The recipient's email address is in an accepted domain that's configured as an authoritative domain or an internal relay domain in your organization, _and_ the message was sent or received over an authenticated connection.</span></span>

<span data-ttu-id="58968-224">구문과 매개 변수에 대한 자세한 내용은 [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/New-TransportRule)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="58968-224">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/New-TransportRule).</span></span>

## <a name="related-topics"></a><span data-ttu-id="58968-225">관련 주제</span><span class="sxs-lookup"><span data-stu-id="58968-225">Related Topics</span></span>

[<span data-ttu-id="58968-226">Office 365의 암호화</span><span class="sxs-lookup"><span data-stu-id="58968-226">Encryption in Office 365</span></span>](encryption.md)

[<span data-ttu-id="58968-227">새로운 Office 365 메시지 암호화 기능 설정</span><span class="sxs-lookup"><span data-stu-id="58968-227">Set up new Office 365 Message Encryption capabilities</span></span>](set-up-new-message-encryption-capabilities.md)

[<span data-ttu-id="58968-228">암호화된 메시지에 브랜딩 추가</span><span class="sxs-lookup"><span data-stu-id="58968-228">Add branding to encrypted messages</span></span>](add-your-organization-brand-to-encrypted-messages.md)

[<span data-ttu-id="58968-229">Exchange Online의 메일 흐름 규칙 (전송 규칙)</span><span class="sxs-lookup"><span data-stu-id="58968-229">Mail flow rules (transport rules) in Exchange Online</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=506707)

[<span data-ttu-id="58968-230">Exchange Online Protection의 메일 흐름 규칙(전송 규칙)</span><span class="sxs-lookup"><span data-stu-id="58968-230">Mail flow rules (transport rules) in Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=506708)
