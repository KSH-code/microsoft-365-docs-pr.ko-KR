---
title: Microsoft Defender for Office 365에서 안전한 첨부 파일 정책 설정
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 078eb946-819a-4e13-8673-fe0c0ad3a775
ms.collection:
- M365-security-compliance
description: 안전한 첨부 파일 정책을 정의 하 여 전자 메일의 악의적인 파일 로부터 조직을 보호 하는 방법에 대해 알아봅니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ca0bfb7ba91f86fee187cfe3445c0dd6c8d4ad56
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48845495"
---
# <a name="set-up-safe-attachments-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="9ce8f-103">Microsoft Defender for Office 365에서 안전한 첨부 파일 정책 설정</span><span class="sxs-lookup"><span data-stu-id="9ce8f-103">Set up Safe Attachments policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> <span data-ttu-id="9ce8f-104">이 문서는 [Office 365 용 Microsoft Defender](office-365-atp.md)가 있는 비즈니스 고객을 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-104">This article is intended for business customers who have [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="9ce8f-105">Outlook에서 첨부 파일을 검색 하는 방법에 대 한 자세한 내용은 [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-105">If you're a home user looking for information about attachment scanning in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="9ce8f-106">안전한 첨부 파일은 [Microsoft Defender For Office 365](office-365-atp.md) 에서 가상 환경을 사용 하 여 [EOP (Exchange Online protection)의 맬웨어 방지 보호](anti-malware-protection.md)기능으로 검색 한 후 받는 사람에 게 배달 하기 전에 인바운드 전자 메일 메시지의 첨부 파일을 확인 하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-106">Safe Attachments is a feature in [Microsoft Defender for Office 365](office-365-atp.md) that uses a virtual environment to check attachments in inbound email messages after they've been scanned by [anti-malware protection in Exchange Online Protection (EOP)](anti-malware-protection.md), but before delivery to recipients.</span></span> <span data-ttu-id="9ce8f-107">자세한 내용은 [Office 용 Microsoft Defender 365의 안전한 첨부 파일](atp-safe-attachments.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-107">For more information, see [Safe Attachments in Microsoft Defender for Office 365](atp-safe-attachments.md).</span></span>

<span data-ttu-id="9ce8f-108">기본 제공 또는 기본 안전 첨부 파일 정책이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-108">There's no built-in or default Safe Attachments policy.</span></span> <span data-ttu-id="9ce8f-109">전자 메일 메시지 첨부 파일에 대 한 안전한 첨부 파일 검색을 받으려면이 문서에 설명 된 대로 하나 이상의 안전한 첨부 파일 정책을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-109">To get Safe Attachments scanning of email message attachments, you need to create one or more Safe Attachments policies as described in this article.</span></span>

<span data-ttu-id="9ce8f-110">보안 & 준수 센터 또는 PowerShell (exchange online에 사서함이 있는 적격 Microsoft 365 조직에 대 한 Exchange Online PowerShell, exchange online 사서함이 없는 조직의 경우 독립 실행형 EOP PowerShell, Office 365 추가 기능 구독의 경우 Defender를 사용 하 여)에서 안전한 첨부 파일 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-110">You can configure Safe Attachments policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="9ce8f-111">안전한 첨부 파일 정책의 기본 요소는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-111">The basic elements of a Safe Attachments policy are:</span></span>

- <span data-ttu-id="9ce8f-112">**안전한 첨부 파일 정책** : 알 수 없는 맬웨어 검색, 지정 된 전자 메일 주소에 맬웨어 첨부 파일을 포함 하는 메시지를 보낼지 여부 및 안전한 첨부 파일 검사를 완료할 수 없는 경우 메시지를 배달할 지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-112">**The safe attachment policy** : Specifies the actions for unknown malware detections, whether to send messages with malware attachments to a specified email address, and whether to deliver messages if Safe Attachments scanning can't complete.</span></span>
- <span data-ttu-id="9ce8f-113">**Safe 첨부 파일 규칙** : 우선 순위 및 받는 사람 필터 (정책이 적용 되는 사용자)를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-113">**The safe attachment rule** : Specifies the priority and recipient filters (who the policy applies to).</span></span>

<span data-ttu-id="9ce8f-114">보안 & 준수 센터에서 안전한 첨부 파일 정책을 관리할 때는 이러한 두 가지 요소 간의 차이가 명확 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-114">The difference between these two elements isn't obvious when you manage Safe Attachments polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="9ce8f-115">안전한 첨부 파일 정책을 만드는 경우 실제로는 둘 다에 대해 동일한 이름을 사용 하 여 안전한 첨부 파일 규칙과 연결 된 안전한 첨부 파일 정책을 동시에 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-115">When you create a Safe Attachments policy, you're actually creating a safe attachment rule and the associated safe attachment policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="9ce8f-116">안전한 첨부 파일 정책을 수정 하면 이름, 우선 순위, 사용/사용 안 함 및 받는 사람 필터와 관련 된 설정이 안전한 첨부 파일 규칙을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-116">When you modify a Safe Attachments policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe attachment rule.</span></span> <span data-ttu-id="9ce8f-117">다른 모든 설정은 연결 된 안전한 첨부 파일 정책을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-117">All other settings modify the associated safe attachment policy.</span></span>
- <span data-ttu-id="9ce8f-118">안전한 첨부 파일 정책을 제거 하면 안전한 첨부 파일 규칙과 연결 된 안전한 첨부 파일 정책이 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-118">When you remove a Safe Attachments policy, the safe attachment rule and the associated safe attachment policy are removed.</span></span>

<span data-ttu-id="9ce8f-119">Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell에서 정책과 규칙을 개별적으로 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-119">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="9ce8f-120">자세한 내용은이 문서 뒷부분에 나오는 [Exchange Online PowerShell 또는 독립 실행형 EOP powershell을 사용 하 여 안전한 첨부 파일 정책 구성](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-120">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Attachments policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) section later in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="9ce8f-121">안전한 첨부 파일 설정의 전역 설정 영역에서 안전한 첨부 파일 정책에 종속 되지 않는 기능을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-121">In the global settings area of Safe Attachments settings, you configure features that are not dependent on Safe Attachments policies.</span></span> <span data-ttu-id="9ce8f-122">지침에 대해서는 [microsoft 365 E5의](safe-docs.md) [SharePoint, OneDrive 및 Microsoft 팀 및 안전 문서에 대 한 ATP 끄기를](turn-on-atp-for-spo-odb-and-teams.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-122">For instructions see [Turn on ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md) and [Safe Documents in Microsoft 365 E5](safe-docs.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="9ce8f-123">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="9ce8f-123">What do you need to know before you begin?</span></span>

- <span data-ttu-id="9ce8f-124"><https://protection.office.com/>에서 보안 및 준수 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-124">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="9ce8f-125">**안전한 첨부 파일** 페이지로 바로 이동 하려면을 사용 <https://protection.office.com/safeattachmentv2> 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-125">To go directly to the **Safe Attachments** page, use <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="9ce8f-126">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-126">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="9ce8f-127">독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-127">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="9ce8f-128">안전한 첨부 파일 정책을 보고, 만들고, 수정 하 고, 삭제 하려면 다음 역할 그룹 중 하나의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-128">To view, create, modify, and delete Safe Attachments policies, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="9ce8f-129">[보안 및 준수 센터](permissions-in-the-security-and-compliance-center.md)의 **조직 관리** 또는 **보안 관리자**</span><span class="sxs-lookup"><span data-stu-id="9ce8f-129">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  - <span data-ttu-id="9ce8f-130">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **조직 관리**</span><span class="sxs-lookup"><span data-stu-id="9ce8f-130">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="9ce8f-131">안전한 첨부 파일 정책에 대 한 권장 설정에 대 한 자세한 내용은 [안전한 첨부 파일 설정을](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-131">For our recommended settings for Safe Attachments policies, see [Safe Attachments settings](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings).</span></span>

- <span data-ttu-id="9ce8f-132">새 정책이 나 업데이트 된 정책을 적용할 최대 30 분을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-132">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

## <a name="use-the-security--compliance-center-to-create-safe-attachments-policies"></a><span data-ttu-id="9ce8f-133">보안 & 준수 센터를 사용 하 여 안전한 첨부 파일 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="9ce8f-133">Use the Security & Compliance Center to create Safe Attachments policies</span></span>

<span data-ttu-id="9ce8f-134">보안 & 준수 센터에서 사용자 지정 안전 첨부 파일 정책을 만들면 둘 다에 대해 동일한 이름을 사용 하 여 안전한 첨부 파일 규칙과 연결 된 안전한 첨부 파일 정책이 동시에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-134">Creating a custom Safe Attachments policy in the Security & Compliance Center creates the safe attachment rule and the associated safe attachment policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="9ce8f-135">보안 & 준수 센터에서 **위협 관리** \> **정책** \> **ATP 안전한 첨부 파일로** 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-135">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="9ce8f-136">**안전한 첨부 파일** 페이지에서 **만들기** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-136">On the **Safe Attachments** page, click **Create**.</span></span>

3. <span data-ttu-id="9ce8f-137">**새 안전 첨부 파일 정책** 마법사가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-137">The **New Safe Attachments policy** wizard opens.</span></span> <span data-ttu-id="9ce8f-138">**정책 이름** 설정 페이지에서 다음 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-138">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="9ce8f-139">**이름** : 정책을 설명하는 고유한 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-139">**Name** : Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="9ce8f-140">**설명** : 정책에 대한 선택적 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-140">**Description** : Enter an optional description for the policy.</span></span>

   <span data-ttu-id="9ce8f-141">작업을 마친 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-141">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="9ce8f-142">**설정** 페이지가 나타나면 다음 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-142">On the **Settings** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="9ce8f-143">**안전한 첨부 파일 알 수 없는 맬웨어 응답** : 다음 값 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-143">**Safe Attachments unknown malware response** : Select one of the following values:</span></span>

     - <span data-ttu-id="9ce8f-144">**해제** : 일반적으로이 값을 권장 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-144">**Off** : Typically, we don't recommend this value.</span></span>
     - <span data-ttu-id="9ce8f-145">**모니터만**</span><span class="sxs-lookup"><span data-stu-id="9ce8f-145">**Monitor**</span></span>
     - <span data-ttu-id="9ce8f-146">**Block** :이 값은 기본값 이며 표준 및 엄격한 [사전 설정 보안 정책](preset-security-policies.md)에서 권장 되는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-146">**Block** : This is the default value, and the recommended value in Standard and Strict [preset security policies](preset-security-policies.md).</span></span>
     - <span data-ttu-id="9ce8f-147">**바꾸기**</span><span class="sxs-lookup"><span data-stu-id="9ce8f-147">**Replace**</span></span>
     - <span data-ttu-id="9ce8f-148">**동적 배달 (미리 보기 기능)**</span><span class="sxs-lookup"><span data-stu-id="9ce8f-148">**Dynamic Delivery (Preview Feature)**</span></span>

     <span data-ttu-id="9ce8f-149">이러한 값은 [안전한 첨부 파일 정책 설정](atp-safe-attachments.md#safe-attachments-policy-settings)에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-149">These values are explained in [Safe Attachments policy settings](atp-safe-attachments.md#safe-attachments-policy-settings).</span></span>

   - <span data-ttu-id="9ce8f-150">**첨부 파일을 다음 전자 메일 주소로 보내기** : 작업 값 **차단** , **모니터** 또는 **바꾸기** 에 대해 **리디렉션 사용** 을 선택 하 여 분석 및 조사를 위해 지정 된 내부 또는 외부 전자 메일 주소에 맬웨어 첨부 파일이 포함 된 메시지를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-150">**Send the attachment to the following email address** : For the action values **Block** , **Monitor** , or **Replace** , you can select **Enable redirect** to send messages that contain malware attachments to the specified internal or external email address for analysis and investigation.</span></span>

     <span data-ttu-id="9ce8f-151">표준 및 엄격한 정책 설정에 대 한 권장 사항은 리디렉션을 사용 하도록 설정 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-151">The recommendation for Standard and Strict policy settings is to enable redirection.</span></span> <span data-ttu-id="9ce8f-152">자세한 내용은 [안전한 첨부 파일 설정을](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-152">For more information, see [Safe Attachments settings](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings).</span></span>

   - <span data-ttu-id="9ce8f-153">**첨부 파일에 대 한 맬웨어 검사 시간이 초과 되거나 오류가 발생 하면 위의 선택 사항을 적용** 합니다. **안전한** 첨부 파일에서 지정한 작업은 안전한 첨부 파일 검색을 완료할 수 없는 경우에도 메시지에 대해 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-153">**Apply the above selection if malware scanning for attachments times out or error occurs** : The action specified by **Safe Attachments unknown malware response** is taken on messages even when Safe Attachments scanning can't complete.</span></span> <span data-ttu-id="9ce8f-154">**사용 리디렉션을** 선택 하는 경우 항상이 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-154">Always select this option if you select **Enabled redirect**.</span></span> <span data-ttu-id="9ce8f-155">그렇지 않으면 메시지가 손실 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-155">Otherwise, messages might be lost.</span></span>

   <span data-ttu-id="9ce8f-156">작업을 마친 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-156">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="9ce8f-157">**적용 대상** 페이지에서 정책이 적용 되는 내부 받는 사람을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-157">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="9ce8f-158">조건이나 예외는 한 번만 사용할 수 있지만, 조건이나 예외에 대한 값을 여러 개 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-158">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="9ce8f-159">동일한 조건의 여러 값이나 예외는 OR 논리를 사용합니다(예: _\<recipient1\>_ 혹은 _\<recipient2\>_ ).</span><span class="sxs-lookup"><span data-stu-id="9ce8f-159">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_ ).</span></span> <span data-ttu-id="9ce8f-160">다양한 조건이나 예외는 AND 논리를 사용합니다(예: _\<recipient1\>_ 및 _\<member of group 1\>_ ).</span><span class="sxs-lookup"><span data-stu-id="9ce8f-160">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_ ).</span></span>

   <span data-ttu-id="9ce8f-161">**조건 추가를** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-161">Click **Add a condition**.</span></span> <span data-ttu-id="9ce8f-162">표시 되는 드롭다운 목록에서 다음의 **경우 적용** 아래의 조건을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-162">In the dropdown that appears, select a condition under **Applied if** :</span></span>

   - <span data-ttu-id="9ce8f-163">**받는 사람** : 조직의 사서함, 메일 사용자 또는 메일 연락처를 하나 이상 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-163">**The recipient is** : Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="9ce8f-164">**받는 사람이 다음 구성원 인** 경우: 조직에서 그룹을 하나 이상 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-164">**The recipient is a member of** : Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="9ce8f-165">**받는 사람 도메인은** 조직에서 구성된 허용 도메인 중 하나 이상에서 받는 사람을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-165">**The recipient domain is** : Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="9ce8f-166">조건을 선택한 후에는 **이러한 상자 중 하나** 에 해당 하는 dropdown이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-166">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="9ce8f-167">상자를 클릭 하 고 선택할 값 목록을 스크롤합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-167">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="9ce8f-168">상자를 클릭 하 고 입력을 시작 하 여 목록을 필터링 하 고 값을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-168">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="9ce8f-169">값을 더 추가 하려면 상자에서 빈 영역을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-169">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="9ce8f-170">개별 항목을 제거 하려면 값에서 제거 아이콘 **제거** 를 클릭 ![ ](../../media/scc-remove-icon.png) 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-170">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="9ce8f-171">전체 조건을 제거 하려면 **Remove** ![ 조건에서 제거 아이콘 제거를 클릭 ](../../media/scc-remove-icon.png) 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-171">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="9ce8f-172">조건을 더 추가 하려면 **조건 추가** 를 클릭 하 고 **적용 된 경우** 에는 나머지 값을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-172">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="9ce8f-173">예외를 추가 하려면 **조건 추가** 를 클릭 하 고 다음의 **경우 제외** 에서 예외를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-173">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="9ce8f-174">설정 및 동작은 조건과 정확히 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-174">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="9ce8f-175">작업을 마친 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-175">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="9ce8f-176">**설정 검토** 페이지가 나타나면 설정을 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-176">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="9ce8f-177">각 설정에 대해 **편집** 을 클릭 하 여 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-177">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="9ce8f-178">작업이 완료 되 면 **마침을** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-178">When you're finished, click **Finish**.</span></span>

## <a name="use-the-security--compliance-center-to-view-safe-attachments-policies"></a><span data-ttu-id="9ce8f-179">보안 & 준수 센터를 사용 하 여 안전한 첨부 파일 정책 보기</span><span class="sxs-lookup"><span data-stu-id="9ce8f-179">Use the Security & Compliance Center to view Safe Attachments policies</span></span>

1. <span data-ttu-id="9ce8f-180">보안 & 준수 센터에서 **위협 관리** \> **정책** \> **ATP 안전한 첨부 파일로** 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-180">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="9ce8f-181">**안전한 첨부 파일** 페이지의 목록에서 정책을 선택 하 고 다음을 클릭 합니다 (확인란을 선택 하지 않음).</span><span class="sxs-lookup"><span data-stu-id="9ce8f-181">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

   <span data-ttu-id="9ce8f-182">정책 세부 정보가 플라이 아웃에 표시 됨</span><span class="sxs-lookup"><span data-stu-id="9ce8f-182">The policy details appear in a fly out</span></span>

## <a name="use-the-security--compliance-center-to-modify-safe-attachments-policies"></a><span data-ttu-id="9ce8f-183">보안 & 준수 센터를 사용 하 여 안전한 첨부 파일 정책 수정</span><span class="sxs-lookup"><span data-stu-id="9ce8f-183">Use the Security & Compliance Center to modify Safe Attachments policies</span></span>

1. <span data-ttu-id="9ce8f-184">보안 & 준수 센터에서 **위협 관리** \> **정책** \> **ATP 안전한 첨부 파일로** 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-184">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="9ce8f-185">**안전한 첨부 파일** 페이지의 목록에서 정책을 선택 하 고 다음을 클릭 합니다 (확인란을 선택 하지 않음).</span><span class="sxs-lookup"><span data-stu-id="9ce8f-185">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="9ce8f-186">정책 세부 정보가 표시 되 면 **정책 편집** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-186">In the policy details fly out that appears, click **Edit policy**.</span></span>

<span data-ttu-id="9ce8f-187">즉시 표시 되는 사용 가능한 설정은 [보안 & 준수 센터를 사용 하 여 안전한 첨부 파일 정책 만들기](#use-the-security--compliance-center-to-create-safe-attachments-policies) 섹션에 설명 된 설정과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-187">The available settings in the fly out that appears are identical to those described in the [Use the Security & Compliance Center to create Safe Attachments policies](#use-the-security--compliance-center-to-create-safe-attachments-policies) section.</span></span>

<span data-ttu-id="9ce8f-188">정책을 사용 하거나 사용 하지 않도록 설정 하려면 다음 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-188">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-attachments-policies"></a><span data-ttu-id="9ce8f-189">안전한 첨부 파일 정책 사용 또는 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="9ce8f-189">Enable or disable Safe Attachments policies</span></span>

1. <span data-ttu-id="9ce8f-190">보안 & 준수 센터에서 **위협 관리** \> **정책** \> **ATP 안전한 첨부 파일로** 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-190">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="9ce8f-191">**상태** 열에서 다음 값을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-191">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="9ce8f-192">왼쪽으로 토글</span><span class="sxs-lookup"><span data-stu-id="9ce8f-192">Move the toggle to the left</span></span> ![정책 해제](../../media/scc-toggle-off.png) <span data-ttu-id="9ce8f-194">정책을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-194">to disable the policy.</span></span>

   - <span data-ttu-id="9ce8f-195">오른쪽으로 토글</span><span class="sxs-lookup"><span data-stu-id="9ce8f-195">Move the toggle to the right</span></span> ![정책 설정](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) <span data-ttu-id="9ce8f-197">정책을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-197">to enable the policy.</span></span>

### <a name="set-the-priority-of-safe-attachments-policies"></a><span data-ttu-id="9ce8f-198">안전한 첨부 파일 정책의 우선 순위 설정</span><span class="sxs-lookup"><span data-stu-id="9ce8f-198">Set the priority of Safe Attachments policies</span></span>

<span data-ttu-id="9ce8f-199">기본적으로 안전한 첨부 파일 정책에는 만들어진 순서를 기준으로 하는 우선 순위가 지정 됩니다 (최신 정책은 이전 정책 보다 낮은 우선 순위).</span><span class="sxs-lookup"><span data-stu-id="9ce8f-199">By default, Safe Attachments policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="9ce8f-200">낮은 우선순위 번호는 정책의 높은 우선순위(0이 가장 높음)를 나타내고 정책은 우선순위 순서에 따라 처리됩니다(높은 우선순위 정책은 낮은 우선순위 정책보다 먼저 처리됨).</span><span class="sxs-lookup"><span data-stu-id="9ce8f-200">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="9ce8f-201">두 정책의 우선순위는 동일 할 수 없으며, 첫 번째 정책이 적용된 후에는 정책 처리가 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-201">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="9ce8f-202">우선순위 및 여러 정책을 평가하고 적용하는 방법에 대 한 자세한 내용은 전자 메일의 [전자 메일의 우선순위 및 보호](how-policies-and-protections-are-combined.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-202">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="9ce8f-203">안전한 첨부 파일 정책은 처리 되는 순서 대로 표시 됩니다 (첫 번째 정책의 **우선 순위** 값은 0).</span><span class="sxs-lookup"><span data-stu-id="9ce8f-203">Safe Attachments policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span>

<span data-ttu-id="9ce8f-204">**참고** : 보안 & 준수 센터에서는 안전한 첨부 파일 정책의 우선 순위를 만든 후에만 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-204">**Note** : In the Security & Compliance Center, you can only change the priority of the Safe Attachments policy after you create it.</span></span> <span data-ttu-id="9ce8f-205">PowerShell에서는 안전한 첨부 파일 규칙을 만들 때 기본 우선 순위를 무시할 수 있습니다 (기존 규칙의 우선 순위에 영향을 줄 수 있음).</span><span class="sxs-lookup"><span data-stu-id="9ce8f-205">In PowerShell, you can override the default priority when you create the safe attachment rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="9ce8f-206">정책의 우선순위를 변경하려면 목록에서 정책을 위나 아래로 이동합니다. 보안 및 준수 센터에서 **우선순위** 번호를 직접 수정할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-206">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="9ce8f-207">보안 & 준수 센터에서 **위협 관리** \> **정책** \> **ATP 안전한 첨부 파일로** 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-207">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="9ce8f-208">**안전한 첨부 파일** 페이지의 목록에서 정책을 선택 하 고 다음을 클릭 합니다 (확인란을 선택 하지 않음).</span><span class="sxs-lookup"><span data-stu-id="9ce8f-208">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="9ce8f-209">정책 세부 정보가 표시 되 면 사용 가능한 우선 순위 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-209">In the policy details fly out that appears, click the available priority button.</span></span>

   - <span data-ttu-id="9ce8f-210">**우선 순위** 값이 **0** 인 안전 첨부 파일 정책에는 **우선 순위 낮추기** 단추만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-210">The Safe Attachments policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="9ce8f-211">**우선 순위** 값이 가장 낮은 안전한 첨부 파일 정책 (예: **3** )에는 **우선 순위 향상** 단추만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-211">The Safe Attachments policy with the lowest **Priority** value (for example, **3** ) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="9ce8f-212">안전한 첨부 파일 정책이 셋 이상인 경우 가장 높거나 낮은 우선 순위 값 사이의 정책에는 **우선 순위 증가** 와 **우선 순위 낮추기** 단추가 모두 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-212">If you have three or more Safe Attachments policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="9ce8f-213">우선 **순위 높임** 또는 **우선 순위 낮추기** 를 클릭 하 여 **우선 순위** 값을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-213">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="9ce8f-214">작업을 마쳤으면 **닫기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-214">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-safe-attachments-policies"></a><span data-ttu-id="9ce8f-215">보안 & 준수 센터를 사용 하 여 안전한 첨부 파일 정책 제거</span><span class="sxs-lookup"><span data-stu-id="9ce8f-215">Use the Security & Compliance Center to remove Safe Attachments policies</span></span>

1. <span data-ttu-id="9ce8f-216">보안 & 준수 센터에서 **위협 관리** \> **정책** \> **ATP 안전한 첨부 파일로** 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-216">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="9ce8f-217">**안전한 첨부 파일** 페이지의 목록에서 정책을 선택 하 고 다음을 클릭 합니다 (확인란을 선택 하지 않음).</span><span class="sxs-lookup"><span data-stu-id="9ce8f-217">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="9ce8f-218">정책 세부 정보가 표시 되 면 **정책 삭제** 를 클릭 한 다음 표시 되는 경고 대화 상자에서 **예** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-218">In the policy details fly out that appears, click **Delete policy** , and then click **Yes** in the warning dialog that appears.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies"></a><span data-ttu-id="9ce8f-219">Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell을 사용 하 여 안전한 첨부 파일 정책 구성</span><span class="sxs-lookup"><span data-stu-id="9ce8f-219">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Attachments policies</span></span>

<span data-ttu-id="9ce8f-220">앞에서 설명한 것 처럼 안전한 첨부 파일 정책은 안전한 첨부 파일 정책 및 안전한 첨부 파일 규칙으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-220">As previously described, a Safe Attachments policy consists of a safe attachment policy and a safe attachment rule.</span></span>

<span data-ttu-id="9ce8f-221">PowerShell에서는 안전한 첨부 파일 정책 및 안전한 첨부 파일 규칙 간의 차이가 명백 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-221">In PowerShell, the difference between safe attachment policies and safe attachment rules is apparent.</span></span> <span data-ttu-id="9ce8f-222">**\* -Get-safeattachmentpolicy** cmdlet을 사용 하 여 안전한 첨부 파일 정책을 관리 하 고 **\* -disable-safeattachmentrule** cmdlet을 사용 하 여 안전한 첨부 파일 규칙을 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-222">You manage safe attachment policies by using the **\*-SafeAttachmentPolicy** cmdlets, and you manage safe attachment rules by using the **\*-SafeAttachmentRule** cmdlets.</span></span>

- <span data-ttu-id="9ce8f-223">PowerShell에서는 먼저 안전한 첨부 파일 정책을 만든 다음 규칙이 적용 되는 정책을 식별 하는 수신 허용-첨부 파일 규칙을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-223">In PowerShell, you create the safe attachment policy first, then you create the safe attachment rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="9ce8f-224">PowerShell에서는 안전한 첨부 파일 정책 및 안전한 첨부 파일 규칙의 설정을 개별적으로 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-224">In PowerShell, you modify the settings in the safe attachment policy and the safe attachment rule separately.</span></span>
- <span data-ttu-id="9ce8f-225">PowerShell에서 안전한 첨부 파일 정책을 제거 하면 해당 하는 안전 첨부 파일 규칙이 자동으로 제거 되지 않으며 그 반대의 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-225">When you remove a safe attachment policy from PowerShell, the corresponding safe attachment rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-attachments-policies"></a><span data-ttu-id="9ce8f-226">PowerShell을 사용 하 여 안전한 첨부 파일 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="9ce8f-226">Use PowerShell to create Safe Attachments policies</span></span>

<span data-ttu-id="9ce8f-227">PowerShell에서 안전한 첨부 파일 정책을 만드는 과정은 두 단계로 진행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-227">Creating a Safe Attachments policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="9ce8f-228">안전한 첨부 파일 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-228">Create the safe attachment policy.</span></span>
2. <span data-ttu-id="9ce8f-229">규칙이 적용 되는 안전한 첨부 파일 정책을 지정 하는 안전한 첨부 파일 규칙을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-229">Create the safe attachment rule that specifies the safe attachment policy that the rule applies to.</span></span>

 <span data-ttu-id="9ce8f-230">**참고** :</span><span class="sxs-lookup"><span data-stu-id="9ce8f-230">**Notes** :</span></span>

- <span data-ttu-id="9ce8f-231">안전한 첨부 파일 규칙을 새로 만들고 연결 되지 않은 기존 안전한 첨부 파일 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-231">You can create a new safe attachment rule and assign an existing, unassociated safe attachment policy to it.</span></span> <span data-ttu-id="9ce8f-232">안전한 첨부 파일 규칙은 둘 이상의 안전한 첨부 파일 정책에 연결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-232">A safe attachment rule can't be associated with more than one safe attachment policy.</span></span>

- <span data-ttu-id="9ce8f-233">정책을 만든 후에 야 보안 & 준수 센터에서 사용할 수 없는 PowerShell의 새 안전 첨부 파일 정책에 대해 다음 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-233">You can configure the following settings on new safe attachment policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>
  - <span data-ttu-id="9ce8f-234">Disable-safeattachmentrule cmdlet에서 _사용 하도록 설정_ 된 새 정책을 사용 하지 않도록 설정 `$false` **New-SafeAttachmentRule** 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-234">Create the new policy as disabled ( _Enabled_ `$false` on the **New-SafeAttachmentRule** cmdlet).</span></span>
  - <span data-ttu-id="9ce8f-235">Disable-safeattachmentrule cmdlet에 대 한 생성 ( _우선 순위_ ) 중에 정책의 우선 순위를 설정 _\<Number\>_ 합니다. **New-SafeAttachmentRule**</span><span class="sxs-lookup"><span data-stu-id="9ce8f-235">Set the priority of the policy during creation ( _Priority_ _\<Number\>_ ) on the **New-SafeAttachmentRule** cmdlet).</span></span>

- <span data-ttu-id="9ce8f-236">안전한 첨부 파일 규칙에 정책을 할당 해야 PowerShell에서 만든 새 안전한 첨부 파일 정책이 보안 & 준수 센터에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-236">A new safe attachment policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a safe attachment rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-attachment-policy"></a><span data-ttu-id="9ce8f-237">1 단계: PowerShell을 사용 하 여 안전한 첨부 파일 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="9ce8f-237">Step 1: Use PowerShell to create a safe attachment policy</span></span>

<span data-ttu-id="9ce8f-238">안전한 첨부 파일 정책을 만들려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-238">To create a safe attachment policy, use this syntax:</span></span>

```PowerShell
New-SafeAttachmentPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-Action <Allow | Block | Replace | DynamicDelivery>] [-Redirect <$true | $false>] [-RedirectAddress <SMTPEmailAddress>] [-ActionOnError <$true | $false>]
```

<span data-ttu-id="9ce8f-239">이 예에서는 다음 값을 사용 하 여 Contoso All 이라는 안전한 첨부 파일 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-239">This example creates a safe attachment policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="9ce8f-240">안전한 문서 검색을 통해 맬웨어가 포함 되도록 찾은 메시지 차단 ( _Action_ 매개 변수를 사용 하지 않으며 기본값은 is `Block` )</span><span class="sxs-lookup"><span data-stu-id="9ce8f-240">Block messages that are found to contain malware by Safe Documents scanning (we aren't using the _Action_ parameter, and the default value is `Block`).</span></span>
- <span data-ttu-id="9ce8f-241">리디렉션이 사용 되 고 맬웨어를 포함 하는 메시지는 분석 및 조사를 위해 sec-ops@contoso.com로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-241">Redirection is enabled, and messages that are found to contain malware are sent to sec-ops@contoso.com for analysis and investigation.</span></span>
- <span data-ttu-id="9ce8f-242">안전한 첨부 파일 검색을 사용할 수 없거나 오류가 발생할 경우 메시지를 배달 하지 않습니다 ( _Actiononerror_ 매개 변수를 사용 하지 않으며 기본값은 is `$true` ).</span><span class="sxs-lookup"><span data-stu-id="9ce8f-242">If Safe Attachments scanning isn't available or encounters errors, don't deliver the message (we aren't using the _ActionOnError_ parameter, and the default value is `$true`).</span></span>

```PowerShell
New-SafeAttachmentPolicy -Name "Contoso All" -Redirect $true -RedirectAddress sec-ops@contoso.com
```

<span data-ttu-id="9ce8f-243">구문과 매개 변수에 대 한 자세한 내용은 [get-safeattachmentpolicy](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentpolicy)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-243">For detailed syntax and parameter information, see [New-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-attachment-rule"></a><span data-ttu-id="9ce8f-244">2 단계: PowerShell을 사용 하 여 안전한 첨부 파일 규칙 만들기</span><span class="sxs-lookup"><span data-stu-id="9ce8f-244">Step 2: Use PowerShell to create a safe attachment rule</span></span>

<span data-ttu-id="9ce8f-245">안전한 첨부 파일 규칙을 만들려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-245">To create a safe attachment rule, use this syntax:</span></span>

```PowerShell
New-SafeAttachmentRule -Name "<RuleName>" -SafeAttachmentPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="9ce8f-246">이 예에서는 다음과 같은 조건을 가진 Contoso All 이라는 안전한 첨부 파일 규칙을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-246">This example creates a safe attachment rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="9ce8f-247">이 규칙은 Contoso All 이라는 안전한 첨부 파일 정책에 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-247">The rule is associated with the safe attachment policy named Contoso All.</span></span>
- <span data-ttu-id="9ce8f-248">규칙은 contoso.com 도메인의 모든 받는 사람에 게 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-248">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="9ce8f-249">_Priority_ 매개 변수를 사용 하지 않으므로 기본 우선 순위가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-249">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="9ce8f-250">이 규칙이 사용 하도록 설정 되어 있습니다 ( _enabled_ 매개 변수를 사용 하지 않으며 기본값은 `$true` ).</span><span class="sxs-lookup"><span data-stu-id="9ce8f-250">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeAttachmentRule -Name "Contoso All" -SafeAttachmentPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="9ce8f-251">구문과 매개 변수에 대 한 자세한 내용은 [disable-safeattachmentrule](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentrule)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-251">For detailed syntax and parameter information, see [New-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentrule).</span></span>

### <a name="use-powershell-to-view-safe-attachment-policies"></a><span data-ttu-id="9ce8f-252">PowerShell을 사용 하 여 안전한 첨부 파일 정책 보기</span><span class="sxs-lookup"><span data-stu-id="9ce8f-252">Use PowerShell to view safe attachment policies</span></span>

<span data-ttu-id="9ce8f-253">기존의 안전한 첨부 파일 정책을 보려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-253">To view existing safe attachment policies, use the following syntax:</span></span>

```PowerShell
Get-SafeAttachmentPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="9ce8f-254">이 예에서는 모든 안전 첨부 파일 정책의 요약 목록을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-254">This example returns a summary list of all safe attachment policies.</span></span>

```PowerShell
Get-SafeAttachmentPolicy
```

<span data-ttu-id="9ce8f-255">이 예에서는 Contoso 임원 이라는 안전한 첨부 파일 정책에 대 한 자세한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-255">This example returns detailed information for the safe attachment policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeAttachmentPolicy -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="9ce8f-256">구문과 매개 변수에 대 한 자세한 내용은 [get-safeattachmentpolicy](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentpolicy)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-256">For detailed syntax and parameter information, see [Get-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-view-safe-attachment-rules"></a><span data-ttu-id="9ce8f-257">PowerShell을 사용 하 여 안전한 첨부 파일 규칙 보기</span><span class="sxs-lookup"><span data-stu-id="9ce8f-257">Use PowerShell to view safe attachment rules</span></span>

<span data-ttu-id="9ce8f-258">기존의 안전한 첨부 파일 규칙을 보려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-258">To view existing safe attachment rules, use the following syntax:</span></span>

```PowerShell
Get-SafeAttachmentRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="9ce8f-259">이 예에서는 모든 안전 첨부 파일 규칙의 요약 목록을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-259">This example returns a summary list of all safe attachment rules.</span></span>

```PowerShell
Get-SafeAttachmentRule
```

<span data-ttu-id="9ce8f-260">활성화된 또는 비활성화된 규칙을 기준으로 목록을 필터링하려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-260">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeAttachmentRule -State Disabled
```

```PowerShell
Get-SafeAttachmentRule -State Enabled
```

<span data-ttu-id="9ce8f-261">이 예에서는 Contoso 임원 이라는 안전한 첨부 파일 규칙에 대 한 자세한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-261">This example returns detailed information for the safe attachment rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeAttachmentRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="9ce8f-262">구문과 매개 변수에 대 한 자세한 내용은 [disable-safeattachmentrule](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentrule)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-262">For detailed syntax and parameter information, see [Get-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentrule).</span></span>

### <a name="use-powershell-to-modify-safe-attachment-policies"></a><span data-ttu-id="9ce8f-263">PowerShell을 사용 하 여 안전한 첨부 파일 정책 수정</span><span class="sxs-lookup"><span data-stu-id="9ce8f-263">Use PowerShell to modify safe attachment policies</span></span>

<span data-ttu-id="9ce8f-264">PowerShell에서 안전한 첨부 파일 정책의 이름을 바꿀 수는 없습니다 (Get-safeattachmentpolicy cmdlet은 _Name_ 매개 변수를 **사용** 하지 않음).</span><span class="sxs-lookup"><span data-stu-id="9ce8f-264">You can't rename a safe attachment policy in PowerShell (the **Set-SafeAttachmentPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="9ce8f-265">보안 & 준수 센터에서 안전 첨부 파일 정책의 이름을 바꾸면 안전한 첨부 파일 _규칙만_ 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-265">When you rename a Safe Attachments policy in the Security & Compliance Center, you're only renaming the safe attachment _rule_.</span></span>

<span data-ttu-id="9ce8f-266">그렇지 않은 경우에는이 문서의 앞부분에 나오는 [1 단계: PowerShell을 사용 하 여 안전한 첨부 파일 정책 만들기](#step-1-use-powershell-to-create-a-safe-attachment-policy) 섹션에 설명 된 대로 안전한 첨부 파일 정책을 만드는 경우에도 동일한 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-266">Otherwise, the same settings are available when you create a safe attachment policy as described in the [Step 1: Use PowerShell to create a safe attachment policy](#step-1-use-powershell-to-create-a-safe-attachment-policy) section earlier in this article.</span></span>

<span data-ttu-id="9ce8f-267">안전한 첨부 파일 정책을 수정 하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-267">To modify a safe attachment policy, use this syntax:</span></span>

```PowerShell
Set-SafeAttachmentPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="9ce8f-268">구문 및 매개 변수에 대 한 자세한 내용은 [get-safeattachmentpolicy](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentpolicy)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-268">For detailed syntax and parameter information, see [Set-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-modify-safe-attachment-rules"></a><span data-ttu-id="9ce8f-269">PowerShell을 사용 하 여 안전한 첨부 파일 규칙 수정</span><span class="sxs-lookup"><span data-stu-id="9ce8f-269">Use PowerShell to modify safe attachment rules</span></span>

<span data-ttu-id="9ce8f-270">PowerShell에서 안전한 첨부 파일 규칙을 수정할 때 사용할 수 없는 유일한 설정은 사용 하지 않도록 설정 된 규칙을 만들 수 있는 _Enabled_ 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-270">The only setting that's not available when you modify a safe attachment rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="9ce8f-271">기존의 안전한 첨부 파일 규칙을 사용 하거나 사용 하지 않도록 설정 하려면 다음 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-271">To enable or disable existing safe attachment rules, see the next section.</span></span>

<span data-ttu-id="9ce8f-272">그렇지 않은 경우에는이 문서의 앞부분에 나오는 [2 단계: PowerShell을 사용 하 여 안전한 첨부 파일 규칙 만들기](#step-2-use-powershell-to-create-a-safe-attachment-rule) 섹션에 설명 된 대로 규칙을 만들 때도 같은 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-272">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe attachment rule](#step-2-use-powershell-to-create-a-safe-attachment-rule) section earlier in this article.</span></span>

<span data-ttu-id="9ce8f-273">안전한 첨부 파일 규칙을 수정 하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-273">To modify a safe attachment rule, use this syntax:</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="9ce8f-274">구문 및 매개 변수에 대 한 자세한 내용은 [disable-safeattachmentrule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-274">For detailed syntax and parameter information, see [Set-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-attachment-rules"></a><span data-ttu-id="9ce8f-275">PowerShell을 사용 하 여 안전한 첨부 파일 규칙을 사용 하거나 사용 하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="9ce8f-275">Use PowerShell to enable or disable safe attachment rules</span></span>

<span data-ttu-id="9ce8f-276">PowerShell에서 안전한 첨부 파일 규칙을 사용 하거나 사용 하지 않도록 설정 하면 전체 안전 첨부 파일 정책 (안전한 첨부 파일 규칙 및 할당 된 안전한 첨부 파일 정책)을 사용 하거나 사용 하지 않도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-276">Enabling or disabling a safe attachment rule in PowerShell enables or disables the whole Safe Attachments policy (the safe attachment rule and the assigned safe attachment policy).</span></span>

<span data-ttu-id="9ce8f-277">PowerShell에서 안전한 첨부 파일 규칙을 사용 하거나 사용 하지 않도록 설정 하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-277">To enable or disable a safe attachment rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeAttachmentRule | Disable-SafeAttachmentRule> -Identity "<RuleName>"
```

<span data-ttu-id="9ce8f-278">이 예에서는 Marketing 부서 라는 안전한 첨부 파일 규칙을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-278">This example disables the safe attachment rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="9ce8f-279">다음은 동일한 규칙을 사용하도록 설정하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-279">This example enables same rule.</span></span>

```PowerShell
Enable-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="9ce8f-280">구문 및 매개 변수에 대 한 자세한 내용은 [Enable-disable-safeattachmentrule](https://docs.microsoft.com/powershell/module/exchange/enable-safeattachmentrule) 및 [Disable-disable-safeattachmentrule](https://docs.microsoft.com/powershell/module/exchange/disable-safeattachmentrule)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-280">For detailed syntax and parameter information, see [Enable-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/enable-safeattachmentrule) and [Disable-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/disable-safeattachmentrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-attachment-rules"></a><span data-ttu-id="9ce8f-281">PowerShell을 사용 하 여 안전한 첨부 파일 규칙의 우선 순위 설정</span><span class="sxs-lookup"><span data-stu-id="9ce8f-281">Use PowerShell to set the priority of safe attachment rules</span></span>

<span data-ttu-id="9ce8f-282">규칙에 설정 가능한 가장 높은 우선 순위 값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-282">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="9ce8f-283">설정할 수 있는 가장 낮은 값은 규칙 수에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-283">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="9ce8f-284">예를 들어 규칙이 5개 있는 경우, 우선순위 값 0~4를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-284">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="9ce8f-285">기존 규칙의 우선순위를 변경하면 다른 규칙에 계단식 효과를 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-285">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="9ce8f-286">예를 들어 사용자 지정 규칙 5개(우선순위: 0~4)가 있고 규칙의 우선순위를 2로 변경하면, 우선순위 2인 기존 규칙이 우선순위 3으로 변경되고, 우선순위 3인 규칙이 우선순위 4로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-286">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="9ce8f-287">PowerShell에서 안전한 첨부 파일 규칙의 우선 순위를 설정 하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-287">To set the priority of a safe attachment rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="9ce8f-288">다음은 Marketing Department라는 규칙의 우선순위를 2로 설정하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-288">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="9ce8f-289">우선순위가 2 이하인 모든 기존 규칙은 1씩 감소합니다(우선순위 번호는 1씩 증가함).</span><span class="sxs-lookup"><span data-stu-id="9ce8f-289">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="9ce8f-290">**참고** : 새 규칙을 만들 때 우선 순위를 설정 하려면 대신 **Disable-safeattachmentrule** cmdlet에서 _priority_ 매개 변수를 사용 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-290">**Note** : To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeAttachmentRule** cmdlet instead.</span></span>

<span data-ttu-id="9ce8f-291">구문 및 매개 변수에 대 한 자세한 내용은 [disable-safeattachmentrule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-291">For detailed syntax and parameter information, see [Set-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule).</span></span>

### <a name="use-powershell-to-remove-safe-attachment-policies"></a><span data-ttu-id="9ce8f-292">PowerShell을 사용 하 여 안전한 첨부 파일 정책 제거</span><span class="sxs-lookup"><span data-stu-id="9ce8f-292">Use PowerShell to remove safe attachment policies</span></span>

<span data-ttu-id="9ce8f-293">PowerShell을 사용 하 여 안전한 첨부 파일 정책을 제거 해도 해당 하는 안전한 첨부 파일 규칙은 제거 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-293">When you use PowerShell to remove a safe attachment policy, the corresponding safe attachment rule isn't removed.</span></span>

<span data-ttu-id="9ce8f-294">PowerShell에서 안전한 첨부 파일 정책을 제거 하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-294">To remove a safe attachment policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeAttachmentPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="9ce8f-295">이 예에서는 Marketing 학과 라는 안전한 첨부 파일 정책을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-295">This example removes the safe attachment policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeAttachmentPolicy -Identity "Marketing Department"
```

<span data-ttu-id="9ce8f-296">구문과 매개 변수에 대 한 자세한 내용은 [get-safeattachmentpolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentpolicy)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-296">For detailed syntax and parameter information, see [Remove-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-remove-safe-attachment-rules"></a><span data-ttu-id="9ce8f-297">PowerShell을 사용 하 여 안전한 첨부 파일 규칙 제거</span><span class="sxs-lookup"><span data-stu-id="9ce8f-297">Use PowerShell to remove safe attachment rules</span></span>

<span data-ttu-id="9ce8f-298">PowerShell을 사용 하 여 안전한 첨부 파일 규칙을 제거 하는 경우 해당 하는 안전한 첨부 파일 정책은 제거 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-298">When you use PowerShell to remove a safe attachment rule, the corresponding safe attachment policy isn't removed.</span></span>

<span data-ttu-id="9ce8f-299">PowerShell에서 안전한 첨부 파일 규칙을 제거 하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-299">To remove a safe attachment rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeAttachmentRule -Identity "<PolicyName>"
```

<span data-ttu-id="9ce8f-300">이 예에서는 Marketing 부서 라는 안전한 첨부 파일 규칙을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-300">This example removes the safe attachment rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="9ce8f-301">구문과 매개 변수에 대 한 자세한 내용은 [disable-safeattachmentrule](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentrule)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-301">For detailed syntax and parameter information, see [Remove-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentrule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="9ce8f-302">이 절차가 제대로 수행되었는지 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="9ce8f-302">How do you know these procedures worked?</span></span>

<span data-ttu-id="9ce8f-303">안전한 첨부 파일 정책이 성공적으로 생성, 수정 또는 제거 되었는지 확인 하려면 다음 단계 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-303">To verify that you've successfully created, modified, or removed Safe Attachments policies, do any of the following steps:</span></span>

- <span data-ttu-id="9ce8f-304">보안 & 준수 센터에서 **위협 관리** \> **정책** \> **ATP 안전한 첨부 파일로** 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-304">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span> <span data-ttu-id="9ce8f-305">정책 목록, 해당 **상태** 값 및 해당 **우선 순위** 값을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-305">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="9ce8f-306">자세한 내용을 보려면 목록에서 정책을 선택 하 고 플라이 아웃에서 세부 정보를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-306">To view more details, select the policy from the list, and view the details in the fly out.</span></span>

- <span data-ttu-id="9ce8f-307">Exchange Online PowerShell 또는 Exchange Online Protection PowerShell에서 \<Name\> 정책 또는 규칙의 이름으로 바꾸고 다음 명령을 실행 하 고 설정을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-307">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeAttachmentPolicy -Identity "<Name>" | Format-List
  ```

  ```PowerShell
  Get-SafeAttachmentRule -Identity "<Name>" | Format-List
  ```

<span data-ttu-id="9ce8f-308">안전한 첨부 파일이 메시지를 검색 하는지 확인 하려면 사용 가능한 Defender for Office 365 reports를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-308">To verify that Safe Attachments is scanning messages, check the available Defender for Office 365 reports.</span></span> <span data-ttu-id="9ce8f-309">자세한 내용은 [View reports For Office 365](view-reports-for-atp.md) 및 [Security & 준수 센터에서 탐색기 사용](threat-explorer.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9ce8f-309">For more information, see [View reports for Defender for Office 365](view-reports-for-atp.md) and [Use Explorer in the Security & Compliance Center](threat-explorer.md).</span></span>
