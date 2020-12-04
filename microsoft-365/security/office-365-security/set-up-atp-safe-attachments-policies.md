---
title: Office 365용 Microsoft Defender에서 안전한 첨부 파일 정책 설정
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
description: 전자 메일의 악성 파일로부터 조직을 보호하기 위해 안전한 첨부 파일 정책을 정의하는 방법에 대해 자세히 알아보습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a14f5a22795fc08b76165466d8e44ee38d8a2d81
ms.sourcegitcommit: d81c7cea85af6ad5fef81d3c930514a51464368c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/04/2020
ms.locfileid: "49572645"
---
# <a name="set-up-safe-attachments-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="6769d-103">Office 365용 Microsoft Defender에서 안전한 첨부 파일 정책 설정</span><span class="sxs-lookup"><span data-stu-id="6769d-103">Set up Safe Attachments policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> <span data-ttu-id="6769d-104">이 문서는 [Office 365용 Microsoft Defender가](office-365-atp.md)있는 비즈니스 고객을 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-104">This article is intended for business customers who have [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="6769d-105">Outlook에서 첨부 파일 검색에 대한 정보를 찾고 있는 가정용 사용자는 고급 보안 [Outlook.com.](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)</span><span class="sxs-lookup"><span data-stu-id="6769d-105">If you're a home user looking for information about attachment scanning in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="6769d-106">안전한 첨부 파일은 [EOP(Exchange Online](anti-malware-protection.md)Protection)에서 맬웨어 방지 보호 기능으로 검색된 후 받는 사람에게 배달되기 전에 가상 환경을 사용하여 인바운드 전자 메일 메시지의 첨부 파일을 검사하는 [Office 365용 Microsoft Defender의](office-365-atp.md) 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-106">Safe Attachments is a feature in [Microsoft Defender for Office 365](office-365-atp.md) that uses a virtual environment to check attachments in inbound email messages after they've been scanned by [anti-malware protection in Exchange Online Protection (EOP)](anti-malware-protection.md), but before delivery to recipients.</span></span> <span data-ttu-id="6769d-107">자세한 내용은 [Office 365용 Microsoft Defender의](atp-safe-attachments.md)안전 첨부 파일을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6769d-107">For more information, see [Safe Attachments in Microsoft Defender for Office 365](atp-safe-attachments.md).</span></span>

<span data-ttu-id="6769d-108">기본 제공 또는 기본 안전 첨부 파일 정책이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-108">There's no built-in or default Safe Attachments policy.</span></span> <span data-ttu-id="6769d-109">전자 메일 메시지 첨부 파일을 안전한 첨부 파일 검색하려면 이 문서에 설명된 하나 이상의 안전 첨부 파일 정책을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-109">To get Safe Attachments scanning of email message attachments, you need to create one or more Safe Attachments policies as described in this article.</span></span>

<span data-ttu-id="6769d-110">보안 & 준수 센터 또는 PowerShell에서 안전 첨부 파일 정책을 구성할 수 있습니다(Exchange Online에 사서함이 있는 적격 Microsoft 365 조직, Exchange Online 사서함이 없지만 Office 365 추가 기능 구독에 대한 Defender를 사용하여 조직의 독립 실행형 EOP PowerShell).</span><span class="sxs-lookup"><span data-stu-id="6769d-110">You can configure Safe Attachments policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="6769d-111">안전 첨부 파일 정책의 기본 요소는 다음입니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-111">The basic elements of a Safe Attachments policy are:</span></span>

- <span data-ttu-id="6769d-112">**안전한** 첨부 파일 정책: 알 수 없는 맬웨어 검색에 대한 작업, 맬웨어 첨부 파일이 있는 메시지를 지정된 전자 메일 주소로 보낼지 여부 및 안전한 첨부 파일 검색을 완료할 수 없는 경우 메시지를 배달할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-112">**The safe attachment policy**: Specifies the actions for unknown malware detections, whether to send messages with malware attachments to a specified email address, and whether to deliver messages if Safe Attachments scanning can't complete.</span></span>
- <span data-ttu-id="6769d-113">**안전한 첨부 파일 규칙:** 우선 순위 및 받는 사람 필터(정책이 적용되는 사람)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-113">**The safe attachment rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

<span data-ttu-id="6769d-114">보안 및 준수 센터에서 안전 첨부 파일 정책 관리 시 이러한 두 요소의 차이는 & 명확하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-114">The difference between these two elements isn't obvious when you manage Safe Attachments polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="6769d-115">안전 첨부 파일 정책을 만들 때 실제로는 동일한 이름을 사용하여 안전한 첨부 파일 규칙과 연결된 안전한 첨부 파일 정책을 동시에 만들게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-115">When you create a Safe Attachments policy, you're actually creating a safe attachment rule and the associated safe attachment policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="6769d-116">안전 첨부 파일 정책을 수정할 때 이름, 우선 순위, 사용 또는 사용 안 하도록 설정 및 받는 사람 필터와 관련된 설정은 안전한 첨부 파일 규칙을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-116">When you modify a Safe Attachments policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe attachment rule.</span></span> <span data-ttu-id="6769d-117">다른 모든 설정은 연결된 안전한 첨부 파일 정책을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-117">All other settings modify the associated safe attachment policy.</span></span>
- <span data-ttu-id="6769d-118">안전 첨부 파일 정책을 제거하면 안전한 첨부 파일 규칙 및 연결된 안전 첨부 파일 정책이 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-118">When you remove a Safe Attachments policy, the safe attachment rule and the associated safe attachment policy are removed.</span></span>

<span data-ttu-id="6769d-119">Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell에서 정책과 규칙을 개별적으로 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-119">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="6769d-120">자세한 내용은 이 문서 부분의 Exchange Online PowerShell 또는 독립 실행형 [EOP PowerShell을](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) 사용하여 안전한 첨부 파일 정책 구성 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6769d-120">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Attachments policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) section later in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="6769d-121">안전 첨부 파일 설정의 전역 설정 영역에는 안전 첨부 파일 정책에 종속되지 않는 기능을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-121">In the global settings area of Safe Attachments settings, you configure features that are not dependent on Safe Attachments policies.</span></span> <span data-ttu-id="6769d-122">자세한 내용은 [Microsoft 365 E5에서](safe-docs.md) [SharePoint, OneDrive 및 Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md) 및 안전한 문서에 대한 ATP 켜기를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6769d-122">For instructions see [Turn on ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md) and [Safe Documents in Microsoft 365 E5](safe-docs.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="6769d-123">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="6769d-123">What do you need to know before you begin?</span></span>

- <span data-ttu-id="6769d-124"><https://protection.office.com/>에서 보안 및 준수 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-124">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="6769d-125">안전한 첨부 파일 **페이지로** 직접 이동하기 위해 다음을 <https://protection.office.com/safeattachmentv2> 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="6769d-125">To go directly to the **Safe Attachments** page, use <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="6769d-126">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6769d-126">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="6769d-127">독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6769d-127">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="6769d-128">이 문서의 절차를 수행하려면 먼저 보안 및 준수 & 사용 권한을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-128">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="6769d-129">안전한 첨부 파일 정책을 만들고 수정하고 삭제하려면 **조직** 관리 또는 보안 관리자 역할 그룹의 구성원이 **되거나** 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-129">To create, modify, and delete Safe Attachments policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="6769d-130">안전 첨부 파일 정책에 대한 읽기 전용 액세스의 경우 **Global Reader** 전역 읽기 사용자 또는 보안 읽기 권한이 있는 역할 그룹의 **구성원이** 되거나,</span><span class="sxs-lookup"><span data-stu-id="6769d-130">For read-only access to Safe Attachments policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="6769d-131">자세한 내용은 [보안 및 준수 센터의 사용 권한](permissions-in-the-security-and-compliance-center.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6769d-131">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="6769d-132">**참고**:</span><span class="sxs-lookup"><span data-stu-id="6769d-132">**Notes**:</span></span>

  - <span data-ttu-id="6769d-133">Microsoft 365 관리 센터에서 해당 Azure Active Directory 역할에 사용자를 추가하면 사용자에게 보안 & _and_ 준수 센터에서 필요한 사용 권한과 Microsoft 365의 다른 기능에 대한 사용 권한이 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-133">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="6769d-134">자세한 내용은 [관리자 역할 정보](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6769d-134">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="6769d-135">[또한 Exchange Online의](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 보기 **전용 조직** 관리 역할 그룹은 기능에 대한 읽기 전용 액세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-135">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="6769d-136">안전한 첨부 파일 정책에 대한 권장 설정은 안전 첨부 파일 설정을 [참조하세요.](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings)</span><span class="sxs-lookup"><span data-stu-id="6769d-136">For our recommended settings for Safe Attachments policies, see [Safe Attachments settings](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings).</span></span>

- <span data-ttu-id="6769d-137">새 정책 또는 업데이트된 정책을 적용하는 데 최대 30분을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-137">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

## <a name="use-the-security--compliance-center-to-create-safe-attachments-policies"></a><span data-ttu-id="6769d-138">보안 및 & 센터를 사용하여 안전한 첨부 파일 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="6769d-138">Use the Security & Compliance Center to create Safe Attachments policies</span></span>

<span data-ttu-id="6769d-139">보안 및 준수 센터에서 사용자 지정 안전 첨부 & 정책을 만들면 안전한 첨부 파일 규칙과 연결된 안전 첨부 파일 정책이 동시에 두 가지에 대해 동일한 이름을 사용하여 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-139">Creating a custom Safe Attachments policy in the Security & Compliance Center creates the safe attachment rule and the associated safe attachment policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="6769d-140">보안 & 준수 센터에서 위협 **관리** \> **Policy** \> **정책 ATP 안전한 첨부 파일로 이동하십시오.**</span><span class="sxs-lookup"><span data-stu-id="6769d-140">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="6769d-141">안전한 첨부 **파일 페이지에서** 만들기를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6769d-141">On the **Safe Attachments** page, click **Create**.</span></span>

3. <span data-ttu-id="6769d-142">새 **안전 첨부 파일 정책 마법사가** 열립니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-142">The **New Safe Attachments policy** wizard opens.</span></span> <span data-ttu-id="6769d-143">정책 **이름 페이지에서** 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-143">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="6769d-144">**이름**: 정책을 설명하는 고유한 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-144">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="6769d-145">**설명**: 정책에 대한 선택적 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-145">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="6769d-146">작업을 마친 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-146">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="6769d-147">나타나는 **설정** 페이지에서 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-147">On the **Settings** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="6769d-148">안전한 첨부 파일 알 수 **없는 맬웨어 응답:** 다음 값 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-148">**Safe Attachments unknown malware response**: Select one of the following values:</span></span>

     - <span data-ttu-id="6769d-149">**Off**: 일반적으로 이 값은 권장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-149">**Off**: Typically, we don't recommend this value.</span></span>
     - <span data-ttu-id="6769d-150">**모니터**</span><span class="sxs-lookup"><span data-stu-id="6769d-150">**Monitor**</span></span>
     - <span data-ttu-id="6769d-151">**Block**: 이 값은 기본값으로, Standard 및 Strict 미리 설정 보안 정책에서 [권장되는 값입니다.](preset-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="6769d-151">**Block**: This is the default value, and the recommended value in Standard and Strict [preset security policies](preset-security-policies.md).</span></span>
     - <span data-ttu-id="6769d-152">**바꾸기**</span><span class="sxs-lookup"><span data-stu-id="6769d-152">**Replace**</span></span>
     - <span data-ttu-id="6769d-153">**동적 배달(미리 보기 기능)**</span><span class="sxs-lookup"><span data-stu-id="6769d-153">**Dynamic Delivery (Preview Feature)**</span></span>

     <span data-ttu-id="6769d-154">이러한 값은 안전 첨부 파일 정책 [설정에서 설명됩니다.](atp-safe-attachments.md#safe-attachments-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="6769d-154">These values are explained in [Safe Attachments policy settings](atp-safe-attachments.md#safe-attachments-policy-settings).</span></span>

   - <span data-ttu-id="6769d-155">다음 전자 **Enable redirect** 메일 **주소로** 첨부 파일 보내기: 작업 **Replace** 값 **차단,** 모니터링 또는 바꾸기 작업의 경우 리디렉션을 선택하여 맬웨어 첨부 파일이 포함된 메시지를 분석 및 조사를 위해 지정된 내부 또는 외부 전자 메일 주소로 보낼 수 있습니다. **Monitor**</span><span class="sxs-lookup"><span data-stu-id="6769d-155">**Send the attachment to the following email address**: For the action values **Block**, **Monitor**, or **Replace**, you can select **Enable redirect** to send messages that contain malware attachments to the specified internal or external email address for analysis and investigation.</span></span>

     <span data-ttu-id="6769d-156">표준 및 엄격한 정책 설정에 대한 권장은 리디렉션을 사용하도록 설정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-156">The recommendation for Standard and Strict policy settings is to enable redirection.</span></span> <span data-ttu-id="6769d-157">자세한 내용은 안전 첨부 파일 [설정을 참조하십시오.](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings)</span><span class="sxs-lookup"><span data-stu-id="6769d-157">For more information, see [Safe Attachments settings](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings).</span></span>

   - <span data-ttu-id="6769d-158">**첨부 파일에** 대한 맬웨어 검색이 시간보다 멀어지거나 **Safe Attachments unknown malware response** 오류가 발생하는 경우 위의 선택을 적용합니다. 안전 첨부 파일 검색을 완료할 수 없는 경우에도 메시지에 대해 알 수 없는 맬웨어 응답이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-158">**Apply the above selection if malware scanning for attachments times out or error occurs**: The action specified by **Safe Attachments unknown malware response** is taken on messages even when Safe Attachments scanning can't complete.</span></span> <span data-ttu-id="6769d-159">사용 리디렉션을 선택하는 경우 항상 이 **옵션을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6769d-159">Always select this option if you select **Enabled redirect**.</span></span> <span data-ttu-id="6769d-160">그렇지 않으면 메시지가 손실될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-160">Otherwise, messages might be lost.</span></span>

   <span data-ttu-id="6769d-161">작업을 마친 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-161">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="6769d-162">적용 **대상** 페이지가 나타나면 정책이 적용되는 내부 받는 사람을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-162">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="6769d-163">조건이나 예외는 한 번만 사용할 수 있지만, 조건이나 예외에 대한 값을 여러 개 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-163">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="6769d-164">동일한 조건의 여러 값이나 예외는 OR 논리를 사용합니다(예: _\<recipient1\>_ 혹은 _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="6769d-164">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="6769d-165">다양한 조건이나 예외는 AND 논리를 사용합니다(예: _\<recipient1\>_ 및 _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="6769d-165">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="6769d-166">조건 **추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6769d-166">Click **Add a condition**.</span></span> <span data-ttu-id="6769d-167">나타나는 드롭다운에서 적용된 조건(다음의 **경우)을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6769d-167">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="6769d-168">**받는 사람:** 조직에서 하나 이상의 사서함, 메일 사용자 또는 메일 연락처를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-168">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="6769d-169">**받는 사람이 다음의** 구성원입니다. 조직에서 하나 이상의 그룹을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-169">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="6769d-170">**받는 사람 도메인은** 조직에서 구성된 허용 도메인 중 하나 이상에서 받는 사람을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-170">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="6769d-171">조건을 선택하면 해당 드롭다운이 다음 **상자와 함께** 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-171">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="6769d-172">상자를 클릭하고 선택할 값 목록을 스크롤합니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-172">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="6769d-173">상자를 클릭하고 입력을 시작하여 목록을 필터링하고 값을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-173">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="6769d-174">값을 더 추가하려면 상자의 빈 영역을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-174">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="6769d-175">개별 항목을 제거하려면 **Remove** 값에서 제거 ![ ](../../media/scc-remove-icon.png) 아이콘을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-175">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="6769d-176">전체 조건을 제거하려면 **조건에서** 제거 ![ ](../../media/scc-remove-icon.png) 아이콘을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-176">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="6769d-177">조건을 더 추가하려면 **조건** 추가를 클릭하고 적용된 경우 나머지 **값을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6769d-177">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="6769d-178">예외를 추가하려면 **조건** 추가를 클릭하고 다음의 예외를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6769d-178">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="6769d-179">설정 및 동작은 조건과 정확히 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-179">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="6769d-180">작업을 마친 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-180">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="6769d-181">나타나는 **설정** 검토 페이지에서 설정을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-181">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="6769d-182">각 **설정에서** 편집을 클릭하여 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-182">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="6769d-183">완료되면 마쳤습니다. **Finish**</span><span class="sxs-lookup"><span data-stu-id="6769d-183">When you're finished, click **Finish**.</span></span>

## <a name="use-the-security--compliance-center-to-view-safe-attachments-policies"></a><span data-ttu-id="6769d-184">보안 및 & 센터를 사용하여 안전한 첨부 파일 정책 보기</span><span class="sxs-lookup"><span data-stu-id="6769d-184">Use the Security & Compliance Center to view Safe Attachments policies</span></span>

1. <span data-ttu-id="6769d-185">보안 & 준수 센터에서 위협 **관리** \> **Policy** \> **정책 ATP 안전한 첨부 파일로 이동하십시오.**</span><span class="sxs-lookup"><span data-stu-id="6769d-185">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="6769d-186">안전 첨부 **파일** 페이지에서 목록에서 정책을 선택하고 해당 정책을 클릭합니다(확인란을 선택하지 않습니다).</span><span class="sxs-lookup"><span data-stu-id="6769d-186">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

   <span data-ttu-id="6769d-187">정책 세부 정보가 플라이아웃에 표시</span><span class="sxs-lookup"><span data-stu-id="6769d-187">The policy details appear in a fly out</span></span>

## <a name="use-the-security--compliance-center-to-modify-safe-attachments-policies"></a><span data-ttu-id="6769d-188">보안 및 & 센터를 사용하여 안전한 첨부 파일 정책 수정</span><span class="sxs-lookup"><span data-stu-id="6769d-188">Use the Security & Compliance Center to modify Safe Attachments policies</span></span>

1. <span data-ttu-id="6769d-189">보안 & 준수 센터에서 위협 **관리** \> **Policy** \> **정책 ATP 안전한 첨부 파일로 이동하십시오.**</span><span class="sxs-lookup"><span data-stu-id="6769d-189">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="6769d-190">안전 첨부 **파일** 페이지에서 목록에서 정책을 선택하고 해당 정책을 클릭합니다(확인란을 선택하지 않습니다).</span><span class="sxs-lookup"><span data-stu-id="6769d-190">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="6769d-191">나타나는 정책 세부 정보에서 정책 편집을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6769d-191">In the policy details fly out that appears, click **Edit policy**.</span></span>

<span data-ttu-id="6769d-192">플라이아웃에 나타나는 사용 가능한 설정은 보안 및 준수 센터를 사용하여 안전한 첨부 파일 정책 & 섹션에 설명된 설정과 [동일합니다.](#use-the-security--compliance-center-to-create-safe-attachments-policies)</span><span class="sxs-lookup"><span data-stu-id="6769d-192">The available settings in the fly out that appears are identical to those described in the [Use the Security & Compliance Center to create Safe Attachments policies](#use-the-security--compliance-center-to-create-safe-attachments-policies) section.</span></span>

<span data-ttu-id="6769d-193">정책을 활성화 또는 비활성화하거나 정책 우선 순위 순서를 설정하려면 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6769d-193">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-attachments-policies"></a><span data-ttu-id="6769d-194">안전 첨부 파일 정책 사용 또는 사용 안 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="6769d-194">Enable or disable Safe Attachments policies</span></span>

1. <span data-ttu-id="6769d-195">보안 & 준수 센터에서 위협 **관리** \> **Policy** \> **정책 ATP 안전한 첨부 파일로 이동하십시오.**</span><span class="sxs-lookup"><span data-stu-id="6769d-195">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="6769d-196">상태 열의 **값을** 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-196">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="6769d-197">토글을 왼쪽으로 이동</span><span class="sxs-lookup"><span data-stu-id="6769d-197">Move the toggle to the left</span></span> ![정책 끄기](../../media/scc-toggle-off.png) <span data-ttu-id="6769d-199">정책을 사용하지 않도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-199">to disable the policy.</span></span>

   - <span data-ttu-id="6769d-200">오른쪽으로 토글 이동</span><span class="sxs-lookup"><span data-stu-id="6769d-200">Move the toggle to the right</span></span> ![정책 켜기](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) <span data-ttu-id="6769d-202">을 사용하여 정책을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-202">to enable the policy.</span></span>

### <a name="set-the-priority-of-safe-attachments-policies"></a><span data-ttu-id="6769d-203">안전 첨부 파일 정책의 우선 순위 설정</span><span class="sxs-lookup"><span data-stu-id="6769d-203">Set the priority of Safe Attachments policies</span></span>

<span data-ttu-id="6769d-204">기본적으로 안전한 첨부 파일 정책에는 만들어진 순서에 따라 우선 순위가 부여됩니다(새 정책은 이전 정책보다 우선 순위가 낮음).</span><span class="sxs-lookup"><span data-stu-id="6769d-204">By default, Safe Attachments policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="6769d-205">낮은 우선순위 번호는 정책의 높은 우선순위(0이 가장 높음)를 나타내고 정책은 우선순위 순서에 따라 처리됩니다(높은 우선순위 정책은 낮은 우선순위 정책보다 먼저 처리됨).</span><span class="sxs-lookup"><span data-stu-id="6769d-205">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="6769d-206">두 정책의 우선순위는 동일 할 수 없으며, 첫 번째 정책이 적용된 후에는 정책 처리가 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-206">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="6769d-207">우선순위 및 여러 정책을 평가하고 적용하는 방법에 대 한 자세한 내용은 전자 메일의 [전자 메일의 우선순위 및 보호](how-policies-and-protections-are-combined.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6769d-207">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="6769d-208">안전한 첨부 파일 정책은 처리되는 순서대로 표시됩니다(첫 번째 **Priority** 정책의 우선 순위 값은 0).</span><span class="sxs-lookup"><span data-stu-id="6769d-208">Safe Attachments policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span>

<span data-ttu-id="6769d-209">**참고:** 보안 & 준수 센터에서는 안전 첨부 파일 정책을 만든 후에만 안전 첨부 파일 정책의 우선 순위를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-209">**Note**: In the Security & Compliance Center, you can only change the priority of the Safe Attachments policy after you create it.</span></span> <span data-ttu-id="6769d-210">PowerShell에서 안전한 첨부 파일 규칙을 만들 때 기본 우선 순위를 다시 정할 수 있습니다(기존 규칙의 우선 순위에 영향을 줄 수 있습니다).</span><span class="sxs-lookup"><span data-stu-id="6769d-210">In PowerShell, you can override the default priority when you create the safe attachment rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="6769d-211">정책의 우선순위를 변경하려면 목록에서 정책을 위나 아래로 이동합니다. 보안 및 준수 센터에서 **우선순위** 번호를 직접 수정할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-211">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="6769d-212">보안 & 준수 센터에서 위협 **관리** \> **Policy** \> **정책 ATP 안전한 첨부 파일로 이동하십시오.**</span><span class="sxs-lookup"><span data-stu-id="6769d-212">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="6769d-213">안전 첨부 **파일** 페이지에서 목록에서 정책을 선택하고 해당 정책을 클릭합니다(확인란을 선택하지 않습니다).</span><span class="sxs-lookup"><span data-stu-id="6769d-213">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="6769d-214">정책 세부 정보가 나타나는 플라이아웃에서 사용 가능한 우선 순위 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-214">In the policy details fly out that appears, click the available priority button.</span></span>

   - <span data-ttu-id="6769d-215">우선 순위 값이 **0인** 안전 첨부 파일 정책에는 우선 순위 감소 단추만 사용할 **Priority** **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-215">The Safe Attachments policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="6769d-216">우선 순위 값이 가장 **Priority** 낮은 안전 첨부 파일 정책(예: **3)에는** 우선 순위 늘리기 단추만 사용할 **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-216">The Safe Attachments policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="6769d-217">안전 첨부 파일 정책이 세 개 이상 있는 경우 우선 순위가 가장 높은 값과 가장 낮은 값 사이의 정책에는 우선 순위 늘리기 및 우선 순위 감소 단추를 모두 사용할 **수** 있습니다. **Increase priority**</span><span class="sxs-lookup"><span data-stu-id="6769d-217">If you have three or more Safe Attachments policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="6769d-218">우선 **순위 늘리기 또는** 우선 순위 **감소를** 클릭하여 우선 순위 값을 **변경합니다.**</span><span class="sxs-lookup"><span data-stu-id="6769d-218">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="6769d-219">작업을 마쳤으면 **닫기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-219">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-safe-attachments-policies"></a><span data-ttu-id="6769d-220">보안 및 & 센터를 사용하여 안전한 첨부 파일 정책 제거</span><span class="sxs-lookup"><span data-stu-id="6769d-220">Use the Security & Compliance Center to remove Safe Attachments policies</span></span>

1. <span data-ttu-id="6769d-221">보안 & 준수 센터에서 위협 **관리** \> **Policy** \> **정책 ATP 안전한 첨부 파일로 이동하십시오.**</span><span class="sxs-lookup"><span data-stu-id="6769d-221">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="6769d-222">안전 첨부 **파일** 페이지에서 목록에서 정책을 선택하고 해당 정책을 클릭합니다(확인란을 선택하지 않습니다).</span><span class="sxs-lookup"><span data-stu-id="6769d-222">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="6769d-223">정책 세부 정보가 나타나는 플라이아웃에서 **Delete policy** 정책 삭제를 **Yes** 클릭한 다음 나타나는 경고 대화 상자에서 예를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-223">In the policy details fly out that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies"></a><span data-ttu-id="6769d-224">Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell을 사용하여 안전한 첨부 파일 정책 구성</span><span class="sxs-lookup"><span data-stu-id="6769d-224">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Attachments policies</span></span>

<span data-ttu-id="6769d-225">앞서 설명한 바와 같이 안전한 첨부 파일 정책은 안전한 첨부 파일 정책과 안전한 첨부 파일 규칙으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-225">As previously described, a Safe Attachments policy consists of a safe attachment policy and a safe attachment rule.</span></span>

<span data-ttu-id="6769d-226">PowerShell에서 안전한 첨부 파일 정책과 안전한 첨부 파일 규칙의 차이는 분명합니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-226">In PowerShell, the difference between safe attachment policies and safe attachment rules is apparent.</span></span> <span data-ttu-id="6769d-227">**\* -SafeAttachmentPolicy** cmdlet을 사용하여 안전한 첨부 파일 정책을 관리하고 **\* -SafeAttachmentRule** cmdlet을 사용하여 안전한 첨부 파일 규칙을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-227">You manage safe attachment policies by using the **\*-SafeAttachmentPolicy** cmdlets, and you manage safe attachment rules by using the **\*-SafeAttachmentRule** cmdlets.</span></span>

- <span data-ttu-id="6769d-228">PowerShell에서 먼저 안전한 첨부 파일 정책을 만든 다음 규칙이 적용되는 정책을 식별하는 안전한 첨부 파일 규칙을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-228">In PowerShell, you create the safe attachment policy first, then you create the safe attachment rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="6769d-229">PowerShell에서는 안전한 첨부 파일 정책 및 안전한 첨부 파일 규칙의 설정을 개별적으로 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-229">In PowerShell, you modify the settings in the safe attachment policy and the safe attachment rule separately.</span></span>
- <span data-ttu-id="6769d-230">PowerShell에서 안전한 첨부 파일 정책을 제거하면 해당 안전 첨부 파일 규칙이 자동으로 제거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-230">When you remove a safe attachment policy from PowerShell, the corresponding safe attachment rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-attachments-policies"></a><span data-ttu-id="6769d-231">PowerShell을 사용하여 안전한 첨부 파일 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="6769d-231">Use PowerShell to create Safe Attachments policies</span></span>

<span data-ttu-id="6769d-232">PowerShell에서 안전한 첨부 파일 정책을 만드는 과정은 다음 두 단계로 진행됩니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-232">Creating a Safe Attachments policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="6769d-233">안전한 첨부 파일 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-233">Create the safe attachment policy.</span></span>
2. <span data-ttu-id="6769d-234">규칙이 적용되는 안전한 첨부 파일 정책을 지정하는 안전한 첨부 파일 규칙을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-234">Create the safe attachment rule that specifies the safe attachment policy that the rule applies to.</span></span>

 <span data-ttu-id="6769d-235">**참고**:</span><span class="sxs-lookup"><span data-stu-id="6769d-235">**Notes**:</span></span>

- <span data-ttu-id="6769d-236">새 안전한 첨부 파일 규칙을 만들고 연결되지 않은 기존 안전 첨부 파일 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-236">You can create a new safe attachment rule and assign an existing, unassociated safe attachment policy to it.</span></span> <span data-ttu-id="6769d-237">안전한 첨부 파일 규칙은 두 개 이상의 안전한 첨부 파일 정책과 연결될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-237">A safe attachment rule can't be associated with more than one safe attachment policy.</span></span>

- <span data-ttu-id="6769d-238">정책을 만든 후 보안 및 준수 센터에서 사용할 수 없는 PowerShell의 새 안전 첨부 파일 정책에 대해 다음 설정을 구성할 수 & 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-238">You can configure the following settings on new safe attachment policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>
  - <span data-ttu-id="6769d-239">새 정책을 사용할 수 _Enabled_ `$false` **없습니다(New-SafeAttachmentRule** cmdlet에서 사용).</span><span class="sxs-lookup"><span data-stu-id="6769d-239">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeAttachmentRule** cmdlet).</span></span>
  - <span data-ttu-id="6769d-240">_Priority_ _\<Number\>_ **New-SafeAttachmentRule** cmdlet에서 만들기 중에 정책의 우선 순위(우선 순위)를 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="6769d-240">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeAttachmentRule** cmdlet).</span></span>

- <span data-ttu-id="6769d-241">PowerShell에서 만든 새 안전 첨부 파일 정책은 안전한 첨부 파일 규칙에 정책을 할당할 때까지 보안 & 준수 센터에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-241">A new safe attachment policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a safe attachment rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-attachment-policy"></a><span data-ttu-id="6769d-242">1단계: PowerShell을 사용하여 안전한 첨부 파일 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="6769d-242">Step 1: Use PowerShell to create a safe attachment policy</span></span>

<span data-ttu-id="6769d-243">안전한 첨부 파일 정책을 만들 수 있도록 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-243">To create a safe attachment policy, use this syntax:</span></span>

```PowerShell
New-SafeAttachmentPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-Action <Allow | Block | Replace | DynamicDelivery>] [-Redirect <$true | $false>] [-RedirectAddress <SMTPEmailAddress>] [-ActionOnError <$true | $false>]
```

<span data-ttu-id="6769d-244">이 예에서는 다음 값을 가지는 Contoso All이라는 안전한 첨부 파일 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-244">This example creates a safe attachment policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="6769d-245">안전한 문서 검색에서 맬웨어를 포함하는 것으로 확인된 메시지를 _차단합니다(Action_ 매개 변수를 사용하지 않습니다. 기본값은 `Block` ).</span><span class="sxs-lookup"><span data-stu-id="6769d-245">Block messages that are found to contain malware by Safe Documents scanning (we aren't using the _Action_ parameter, and the default value is `Block`).</span></span>
- <span data-ttu-id="6769d-246">리디렉션이 사용하도록 설정되어 있으며 맬웨어가 포함된 것으로 확인된 메시지는 분석 및 sec-ops@contoso.com 위해 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-246">Redirection is enabled, and messages that are found to contain malware are sent to sec-ops@contoso.com for analysis and investigation.</span></span>
- <span data-ttu-id="6769d-247">안전 첨부 파일 검색을 사용할 수 없는 경우 또는 오류가 발생하는 경우 메시지를 배달하지 _않습니다(ActionOnError_ 매개 변수를 사용하지 않습니다. 기본값은 `$true` ).</span><span class="sxs-lookup"><span data-stu-id="6769d-247">If Safe Attachments scanning isn't available or encounters errors, don't deliver the message (we aren't using the _ActionOnError_ parameter, and the default value is `$true`).</span></span>

```PowerShell
New-SafeAttachmentPolicy -Name "Contoso All" -Redirect $true -RedirectAddress sec-ops@contoso.com
```

<span data-ttu-id="6769d-248">구문과 매개 변수에 대한 자세한 내용은 [New-SafeAttachmentPolicy를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentpolicy)</span><span class="sxs-lookup"><span data-stu-id="6769d-248">For detailed syntax and parameter information, see [New-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-attachment-rule"></a><span data-ttu-id="6769d-249">2단계: PowerShell을 사용하여 안전한 첨부 파일 규칙 만들기</span><span class="sxs-lookup"><span data-stu-id="6769d-249">Step 2: Use PowerShell to create a safe attachment rule</span></span>

<span data-ttu-id="6769d-250">안전한 첨부 파일 규칙을 만들 수 있도록 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-250">To create a safe attachment rule, use this syntax:</span></span>

```PowerShell
New-SafeAttachmentRule -Name "<RuleName>" -SafeAttachmentPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="6769d-251">이 예에서는 다음 조건을 통해 Contoso All이라는 안전한 첨부 파일 규칙을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-251">This example creates a safe attachment rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="6769d-252">이 규칙은 Contoso All이라는 안전한 첨부 파일 정책과 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-252">The rule is associated with the safe attachment policy named Contoso All.</span></span>
- <span data-ttu-id="6769d-253">이 규칙은 도메인의 모든 받는 사람에게 contoso.com 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-253">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="6769d-254">Priority 매개 변수를 _Priority_ 사용하지 않는 경우 기본 우선 순위가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-254">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="6769d-255">이 규칙은 사용하도록 설정됩니다(Enabled _Enabled_ 매개 변수를 사용하지 않습니다. 기본값은 `$true` ).</span><span class="sxs-lookup"><span data-stu-id="6769d-255">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeAttachmentRule -Name "Contoso All" -SafeAttachmentPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="6769d-256">구문과 매개 변수에 대한 자세한 내용은 [New-SafeAttachmentRule을 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentrule)</span><span class="sxs-lookup"><span data-stu-id="6769d-256">For detailed syntax and parameter information, see [New-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentrule).</span></span>

### <a name="use-powershell-to-view-safe-attachment-policies"></a><span data-ttu-id="6769d-257">PowerShell을 사용하여 안전한 첨부 파일 정책 보기</span><span class="sxs-lookup"><span data-stu-id="6769d-257">Use PowerShell to view safe attachment policies</span></span>

<span data-ttu-id="6769d-258">기존의 안전한 첨부 파일 정책을 보시고 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-258">To view existing safe attachment policies, use the following syntax:</span></span>

```PowerShell
Get-SafeAttachmentPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="6769d-259">이 예에서는 모든 안전한 첨부 파일 정책의 요약 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-259">This example returns a summary list of all safe attachment policies.</span></span>

```PowerShell
Get-SafeAttachmentPolicy
```

<span data-ttu-id="6769d-260">이 예에서는 Contoso Executives라는 안전한 첨부 파일 정책에 대한 자세한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-260">This example returns detailed information for the safe attachment policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeAttachmentPolicy -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="6769d-261">구문과 매개 변수에 대한 자세한 내용은 [Get-SafeAttachmentPolicy를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentpolicy)</span><span class="sxs-lookup"><span data-stu-id="6769d-261">For detailed syntax and parameter information, see [Get-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-view-safe-attachment-rules"></a><span data-ttu-id="6769d-262">PowerShell을 사용하여 안전한 첨부 파일 규칙 보기</span><span class="sxs-lookup"><span data-stu-id="6769d-262">Use PowerShell to view safe attachment rules</span></span>

<span data-ttu-id="6769d-263">기존의 안전한 첨부 파일 규칙을 보시고 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-263">To view existing safe attachment rules, use the following syntax:</span></span>

```PowerShell
Get-SafeAttachmentRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="6769d-264">이 예에서는 모든 안전한 첨부 파일 규칙의 요약 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-264">This example returns a summary list of all safe attachment rules.</span></span>

```PowerShell
Get-SafeAttachmentRule
```

<span data-ttu-id="6769d-265">활성화된 또는 비활성화된 규칙을 기준으로 목록을 필터링하려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-265">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeAttachmentRule -State Disabled
```

```PowerShell
Get-SafeAttachmentRule -State Enabled
```

<span data-ttu-id="6769d-266">이 예에서는 Contoso Executives라는 안전한 첨부 파일 규칙에 대한 자세한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-266">This example returns detailed information for the safe attachment rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeAttachmentRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="6769d-267">구문과 매개 변수에 대한 자세한 내용은 [Get-SafeAttachmentRule을 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentrule)</span><span class="sxs-lookup"><span data-stu-id="6769d-267">For detailed syntax and parameter information, see [Get-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentrule).</span></span>

### <a name="use-powershell-to-modify-safe-attachment-policies"></a><span data-ttu-id="6769d-268">PowerShell을 사용하여 안전한 첨부 파일 정책 수정</span><span class="sxs-lookup"><span data-stu-id="6769d-268">Use PowerShell to modify safe attachment policies</span></span>

<span data-ttu-id="6769d-269">PowerShell에서 안전한 첨부 파일 정책의 이름을 설정할 수 **없습니다(Set-SafeAttachmentPolicy** cmdlet에는 Name 매개 _변수가_ 없음).</span><span class="sxs-lookup"><span data-stu-id="6769d-269">You can't rename a safe attachment policy in PowerShell (the **Set-SafeAttachmentPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="6769d-270">보안 및 준수 센터에서 안전 첨부 파일 정책의 & 경우 안전한 첨부 파일 규칙의 이름만 다시 _매기게 됩니다._</span><span class="sxs-lookup"><span data-stu-id="6769d-270">When you rename a Safe Attachments policy in the Security & Compliance Center, you're only renaming the safe attachment _rule_.</span></span>

<span data-ttu-id="6769d-271">그렇지 않으면 이 문서 앞부분의 PowerShell을 사용하여 안전한 첨부 파일 정책 섹션을 만드는 [1단계에](#step-1-use-powershell-to-create-a-safe-attachment-policy) 설명된 대로 안전한 첨부 파일 정책을 만들 때도 동일한 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-271">Otherwise, the same settings are available when you create a safe attachment policy as described in the [Step 1: Use PowerShell to create a safe attachment policy](#step-1-use-powershell-to-create-a-safe-attachment-policy) section earlier in this article.</span></span>

<span data-ttu-id="6769d-272">안전한 첨부 파일 정책을 수정하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-272">To modify a safe attachment policy, use this syntax:</span></span>

```PowerShell
Set-SafeAttachmentPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="6769d-273">구문과 매개 변수에 대한 자세한 내용은 [Set-SafeAttachmentPolicy를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentpolicy)</span><span class="sxs-lookup"><span data-stu-id="6769d-273">For detailed syntax and parameter information, see [Set-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-modify-safe-attachment-rules"></a><span data-ttu-id="6769d-274">PowerShell을 사용하여 안전한 첨부 파일 규칙 수정</span><span class="sxs-lookup"><span data-stu-id="6769d-274">Use PowerShell to modify safe attachment rules</span></span>

<span data-ttu-id="6769d-275">PowerShell에서 안전한 첨부 파일 규칙을 수정할 때 사용할 수 없는 설정은 _사용되지_ 않는 규칙을 만들 수 있는 Enabled 매개 변수뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-275">The only setting that's not available when you modify a safe attachment rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="6769d-276">기존 안전 첨부 파일 규칙을 사용하도록 설정하거나 사용하지 않도록 설정하려면 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6769d-276">To enable or disable existing safe attachment rules, see the next section.</span></span>

<span data-ttu-id="6769d-277">그렇지 않으면 [2단계: PowerShell을](#step-2-use-powershell-to-create-a-safe-attachment-rule) 사용하여 이 문서 앞부분의 안전한 첨부 파일 규칙 섹션을 만드는 규칙에 설명된 대로 동일한 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-277">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe attachment rule](#step-2-use-powershell-to-create-a-safe-attachment-rule) section earlier in this article.</span></span>

<span data-ttu-id="6769d-278">안전한 첨부 파일 규칙을 수정하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-278">To modify a safe attachment rule, use this syntax:</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="6769d-279">구문과 매개 변수에 대한 자세한 내용은 [Set-SafeAttachmentRule을 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule)</span><span class="sxs-lookup"><span data-stu-id="6769d-279">For detailed syntax and parameter information, see [Set-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-attachment-rules"></a><span data-ttu-id="6769d-280">PowerShell을 사용하여 안전한 첨부 파일 규칙을 사용하도록 설정하거나 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="6769d-280">Use PowerShell to enable or disable safe attachment rules</span></span>

<span data-ttu-id="6769d-281">PowerShell에서 안전한 첨부 파일 규칙을 설정하거나 사용하지 않도록 설정하면 전체 안전 첨부 파일 정책(안전한 첨부 파일 규칙 및 할당된 안전 첨부 파일 정책)을 활성화하거나 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-281">Enabling or disabling a safe attachment rule in PowerShell enables or disables the whole Safe Attachments policy (the safe attachment rule and the assigned safe attachment policy).</span></span>

<span data-ttu-id="6769d-282">PowerShell에서 안전한 첨부 파일 규칙을 사용하도록 설정하거나 사용하지 않도록 설정하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-282">To enable or disable a safe attachment rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeAttachmentRule | Disable-SafeAttachmentRule> -Identity "<RuleName>"
```

<span data-ttu-id="6769d-283">이 예에서는 Marketing Department라는 안전 첨부 파일 규칙을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-283">This example disables the safe attachment rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="6769d-284">다음은 동일한 규칙을 사용하도록 설정하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-284">This example enables same rule.</span></span>

```PowerShell
Enable-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="6769d-285">구문과 매개 변수에 대한 자세한 내용은 [Enable-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/enable-safeattachmentrule) 및 [Disable-SafeAttachmentRule을 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/disable-safeattachmentrule)</span><span class="sxs-lookup"><span data-stu-id="6769d-285">For detailed syntax and parameter information, see [Enable-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/enable-safeattachmentrule) and [Disable-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/disable-safeattachmentrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-attachment-rules"></a><span data-ttu-id="6769d-286">PowerShell을 사용하여 안전한 첨부 파일 규칙의 우선 순위 설정</span><span class="sxs-lookup"><span data-stu-id="6769d-286">Use PowerShell to set the priority of safe attachment rules</span></span>

<span data-ttu-id="6769d-287">규칙에 설정 가능한 가장 높은 우선 순위 값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-287">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="6769d-288">설정할 수 있는 가장 낮은 값은 규칙 수에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-288">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="6769d-289">예를 들어 규칙이 5개 있는 경우, 우선순위 값 0~4를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-289">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="6769d-290">기존 규칙의 우선순위를 변경하면 다른 규칙에 계단식 효과를 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-290">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="6769d-291">예를 들어 사용자 지정 규칙 5개(우선순위: 0~4)가 있고 규칙의 우선순위를 2로 변경하면, 우선순위 2인 기존 규칙이 우선순위 3으로 변경되고, 우선순위 3인 규칙이 우선순위 4로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-291">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="6769d-292">PowerShell에서 안전한 첨부 파일 규칙의 우선 순위를 설정하기 위해 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-292">To set the priority of a safe attachment rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="6769d-293">다음은 Marketing Department라는 규칙의 우선순위를 2로 설정하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-293">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="6769d-294">우선순위가 2 이하인 모든 기존 규칙은 1씩 감소합니다(우선순위 번호는 1씩 증가함).</span><span class="sxs-lookup"><span data-stu-id="6769d-294">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="6769d-295">**참고:** 새 규칙을 만들 때 새 규칙의 우선 순위를 설정하기 위해 **New-SafeAttachmentRule** cmdlet에서 _Priority_ 매개 변수를 대신 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-295">**Note**: To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeAttachmentRule** cmdlet instead.</span></span>

<span data-ttu-id="6769d-296">구문과 매개 변수에 대한 자세한 내용은 [Set-SafeAttachmentRule을 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule)</span><span class="sxs-lookup"><span data-stu-id="6769d-296">For detailed syntax and parameter information, see [Set-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule).</span></span>

### <a name="use-powershell-to-remove-safe-attachment-policies"></a><span data-ttu-id="6769d-297">PowerShell을 사용하여 안전한 첨부 파일 정책 제거</span><span class="sxs-lookup"><span data-stu-id="6769d-297">Use PowerShell to remove safe attachment policies</span></span>

<span data-ttu-id="6769d-298">PowerShell을 사용하여 안전한 첨부 파일 정책을 제거하면 해당 안전 첨부 파일 규칙이 제거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-298">When you use PowerShell to remove a safe attachment policy, the corresponding safe attachment rule isn't removed.</span></span>

<span data-ttu-id="6769d-299">PowerShell에서 안전한 첨부 파일 정책을 제거하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-299">To remove a safe attachment policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeAttachmentPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="6769d-300">이 예에서는 Marketing Department라는 안전 첨부 파일 정책을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-300">This example removes the safe attachment policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeAttachmentPolicy -Identity "Marketing Department"
```

<span data-ttu-id="6769d-301">구문과 매개 변수에 대한 자세한 내용은 [Remove-SafeAttachmentPolicy를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentpolicy)</span><span class="sxs-lookup"><span data-stu-id="6769d-301">For detailed syntax and parameter information, see [Remove-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-remove-safe-attachment-rules"></a><span data-ttu-id="6769d-302">PowerShell을 사용하여 안전한 첨부 파일 규칙 제거</span><span class="sxs-lookup"><span data-stu-id="6769d-302">Use PowerShell to remove safe attachment rules</span></span>

<span data-ttu-id="6769d-303">PowerShell을 사용하여 안전한 첨부 파일 규칙을 제거하면 해당 안전 첨부 파일 정책이 제거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-303">When you use PowerShell to remove a safe attachment rule, the corresponding safe attachment policy isn't removed.</span></span>

<span data-ttu-id="6769d-304">PowerShell에서 안전한 첨부 파일 규칙을 제거하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-304">To remove a safe attachment rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeAttachmentRule -Identity "<PolicyName>"
```

<span data-ttu-id="6769d-305">이 예에서는 Marketing Department라는 안전 첨부 파일 규칙을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-305">This example removes the safe attachment rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="6769d-306">구문과 매개 변수에 대한 자세한 내용은 [Remove-SafeAttachmentRule을 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentrule)</span><span class="sxs-lookup"><span data-stu-id="6769d-306">For detailed syntax and parameter information, see [Remove-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentrule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="6769d-307">이 절차가 제대로 수행되었는지 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="6769d-307">How do you know these procedures worked?</span></span>

<span data-ttu-id="6769d-308">안전한 첨부 파일 정책을 성공적으로 만들거나 수정 또는 제거한 경우 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-308">To verify that you've successfully created, modified, or removed Safe Attachments policies, do any of the following steps:</span></span>

- <span data-ttu-id="6769d-309">보안 & 준수 센터에서 위협 **관리** \> **Policy** \> **정책 ATP 안전한 첨부 파일로 이동하십시오.**</span><span class="sxs-lookup"><span data-stu-id="6769d-309">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span> <span data-ttu-id="6769d-310">정책 목록, **정책** 상태 값 및 우선 순위 값을 **검증합니다.**</span><span class="sxs-lookup"><span data-stu-id="6769d-310">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="6769d-311">자세한 내용을 확인하려면 목록에서 정책을 선택하고 플라이아웃의 세부 정보를 하세요.</span><span class="sxs-lookup"><span data-stu-id="6769d-311">To view more details, select the policy from the list, and view the details in the fly out.</span></span>

- <span data-ttu-id="6769d-312">Exchange Online PowerShell 또는 Exchange Online Protection PowerShell에서 정책 또는 규칙의 이름으로 바꾸고 다음 명령을 실행하고 설정을 \<Name\> 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-312">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeAttachmentPolicy -Identity "<Name>" | Format-List
  ```

  ```PowerShell
  Get-SafeAttachmentRule -Identity "<Name>" | Format-List
  ```

<span data-ttu-id="6769d-313">안전한 첨부 파일이 메시지를 검사하고 있는지 확인을 위해 Office 365 보고서에 대해 사용 가능한 Defender를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6769d-313">To verify that Safe Attachments is scanning messages, check the available Defender for Office 365 reports.</span></span> <span data-ttu-id="6769d-314">자세한 내용은 보안 및 준수 센터에서 [Office 365용 Defender](view-reports-for-atp.md) [및 탐색기 사용에 대한 & 참조하세요.](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="6769d-314">For more information, see [View reports for Defender for Office 365](view-reports-for-atp.md) and [Use Explorer in the Security & Compliance Center](threat-explorer.md).</span></span>
