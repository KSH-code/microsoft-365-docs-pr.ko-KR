---
title: Office 365 ATP에서 안전한 링크 정책 설정
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
ms.collection:
- M365-security-compliance
description: 관리자는 Office 365 ATP (Advanced Threat Protection)에서 안전한 링크 정책 및 전역 안전한 링크 설정을 확인, 작성, 수정 및 삭제 하는 방법을 확인할 수 있습니다.
ms.openlocfilehash: b6b013364fc763450ac8bef0d06bd2fad8d55daa
ms.sourcegitcommit: 3a0accd616ca94d6ba7f50e502552b45e9661a95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/03/2020
ms.locfileid: "48350722"
---
# <a name="set-up-safe-links-policies-in-office-365-atp"></a><span data-ttu-id="d39f9-103">Office 365 ATP에서 안전한 링크 정책 설정</span><span class="sxs-lookup"><span data-stu-id="d39f9-103">Set up Safe Links policies in Office 365 ATP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> <span data-ttu-id="d39f9-104">이 문서는 [Office 365 Advanced Threat Protection](office-365-atp.md)이 있는 비즈니스 고객을 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-104">This article is intended for business customers who have [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="d39f9-105">Outlook에서 Safelinks에 대 한 정보를 검색 하는 개인 사용자는 [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d39f9-105">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="d39f9-106">안전한 링크는 메일 흐름에서 인바운드 전자 메일 메시지의 URL 검색을 제공 하 고 전자 메일 메시지와 다른 위치의 Url 및 링크 확인을 클릭 하는 경우 [Office 365 ATP (Advanced Threat Protection)](office-365-atp.md) 의 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-106">Safe Links is a feature in [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md) that provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="d39f9-107">자세한 내용은 [Office 365 ATP의 안전한 링크](atp-safe-links.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d39f9-107">For more information, see [Safe Links in Office 365 ATP](atp-safe-links.md).</span></span>

<span data-ttu-id="d39f9-108">기본 제공 또는 기본 안전 링크 정책이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-108">There's no built-in or default Safe Links policy.</span></span> <span data-ttu-id="d39f9-109">안전한 링크 Url 검색을 얻으려면이 문서에 설명 된 대로 하나 이상의 안전한 링크 정책을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-109">To get Safe Links scanning of URLs, you need to create one or more Safe Links policies as described in this article.</span></span>

<span data-ttu-id="d39f9-110">보안 & 준수 센터 또는 PowerShell (exchange online에 사서함이 있는 적격 Microsoft 365 조직에 대 한 Exchange Online PowerShell, exchange online 사서함이 없는 조직의 경우 독립 실행형 EOP PowerShell, Office 365 ATP 추가 기능 구독이 있는 경우)에서 안전한 링크 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-110">You can configure Safe Links policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Office 365 ATP add-on subscriptions).</span></span>

<span data-ttu-id="d39f9-111">안전한 링크 정책의 기본 요소는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-111">The basic elements of a Safe Links policy are:</span></span>

- <span data-ttu-id="d39f9-112">**안전한 링크 정책**: 안전한 링크 보호를 설정 하 고, 실시간 URL 검색을 사용 하도록 설정 하 고, 메시지를 배달 하기 전에 실시간 검색이 완료 되기를 기다릴지 여부를 지정 하 고, 내부 메시지에 대 한 검색을 설정 하 고, 사용자가 url을 클릭 하는지 여부를 지정 하 고, 사용자가 원래 url을 클릭할 수 있도록 허용할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-112">**The safe links policy**: Turn on Safe Links protection, turn on real-time URL scanning, specify whether to wait for real-time scanning to complete before delivering the message, turn on scanning for internal messages, specify whether to track user clicks on URLs, and specify whether to allow users to click trough to the original URL.</span></span>
- <span data-ttu-id="d39f9-113">**Safe links rule**: 우선 순위 및 받는 사람 필터 (정책이 적용 되는 사용자)를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-113">**The safe links rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

<span data-ttu-id="d39f9-114">보안 & 준수 센터에서 안전 링크 정책을 관리할 때는 이러한 두 가지 요소 간의 차이가 명확 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-114">The difference between these two elements isn't obvious when you manage Safe Links polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="d39f9-115">안전한 링크 정책을 만드는 경우 실제로는 둘 다에 대해 동일한 이름을 사용 하 여 안전한 링크 규칙과 연결 된 안전한 링크 정책을 동시에 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-115">When you create a Safe Links policy, you're actually creating a safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="d39f9-116">안전한 링크 정책을 수정 하면 이름, 우선 순위, 사용/사용 안 함 및 받는 사람 필터와 관련 된 설정이 안전한 링크 규칙을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-116">When you modify a Safe Links policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe links rule.</span></span> <span data-ttu-id="d39f9-117">다른 모든 설정은 연결 된 안전 링크 정책을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-117">All other settings modify the associated safe links policy.</span></span>
- <span data-ttu-id="d39f9-118">안전한 링크 정책을 제거 하면 안전한 링크 규칙과 관련 된 안전 링크 정책이 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-118">When you remove a Safe Links policy, the safe links rule and the associated safe links policy are removed.</span></span>

<span data-ttu-id="d39f9-119">Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell에서 정책과 규칙을 개별적으로 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-119">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="d39f9-120">자세한 내용은이 문서 뒷부분에 나오는 [Exchange Online PowerShell 또는 독립 실행형 EOP powershell을 사용 하 여 안전한 링크 정책 구성](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d39f9-120">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) section later in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="d39f9-121">안전한 링크 보호 정책 **외부** 에서 안전한 링크 방지에 대 한 전역 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-121">You configure the global settings for Safe Links protection **outside** of Safe Links policies.</span></span> <span data-ttu-id="d39f9-122">자세한 내용은 [Office 365 ATP에서 안전한 링크에 대 한 전역 설정 구성을](configure-global-settings-for-safe-links.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d39f9-122">For instructions, see [Configure global settings for Safe Links in Office 365 ATP](configure-global-settings-for-safe-links.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d39f9-123">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="d39f9-123">What do you need to know before you begin?</span></span>

- <span data-ttu-id="d39f9-124"><https://protection.office.com/>에서 보안 및 준수 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-124">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="d39f9-125">**ATP 안전한 링크** 페이지로 바로 이동 하려면을 사용 <https://protection.office.com/safelinksv2> 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-125">To go directly to the **ATP Safe Links** page, use <https://protection.office.com/safelinksv2>.</span></span>

- <span data-ttu-id="d39f9-126">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d39f9-126">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="d39f9-127">독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d39f9-127">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="d39f9-128">안전한 링크 정책을 보고, 만들고, 수정 하 고, 삭제 하려면 다음 역할 그룹 중 하나의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-128">To view, create, modify, and delete Safe Links policies, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="d39f9-129">[보안 및 준수 센터](permissions-in-the-security-and-compliance-center.md)의 **조직 관리** 또는 **보안 관리자**</span><span class="sxs-lookup"><span data-stu-id="d39f9-129">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  - <span data-ttu-id="d39f9-130">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **조직 관리**</span><span class="sxs-lookup"><span data-stu-id="d39f9-130">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="d39f9-131">안전한 링크 정책에 대 한 권장 설정은 [안전한 링크 정책 설정을](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d39f9-131">For our recommended settings for Safe Links policies, see [Safe Links policy settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).</span></span>

- <span data-ttu-id="d39f9-132">새 정책이 나 업데이트 된 정책을 적용할 최대 30 분을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-132">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="d39f9-133">[새 기능은 ATP에 계속 추가 됩니다](office-365-atp.md#new-features-in-office-365-atp).</span><span class="sxs-lookup"><span data-stu-id="d39f9-133">[New features are continually being added to ATP](office-365-atp.md#new-features-in-office-365-atp).</span></span> <span data-ttu-id="d39f9-134">새 기능을 추가 하면 기존 안전한 링크 정책을 조정 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-134">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="use-the-security--compliance-center-to-create-safe-links-policies"></a><span data-ttu-id="d39f9-135">보안 & 준수 센터를 사용 하 여 안전한 링크 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="d39f9-135">Use the Security & Compliance Center to create Safe Links policies</span></span>

<span data-ttu-id="d39f9-136">보안 & 준수 센터에서 사용자 지정 안전 링크 정책을 만들면 둘 다에 동일한 이름을 사용 하 여 안전 링크 규칙과 연결 된 안전한 링크 정책이 동시에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-136">Creating a custom Safe Links policy in the Security & Compliance Center creates the safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="d39f9-137">보안 & 준수 센터에서 **위협 관리** \> **정책** \> **ATP 안전한 링크로**이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-137">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="d39f9-138">**안전한 링크** 페이지에서 **만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-138">On the **Safe Links** page, click **Create**.</span></span>

3. <span data-ttu-id="d39f9-139">**새 안전 링크 정책** 마법사가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-139">The **New Safe Links policy** wizard opens.</span></span> <span data-ttu-id="d39f9-140">**정책 이름** 설정 페이지에서 다음 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-140">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="d39f9-141">**이름**: 정책을 설명하는 고유한 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-141">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="d39f9-142">**설명**: 정책에 대한 선택적 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-142">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="d39f9-143">작업을 마친 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-143">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="d39f9-144">**설정** 페이지가 나타나면 다음 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-144">On the **Settings** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="d39f9-145">**메시지에서 알 수 없는 잠재적 악성 url에 대 한 작업을 선택** **합니다.**</span><span class="sxs-lookup"><span data-stu-id="d39f9-145">**Select the action for unknown potentially malicious URLs in messages**: Select **On**.</span></span>

   - <span data-ttu-id="d39f9-146">**메시지에서 알 수 없는 잠재적 악성 url에 대 한 작업 선택**: 선택 또는 기본값 **해제** **를 선택 합니다** .</span><span class="sxs-lookup"><span data-stu-id="d39f9-146">**Select the action for unknown potentially malicious URLs in messages**: Select **On** or leave the default value **Off** selected.</span></span>

   - <span data-ttu-id="d39f9-147">**의심 스러운 링크 및 파일을 가리키는 링크에 대해 실시간 URL 검색을 적용**합니다. 전자 메일 메시지에서 실시간으로 링크를 검색할 수 있도록 하려면이 설정을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-147">**Apply real-time URL scanning for suspicious links and links that point to files**: Select this setting to enable real-time scanning of links in email messages.</span></span>

   - <span data-ttu-id="d39f9-148">**메시지를 배달 하기 전에 URL 검색이 완료 될 때까지 기다립니다**. 메시지를 배달 하기 전에 실시간 url 검색이 완료 될 때까지 기다리려면이 설정을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-148">**Wait for URL scanning to complete before delivering the message**: Select this setting to wait for real-time URL scanning to complete before delivering the message.</span></span>

   - <span data-ttu-id="d39f9-149">**조직 내에서 전송 되는 전자 메일 메시지에 안전한 링크 적용**: 내부 보낸 사람과 내부 받는 사람 간의 메시지에 안전한 링크 정책을 적용 하려면이 설정을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-149">**Apply safe links to email messages sent within the organization**: Select this setting to apply the Safe Links policy to messages between internal senders and internal recipients.</span></span>

   - <span data-ttu-id="d39f9-150">**사용자 클릭 추적 안 함**: 추적 사용자가 전자 메일 메시지의 url을 클릭할 수 있도록 하려면이 설정을 선택 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-150">**Do not track user clicks**: Leave this setting unselected to enable the tracking user clicks on URLs in email messages.</span></span>

   - <span data-ttu-id="d39f9-151">**사용자가 원래 url로 이동**하는 것을 허용 하지 않습니다. 사용자가 [경고 페이지](atp-safe-links.md#warning-pages-from-safe-links)의 원래 url을 클릭 하지 못하도록 차단 하려면이 설정을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-151">**Do not allow users to click through to original URL**: Select this setting to block users from clicking through to the original URL in [warning pages](atp-safe-links.md#warning-pages-from-safe-links).</span></span>

   - <span data-ttu-id="d39f9-152">**다음 url은 다시 쓰지**않습니다. 안전한 링크에 의해 차단 되는 지정 된 url에 액세스할 수 있도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-152">**Do not rewrite the following URLs**: Allows access the specified URLs that would otherwise be blocked by Safe Links.</span></span>

     <span data-ttu-id="d39f9-153">상자에 원하는 URL 또는 값을 입력 하 고</span><span class="sxs-lookup"><span data-stu-id="d39f9-153">In the box, type the URL or value that you want, and then click</span></span> ![단추 추가 아이콘](../../media/ITPro-EAC-AddIcon.png)<span data-ttu-id="d39f9-155">.</span><span class="sxs-lookup"><span data-stu-id="d39f9-155">.</span></span>

     <span data-ttu-id="d39f9-156">기존 항목을 제거 하려면 선택 하 고</span><span class="sxs-lookup"><span data-stu-id="d39f9-156">To remove an existing entry, select it and then click</span></span> ![삭제 단추 아이콘](../../media/ITPro-EAC-DeleteIcon.png)<span data-ttu-id="d39f9-158">.</span><span class="sxs-lookup"><span data-stu-id="d39f9-158">.</span></span>

     <span data-ttu-id="d39f9-159">항목 구문에 대 한 자세한 내용은 ["다음 url을 다시 쓰지 않음" 목록의 항목 구문을](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d39f9-159">For entry syntax, see [Entry syntax for the "Do not rewrite the following URLs" list](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>

   <span data-ttu-id="d39f9-160">이러한 설정에 대 한 자세한 내용은 [Microsoft 팀에 대 한](atp-safe-links.md#safe-links-settings-for-microsoft-teams)전자 메일 메시지 및 안전한 링크 설정 [에 대 한 안전한 링크 설정을](atp-safe-links.md#safe-links-settings-for-email-messages) 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d39f9-160">For detailed information about these settings, see [Safe Links settings for email messages](atp-safe-links.md#safe-links-settings-for-email-messages) and [Safe Links settings for Microsoft Teams](atp-safe-links.md#safe-links-settings-for-microsoft-teams).</span></span>

   <span data-ttu-id="d39f9-161">표준 및 엄격한 정책 설정에 대 한 권장 값은 [안전한 링크 정책 설정을](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d39f9-161">For more the recommended values for Standard and Strict policy settings, see [Safe Links policy settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).</span></span>

   <span data-ttu-id="d39f9-162">작업을 마친 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-162">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="d39f9-163">**적용 대상** 페이지에서 정책이 적용 되는 내부 받는 사람을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-163">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="d39f9-164">조건이나 예외는 한 번만 사용할 수 있지만, 조건이나 예외에 대한 값을 여러 개 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-164">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="d39f9-165">동일한 조건의 여러 값이나 예외는 OR 논리를 사용합니다(예: _\<recipient1\>_ 혹은 _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="d39f9-165">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="d39f9-166">다양한 조건이나 예외는 AND 논리를 사용합니다(예: _\<recipient1\>_ 및 _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="d39f9-166">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="d39f9-167">**조건 추가를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-167">Click **Add a condition**.</span></span> <span data-ttu-id="d39f9-168">표시 되는 드롭다운 목록에서 다음의 **경우 적용**아래의 조건을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-168">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="d39f9-169">**받는 사람**: 조직의 사서함, 메일 사용자 또는 메일 연락처를 하나 이상 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-169">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="d39f9-170">**받는 사람이 다음 구성원 인**경우: 조직에서 그룹을 하나 이상 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-170">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="d39f9-171">**받는 사람 도메인은** 조직에서 구성된 허용 도메인 중 하나 이상에서 받는 사람을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-171">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="d39f9-172">조건을 선택한 후에는 **이러한 상자 중 하나** 에 해당 하는 dropdown이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-172">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="d39f9-173">상자를 클릭 하 고 선택할 값 목록을 스크롤합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-173">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="d39f9-174">상자를 클릭 하 고 입력을 시작 하 여 목록을 필터링 하 고 값을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-174">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="d39f9-175">값을 더 추가 하려면 상자에서 빈 영역을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-175">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="d39f9-176">개별 항목을 제거 하려면 값에서 제거 아이콘 **제거** 를 클릭 ![ ](../../media/scc-remove-icon.png) 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-176">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="d39f9-177">전체 조건을 제거 하려면 **Remove** ![ 조건에서 제거 아이콘 제거를 클릭 ](../../media/scc-remove-icon.png) 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-177">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="d39f9-178">조건을 더 추가 하려면 **조건 추가** 를 클릭 하 고 **적용 된 경우**에는 나머지 값을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-178">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="d39f9-179">예외를 추가 하려면 **조건 추가** 를 클릭 하 고 다음의 **경우 제외**에서 예외를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-179">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="d39f9-180">설정 및 동작은 조건과 정확히 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-180">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="d39f9-181">작업을 마친 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-181">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="d39f9-182">**설정 검토** 페이지가 나타나면 설정을 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-182">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="d39f9-183">각 설정에 대해 **편집** 을 클릭 하 여 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-183">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="d39f9-184">작업이 완료 되 면 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-184">When you're finished, click **Finish**.</span></span>

## <a name="use-the-security--compliance-center-to-view-safe-links-policies"></a><span data-ttu-id="d39f9-185">보안 & 준수 센터를 사용 하 여 안전한 링크 정책 보기</span><span class="sxs-lookup"><span data-stu-id="d39f9-185">Use the Security & Compliance Center to view Safe Links policies</span></span>

1. <span data-ttu-id="d39f9-186">보안 & 준수 센터에서 **위협 관리** \> **정책** \> **ATP 안전한 링크로**이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-186">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="d39f9-187">**안전한 링크** 페이지의 목록에서 정책을 선택 하 고 다음을 클릭 합니다 (확인란을 선택 하지 않음).</span><span class="sxs-lookup"><span data-stu-id="d39f9-187">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

   <span data-ttu-id="d39f9-188">정책 세부 정보가 플라이 아웃에 표시 됨</span><span class="sxs-lookup"><span data-stu-id="d39f9-188">The policy details appear in a fly out</span></span>

## <a name="use-the-security--compliance-center-to-modify-safe-links-policies"></a><span data-ttu-id="d39f9-189">보안 & 준수 센터를 사용 하 여 안전한 링크 정책 수정</span><span class="sxs-lookup"><span data-stu-id="d39f9-189">Use the Security & Compliance Center to modify Safe Links policies</span></span>

1. <span data-ttu-id="d39f9-190">보안 & 준수 센터에서 **위협 관리** \> **정책** \> **ATP 안전한 링크로**이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-190">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="d39f9-191">**안전한 링크** 페이지의 목록에서 정책을 선택 하 고 다음을 클릭 합니다 (확인란을 선택 하지 않음).</span><span class="sxs-lookup"><span data-stu-id="d39f9-191">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="d39f9-192">정책 세부 정보가 표시 되 면 **정책 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-192">In the policy details fly out that appears, click **Edit policy**.</span></span>

<span data-ttu-id="d39f9-193">즉시 표시 되는 사용 가능한 설정은 [보안 & 준수 센터를 사용 하 여 안전한 링크 정책 만들기](#use-the-security--compliance-center-to-create-safe-links-policies) 섹션에 설명 된 설정과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-193">The available settings in the fly out that appears are identical to those described in the [Use the Security & Compliance Center to create Safe Links policies](#use-the-security--compliance-center-to-create-safe-links-policies) section.</span></span>

<span data-ttu-id="d39f9-194">정책을 사용 하거나 사용 하지 않도록 설정 하려면 다음 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d39f9-194">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-links-policies"></a><span data-ttu-id="d39f9-195">안전한 링크 정책 설정 또는 해제</span><span class="sxs-lookup"><span data-stu-id="d39f9-195">Enable or disable Safe Links policies</span></span>

1. <span data-ttu-id="d39f9-196">보안 & 준수 센터에서 **위협 관리** \> **정책** \> **ATP 안전한 링크로**이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-196">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="d39f9-197">**상태** 열에서 다음 값을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-197">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="d39f9-198">토글을 왼쪽으로 이동하여 정책을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-198">Move the toggle to the left to disable the policy:</span></span> ![정책 해제](../../media/scc-toggle-off.png)<span data-ttu-id="d39f9-200">.</span><span class="sxs-lookup"><span data-stu-id="d39f9-200">.</span></span>

   - <span data-ttu-id="d39f9-201">토글을 오른쪽으로 이동하여 정책을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-201">Move the toggle to the right to enable the policy:</span></span> ![정책 설정](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="d39f9-203">.</span><span class="sxs-lookup"><span data-stu-id="d39f9-203">.</span></span>

### <a name="set-the-priority-of-safe-links-policies"></a><span data-ttu-id="d39f9-204">안전한 링크 정책의 우선 순위 설정</span><span class="sxs-lookup"><span data-stu-id="d39f9-204">Set the priority of Safe Links policies</span></span>

<span data-ttu-id="d39f9-205">기본적으로 안전한 링크 정책에는 만들어진 순서를 기준으로 하는 우선 순위가 지정 됩니다 (최신 정책은 이전 정책 보다 낮은 우선 순위).</span><span class="sxs-lookup"><span data-stu-id="d39f9-205">By default, Safe Links policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="d39f9-206">낮은 우선순위 번호는 정책의 높은 우선순위(0이 가장 높음)를 나타내고 정책은 우선순위 순서에 따라 처리됩니다(높은 우선순위 정책은 낮은 우선순위 정책보다 먼저 처리됨).</span><span class="sxs-lookup"><span data-stu-id="d39f9-206">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="d39f9-207">두 정책의 우선순위는 동일 할 수 없으며, 첫 번째 정책이 적용된 후에는 정책 처리가 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-207">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="d39f9-208">우선순위 및 여러 정책을 평가하고 적용하는 방법에 대 한 자세한 내용은 전자 메일의 [전자 메일의 우선순위 및 보호](how-policies-and-protections-are-combined.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d39f9-208">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="d39f9-209">안전한 링크 정책은 처리 되는 순서 대로 표시 됩니다 (첫 번째 정책의 **우선 순위** 값은 0).</span><span class="sxs-lookup"><span data-stu-id="d39f9-209">Safe Links policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span>

<span data-ttu-id="d39f9-210">**참고**: 보안 & 준수 센터에서는 안전한 링크 정책의 우선 순위를 만든 후에만 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-210">**Note**: In the Security & Compliance Center, you can only change the priority of the Safe Links policy after you create it.</span></span> <span data-ttu-id="d39f9-211">PowerShell에서는 안전한 링크 규칙을 만들 때 기본 우선 순위를 재정의할 수 있습니다 (기존 규칙의 우선 순위에 영향을 줄 수 있음).</span><span class="sxs-lookup"><span data-stu-id="d39f9-211">In PowerShell, you can override the default priority when you create the safe links rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="d39f9-212">정책의 우선순위를 변경하려면 목록에서 정책을 위나 아래로 이동합니다. 보안 및 준수 센터에서 **우선순위** 번호를 직접 수정할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-212">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="d39f9-213">보안 & 준수 센터에서 **위협 관리** \> **정책** \> **ATP 안전한 링크로**이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-213">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="d39f9-214">**안전한 링크** 페이지의 목록에서 정책을 선택 하 고 다음을 클릭 합니다 (확인란을 선택 하지 않음).</span><span class="sxs-lookup"><span data-stu-id="d39f9-214">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="d39f9-215">정책 세부 정보가 표시 되 면 사용 가능한 우선 순위 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-215">In the policy details fly out that appears, click the available priority button:</span></span>

   - <span data-ttu-id="d39f9-216">**우선 순위** 값이 **0** 인 안전한 링크 정책에는 **우선 순위 낮추기** 단추만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-216">The Safe Links policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="d39f9-217">**우선 순위** 값이 가장 낮은 안전한 링크 정책 (예: **3**)에는 **우선 순위 향상** 단추만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-217">The Safe Links policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="d39f9-218">안전 링크 정책이 3 개 이상인 경우 가장 높거나 낮은 우선 순위 값 사이의 정책에는 **우선 순위 증가** 와 **우선 순위 낮추기** 단추가 모두 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-218">If you have three or more Safe Links policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="d39f9-219">우선 **순위 높임** 또는 **우선 순위 낮추기** 를 클릭 하 여 **우선 순위** 값을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-219">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="d39f9-220">작업을 마쳤으면 **닫기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-220">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-safe-links-policies"></a><span data-ttu-id="d39f9-221">보안 & 준수 센터를 사용 하 여 안전한 링크 정책 제거</span><span class="sxs-lookup"><span data-stu-id="d39f9-221">Use the Security & Compliance Center to remove Safe Links policies</span></span>

1. <span data-ttu-id="d39f9-222">보안 & 준수 센터에서 **위협 관리** \> **정책** \> **ATP 안전한 링크로**이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-222">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="d39f9-223">**안전한 링크** 페이지의 목록에서 정책을 선택 하 고 다음을 클릭 합니다 (확인란을 선택 하지 않음).</span><span class="sxs-lookup"><span data-stu-id="d39f9-223">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="d39f9-224">정책 세부 정보가 표시 되 면 **정책 삭제**를 클릭 한 다음 표시 되는 경고 대화 상자에서 **예** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-224">In the policy details fly out that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a><span data-ttu-id="d39f9-225">Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell을 사용 하 여 안전한 링크 정책 구성</span><span class="sxs-lookup"><span data-stu-id="d39f9-225">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies</span></span>

<span data-ttu-id="d39f9-226">앞에서 설명한 것 처럼 안전한 링크 정책은 안전한 링크 정책 및 안전한 링크 규칙으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-226">As previously described, a Safe Links policy consists of a safe links policy and a safe links rule.</span></span>

<span data-ttu-id="d39f9-227">PowerShell에서는 안전한 링크 정책과 안전한 링크 규칙 간의 차이가 명백 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-227">In PowerShell, the difference between safe links policies and safe links rules is apparent.</span></span> <span data-ttu-id="d39f9-228">\*\* \* -Get-safelinkspolicy\*\* cmdlet을 사용 하 여 안전한 링크 정책을 관리 하 고 \*\* \* -disable-safelinksrule\*\* cmdlet을 사용 하 여 안전한 링크 규칙을 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-228">You manage safe links policies by using the **\*-SafeLinksPolicy** cmdlets, and you manage safe links rules by using the **\*-SafeLinksRule** cmdlets.</span></span>

- <span data-ttu-id="d39f9-229">PowerShell에서는 먼저 안전한 링크 정책을 만든 다음 규칙이 적용 되는 정책을 식별 하는 안전 링크 규칙을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-229">In PowerShell, you create the safe links policy first, then you create the safe links rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="d39f9-230">PowerShell에서는 안전 링크 정책의 설정과 안전 링크 규칙을 각각 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-230">In PowerShell, you modify the settings in the safe links policy and the safe links rule separately.</span></span>
- <span data-ttu-id="d39f9-231">PowerShell에서 안전 링크 정책을 제거 하면 해당 하는 안전 링크 규칙이 자동으로 제거 되지 않으며 그 반대의 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-231">When you remove a safe links policy from PowerShell, the corresponding safe links rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-links-policies"></a><span data-ttu-id="d39f9-232">PowerShell을 사용 하 여 안전한 링크 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="d39f9-232">Use PowerShell to create Safe Links policies</span></span>

<span data-ttu-id="d39f9-233">PowerShell에서 안전한 링크 정책을 만드는 과정은 두 단계로 진행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-233">Creating a Safe Links policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="d39f9-234">안전한 링크 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-234">Create the safe links policy.</span></span>
2. <span data-ttu-id="d39f9-235">규칙이 적용 되는 안전한 링크 정책을 지정 하는 안전 링크 규칙을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-235">Create the safe links rule that specifies the safe links policy that the rule applies to.</span></span>

 <span data-ttu-id="d39f9-236">**참고:**</span><span class="sxs-lookup"><span data-stu-id="d39f9-236">**Notes**:</span></span>

- <span data-ttu-id="d39f9-237">새 안전 링크 규칙을 만들고 연결 되지 않은 기존 안전 링크 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-237">You can create a new safe links rule and assign an existing, unassociated safe links policy to it.</span></span> <span data-ttu-id="d39f9-238">안전한 링크 규칙은 둘 이상의 안전한 링크 정책에 연결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-238">A safe links rule can't be associated with more than one safe links policy.</span></span>

- <span data-ttu-id="d39f9-239">정책을 만든 후에 야 보안 & 준수 센터에서 사용할 수 없는 PowerShell의 새 안전 링크 정책에 대해 다음 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-239">You can configure the following settings on new safe links policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="d39f9-240">Disable-safelinksrule cmdlet에서_사용 하도록 설정_ 된 새 정책을 사용 하지 않도록 설정 `$false` **New-SafeLinksRule** 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-240">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeLinksRule** cmdlet).</span></span>
  - <span data-ttu-id="d39f9-241">Disable-safelinksrule cmdlet에 대 한 생성 (_우선 순위_ ) 중에 정책의 우선 순위를 설정 _\<Number\>_ 합니다. **New-SafeLinksRule**</span><span class="sxs-lookup"><span data-stu-id="d39f9-241">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeLinksRule** cmdlet).</span></span>

- <span data-ttu-id="d39f9-242">PowerShell에서 만든 새 안전 링크 정책은 안전한 링크 규칙에 정책을 할당할 때까지 보안 & 준수 센터에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-242">A new safe links policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a safe links rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a><span data-ttu-id="d39f9-243">1 단계: PowerShell을 사용 하 여 안전한 링크 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="d39f9-243">Step 1: Use PowerShell to create a safe links policy</span></span>

<span data-ttu-id="d39f9-244">안전한 링크 정책을 만들려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-244">To create a safe links policy, use this syntax:</span></span>

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

<span data-ttu-id="d39f9-245">**참고:**</span><span class="sxs-lookup"><span data-stu-id="d39f9-245">**Notes**:</span></span>

- <span data-ttu-id="d39f9-246">_DoNotRewriteUrls_ 매개 변수에 사용할 항목 구문에 대 한 자세한 내용은 ["다음 url을 다시 쓰지 않음" 목록의 항목 구문을](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d39f9-246">For details about the entry syntax to use for the _DoNotRewriteUrls_ parameter, see [Entry syntax for the "Do not rewrite the following URLs" list](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>

- <span data-ttu-id="d39f9-247">**Get-safelinkspolicy** cmdlet을 사용 하 여 기존 안전한 링크 정책을 수정할 때 _DoNotRewriteUrls_ 매개 변수에 사용할 수 있는 추가 구문을 보려면이 문서 뒷부분에 나오는 [PowerShell을 사용 하 여 안전한 링크 정책 수정](#use-powershell-to-modify-safe-links-policies) 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d39f9-247">For additional syntax that you can use for the _DoNotRewriteUrls_ parameter when you modify existing safe links policies by using the **Set-SafeLinksPolicy** cmdlet, see the [Use PowerShell to modify safe links policies](#use-powershell-to-modify-safe-links-policies) section later in this article.</span></span>

<span data-ttu-id="d39f9-248">이 예에서는 다음과 같은 값을 가진 Contoso All 이라는 안전한 링크 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-248">This example creates a safe links policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="d39f9-249">전자 메일 메시지에서 URL 검색 및 다시 쓰기를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-249">Turn on URL scanning and rewriting in email messages.</span></span>
- <span data-ttu-id="d39f9-250">팀에서 URL 검색을 설정 합니다 (탭 미리 보기에만 해당).</span><span class="sxs-lookup"><span data-stu-id="d39f9-250">Turn on URL scanning in Teams (TAP Preview only).</span></span>
- <span data-ttu-id="d39f9-251">클릭 한 Url에 대해 실시간 검색을 설정 하 고 파일을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-251">Turn on real-time scanning of clicked URLs, including clicked links that point to files.</span></span>
- <span data-ttu-id="d39f9-252">메시지를 배달 하기 전에 URL 검색이 완료 될 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-252">Wait for URL scanning to complete before delivering the message.</span></span>
- <span data-ttu-id="d39f9-253">내부 메시지에 대 한 URL 검색 및 다시 쓰기를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-253">Turn on URL scanning and rewriting for internal messages.</span></span>
- <span data-ttu-id="d39f9-254">Track 사용자가 _DoNotTrackUserClicks_ 매개 변수를 사용 하지 않는 안전한 링크 보호와 관련 되어 있으며 기본값은 $false 이며,이 값은 사용자 클릭이 추적 됨을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-254">Track user clicks related to Safe Links protection (we aren't using the _DoNotTrackUserClicks_ parameter, and the default value is $false, which means user clicks are tracked).</span></span>
- <span data-ttu-id="d39f9-255">사용자가 원래 URL을 클릭 하도록 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-255">Do not allow users to click through to the original URL.</span></span>

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

<span data-ttu-id="d39f9-256">구문과 매개 변수에 대 한 자세한 내용은 [get-safelinkspolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d39f9-256">For detailed syntax and parameter information, see [New-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a><span data-ttu-id="d39f9-257">2 단계: PowerShell을 사용 하 여 안전한 링크 규칙 만들기</span><span class="sxs-lookup"><span data-stu-id="d39f9-257">Step 2: Use PowerShell to create a safe links rule</span></span>

<span data-ttu-id="d39f9-258">안전한 링크 규칙을 만들려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-258">To create a safe links rule, use this syntax:</span></span>

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="d39f9-259">이 예에서는 다음과 같은 조건에 대해 Contoso 라는 안전 링크 규칙을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-259">This example creates a safe links rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="d39f9-260">이 규칙은 Contoso All 이라는 안전한 링크 정책과 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-260">The rule is associated with the safe links policy named Contoso All.</span></span>
- <span data-ttu-id="d39f9-261">규칙은 contoso.com 도메인의 모든 받는 사람에 게 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-261">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="d39f9-262">_Priority_ 매개 변수를 사용 하지 않으므로 기본 우선 순위가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-262">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="d39f9-263">이 규칙이 사용 하도록 설정 되어 있습니다 ( _enabled_ 매개 변수를 사용 하지 않으며 기본값은 `$true` ).</span><span class="sxs-lookup"><span data-stu-id="d39f9-263">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="d39f9-264">구문과 매개 변수에 대 한 자세한 내용은 [disable-safelinksrule](https://docs.microsoft.com/powershell/module/exchange/new-safelinksrule)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d39f9-264">For detailed syntax and parameter information, see [New-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/new-safelinksrule).</span></span>

### <a name="use-powershell-to-view-safe-links-policies"></a><span data-ttu-id="d39f9-265">PowerShell을 사용 하 여 안전한 링크 정책 보기</span><span class="sxs-lookup"><span data-stu-id="d39f9-265">Use PowerShell to view safe links policies</span></span>

<span data-ttu-id="d39f9-266">기존 안전한 링크 정책을 보려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-266">To view existing safe links policies, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="d39f9-267">이 예에서는 모든 안전 링크 정책의 요약 목록을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-267">This example returns a summary list of all safe links policies.</span></span>

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

<span data-ttu-id="d39f9-268">이 예에서는 Contoso 임원 이라는 안전한 링크 정책에 대 한 자세한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-268">This example returns detailed information for the safe links policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

<span data-ttu-id="d39f9-269">구문과 매개 변수에 대 한 자세한 내용은 [get-safelinkspolicy](https://docs.microsoft.com/powershell/module/exchange/get-safelinkspolicy)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d39f9-269">For detailed syntax and parameter information, see [Get-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safelinkspolicy).</span></span>

### <a name="use-powershell-to-view-safe-links-rules"></a><span data-ttu-id="d39f9-270">PowerShell을 사용 하 여 안전한 링크 규칙 보기</span><span class="sxs-lookup"><span data-stu-id="d39f9-270">Use PowerShell to view safe links rules</span></span>

<span data-ttu-id="d39f9-271">기존 안전 링크 규칙을 보려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-271">To view existing safe links rules, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="d39f9-272">이 예에서는 모든 안전 링크 규칙의 요약 목록을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-272">This example returns a summary list of all safe links rules.</span></span>

```PowerShell
Get-SafeLinksRule | Format-Table Name,State
```

<span data-ttu-id="d39f9-273">활성화된 또는 비활성화된 규칙을 기준으로 목록을 필터링하려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-273">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeLinksRule -State Disabled
```

```PowerShell
Get-SafeLinksRule -State Enabled
```

<span data-ttu-id="d39f9-274">이 예에서는 Contoso 임원 이라는 안전 링크 규칙에 대 한 자세한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-274">This example returns detailed information for the safe links rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksRule -Identity "Contoso Executives"
```

<span data-ttu-id="d39f9-275">구문과 매개 변수에 대 한 자세한 내용은 [disable-safelinksrule](https://docs.microsoft.com/powershell/module/exchange/get-safelinksrule)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d39f9-275">For detailed syntax and parameter information, see [Get-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/get-safelinksrule).</span></span>

### <a name="use-powershell-to-modify-safe-links-policies"></a><span data-ttu-id="d39f9-276">PowerShell을 사용 하 여 안전한 링크 정책 수정</span><span class="sxs-lookup"><span data-stu-id="d39f9-276">Use PowerShell to modify safe links policies</span></span>

<span data-ttu-id="d39f9-277">PowerShell에서 안전한 링크 정책의 이름을 바꿀 수는 없습니다 ( **get-safelinkspolicy** Cmdlet은 _Name_ 매개 변수를 사용 하지 않음).</span><span class="sxs-lookup"><span data-stu-id="d39f9-277">You can't rename a safe links policy in PowerShell (the **Set-SafeLinksPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="d39f9-278">보안 & 준수 센터에서 안전 링크 정책의 이름을 바꿀 때 안전한 링크 _규칙만_이름을 변경 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-278">When you rename a Safe Links policy in the Security & Compliance Center, you're only renaming the safe links _rule_.</span></span>

<span data-ttu-id="d39f9-279">PowerShell에서 안전한 링크 정책을 수정 하는 경우에는 _DoNotRewriteUrls_ 매개 변수 ( ["다음 url을 다시 쓰지 않음" 목록](atp-safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies))에 대해 사용 가능한 추가 고려 사항은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-279">The only additional consideration for modifying safe links policies in PowerShell is the available syntax for the _DoNotRewriteUrls_ parameter (the ["Do not rewrite the following URLs" list](atp-safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)):</span></span>

- <span data-ttu-id="d39f9-280">기존 항목을 대체 하는 값을 추가 하려면 다음 구문을 `"Entry1","Entry2,..."EntryN"` 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-280">To add values that will replace any existing entries, use the following syntax: `"Entry1","Entry2,..."EntryN"`.</span></span>
- <span data-ttu-id="d39f9-281">기존의 다른 항목에 영향을 주지 않고 값을 추가 하거나 제거 하려면 다음 구문을 사용 합니다. `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span><span class="sxs-lookup"><span data-stu-id="d39f9-281">To add or remove values without affecting other existing entries, use the following syntax: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span></span>

<span data-ttu-id="d39f9-282">그렇지 않은 경우에는이 문서의 앞부분에 나오는 [1 단계: PowerShell을 사용 하 여 안전한 링크 정책 만들기](#step-1-use-powershell-to-create-a-safe-links-policy) 섹션에 설명 된 대로 안전한 링크 정책을 만드는 경우에도 동일한 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-282">Otherwise, the same settings are available when you create a safe links policy as described in the [Step 1: Use PowerShell to create a safe links policy](#step-1-use-powershell-to-create-a-safe-links-policy) section earlier in this article.</span></span>

<span data-ttu-id="d39f9-283">안전한 링크 정책을 수정 하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-283">To modify a safe links policy, use this syntax:</span></span>

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="d39f9-284">구문 및 매개 변수에 대 한 자세한 내용은 [get-safelinkspolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d39f9-284">For detailed syntax and parameter information, see [Set-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy).</span></span>

### <a name="use-powershell-to-modify-safe-links-rules"></a><span data-ttu-id="d39f9-285">PowerShell을 사용 하 여 안전한 링크 규칙 수정</span><span class="sxs-lookup"><span data-stu-id="d39f9-285">Use PowerShell to modify safe links rules</span></span>

<span data-ttu-id="d39f9-286">PowerShell에서 안전 링크 규칙을 수정할 때 사용할 수 없는 유일한 설정은 사용 하지 않도록 설정 된 규칙을 만들 수 있는 _Enabled_ 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-286">The only setting that's not available when you modify a safe links rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="d39f9-287">기존 안전한 링크 규칙을 사용 하거나 사용 하지 않도록 설정 하려면 다음 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d39f9-287">To enable or disable existing safe links rules, see the next section.</span></span>

<span data-ttu-id="d39f9-288">그렇지 않은 경우에는이 문서의 앞부분에 나오는 [2 단계: PowerShell을 사용 하 여 안전한 링크 규칙 만들기](#step-2-use-powershell-to-create-a-safe-links-rule) 섹션에 설명 된 대로 규칙을 만들 때도 같은 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-288">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe links rule](#step-2-use-powershell-to-create-a-safe-links-rule) section earlier in this article.</span></span>

<span data-ttu-id="d39f9-289">안전한 링크 규칙을 수정 하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-289">To modify a safe links rule, use this syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="d39f9-290">구문 및 매개 변수에 대 한 자세한 내용은 [disable-safelinksrule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d39f9-290">For detailed syntax and parameter information, see [Set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a><span data-ttu-id="d39f9-291">PowerShell을 사용 하 여 안전한 링크 규칙 사용 또는 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="d39f9-291">Use PowerShell to enable or disable safe links rules</span></span>

<span data-ttu-id="d39f9-292">PowerShell에서 안전 링크 규칙을 사용 하거나 사용 하지 않도록 설정 하면 전체 안전 링크 정책 (안전한 링크 규칙 및 할당 된 안전한 링크 정책)을 사용 하거나 사용 하지 않도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-292">Enabling or disabling a safe links rule in PowerShell enables or disables the whole Safe Links policy (the safe links rule and the assigned safe links policy).</span></span>

<span data-ttu-id="d39f9-293">PowerShell에서 안전 링크 규칙을 사용 하거나 사용 하지 않도록 설정 하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-293">To enable or disable a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeLinksRule | Disable-SafeLinksRule> -Identity "<RuleName>"
```

<span data-ttu-id="d39f9-294">이 예에서는 Marketing 부서 라는 안전 링크 규칙을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-294">This example disables the safe links rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="d39f9-295">다음은 동일한 규칙을 사용하도록 설정하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-295">This example enables same rule.</span></span>

```PowerShell
Enable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="d39f9-296">구문 및 매개 변수에 대 한 자세한 내용은 [Enable-disable-safelinksrule](https://docs.microsoft.com/powershell/module/exchange/enable-safelinksrule) 및 [Disable-disable-safelinksrule](https://docs.microsoft.com/powershell/module/exchange/disable-safelinksrule)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d39f9-296">For detailed syntax and parameter information, see [Enable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/enable-safelinksrule) and [Disable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/disable-safelinksrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-links-rules"></a><span data-ttu-id="d39f9-297">PowerShell을 사용 하 여 안전한 링크 규칙의 우선 순위 설정</span><span class="sxs-lookup"><span data-stu-id="d39f9-297">Use PowerShell to set the priority of safe links rules</span></span>

<span data-ttu-id="d39f9-298">규칙에 설정 가능한 가장 높은 우선 순위 값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-298">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="d39f9-299">설정할 수 있는 가장 낮은 값은 규칙 수에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-299">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="d39f9-300">예를 들어 규칙이 5개 있는 경우, 우선순위 값 0~4를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-300">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="d39f9-301">기존 규칙의 우선순위를 변경하면 다른 규칙에 계단식 효과를 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-301">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="d39f9-302">예를 들어 사용자 지정 규칙 5개(우선순위: 0~4)가 있고 규칙의 우선순위를 2로 변경하면, 우선순위 2인 기존 규칙이 우선순위 3으로 변경되고, 우선순위 3인 규칙이 우선순위 4로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-302">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="d39f9-303">PowerShell에서 안전한 링크 규칙의 우선 순위를 설정 하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-303">To set the priority of a safe links rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="d39f9-304">다음은 Marketing Department라는 규칙의 우선순위를 2로 설정하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-304">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="d39f9-305">우선순위가 2 이하인 모든 기존 규칙은 1씩 감소합니다(우선순위 번호는 1씩 증가함).</span><span class="sxs-lookup"><span data-stu-id="d39f9-305">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeLinksRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="d39f9-306">**참고**: 새 규칙을 만들 때 우선 순위를 설정 하려면 대신 **Disable-safelinksrule** cmdlet에서 _priority_ 매개 변수를 사용 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d39f9-306">**Note**: To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeLinksRule** cmdlet instead.</span></span>

<span data-ttu-id="d39f9-307">구문 및 매개 변수에 대 한 자세한 내용은 [disable-safelinksrule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d39f9-307">For detailed syntax and parameter information, see [Set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-remove-safe-links-policies"></a><span data-ttu-id="d39f9-308">PowerShell을 사용 하 여 안전한 링크 정책 제거</span><span class="sxs-lookup"><span data-stu-id="d39f9-308">Use PowerShell to remove safe links policies</span></span>

<span data-ttu-id="d39f9-309">PowerShell을 사용 하 여 안전한 링크 정책을 제거 하면 해당 하는 안전 링크 규칙이 제거 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-309">When you use PowerShell to remove a safe links policy, the corresponding safe links rule isn't removed.</span></span>

<span data-ttu-id="d39f9-310">PowerShell에서 안전한 링크 정책을 제거 하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-310">To remove a safe links policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="d39f9-311">이 예에서는 Marketing 부서 라는 안전 링크 정책을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-311">This example removes the safe links policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

<span data-ttu-id="d39f9-312">구문과 매개 변수에 대 한 자세한 내용은 [get-safelinkspolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safelinkspolicy)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d39f9-312">For detailed syntax and parameter information, see [Remove-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safelinkspolicy).</span></span>

### <a name="use-powershell-to-remove-safe-links-rules"></a><span data-ttu-id="d39f9-313">PowerShell을 사용 하 여 안전한 링크 규칙 제거</span><span class="sxs-lookup"><span data-stu-id="d39f9-313">Use PowerShell to remove safe links rules</span></span>

<span data-ttu-id="d39f9-314">PowerShell을 사용 하 여 안전한 링크 규칙을 제거 하면 해당 하는 안전한 링크 정책이 제거 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-314">When you use PowerShell to remove a safe links rule, the corresponding safe links policy isn't removed.</span></span>

<span data-ttu-id="d39f9-315">PowerShell에서 안전 링크 규칙을 제거 하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-315">To remove a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

<span data-ttu-id="d39f9-316">이 예에서는 Marketing 부서 라는 안전 링크 규칙을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-316">This example removes the safe links rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="d39f9-317">구문과 매개 변수에 대 한 자세한 내용은 [disable-safelinksrule](https://docs.microsoft.com/powershell/module/exchange/remove-safelinksrule)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d39f9-317">For detailed syntax and parameter information, see [Remove-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/remove-safelinksrule).</span></span>

<span data-ttu-id="d39f9-318">안전한 링크가 메시지를 검색 하는지 확인 하려면 사용 가능한 Advanced Threat Protection 보고서를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-318">To verify that Safe Links is scanning messages, check the available Advanced Threat Protection reports.</span></span> <span data-ttu-id="d39f9-319">자세한 내용은 [View reports For Office 365 ATP](view-reports-for-atp.md) 및 [Security & 준수 센터에서 탐색기 사용](threat-explorer.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d39f9-319">For more information, see [View reports for Office 365 ATP](view-reports-for-atp.md) and [Use Explorer in the Security & Compliance Center](threat-explorer.md).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="d39f9-320">이 절차가 제대로 수행되었는지 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="d39f9-320">How do you know these procedures worked?</span></span>

<span data-ttu-id="d39f9-321">안전한 링크 정책이 성공적으로 생성, 수정 또는 제거 되었는지 확인 하려면 다음 단계 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-321">To verify that you've successfully created, modified, or removed Safe Links policies, do any of the following steps:</span></span>

- <span data-ttu-id="d39f9-322">보안 & 준수 센터에서 **위협 관리** \> **정책** \> **ATP 안전한 링크로**이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-322">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span> <span data-ttu-id="d39f9-323">정책 목록, 해당 **상태** 값 및 해당 **우선 순위** 값을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-323">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="d39f9-324">자세한 내용을 보려면 목록에서 정책을 선택 하 고 플라이 아웃에서 세부 정보를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-324">To view more details, select the policy from the list, and view the details in the fly out.</span></span>

- <span data-ttu-id="d39f9-325">Exchange Online PowerShell 또는 Exchange Online Protection PowerShell에서 \<Name\> 정책 또는 규칙의 이름으로 바꾸고 다음 명령을 실행 하 고 설정을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d39f9-325">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```
