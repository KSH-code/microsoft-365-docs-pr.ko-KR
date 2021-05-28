---
title: 테넌트 허용/차단 목록에서 허용 및 차단 관리
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 관리자는 보안 포털의 테넌트 허용/차단 목록에서 허용 및 차단을 구성하는 방법을 배울 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 636114180a1814f5ef842b2a704f2df98488f46e
ms.sourcegitcommit: 5377b00703b6f559092afe44fb61462e97968a60
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694488"
---
# <a name="manage-the-tenant-allowblock-list"></a><span data-ttu-id="37c61-103">테넌트 허용/차단 목록 관리</span><span class="sxs-lookup"><span data-stu-id="37c61-103">Manage the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="37c61-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="37c61-104">**Applies to**</span></span>
- [<span data-ttu-id="37c61-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="37c61-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="37c61-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="37c61-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="37c61-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="37c61-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
>
> <span data-ttu-id="37c61-108">이 문서에 설명된 기능은 미리 보기에 있으며 변경될 수 있으며 일부 조직에서는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-108">The features described in this article are in Preview, are subject to change, and are not available in all organizations.</span></span>  <span data-ttu-id="37c61-109">이 문서에 설명된 스푸핑 기능이 조직에 없는 경우 [EOP에서](walkthrough-spoof-intelligence-insight.md)스푸핑 인텔리전스 정책을 사용하여 스푸핑된 보낸 사람 관리에서 이전 스푸핑 관리 환경을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="37c61-109">If your organization does not have the spoof features as described in this article, see the older spoof management experience at [Manage spoofed senders using the spoof intelligence policy and spoof intelligence insight in EOP](walkthrough-spoof-intelligence-insight.md).</span></span>
>
> <span data-ttu-id="37c61-110">현재는 **테넌트** 허용/차단 목록에서 허용된 URL 또는 파일 항목을 구성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-110">You can't **configure** allowed URL or file items in the Tenant Allow/Block List at this time.</span></span>

<span data-ttu-id="37c61-111">Microsoft 365 사서함이 없는 Exchange Online 또는 EOP(독립 실행형 Exchange Online Protection) 조직에서 Exchange Online EOP 필터링 판정에 동의하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-111">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="37c61-112">예를 들어 양호한 메시지는 나쁜 메시지(가음성)로 표시되거나 잘못된 메시지가 통과(거짓 부정)로 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-112">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="37c61-113">보안 및 준수 센터의 테넌트 허용/차단 & 필터링 판정을 수동으로 Microsoft 365 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-113">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="37c61-114">테넌트 허용/차단 목록은 메일 흐름 중과 사용자가 클릭할 때 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-114">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="37c61-115">다음과 같은 유형의 다시 지정을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-115">You can specify the following types of overrides:</span></span>

- <span data-ttu-id="37c61-116">차단할 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-116">URLs to block.</span></span>
- <span data-ttu-id="37c61-117">차단할 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-117">Files to block.</span></span>
- <span data-ttu-id="37c61-118">허용하거나 차단할 스푸핑된 보낸 사람입니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-118">Spoofed senders to allow or block.</span></span> <span data-ttu-id="37c61-119">스푸핑 인텔리전스 인사이트에서 [](learn-about-spoof-intelligence.md)허용 또는 차단 판정을 다시 설정하면 스푸핑된 보낸 사람이 테넌트 허용/차단 목록의 스푸핑 탭에만 나타나는 수동 허용 또는 차단 항목이 됩니다. </span><span class="sxs-lookup"><span data-stu-id="37c61-119">If you override the allow or block verdict in the [spoof intelligence insight](learn-about-spoof-intelligence.md), the spoofed sender becomes a manual allow or block entry that only appears on the **Spoof** tab in the Tenant Allow/Block List.</span></span> <span data-ttu-id="37c61-120">스푸핑 인텔리전스에서 검색되기 전에 여기에 스푸핑된 보낸 사람에 대한 허용 또는 차단 항목을 수동으로 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-120">You can also manually create allow or block entries for spoofed senders here before they're detected by spoof intelligence.</span></span>

<span data-ttu-id="37c61-121">이 문서에서는 보안 & 준수 센터 또는 PowerShell(Exchange Online 사서함이 있는 Microsoft 365 Exchange Online 조직에 대한 Exchange Online PowerShell, Exchange Online 사서함이 없는 조직의 독립 실행형 EOP PowerShell)에서 테넌트 허용/차단 목록의 항목을 구성하는 방법에 대해 설명하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-121">This article describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="37c61-122">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="37c61-122">What do you need to know before you begin?</span></span>

- <span data-ttu-id="37c61-123"><https://protection.office.com/>에서 보안 및 준수 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-123">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="37c61-124">테넌트 **허용/차단 목록 페이지로 직접 이동하기** 위해 를 <https://protection.office.com/tenantAllowBlockList> 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="37c61-124">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="37c61-125">파일의 SHA256 해시 값을 사용하여 파일을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-125">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="37c61-126">파일에서 파일의 SHA256 해시 값을 Windows 명령 프롬프트에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-126">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="37c61-127">값의 예로는 를 들 수 `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-127">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="37c61-128">pHash(지각 해시) 값은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-128">Perceptual hash (pHash) values are not supported.</span></span>

- <span data-ttu-id="37c61-129">사용 가능한 URL 값은 이 문서 부분의 [테넌트 허용/차단](#url-syntax-for-the-tenant-allowblock-list) 목록 섹션에 대한 URL 구문에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-129">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="37c61-130">테넌트 허용/차단 목록을 사용하면 URL에 대해 최대 500개 항목과 파일 해시의 항목 500개가 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-130">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="37c61-131">각 항목의 최대 문자 수는 다음입니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-131">The maximum number of characters for each entry is:</span></span>
  - <span data-ttu-id="37c61-132">파일 해시 = 64</span><span class="sxs-lookup"><span data-stu-id="37c61-132">File hashes = 64</span></span>
  - <span data-ttu-id="37c61-133">URL = 250</span><span class="sxs-lookup"><span data-stu-id="37c61-133">URL = 250</span></span>

- <span data-ttu-id="37c61-134">항목이 30분 이내에 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-134">An entry should be active within 30 minutes.</span></span>

- <span data-ttu-id="37c61-135">기본적으로 테넌트 허용/차단 목록의 항목은 30일 후에 만료됩니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-135">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="37c61-136">날짜를 지정하거나 만료되지 않는 날짜로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-136">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="37c61-137">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="37c61-137">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="37c61-138">독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="37c61-138">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="37c61-139">이 게시물의 절차를 수행하려면 먼저 Exchange Online에서 사용 권한을 할당받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-139">You need to be assigned permissions in Exchange Online before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="37c61-140">**URL 및 파일**:</span><span class="sxs-lookup"><span data-stu-id="37c61-140">**URLs and files**:</span></span>
    - <span data-ttu-id="37c61-141">테넌트 허용/차단 목록에서 값을 추가 및 제거하려면 조직  관리 또는 보안 관리자 역할 그룹의 **구성원이** 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-141">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
    - <span data-ttu-id="37c61-142">테넌트 허용/차단 목록에 대한 읽기 전용 액세스의 경우 전역  읽기 사용자 또는 보안 읽기 권한이 있는 역할 그룹의 **구성원이** 되거나 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-142">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>
  - <span data-ttu-id="37c61-143">**스푸핑:** 다음 조합 중 하나</span><span class="sxs-lookup"><span data-stu-id="37c61-143">**Spoofing**: One of the following combinations:</span></span>
    - <span data-ttu-id="37c61-144">**조직 관리**</span><span class="sxs-lookup"><span data-stu-id="37c61-144">**Organization Management**</span></span>
    - <span data-ttu-id="37c61-145">**보안 관리자** <u>및</u> 보기 전용 **구성** 또는 보기 전용 **조직 관리.**</span><span class="sxs-lookup"><span data-stu-id="37c61-145">**Security Administrator** <u>and</u> **View-Only Configuration** or **View-Only Organization Management**.</span></span>

  <span data-ttu-id="37c61-146">자세한 내용은 [Exchange Online의 사용 권한](/exchange/permissions-exo/permissions-exo)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="37c61-146">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="37c61-147">Microsoft 365 관리 센터의 해당 Azure Active Directory 역할에 사용자를 추가하면 사용자에게 필요한 권한 _및_ Microsoft 365의 다른 기능에 대한 권한이 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-147">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="37c61-148">자세한 내용은 [관리자 역할 정보](../../admin/add-users/about-admin-roles.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="37c61-148">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="37c61-149">[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups)의 **보기 전용 조직 관리** 역할 그룹에도 기능에 대한 읽기 전용 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-149">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-security--compliance-center-to-create-block-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="37c61-150">보안 및 & 센터를 사용하여 테넌트 허용/차단 목록에 차단 URL 항목 만들기</span><span class="sxs-lookup"><span data-stu-id="37c61-150">Use the Security & Compliance Center to create block URL entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="37c61-151">보안 및 & 센터에서 위협 **관리** 정책 \>  \> **테넌트 허용/차단 목록으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="37c61-151">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="37c61-152">**테넌트 허용/차단 목록** 페이지에서 URL  탭이 선택되어 있는지 확인한 다음 **차단을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="37c61-152">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Block**</span></span>

3. <span data-ttu-id="37c61-153">나타나는 **URL 차단** 플라이아웃에서 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-153">In the **Block URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="37c61-154">**차단할 URL 추가:** 줄당 하나의 URL을 입력하고 최대 20개까지 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-154">**Add URLs to block**: Enter one URL per line, up to a maximum of 20.</span></span> <span data-ttu-id="37c61-155">URL 항목의 구문에 대한 자세한 내용은 이 문서 부분의 [테넌트 허용/차단](#url-syntax-for-the-tenant-allowblock-list) 목록 섹션에 대한 URL 구문을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="37c61-155">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

   - <span data-ttu-id="37c61-156">**만료 안 하세요:** 다음 단계 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-156">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="37c61-157">설정이 꺼져 있는지 확인하고(토글 해제) 만료 날짜 상자를 사용하여 항목의 만료 ![ ](../../media/scc-toggle-off.png) 날짜를 지정합니다. </span><span class="sxs-lookup"><span data-stu-id="37c61-157">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

       <span data-ttu-id="37c61-158">또는</span><span class="sxs-lookup"><span data-stu-id="37c61-158">or</span></span>

     - <span data-ttu-id="37c61-159">토글을 오른쪽으로 이동하여 만료되지 않는 항목을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-159">Move the toggle to the right to configure the entries to never expire:</span></span> ![토글 켬](../../media/scc-toggle-on.png)<span data-ttu-id="37c61-161">.</span><span class="sxs-lookup"><span data-stu-id="37c61-161">.</span></span>

   - <span data-ttu-id="37c61-162">**선택 사항:** 항목에 대한 설명 텍스트를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-162">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="37c61-163">작업을 마쳤으면 **추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-163">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-block-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="37c61-164">보안 및 & 센터를 사용하여 테넌트 허용/차단 목록에 차단 파일 항목 만들기</span><span class="sxs-lookup"><span data-stu-id="37c61-164">Use the Security & Compliance Center to create block file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="37c61-165">보안 및 & 센터에서 위협 **관리** 정책 \>  \> **테넌트 허용/차단 목록으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="37c61-165">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="37c61-166">**테넌트 허용/차단 목록 페이지에서**  파일 탭을 선택한 다음 차단을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="37c61-166">On the **Tenant Allow/Block List** page, select the **Files** tab, and then click **Block**.</span></span>

3. <span data-ttu-id="37c61-167">**플라이아웃을 차단할** 파일 추가에서 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-167">In the **Add files to block** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="37c61-168">**파일 해시 추가:** 줄당 SHA256 해시 값 하나(최대 20개)를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-168">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="37c61-169">**만료 안 하세요:** 다음 단계 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-169">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="37c61-170">설정이 꺼져 있는지 확인하고(토글 해제) 만료 날짜 상자를 사용하여 항목의 만료 ![ ](../../media/scc-toggle-off.png) 날짜를 지정합니다. </span><span class="sxs-lookup"><span data-stu-id="37c61-170">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="37c61-171">또는</span><span class="sxs-lookup"><span data-stu-id="37c61-171">or</span></span>

     - <span data-ttu-id="37c61-172">토글을 오른쪽으로 이동하여 만료되지 않는 항목을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-172">Move the toggle to the right to configure the entries to never expire:</span></span> ![토글 켬](../../media/scc-toggle-on.png)<span data-ttu-id="37c61-174">.</span><span class="sxs-lookup"><span data-stu-id="37c61-174">.</span></span>

   - <span data-ttu-id="37c61-175">**선택 사항:** 항목에 대한 설명 텍스트를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-175">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="37c61-176">작업을 마쳤으면 **추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-176">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="37c61-177">보안 및 & 센터를 사용하여 테넌트 허용/차단 목록에서 스푸핑된 보낸 사람 항목을 만들거나 차단</span><span class="sxs-lookup"><span data-stu-id="37c61-177">Use the Security & Compliance Center to create allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="37c61-178">**참고:**</span><span class="sxs-lookup"><span data-stu-id="37c61-178">**Notes**:</span></span>

- <span data-ttu-id="37c61-179">_스푸핑된_ 사용자와 도메인  쌍에 정의된 전송 인프라의 조합만 스푸핑을 특별히 허용하거나 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-179">Only the _combination_ of the spoofed user _and_ the sending infrastructure as defined in the domain pair is specifically allowed or blocked from spoofing.</span></span>
- <span data-ttu-id="37c61-180">도메인 쌍에 대해 허용 또는 차단 항목을 구성하면 해당 도메인 쌍의 메시지가 더 이상 스푸핑 인텔리전스 인사이트에 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-180">When you configure an allow or block entry for a domain pair, messages from that domain pair no longer appear in the spoof intelligence insight.</span></span>
- <span data-ttu-id="37c61-181">스푸핑된 보낸 사람에 대한 항목은 만료되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-181">Entries for spoofed senders never expire.</span></span>

1. <span data-ttu-id="37c61-182">보안 및 & 센터에서 위협 **관리** 정책 \>  \> **테넌트 허용/차단 목록으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="37c61-182">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="37c61-183">**테넌트 허용/차단 목록** 페이지에서  스푸핑 탭을 선택한 다음 추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="37c61-183">On the **Tenant Allow/Block List** page, select the **Spoofing** tab, and then click **Add**.</span></span>

3. <span data-ttu-id="37c61-184">나타나는 **새 도메인** 쌍 추가 플라이아웃에서 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-184">In the **Add new domain pairs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="37c61-185">**와일드카드를 통해** 새 도메인 쌍 추가: 한 줄에 도메인 쌍을 하나씩 입력하고 최대 20개까지 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-185">**Add new domain pairs with wildcards**: Enter one domain pair per line, up to a maximum of 20.</span></span> <span data-ttu-id="37c61-186">스푸핑된 보낸 사람 항목에 대한 구문에 대한 자세한 내용은 이 문서 의 부분에 있는 테넌트 [허용/차단](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) 목록 섹션의 스푸핑된 보낸 사람 항목에 대한 도메인 쌍 구문을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="37c61-186">For details about the syntax for spoofed sender entries, see the [Domain pair syntax for spoofed sender entries in the Tenant Allow/Block List](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) section later in this article.</span></span>

   - <span data-ttu-id="37c61-187">**스푸핑 유형:** 다음 값 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-187">**Spoof type**: Select one of the following values:</span></span>
     - <span data-ttu-id="37c61-188">**내부:** 스푸핑된 보낸 사람이 조직에 속한 도메인(허용 [도메인)에 있습니다.](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)</span><span class="sxs-lookup"><span data-stu-id="37c61-188">**Internal**: The spoofed sender is in a domain that belongs to your organization (an [accepted domain](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)).</span></span>
     - <span data-ttu-id="37c61-189">**외부:** 스푸핑된 보낸 사람이 외부 도메인에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-189">**External**: The spoofed sender is in an external domain.</span></span>

   - <span data-ttu-id="37c61-190">**작업:** 허용 **또는 차단을** **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="37c61-190">**Action**: Select **Allow** or **Block**.</span></span>

4. <span data-ttu-id="37c61-191">작업을 마쳤으면 **추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-191">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="37c61-192">보안 및 & 센터를 사용하여 테넌트 허용/차단 목록의 항목 보기</span><span class="sxs-lookup"><span data-stu-id="37c61-192">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="37c61-193">보안 및 & 센터에서 위협 **관리** 정책 \>  \> **테넌트 허용/차단 목록으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="37c61-193">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="37c61-194">원하는 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-194">Select the tab you want.</span></span> <span data-ttu-id="37c61-195">사용 가능한 열은 선택한 탭에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-195">The columns that are available depend on the tab you selected:</span></span>

   - <span data-ttu-id="37c61-196">**URL**:</span><span class="sxs-lookup"><span data-stu-id="37c61-196">**URLs**:</span></span>
     - <span data-ttu-id="37c61-197">**값:** URL입니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-197">**Value**: The URL.</span></span>
     - <span data-ttu-id="37c61-198">**작업**: 값 **Block 입니다.**</span><span class="sxs-lookup"><span data-stu-id="37c61-198">**Action**: The value **Block**.</span></span>
     - <span data-ttu-id="37c61-199">**마지막으로 업데이트된 날짜**</span><span class="sxs-lookup"><span data-stu-id="37c61-199">**Last updated date**</span></span>
     - <span data-ttu-id="37c61-200">**만료 날짜**</span><span class="sxs-lookup"><span data-stu-id="37c61-200">**Expiration date**</span></span>
     - <span data-ttu-id="37c61-201">**참고**</span><span class="sxs-lookup"><span data-stu-id="37c61-201">**Note**</span></span>

   - <span data-ttu-id="37c61-202">**파일**</span><span class="sxs-lookup"><span data-stu-id="37c61-202">**Files**</span></span>
     - <span data-ttu-id="37c61-203">**값:** 파일 해시입니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-203">**Value**: The file hash.</span></span>
     - <span data-ttu-id="37c61-204">**작업**: 값 **Block 입니다.**</span><span class="sxs-lookup"><span data-stu-id="37c61-204">**Action**: The value **Block**.</span></span>
     - <span data-ttu-id="37c61-205">**마지막으로 업데이트된 날짜**</span><span class="sxs-lookup"><span data-stu-id="37c61-205">**Last updated date**</span></span>
     - <span data-ttu-id="37c61-206">**만료 날짜**</span><span class="sxs-lookup"><span data-stu-id="37c61-206">**Expiration date**</span></span>
     - <span data-ttu-id="37c61-207">**참고**</span><span class="sxs-lookup"><span data-stu-id="37c61-207">**Note**</span></span>

   - <span data-ttu-id="37c61-208">**스푸핑**</span><span class="sxs-lookup"><span data-stu-id="37c61-208">**Spoofing**</span></span>
     - <span data-ttu-id="37c61-209">**스푸핑된 사용자**</span><span class="sxs-lookup"><span data-stu-id="37c61-209">**Spoofed user**</span></span>
     - <span data-ttu-id="37c61-210">**인프라 보내기**</span><span class="sxs-lookup"><span data-stu-id="37c61-210">**Sending infrastructure**</span></span>
     - <span data-ttu-id="37c61-211">**스푸핑 유형**: 내부 또는 외부 **값입니다.** </span><span class="sxs-lookup"><span data-stu-id="37c61-211">**Spoof type**: The value **Internal** or **External**.</span></span>
     - <span data-ttu-id="37c61-212">**작업**: 값 **Block** 또는 **Allow입니다.**</span><span class="sxs-lookup"><span data-stu-id="37c61-212">**Action**: The value **Block** or **Allow**.</span></span>

   <span data-ttu-id="37c61-213">열 제목을 클릭하여 오차 또는 내선 순서로 정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-213">You can click on a column heading to sort in ascending or descending order.</span></span>

   <span data-ttu-id="37c61-214">그룹을 **클릭하여** 결과를 그룹화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-214">You can click **Group** to group the results.</span></span> <span data-ttu-id="37c61-215">사용 가능한 값은 선택한 탭에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-215">The values that are available depend on the tab you selected:</span></span>

   - <span data-ttu-id="37c61-216">**URL:** 작업을 사용하여 결과를 그룹화할 수 **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="37c61-216">**URLs**: You can group the results by **Action**.</span></span>
   - <span data-ttu-id="37c61-217">**파일**: 작업을 사용하여 결과를 그룹화할 **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="37c61-217">**Files**: You can group the results by **Action**.</span></span>
   - <span data-ttu-id="37c61-218">**BCL 우회를 위한** 보낸 사람 도메인: **이** 탭에서는 그룹을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-218">**Sender domains for BCL bypass**: **Group** is not available on this tab.</span></span>
   - <span data-ttu-id="37c61-219">**스푸핑**: 작업 또는 스푸핑 유형별로 결과를 **그룹화할 수 있습니다.** </span><span class="sxs-lookup"><span data-stu-id="37c61-219">**Spoofing**: You can group the results by **Action** or **Spoof type**.</span></span>

   <span data-ttu-id="37c61-220">**검색을** 클릭하고 값의 전체 또는 일부를 입력한 다음 Enter를 눌러 특정 값을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-220">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="37c61-221">완료되면 검색 지우기 **검색** ![ 아이콘 지우기 를 ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-221">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

   <span data-ttu-id="37c61-222">**필터를** 클릭하여 결과를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-222">Click **Filter** to filter the results.</span></span> <span data-ttu-id="37c61-223">필터 플라이아웃에서  사용할 수 있는 값은 선택한 탭에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-223">The values that are available in **Filter** flyout that appears depend on the tab you selected:</span></span>

   - <span data-ttu-id="37c61-224">**URL**</span><span class="sxs-lookup"><span data-stu-id="37c61-224">**URLs**</span></span>
     - <span data-ttu-id="37c61-225">**작업**</span><span class="sxs-lookup"><span data-stu-id="37c61-225">**Action**</span></span>
     - <span data-ttu-id="37c61-226">**만료되지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="37c61-226">**Never expire**</span></span>
     - <span data-ttu-id="37c61-227">**마지막으로 업데이트된 날짜**</span><span class="sxs-lookup"><span data-stu-id="37c61-227">**Last updated date**</span></span>
     - <span data-ttu-id="37c61-228">**만료 날짜**</span><span class="sxs-lookup"><span data-stu-id="37c61-228">**Expiration date**</span></span>

   - <span data-ttu-id="37c61-229">**파일**</span><span class="sxs-lookup"><span data-stu-id="37c61-229">**Files**</span></span>
     - <span data-ttu-id="37c61-230">**작업**</span><span class="sxs-lookup"><span data-stu-id="37c61-230">**Action**</span></span>
     - <span data-ttu-id="37c61-231">**만료되지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="37c61-231">**Never expire**</span></span>
     - <span data-ttu-id="37c61-232">**마지막으로 업데이트된 날짜**</span><span class="sxs-lookup"><span data-stu-id="37c61-232">**Last updated date**</span></span>
     - <span data-ttu-id="37c61-233">**만료 날짜**</span><span class="sxs-lookup"><span data-stu-id="37c61-233">**Expiration date**</span></span>

   - <span data-ttu-id="37c61-234">**BCL 우회를 위한 보낸 사람 도메인**</span><span class="sxs-lookup"><span data-stu-id="37c61-234">**Sender domains for BCL bypass**</span></span>
     - <span data-ttu-id="37c61-235">**만료되지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="37c61-235">**Never expire**</span></span>
     - <span data-ttu-id="37c61-236">**마지막으로 업데이트된 날짜**</span><span class="sxs-lookup"><span data-stu-id="37c61-236">**Last updated date**</span></span>
     - <span data-ttu-id="37c61-237">**만료 날짜**</span><span class="sxs-lookup"><span data-stu-id="37c61-237">**Expiration date**</span></span>

   - <span data-ttu-id="37c61-238">**스푸핑**</span><span class="sxs-lookup"><span data-stu-id="37c61-238">**Spoofing**</span></span>
     - <span data-ttu-id="37c61-239">**작업**</span><span class="sxs-lookup"><span data-stu-id="37c61-239">**Action**</span></span>
     - <span data-ttu-id="37c61-240">**스푸핑 유형**</span><span class="sxs-lookup"><span data-stu-id="37c61-240">**Spoof type**</span></span>

   <span data-ttu-id="37c61-241">완료되면 적용을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="37c61-241">When you're finished, click **Apply**.</span></span> <span data-ttu-id="37c61-242">기존 필터를 지우려면 **필터를** 클릭하고 나타나는 필터  플라이아웃에서 필터 **지우기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="37c61-242">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="37c61-243">보안 및 & 센터를 사용하여 테넌트 허용/차단 목록의 항목 수정</span><span class="sxs-lookup"><span data-stu-id="37c61-243">Use the Security & Compliance Center to modify entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="37c61-244">보안 및 & 센터에서 위협 **관리** 정책 \>  \> **테넌트 허용/차단 목록으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="37c61-244">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="37c61-245">수정할 항목 유형이 포함된 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-245">Select the tab that contains the type of entry that you want to modify:</span></span>
   - <span data-ttu-id="37c61-246">**URL**</span><span class="sxs-lookup"><span data-stu-id="37c61-246">**URLs**</span></span>
   - <span data-ttu-id="37c61-247">**파일**</span><span class="sxs-lookup"><span data-stu-id="37c61-247">**Files**</span></span>
   - <span data-ttu-id="37c61-248">**BCL 우회를 위한 보낸 사람 도메인**</span><span class="sxs-lookup"><span data-stu-id="37c61-248">**Sender domains for BCL bypass**</span></span>
   - <span data-ttu-id="37c61-249">**스푸핑**</span><span class="sxs-lookup"><span data-stu-id="37c61-249">**Spoofing**</span></span>

3. <span data-ttu-id="37c61-250">수정할 항목을 선택하고 편집 편집 아이콘 **을** ![ ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-250">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span> <span data-ttu-id="37c61-251">플라이아웃에서 수정할 수 있는 값은 이전 단계에서 선택한 탭에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-251">The values that you are able to modify in the flyout that appears depend on the tab you selected in the previous step:</span></span>

   - <span data-ttu-id="37c61-252">**URL**</span><span class="sxs-lookup"><span data-stu-id="37c61-252">**URLs**</span></span>
     - <span data-ttu-id="37c61-253">**만료 및/또는** 만료 날짜가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-253">**Never expire** and/or expiration date.</span></span>
     - <span data-ttu-id="37c61-254">**선택 사항 참고 사항**</span><span class="sxs-lookup"><span data-stu-id="37c61-254">**Optional note**</span></span>

   - <span data-ttu-id="37c61-255">**파일**</span><span class="sxs-lookup"><span data-stu-id="37c61-255">**Files**</span></span>
     - <span data-ttu-id="37c61-256">**만료 및/또는** 만료 날짜가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-256">**Never expire** and/or expiration date.</span></span>
     - <span data-ttu-id="37c61-257">**선택 사항 참고 사항**</span><span class="sxs-lookup"><span data-stu-id="37c61-257">**Optional note**</span></span>

   - <span data-ttu-id="37c61-258">**BCL 우회를 위한 보낸 사람 도메인**</span><span class="sxs-lookup"><span data-stu-id="37c61-258">**Sender domains for BCL bypass**</span></span>
     - <span data-ttu-id="37c61-259">**만료 및/또는** 만료 날짜가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-259">**Never expire** and/or expiration date.</span></span>

   - <span data-ttu-id="37c61-260">**스푸핑**</span><span class="sxs-lookup"><span data-stu-id="37c61-260">**Spoofing**</span></span>
     - <span data-ttu-id="37c61-261">**작업:** 값을 허용 또는 **차단으로** 변경할 **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="37c61-261">**Action**: You can change the value to **Allow** or **Block**.</span></span>

4. <span data-ttu-id="37c61-262">작업을 마쳤으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-262">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="37c61-263">보안 및 & 센터를 사용하여 테넌트 허용/차단 목록에서 항목 제거</span><span class="sxs-lookup"><span data-stu-id="37c61-263">Use the Security & Compliance Center to remove entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="37c61-264">보안 및 & 센터에서 위협 **관리** 정책 \>  \> **테넌트 허용/차단 목록으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="37c61-264">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="37c61-265">제거할 항목 유형이 포함된 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-265">Select the tab that contains the type of entry that you want to remove:</span></span>
   - <span data-ttu-id="37c61-266">**URL**</span><span class="sxs-lookup"><span data-stu-id="37c61-266">**URLs**</span></span>
   - <span data-ttu-id="37c61-267">**파일**</span><span class="sxs-lookup"><span data-stu-id="37c61-267">**Files**</span></span>
   - <span data-ttu-id="37c61-268">**BCL 우회를 위한 보낸 사람 도메인**</span><span class="sxs-lookup"><span data-stu-id="37c61-268">**Sender domains for BCL bypass**</span></span>
   - <span data-ttu-id="37c61-269">**스푸핑**</span><span class="sxs-lookup"><span data-stu-id="37c61-269">**Spoofing**</span></span>

3. <span data-ttu-id="37c61-270">제거할 항목을 선택한 다음 삭제 삭제 아이콘 **을** ![ ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-270">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="37c61-271">나타나는 경고 대화 상자에서 삭제를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="37c61-271">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="37c61-272">PowerShell Exchange Online 독립 실행형 EOP PowerShell을 사용하여 테넌트 허용/차단 목록 구성</span><span class="sxs-lookup"><span data-stu-id="37c61-272">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-block-file-or-url-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="37c61-273">PowerShell을 사용하여 테넌트 허용/차단 목록에 차단 파일 또는 URL 항목 추가</span><span class="sxs-lookup"><span data-stu-id="37c61-273">Use PowerShell to add block file or URL entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="37c61-274">테넌트 허용/차단 목록에서 차단 파일 또는 URL 항목을 추가하기 위해 다음 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-274">To add block file or URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <FileHash | Url> -Block -Entries "Value1","Value2",..."ValueN" <-ExpirationDate Date | -NoExpiration> [-Notes <String>]
```

<span data-ttu-id="37c61-275">이 예제에서는 만료되지 않는 지정된 파일에 대한 차단 파일 항목을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-275">This example adds a block file entry for the specified files that never expires.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="37c61-276">이 예제에서는 contoso.com, contoso.com, www.contoso.com 및 하위 xyz.abc.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="37c61-276">This example adds a block URL entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="37c61-277">ExpirationDate 또는 NoExpiration 매개 변수를 사용하지 않았기 때문에 항목이 30일 후에 만료됩니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-277">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

<span data-ttu-id="37c61-278">구문과 매개 변수에 대한 자세한 내용은 [New-TenantAllowBlockListItems를 참조하십시오.](/powershell/module/exchange/new-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="37c61-278">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-add-allow-or-block-spoofed-sender-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="37c61-279">PowerShell을 사용하여 테넌트 허용/차단 목록에 스푸핑된 보낸 사람 항목 추가 또는 차단</span><span class="sxs-lookup"><span data-stu-id="37c61-279">Use PowerShell to add allow or block spoofed sender entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="37c61-280">테넌트 허용/차단 목록에 스푸핑된 보낸 사람 항목을 추가하기 위해 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="37c61-280">To add spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListSpoofItems -SpoofedUser <Domain | EmailAddress | *> -SendingInfrastructure <Domain | IPAddress/24> -SpoofType <External | Internal> -Action <Allow | Block>
```

<span data-ttu-id="37c61-281">구문과 매개 변수에 대한 자세한 내용은 [New-TenantAllowBlockListSpoofItems를 참조하십시오.](/powershell/module/exchange/new-tenantallowblocklistspoofitems)</span><span class="sxs-lookup"><span data-stu-id="37c61-281">For detailed syntax and parameter information, see [New-TenantAllowBlockListSpoofItems](/powershell/module/exchange/new-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-view-block-file-or-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="37c61-282">PowerShell을 사용하여 테넌트 허용/차단 목록에서 차단 파일 또는 URL 항목 보기</span><span class="sxs-lookup"><span data-stu-id="37c61-282">Use PowerShell to view block file or URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="37c61-283">테넌트 허용/차단 목록에서 차단 파일 또는 URL 항목을 보고 다음 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-283">To view block file or URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <FileHash | URL> [-Entry <FileHashValue | URLValue>] [<-ExpirationDate Date | -NoExpiration>]
```

<span data-ttu-id="37c61-284">이 예제에서는 지정한 파일 해시 값에 대한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-284">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="37c61-285">이 예제에서는 차단된 URL을 모두 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-285">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

<span data-ttu-id="37c61-286">구문과 매개 변수에 대한 자세한 내용은 [Get-TenantAllowBlockListItems를 참조하십시오.](/powershell/module/exchange/get-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="37c61-286">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="37c61-287">PowerShell을 사용하여 테넌트 허용/차단 목록에서 스푸핑된 보낸 사람 항목 보기 또는 차단</span><span class="sxs-lookup"><span data-stu-id="37c61-287">Use PowerShell to view allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="37c61-288">테넌트 허용/차단 목록에서 스푸핑된 보낸 사람 항목을 보고 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="37c61-288">To view spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems [-Action <Allow | Block>] [-SpoofType <External | Internal>
```

<span data-ttu-id="37c61-289">이 예에서는 테넌트 허용/차단 목록에 있는 스푸핑된 보낸 사람 항목을 모두 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-289">This example returns all spoofed sender entries in the Tenant Allow/Block List.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems
```

<span data-ttu-id="37c61-290">이 예에서는 내부에 있는 스푸핑된 보낸 사람 항목을 모두 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-290">This example returns all allow spoofed sender entries that are internal.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems -Action Allow -SpoofType Internal
```

<span data-ttu-id="37c61-291">이 예에서는 외부에 있는 차단된 스푸핑된 보낸 사람 항목을 모두 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-291">This example returns all blocked spoofed sender entries that are external.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems -Action Block -SpoofType External
```

<span data-ttu-id="37c61-292">구문과 매개 변수에 대한 자세한 내용은 [Get-TenantAllowBlockListSpoofItems를 참조하십시오.](/powershell/module/exchange/get-tenantallowblocklistspoofitems)</span><span class="sxs-lookup"><span data-stu-id="37c61-292">For detailed syntax and parameter information, see [Get-TenantAllowBlockListSpoofItems](/powershell/module/exchange/get-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-modify-block-file-and-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="37c61-293">PowerShell을 사용하여 테넌트 허용/차단 목록에서 차단 파일 및 URL 항목 수정</span><span class="sxs-lookup"><span data-stu-id="37c61-293">Use PowerShell to modify block file and URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="37c61-294">테넌트 허용/차단 목록에서 차단 파일 및 URL 항목을 수정하려면 다음 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-294">To modify block file and URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN"> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

<span data-ttu-id="37c61-295">이 예에서는 지정한 블록 URL 항목의 만료 날짜를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-295">This example changes the expiration date of the specified block URL entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate "5/30/2020"
```

<span data-ttu-id="37c61-296">구문과 매개 변수에 대한 자세한 내용은 [Set-TenantAllowBlockListItems를 참조하십시오.](/powershell/module/exchange/set-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="37c61-296">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="37c61-297">PowerShell을 사용하여 테넌트 허용/차단 목록에서 스푸핑된 보낸 사람 항목 허용 또는 차단</span><span class="sxs-lookup"><span data-stu-id="37c61-297">Use PowerShell to modify allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="37c61-298">테넌트 허용/차단 목록에서 스푸핑된 보낸 사람 항목을 허용하거나 차단하려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="37c61-298">To modify allow or block spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN"> -Action <Allow | Block>
```

<span data-ttu-id="37c61-299">이 예에서는 스푸핑된 보낸 사람 항목을 허용에서 차단으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-299">This example changes spoofed sender entry from allow to block.</span></span>

```powershell
Set-TenantAllowBlockListItems -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -Action Block
```

<span data-ttu-id="37c61-300">구문과 매개 변수에 대한 자세한 내용은 [Set-TenantAllowBlockListSpoofItems를 참조하십시오.](/powershell/module/exchange/set-tenantallowblocklistspoofitems)</span><span class="sxs-lookup"><span data-stu-id="37c61-300">For detailed syntax and parameter information, see [Set-TenantAllowBlockListSpoofItems](/powershell/module/exchange/set-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-remove-url-or-file-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="37c61-301">PowerShell을 사용하여 테넌트 허용/차단 목록에서 URL 또는 파일 항목 제거</span><span class="sxs-lookup"><span data-stu-id="37c61-301">Use PowerShell to remove URL or file entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="37c61-302">테넌트 허용/차단 목록에서 파일 및 URL 항목을 제거하려면 다음 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-302">To remove file and URL entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="37c61-303">이 예에서는 테넌트 허용/차단 목록에서 지정된 차단 URL 항목을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-303">This example removes the specified block URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="37c61-304">구문과 매개 변수에 대한 자세한 내용은 [Remove-TenantAllowBlockListItems를 참조하십시오.](/powershell/module/exchange/remove-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="37c61-304">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-allow-or-block-spoofed-sender-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="37c61-305">PowerShell을 사용하여 테넌트 허용/차단 목록에서 스푸핑된 보낸 사람 항목 허용 또는 차단</span><span class="sxs-lookup"><span data-stu-id="37c61-305">Use PowerShell to remove allow or block spoofed sender entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="37c61-306">테넌트 허용/차단 목록에서 스푸핑 보낸 사람 항목을 허용하거나 차단하려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="37c61-306">To remove allow or block spoof sender entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="37c61-307">구문과 매개 변수에 대한 자세한 내용은 [Remove-TenantAllowBlockListSpoofItems를 참조하십시오.](/powershell/module/exchange/remove-tenantallowblocklistspoofitems)</span><span class="sxs-lookup"><span data-stu-id="37c61-307">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListSpoofItems](/powershell/module/exchange/remove-tenantallowblocklistspoofitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="37c61-308">테넌트 허용/차단 목록에 대한 URL 구문</span><span class="sxs-lookup"><span data-stu-id="37c61-308">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="37c61-309">IP4v 및 IPv6 주소는 사용할 수 있지만 TCP/UDP 포트는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-309">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="37c61-310">파일 이름 확장명은 허용되지 않습니다(예: test.pdf).</span><span class="sxs-lookup"><span data-stu-id="37c61-310">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="37c61-311">유니코드는 지원되지 않지만 Punycode는 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-311">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="37c61-312">다음 명령문이 모두 true이면 호스트 이름을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-312">Hostnames are allowed if all of the following statements are true:</span></span>
  - <span data-ttu-id="37c61-313">호스트 이름에는 기간이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-313">The hostname contains a period.</span></span>
  - <span data-ttu-id="37c61-314">기간 왼쪽에 하나 이상의 문자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-314">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="37c61-315">이 기간의 오른쪽에는 두 개 이상의 문자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-315">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="37c61-316">예를 들어 `t.co` 허용되거나 `.com` `contoso.` 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-316">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="37c61-317">하위 경로는 암시적이지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-317">Subpaths are not implied.</span></span>

  <span data-ttu-id="37c61-318">예를 들어 `contoso.com` 를 포함하지 `contoso.com/a` 않습니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-318">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="37c61-319">와일드카드(\*)는 다음과 같은 시나리오에서 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-319">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="37c61-320">하위omain을 지정하려면 왼쪽 와일드카드 다음에 기간이 와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-320">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="37c61-321">예를 들어 `*.contoso.com` 허용됩니다. `*contoso.com` 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-321">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="37c61-322">오른쪽 와일드카드는 슬래시(/)를 따라 경로를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-322">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="37c61-323">예를 들어 `contoso.com/*` 허용되거나 `contoso.com*` `contoso.com/ab*` 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-323">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="37c61-324">모든 하위 경로는 올바른 와일드카드로 암시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-324">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="37c61-325">예를 들어 `contoso.com/*` 를 포함하지 `contoso.com/a` 않습니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-325">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="37c61-326">`*.com*` 가 잘못되었습니다(확인 가능한 도메인이 아니며 오른쪽 와일드카드가 슬래시를 따르지 않습니다).</span><span class="sxs-lookup"><span data-stu-id="37c61-326">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="37c61-327">와일드카드는 IP 주소에서 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-327">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="37c61-328">다음 시나리오에서는 선조(~) 문자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-328">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="37c61-329">왼쪽 밀기선은 도메인과 모든 하위 도메인을 암시합니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-329">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="37c61-330">예를 들어 `~contoso.com` 및 `contoso.com` `*.contoso.com` 을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-330">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="37c61-331">URL 항목이 모든 프로토콜에 적용될 수 있기 때문에 프로토콜(예: , 또는 )이 포함된 URL 항목은 `http://` `https://` `ftp://` 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-331">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="37c61-332">사용자 이름 또는 암호는 지원되거나 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-332">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="37c61-333">따옴표(' 또는 ")는 잘못된 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-333">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="37c61-334">URL에는 가능한 경우 모든 리디렉션이 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-334">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="37c61-335">URL 입력 시나리오</span><span class="sxs-lookup"><span data-stu-id="37c61-335">URL entry scenarios</span></span>

<span data-ttu-id="37c61-336">유효한 URL 항목 및 해당 결과는 다음 섹션에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-336">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="37c61-337">시나리오: 와일드카드 없음</span><span class="sxs-lookup"><span data-stu-id="37c61-337">Scenario: No wildcards</span></span>

<span data-ttu-id="37c61-338">**항목**: `contoso.com`</span><span class="sxs-lookup"><span data-stu-id="37c61-338">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="37c61-339">**일치 허용**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="37c61-339">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="37c61-340">**일치하지 않는 허용**:</span><span class="sxs-lookup"><span data-stu-id="37c61-340">**Allow not matched**:</span></span>

  - <span data-ttu-id="37c61-341">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="37c61-341">abc-contoso.com</span></span>
  - <span data-ttu-id="37c61-342">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="37c61-342">contoso.com/a</span></span>
  - <span data-ttu-id="37c61-343">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="37c61-343">payroll.contoso.com</span></span>
  - <span data-ttu-id="37c61-344">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="37c61-344">test.com/contoso.com</span></span>
  - <span data-ttu-id="37c61-345">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="37c61-345">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="37c61-346">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="37c61-346">www.contoso.com</span></span>
  - <span data-ttu-id="37c61-347">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="37c61-347">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="37c61-348">**블록 일치**:</span><span class="sxs-lookup"><span data-stu-id="37c61-348">**Block match**:</span></span>

  - <span data-ttu-id="37c61-349">contoso.com</span><span class="sxs-lookup"><span data-stu-id="37c61-349">contoso.com</span></span>
  - <span data-ttu-id="37c61-350">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="37c61-350">contoso.com/a</span></span>
  - <span data-ttu-id="37c61-351">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="37c61-351">payroll.contoso.com</span></span>
  - <span data-ttu-id="37c61-352">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="37c61-352">test.com/contoso.com</span></span>
  - <span data-ttu-id="37c61-353">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="37c61-353">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="37c61-354">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="37c61-354">www.contoso.com</span></span>
  - <span data-ttu-id="37c61-355">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="37c61-355">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="37c61-356">**블록이 일치하지 않는 경우**: abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="37c61-356">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="37c61-357">시나리오: 왼쪽 와일드카드(하위omain)</span><span class="sxs-lookup"><span data-stu-id="37c61-357">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="37c61-358">**항목**: `*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="37c61-358">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="37c61-359">**일치 및** **차단 일치 허용**:</span><span class="sxs-lookup"><span data-stu-id="37c61-359">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="37c61-360">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="37c61-360">www.contoso.com</span></span>
  - <span data-ttu-id="37c61-361">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="37c61-361">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="37c61-362">**일치하지 않는 허용** 및 **차단이 일치하지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="37c61-362">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="37c61-363">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="37c61-363">123contoso.com</span></span>
  - <span data-ttu-id="37c61-364">contoso.com</span><span class="sxs-lookup"><span data-stu-id="37c61-364">contoso.com</span></span>
  - <span data-ttu-id="37c61-365">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="37c61-365">test.com/contoso.com</span></span>
  - <span data-ttu-id="37c61-366">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="37c61-366">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="37c61-367">시나리오: 경로 맨 위에 있는 오른쪽 와일드카드</span><span class="sxs-lookup"><span data-stu-id="37c61-367">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="37c61-368">**항목**: `contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="37c61-368">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="37c61-369">**일치 및** **차단 일치 허용**:</span><span class="sxs-lookup"><span data-stu-id="37c61-369">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="37c61-370">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="37c61-370">contoso.com/a/b</span></span>
  - <span data-ttu-id="37c61-371">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="37c61-371">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="37c61-372">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="37c61-372">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="37c61-373">**일치하지 않는 허용** 및 **차단이 일치하지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="37c61-373">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="37c61-374">contoso.com</span><span class="sxs-lookup"><span data-stu-id="37c61-374">contoso.com</span></span>
  - <span data-ttu-id="37c61-375">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="37c61-375">contoso.com/a</span></span>
  - <span data-ttu-id="37c61-376">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="37c61-376">www.contoso.com</span></span>
  - <span data-ttu-id="37c61-377">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="37c61-377">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="37c61-378">시나리오: 왼쪽 밀기</span><span class="sxs-lookup"><span data-stu-id="37c61-378">Scenario: Left tilde</span></span>

<span data-ttu-id="37c61-379">**항목**: `~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="37c61-379">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="37c61-380">**일치 및** **차단 일치 허용**:</span><span class="sxs-lookup"><span data-stu-id="37c61-380">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="37c61-381">contoso.com</span><span class="sxs-lookup"><span data-stu-id="37c61-381">contoso.com</span></span>
  - <span data-ttu-id="37c61-382">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="37c61-382">www.contoso.com</span></span>
  - <span data-ttu-id="37c61-383">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="37c61-383">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="37c61-384">**일치하지 않는 허용** 및 **차단이 일치하지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="37c61-384">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="37c61-385">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="37c61-385">123contoso.com</span></span>
  - <span data-ttu-id="37c61-386">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="37c61-386">contoso.com/abc</span></span>
  - <span data-ttu-id="37c61-387">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="37c61-387">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="37c61-388">시나리오: 오른쪽 와일드카드 접미사</span><span class="sxs-lookup"><span data-stu-id="37c61-388">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="37c61-389">**항목**: `contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="37c61-389">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="37c61-390">**일치 및** **차단 일치 허용**:</span><span class="sxs-lookup"><span data-stu-id="37c61-390">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="37c61-391">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="37c61-391">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="37c61-392">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="37c61-392">contoso.com/a</span></span>
  - <span data-ttu-id="37c61-393">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="37c61-393">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="37c61-394">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="37c61-394">contoso.com/ab</span></span>
  - <span data-ttu-id="37c61-395">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="37c61-395">contoso.com/b</span></span>
  - <span data-ttu-id="37c61-396">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="37c61-396">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="37c61-397">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="37c61-397">contoso.com/ba</span></span>

- <span data-ttu-id="37c61-398">**일치하지 않는 허용** 및 **일치하지 않는** 차단 : contoso.com</span><span class="sxs-lookup"><span data-stu-id="37c61-398">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="37c61-399">시나리오: 왼쪽 와일드카드 하위omain 및 오른쪽 와일드카드 접미사</span><span class="sxs-lookup"><span data-stu-id="37c61-399">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="37c61-400">**항목**: `*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="37c61-400">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="37c61-401">**일치 및** **차단 일치 허용**:</span><span class="sxs-lookup"><span data-stu-id="37c61-401">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="37c61-402">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="37c61-402">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="37c61-403">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="37c61-403">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="37c61-404">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="37c61-404">www.contoso.com/a</span></span>
  - <span data-ttu-id="37c61-405">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="37c61-405">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="37c61-406">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="37c61-406">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="37c61-407">**일치하지 않는 허용** 및 **일치하지 않는** 차단 : contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="37c61-407">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="37c61-408">시나리오: 왼쪽 및 오른쪽 밀기</span><span class="sxs-lookup"><span data-stu-id="37c61-408">Scenario: Left and right tilde</span></span>

<span data-ttu-id="37c61-409">**항목**: `~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="37c61-409">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="37c61-410">**일치 및** **차단 일치 허용**:</span><span class="sxs-lookup"><span data-stu-id="37c61-410">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="37c61-411">contoso.com</span><span class="sxs-lookup"><span data-stu-id="37c61-411">contoso.com</span></span>
  - <span data-ttu-id="37c61-412">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="37c61-412">contoso.com/a</span></span>
  - <span data-ttu-id="37c61-413">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="37c61-413">www.contoso.com</span></span>
  - <span data-ttu-id="37c61-414">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="37c61-414">www.contoso.com/b</span></span>
  - <span data-ttu-id="37c61-415">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="37c61-415">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="37c61-416">**일치하지 않는 허용** 및 **차단이 일치하지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="37c61-416">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="37c61-417">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="37c61-417">123contoso.com</span></span>
  - <span data-ttu-id="37c61-418">contoso.org</span><span class="sxs-lookup"><span data-stu-id="37c61-418">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="37c61-419">시나리오: IP 주소</span><span class="sxs-lookup"><span data-stu-id="37c61-419">Scenario: IP address</span></span>

<span data-ttu-id="37c61-420">**항목**: `1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="37c61-420">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="37c61-421">**일치 및** **차단 일치** 허용 : 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="37c61-421">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="37c61-422">**일치하지 않는 허용** 및 **차단이 일치하지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="37c61-422">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="37c61-423">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="37c61-423">1.2.3.4/a</span></span>
  - <span data-ttu-id="37c61-424">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="37c61-424">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="37c61-425">오른쪽 와일드카드가 있는 IP 주소</span><span class="sxs-lookup"><span data-stu-id="37c61-425">IP address with right wildcard</span></span>

<span data-ttu-id="37c61-426">**항목**: `1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="37c61-426">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="37c61-427">**일치 및** **차단 일치 허용**:</span><span class="sxs-lookup"><span data-stu-id="37c61-427">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="37c61-428">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="37c61-428">1.2.3.4/b</span></span>
  - <span data-ttu-id="37c61-429">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="37c61-429">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="37c61-430">잘못된 항목의 예</span><span class="sxs-lookup"><span data-stu-id="37c61-430">Examples of invalid entries</span></span>

<span data-ttu-id="37c61-431">다음 항목이 잘못되었습니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-431">The following entries are invalid:</span></span>

- <span data-ttu-id="37c61-432">**누락되었거나 잘못된 도메인 값**:</span><span class="sxs-lookup"><span data-stu-id="37c61-432">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="37c61-433">contoso</span><span class="sxs-lookup"><span data-stu-id="37c61-433">contoso</span></span>
  - <span data-ttu-id="37c61-434">\*.contoso.\*</span><span class="sxs-lookup"><span data-stu-id="37c61-434">\*.contoso.\*</span></span>
  - <span data-ttu-id="37c61-435">\*.com</span><span class="sxs-lookup"><span data-stu-id="37c61-435">\*.com</span></span>
  - <span data-ttu-id="37c61-436">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="37c61-436">\*.pdf</span></span>

- <span data-ttu-id="37c61-437">**텍스트의 와일드카드 또는 간격 문자가 없는** 경우 :</span><span class="sxs-lookup"><span data-stu-id="37c61-437">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="37c61-438">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="37c61-438">\*contoso.com</span></span>
  - <span data-ttu-id="37c61-439">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="37c61-439">contoso.com\*</span></span>
  - <span data-ttu-id="37c61-440">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="37c61-440">\*1.2.3.4</span></span>
  - <span data-ttu-id="37c61-441">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="37c61-441">1.2.3.4\*</span></span>
  - <span data-ttu-id="37c61-442">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="37c61-442">contoso.com/a\*</span></span>
  - <span data-ttu-id="37c61-443">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="37c61-443">contoso.com/ab\*</span></span>

- <span data-ttu-id="37c61-444">**포트가 있는 IP 주소:**</span><span class="sxs-lookup"><span data-stu-id="37c61-444">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="37c61-445">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="37c61-445">contoso.com:443</span></span>
  - <span data-ttu-id="37c61-446">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="37c61-446">abc.contoso.com:25</span></span>

- <span data-ttu-id="37c61-447">**설명이 없는 와일드카드**:</span><span class="sxs-lookup"><span data-stu-id="37c61-447">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="37c61-448">\*.\*</span><span class="sxs-lookup"><span data-stu-id="37c61-448">\*.\*</span></span>

- <span data-ttu-id="37c61-449">**중간 와일드카드**:</span><span class="sxs-lookup"><span data-stu-id="37c61-449">**Middle wildcards**:</span></span>

  - <span data-ttu-id="37c61-450">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="37c61-450">conto\*so.com</span></span>
  - <span data-ttu-id="37c61-451">conto~so.com</span><span class="sxs-lookup"><span data-stu-id="37c61-451">conto~so.com</span></span>

- <span data-ttu-id="37c61-452">**이중 와일드카드**</span><span class="sxs-lookup"><span data-stu-id="37c61-452">**Double wildcards**</span></span>

  - <span data-ttu-id="37c61-453">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="37c61-453">contoso.com/\*\*</span></span>
  - <span data-ttu-id="37c61-454">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="37c61-454">contoso.com/\*/\*</span></span>

## <a name="domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="37c61-455">테넌트 허용/차단 목록의 스푸핑된 보낸 사람 항목에 대한 도메인 쌍 구문</span><span class="sxs-lookup"><span data-stu-id="37c61-455">Domain pair syntax for spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="37c61-456">테넌트 허용/차단 목록에서 스푸핑된 보낸 사람에 대한 도메인 쌍은 다음 구문을 사용 `<Spoofed user>, <Sending infrastructure>` 합니다. .</span><span class="sxs-lookup"><span data-stu-id="37c61-456">A domain pair for a spoofed sender in the Tenant Allow/Block List uses the following syntax: `<Spoofed user>, <Sending infrastructure>`.</span></span>

- <span data-ttu-id="37c61-457">**스푸핑된 사용자:** 이 값은 전자 메일 클라이언트의 시작 상자에 표시되는  스푸핑된 사용자의 전자 메일 주소와 관련됩니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-457">**Spoofed user**: This value involves the email address of the spoofed user that's displayed in the **From** box in email clients.</span></span> <span data-ttu-id="37c61-458">이 주소를 `5322.From` 주소라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-458">This address is also known as the `5322.From` address.</span></span> <span data-ttu-id="37c61-459">사용할 수 있는 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-459">Valid values include:</span></span>
  - <span data-ttu-id="37c61-460">개별 전자 메일 주소(예: chris@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="37c61-460">An individual email address (for example, chris@contoso.com).</span></span>
  - <span data-ttu-id="37c61-461">전자 메일 도메인(예: contoso.com.</span><span class="sxs-lookup"><span data-stu-id="37c61-461">An email domain (for example, contoso.com).</span></span>
  - <span data-ttu-id="37c61-462">와일드카드 문자(예: \* ).</span><span class="sxs-lookup"><span data-stu-id="37c61-462">The wildcard character (for example, \*).</span></span>

- <span data-ttu-id="37c61-463">**보내는 인프라:** 이 값은 스푸핑된 사용자의 메시지 원본을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-463">**Sending infrastructure**: This value indicates the source of messages from the spoofed user.</span></span> <span data-ttu-id="37c61-464">사용할 수 있는 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-464">Valid values include:</span></span>
  - <span data-ttu-id="37c61-465">원본 전자 메일 서버의 IP 주소(예: PTR 레코드)의 역방향 DNS fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="37c61-465">The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address (for example, fabrikam.com).</span></span>
  - <span data-ttu-id="37c61-466">원본 IP 주소에 PTR 레코드가 없는 경우 보내는 인프라는 \<source IP\> /24(예: 192.168.100.100/24)로 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-466">If the source IP address has no PTR record, then the sending infrastructure is identified as \<source IP\>/24 (for example, 192.168.100.100/24).</span></span>

<span data-ttu-id="37c61-467">다음은 스푸핑된 보낸 사람 식별을 위한 유효한 도메인 쌍의 몇 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-467">Here are some examples of valid domain pairs to identify spoofed senders:</span></span>

- `contoso.com, 192.168.100.100/24`
- `chris@contoso.com, fabrikam.com`
- `*, contoso.net`

<span data-ttu-id="37c61-468">도메인 쌍을 추가하면 스푸핑된 사용자와 보내는 인프라의 조합만 허용하거나 *차단할* 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="37c61-468">Adding a domain pair only allows or blocks the *combination* of the spoofed user *and* the sending infrastructure.</span></span> <span data-ttu-id="37c61-469">또한 모든 원본에서 스푸핑된 사용자의 전자 메일을 허용하지 않으며, 스푸핑된 사용자에 대해 보내는 인프라 원본의 전자 메일을 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-469">It does not allow email from the spoofed user from any source, nor does it allow email from the sending infrastructure source for any spoofed user.</span></span>

<span data-ttu-id="37c61-470">예를 들어 다음 도메인 쌍에 대해 허용 항목을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-470">For example, you add an allow entry for the following domain pair:</span></span>

- <span data-ttu-id="37c61-471">**도메인**: gmail.com</span><span class="sxs-lookup"><span data-stu-id="37c61-471">**Domain**: gmail.com</span></span>
- <span data-ttu-id="37c61-472">**인프라:** tms.mx.com</span><span class="sxs-lookup"><span data-stu-id="37c61-472">**Infrastructure**: tms.mx.com</span></span>

<span data-ttu-id="37c61-473">해당 도메인 및  보내는 인프라 쌍의 메시지만 스푸핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-473">Only messages from that domain *and* sending infrastructure pair are allowed to spoof.</span></span> <span data-ttu-id="37c61-474">스푸핑을 시도하는 gmail.com 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-474">Other senders attempting to spoof gmail.com aren't allowed.</span></span> <span data-ttu-id="37c61-475">다른 도메인의 보낸 사람이 보낸 메시지는 tms.mx.com 인텔리전스를 통해 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="37c61-475">Messages from senders in other domains originating from tms.mx.com are checked by spoof intelligence.</span></span>
