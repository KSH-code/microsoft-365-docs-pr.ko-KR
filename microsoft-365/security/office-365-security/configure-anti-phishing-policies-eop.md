---
title: EOP에서 기본 피싱 방지 정책 구성
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 관리자는 Exchange Online 사서함을 사용 하는 Office 365 조 직의 기본 피싱 방지 정책에서 사용할 수 있는 스푸핑 방지 설정을 수정 하는 방법을 확인할 수 있습니다.
ms.openlocfilehash: 1a8527a55796910e79fbf70b824de828ca48591b
ms.sourcegitcommit: db8702cf578b02c6fd6a2670c177b456efae4748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2020
ms.locfileid: "43537536"
---
# <a name="configure-the-default-anti-phishing-policy-in-eop"></a><span data-ttu-id="2d23d-103">EOP에서 기본 피싱 방지 정책 구성</span><span class="sxs-lookup"><span data-stu-id="2d23d-103">Configure the default anti-phishing policy in EOP</span></span>

<span data-ttu-id="2d23d-104">Exchange online 사서함이 있는 Office 365 조직 및 EOP (독립 실행형 Exchange Online Protection) 조직에는 기본 피싱 방지 정책이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d23d-104">Office 365 organizations with Exchange Online mailboxes and standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes have a default anti-phishing policy.</span></span> <span data-ttu-id="2d23d-105">이 정책에는 기본적으로 사용 하도록 설정 되어 있는 제한 된 수의 스푸핑 방지 기능이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d23d-105">This policy contains a limited number of anti-spoofing features that are enabled by default.</span></span> <span data-ttu-id="2d23d-106">자세한 내용은 [피싱 방지 정책에서 스푸핑 설정을](set-up-anti-phishing-policies.md#spoof-settings)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="2d23d-106">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="2d23d-107">Office 365 Exchange Online 사서함이 있는 조직은 Office 365 보안 & 준수 센터 또는 Exchange Online PowerShell에서 기본 피싱 방지 정책을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d23d-107">Office 365 organizations with Exchange Online mailboxes can modify the default anti-phishing policy in the Office 365 Security & Compliance Center or in Exchange Online PowerShell.</span></span> <span data-ttu-id="2d23d-108">독립 실행형 EOP Exchange Online 사서함이 없는 조직은 기본 피싱 방지 정책을 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2d23d-108">Standalone EOP organizations without Exchange Online mailboxes can't modify their default anti-phishing policy.</span></span>

<span data-ttu-id="2d23d-109">Office 365 Advanced Threat Protection에서 사용할 수 있는 고급 ATP 피싱 방지 정책을 만들고 수정 하는 방법에 대 한 자세한 내용은 [office 365에서 ATP 피싱 방지 정책 구성을](configure-atp-anti-phishing-policies.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2d23d-109">For information about creating and modifying the more advanced ATP anti-phishing policies that are available in Office 365 Advanced Threat Protection, see [Configure ATP anti-phishing policies in Office 365](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="2d23d-110">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="2d23d-110">What do you need to know before you begin?</span></span>

- <span data-ttu-id="2d23d-111"><https://protection.office.com/>에서 보안 및 준수 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2d23d-111">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="2d23d-112">**피싱 방지** 페이지로 바로 이동 하려면을 사용 <https://protection.office.com/antiphishing>합니다.</span><span class="sxs-lookup"><span data-stu-id="2d23d-112">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="2d23d-113">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2d23d-113">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="2d23d-114">이 절차를 수행하려면 먼저 사용 권한을 할당받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d23d-114">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="2d23d-115">피싱 방지 정책을 추가, 수정 및 삭제 하려면 **조직 관리** 또는 **보안 관리자** 역할 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d23d-115">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="2d23d-116">피싱 방지 정책에 대 한 읽기 전용 액세스를 위해서는 **보안 독자** 역할 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d23d-116">For read-only access to anti-phishing policies, you need to be a member of the **Security Reader** role group.</span></span> <span data-ttu-id="2d23d-117">보안 및 규정 준수 센터의 역할 그룹에 대한 자세한 내용은 [Office 365 보안 및 규정 준수 센터의 사용 권한](permissions-in-the-security-and-compliance-center.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2d23d-117">For more information about role groups in the Security & Compliance Center, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="2d23d-118">기본 피싱 방지 정책에 대 한 권장 설정에 대 한 자세한 내용은 [EOP 기본 피싱 방지 정책 설정을](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="2d23d-118">For our recommended settings for the default anti-phishing policy, see [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="2d23d-119">업데이트 된 정책을 적용할 최대 30 분을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d23d-119">Allow up to 30 minutes for the updated policy to be applied.</span></span>

- <span data-ttu-id="2d23d-120">필터링 파이프라인에서 피싱 방지 정책이 적용 되는 위치에 대 한 자세한 내용은 [Office 365의 전자 메일 보호의 주문 및 우선 순위](how-policies-and-protections-are-combined.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2d23d-120">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection in Office 365](how-policies-and-protections-are-combined.md).</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a><span data-ttu-id="2d23d-121">보안 & 준수 센터를 사용 하 여 기본 피싱 방지 정책 수정</span><span class="sxs-lookup"><span data-stu-id="2d23d-121">Use the Security & Compliance Center to modify the default anti-phishing policy</span></span>

<span data-ttu-id="2d23d-122">기본 피싱 방지 정책은 Office365 AntiPhish Default로 이름이 지정 되며 정책 목록에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2d23d-122">The default anti-phishing policy is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="2d23d-123">기본 피싱 방지 정책을 수정 하려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d23d-123">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="2d23d-124">보안 & 준수 센터에서 **위협 관리** \> **정책** \> **피싱 방지**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d23d-124">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="2d23d-125">**피싱 방지** 페이지에서 **기본 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d23d-125">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="2d23d-126">**정책 편집 Office365 AntiPhish 기본값** 페이지가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="2d23d-126">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="2d23d-127">**스푸핑** 섹션에서 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d23d-127">In the **Spoof** section, click **Edit**.</span></span>

   <span data-ttu-id="2d23d-128">이러한 설정은 ATP 피싱 방지 정책에서 사용할 수 있는 스푸핑 설정과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d23d-128">Note that these settings are identical to the spoof settings that are available in ATP anti-phishing policies.</span></span>

   - <span data-ttu-id="2d23d-129">**스푸핑 필터 설정**: 기본값은 **on**이며,이 값을 유지 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2d23d-129">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="2d23d-130">해제 하려면 **토글을 끕니다.**</span><span class="sxs-lookup"><span data-stu-id="2d23d-130">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="2d23d-131">자세한 내용은 [Office 365에서 스푸핑 인텔리전스를 구성](learn-about-spoof-intelligence.md)합니다 .를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="2d23d-131">For more information, see [Configure spoof intelligence in Office 365](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="2d23d-132">MX 레코드가 Office 365를 가리키지 않으면 스푸핑 방지 보호를 사용 하지 않도록 설정할 필요가 없습니다. 대신 커넥터에 대 한 향상 된 필터링을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d23d-132">You don't need to disable anti-spoofing protection if your MX record doesn't point to Office 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="2d23d-133">자세한 내용은 [Exchange Online의 커넥터에 대 한 향상 된 필터링](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="2d23d-133">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="2d23d-134">**인증 되지 않은 보낸 사람 기능 사용**: 메시지가 전자 메일 인증 확인에 실패 하는 경우 보낸 사람의 사진에 물음표를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d23d-134">**Enable Unauthenticated Sender feature**: Adds a question mark to the sender's photo if the message fails email authentication checks.</span></span> <span data-ttu-id="2d23d-135">자세한 내용은 [피싱 방지 정책에서 스푸핑 설정을](set-up-anti-phishing-policies.md#spoof-settings)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="2d23d-135">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span> <span data-ttu-id="2d23d-136">기본값은 **설정**입니다.</span><span class="sxs-lookup"><span data-stu-id="2d23d-136">The default value is **On**.</span></span> <span data-ttu-id="2d23d-137">해제 하려면 **토글을 끕니다.**</span><span class="sxs-lookup"><span data-stu-id="2d23d-137">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="2d23d-138">**작업**: 스푸핑 인텔리전스에 실패 한 메시지에 대해 수행할 작업을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d23d-138">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="2d23d-139">**도메인을 스푸핑할 수 없는 사용자가 전자 메일을 보낸 경우**:</span><span class="sxs-lookup"><span data-stu-id="2d23d-139">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="2d23d-140">**받는 사람의 정크 메일 폴더로 메시지 이동** (이 값은 기본값입니다.)</span><span class="sxs-lookup"><span data-stu-id="2d23d-140">**Move message to the recipients' Junk Email folders** (This is the default value.)</span></span>
     - <span data-ttu-id="2d23d-141">**메시지 격리**</span><span class="sxs-lookup"><span data-stu-id="2d23d-141">**Quarantine the message**</span></span>

   - <span data-ttu-id="2d23d-142">**설정 검토**: 각 개별 단계를 클릭 하지 않고 설정이 요약으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d23d-142">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="2d23d-143">각 섹션에서 **편집** 을 클릭 하 여 관련 페이지로 다시 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d23d-143">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="2d23d-144">이 **페이지에서 다음** 설정을 직접 설정 하거나 **해제할** 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d23d-144">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="2d23d-145">**스푸핑 방지 보호 사용**</span><span class="sxs-lookup"><span data-stu-id="2d23d-145">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="2d23d-146">**인증 되지 않은 보낸 사람 기능 사용**</span><span class="sxs-lookup"><span data-stu-id="2d23d-146">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="2d23d-147">작업이 끝나면 모든 페이지에서 **저장** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d23d-147">When you're finished, click **Save** on any page.</span></span>

4. <span data-ttu-id="2d23d-148">**정책 Office365 AntiPhish 기본값 편집** 페이지에서 설정을 검토 하 고 **닫기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d23d-148">Back on the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-the-default-anti-phishing-policy"></a><span data-ttu-id="2d23d-149">보안 & 준수 센터를 사용 하 여 기본 피싱 방지 정책 보기</span><span class="sxs-lookup"><span data-stu-id="2d23d-149">Use the Security & Compliance Center to view the default anti-phishing policy</span></span>

1. <span data-ttu-id="2d23d-150">보안 & 준수 센터에서 **위협 관리** \> **정책** \> **ATP 피싱 방지**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d23d-150">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="2d23d-151">기본 **정책을** 클릭 하 여 기본 피싱 방지 정책을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d23d-151">Click **Default policy** to view the default anti-phishing policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-the-default-anti-phishing-policy"></a><span data-ttu-id="2d23d-152">Exchange Online PowerShell을 사용 하 여 기본 피싱 방지 정책 구성</span><span class="sxs-lookup"><span data-stu-id="2d23d-152">Use Exchange Online PowerShell to configure the default anti-phishing policy</span></span>

### <a name="use-powershell-to-view-the-default-anti-phish-policy"></a><span data-ttu-id="2d23d-153">PowerShell을 사용 하 여 기본 피싱 정책 보기</span><span class="sxs-lookup"><span data-stu-id="2d23d-153">Use PowerShell to view the default anti-phish policy</span></span>

<span data-ttu-id="2d23d-154">기본 피싱 정책을 보려면 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d23d-154">To view the default anti-phish policy, run the following command:</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Office365 AntiPhish Default"
```

<span data-ttu-id="2d23d-155">구문과 매개 변수에 대 한 자세한 내용은 [AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Get-AntiPhishPolicy)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="2d23d-155">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-the-default-anti-phish-policy"></a><span data-ttu-id="2d23d-156">PowerShell을 사용 하 여 기본 피싱 정책 수정</span><span class="sxs-lookup"><span data-stu-id="2d23d-156">Use PowerShell to modify the default anti-phish policy</span></span>

<span data-ttu-id="2d23d-157">기본 피싱 정책을 수정 하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d23d-157">To modify the default anti-phish policy, use the following syntax:</span></span>

```powershell
Set-AntiPhishPolicy -Identity "Office365 AntiPhish Default" [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableAntispoofEnforcement <$true | $false>] [-EnableUnauthenticatedSender <$true | $false>]
```

<span data-ttu-id="2d23d-158">이 예에서는 인증 확인에 실패 한 스푸핑된 메시지에 대 한 작업을 격리로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d23d-158">This example changes the action for spoofed messages that fail authentication checks to quarantine.</span></span>

```powershell
Set-AntiPhishPolicy -Identity "Office365 AntiPhish Default" -AuthenticationFailAction Quarantine
```

<span data-ttu-id="2d23d-159">구문 및 매개 변수에 대 한 자세한 내용은 [AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="2d23d-159">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="2d23d-160">이 절차가 제대로 수행되었는지 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="2d23d-160">How do you know these procedures worked?</span></span>

<span data-ttu-id="2d23d-161">기본 피싱 방지 정책을 성공적으로 구성 했는지 확인 하려면 다음 단계 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d23d-161">To verify that you've successfully configured the default anti-phishing policy, do any of the following steps:</span></span>

- <span data-ttu-id="2d23d-162">보안 & 준수 센터에서 **위협 관리** \> **정책** \> **피싱** \> 방지 **기본 정책을** 클릭 하 고 플라이 아웃의 세부 정보를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d23d-162">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing** \> click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="2d23d-163">Exchange Online PowerShell에서 다음 명령을 실행 하 고 설정을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d23d-163">In Exchange Online PowerShell, run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "Office365 AntiPhish Default"
  ```
