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
ms.openlocfilehash: 67c3badb86f1cfb9bf644cc202ed67e3163a6772
ms.sourcegitcommit: ac3e9ccb7b43a42e600af8f44e6f30019533faeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/15/2021
ms.locfileid: "52933158"
---
# <a name="manage-the-tenant-allowblock-list"></a><span data-ttu-id="5ede0-103">테넌트 허용/차단 목록 관리</span><span class="sxs-lookup"><span data-stu-id="5ede0-103">Manage the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="5ede0-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="5ede0-104">**Applies to**</span></span>
- [<span data-ttu-id="5ede0-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="5ede0-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="5ede0-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="5ede0-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="5ede0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5ede0-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
>
> <span data-ttu-id="5ede0-108">이 문서에 설명된 기능은 미리 보기에 있으며 변경될 수 있으며 일부 조직에서는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-108">The features described in this article are in Preview, are subject to change, and are not available in all organizations.</span></span>  <span data-ttu-id="5ede0-109">이 문서에 설명된 스푸핑 기능이 조직에 없는 경우 [EOP에서](walkthrough-spoof-intelligence-insight.md)스푸핑 인텔리전스 정책을 사용하여 스푸핑된 보낸 사람 관리에서 이전 스푸핑 관리 환경을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5ede0-109">If your organization does not have the spoof features as described in this article, see the older spoof management experience at [Manage spoofed senders using the spoof intelligence policy and spoof intelligence insight in EOP](walkthrough-spoof-intelligence-insight.md).</span></span>
>
> <span data-ttu-id="5ede0-110">현재는 **테넌트** 허용/차단 목록에서 허용된 URL 또는 파일 항목을 구성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-110">You can't **configure** allowed URL or file items in the Tenant Allow/Block List at this time.</span></span>

<span data-ttu-id="5ede0-111">Microsoft 365 사서함이 없는 Exchange Online 또는 EOP(독립 실행형 Exchange Online Protection) 조직에서 Exchange Online EOP 필터링 판정에 동의하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-111">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="5ede0-112">예를 들어 양호한 메시지는 나쁜 메시지(가음성)로 표시되거나 잘못된 메시지가 통과(거짓 부정)로 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-112">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="5ede0-113">Microsoft 365 Defender 포털의 테넌트 허용/차단 목록은 필터링 Microsoft 365 수동으로 다시 Microsoft 365 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-113">The Tenant Allow/Block List in the Microsoft 365 Defender portal gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="5ede0-114">테넌트 허용/차단 목록은 메일 흐름 중과 사용자가 클릭할 때 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-114">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="5ede0-115">다음과 같은 유형의 다시 지정을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-115">You can specify the following types of overrides:</span></span>

- <span data-ttu-id="5ede0-116">차단할 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-116">URLs to block.</span></span>
- <span data-ttu-id="5ede0-117">차단할 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-117">Files to block.</span></span>
- <span data-ttu-id="5ede0-118">허용하거나 차단할 스푸핑된 보낸 사람입니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-118">Spoofed senders to allow or block.</span></span> <span data-ttu-id="5ede0-119">스푸핑 인텔리전스 인사이트에서 [](learn-about-spoof-intelligence.md)허용 또는 차단 판정을 다시 설정하면 스푸핑된 보낸 사람이 테넌트 허용/차단 목록의 스푸핑 탭에만 나타나는 수동 허용 또는 차단 항목이 됩니다. </span><span class="sxs-lookup"><span data-stu-id="5ede0-119">If you override the allow or block verdict in the [spoof intelligence insight](learn-about-spoof-intelligence.md), the spoofed sender becomes a manual allow or block entry that only appears on the **Spoof** tab in the Tenant Allow/Block List.</span></span> <span data-ttu-id="5ede0-120">스푸핑 인텔리전스에서 검색되기 전에 여기에 스푸핑된 보낸 사람에 대한 허용 또는 차단 항목을 수동으로 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-120">You can also manually create allow or block entries for spoofed senders here before they're detected by spoof intelligence.</span></span>

<span data-ttu-id="5ede0-121">이 문서에서는 Microsoft 365 Defender 포털 또는 PowerShell(Exchange Online 사서함이 있는 Microsoft 365 조직용 Exchange Online PowerShell, Exchange Online 사서함이 없는 조직을 위한 독립 실행형 EOP PowerShell Exchange Online에서 항목을 구성하는 방법에 대해 설명하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-121">This article describes how to configure entries in the Tenant Allow/Block List in the Microsoft 365 Defender portal or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="5ede0-122">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="5ede0-122">What do you need to know before you begin?</span></span>

- <span data-ttu-id="5ede0-123"><https://security.microsoft.com/>에서 Microsoft 365 Defender 포털을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-123">You open the Microsoft 365 Defender portal at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="5ede0-124">테넌트 **허용/차단** 목록 페이지로 직접 이동하기 위해 를 <https://security.microsoft.com/tenantAllowBlockList> 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="5ede0-124">To go directly to the **Tenant Allow/Block Lists** page, use <https://security.microsoft.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="5ede0-125">파일의 SHA256 해시 값을 사용하여 파일을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-125">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="5ede0-126">파일에서 파일의 SHA256 해시 값을 Windows 명령 프롬프트에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-126">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="5ede0-127">값의 예로는 를 들 수 `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-127">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="5ede0-128">pHash(지각 해시) 값은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-128">Perceptual hash (pHash) values are not supported.</span></span>

- <span data-ttu-id="5ede0-129">사용 가능한 URL 값은 이 문서 부분의 [테넌트 허용/차단](#url-syntax-for-the-tenant-allowblock-list) 목록 섹션에 대한 URL 구문에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-129">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="5ede0-130">테넌트 허용/차단 목록을 사용하면 URL에 대해 최대 500개 항목과 파일 해시의 항목 500개가 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-130">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="5ede0-131">각 항목의 최대 문자 수는 다음입니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-131">The maximum number of characters for each entry is:</span></span>
  - <span data-ttu-id="5ede0-132">파일 해시 = 64</span><span class="sxs-lookup"><span data-stu-id="5ede0-132">File hashes = 64</span></span>
  - <span data-ttu-id="5ede0-133">URL = 250</span><span class="sxs-lookup"><span data-stu-id="5ede0-133">URL = 250</span></span>

- <span data-ttu-id="5ede0-134">항목이 30분 이내에 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-134">An entry should be active within 30 minutes.</span></span>

- <span data-ttu-id="5ede0-135">기본적으로 테넌트 허용/차단 목록의 항목은 30일 후에 만료됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-135">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="5ede0-136">날짜를 지정하거나 만료되지 않는 날짜로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-136">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="5ede0-137">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5ede0-137">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="5ede0-138">독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5ede0-138">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="5ede0-139">이 게시물의 절차를 수행하려면 먼저 Exchange Online에서 사용 권한을 할당받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-139">You need to be assigned permissions in Exchange Online before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="5ede0-140">**URL 및 파일**:</span><span class="sxs-lookup"><span data-stu-id="5ede0-140">**URLs and files**:</span></span>
    - <span data-ttu-id="5ede0-141">테넌트 허용/차단 목록에서 값을 추가 및 제거하려면 조직  관리 또는 보안 관리자 역할 그룹의 **구성원이** 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-141">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
    - <span data-ttu-id="5ede0-142">테넌트 허용/차단 목록에 대한 읽기 전용 액세스의 경우 전역  읽기 사용자 또는 보안 읽기 권한이 있는 역할 그룹의 **구성원이** 되거나 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-142">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>
  - <span data-ttu-id="5ede0-143">**스푸핑:** 다음 조합 중 하나</span><span class="sxs-lookup"><span data-stu-id="5ede0-143">**Spoofing**: One of the following combinations:</span></span>
    - <span data-ttu-id="5ede0-144">**조직 관리**</span><span class="sxs-lookup"><span data-stu-id="5ede0-144">**Organization Management**</span></span>
    - <span data-ttu-id="5ede0-145">**보안 관리자** <u>및</u> 보기 전용 **구성** 또는 보기 전용 **조직 관리.**</span><span class="sxs-lookup"><span data-stu-id="5ede0-145">**Security Administrator** <u>and</u> **View-Only Configuration** or **View-Only Organization Management**.</span></span>

  <span data-ttu-id="5ede0-146">자세한 내용은 [Exchange Online의 사용 권한](/exchange/permissions-exo/permissions-exo)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5ede0-146">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="5ede0-147">Microsoft 365 관리 센터의 해당 Azure Active Directory 역할에 사용자를 추가하면 사용자에게 필요한 권한 _및_ Microsoft 365의 다른 기능에 대한 권한이 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-147">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="5ede0-148">자세한 내용은 [관리자 역할 정보](../../admin/add-users/about-admin-roles.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5ede0-148">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="5ede0-149">[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups)의 **보기 전용 조직 관리** 역할 그룹에도 기능에 대한 읽기 전용 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-149">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-block-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="5ede0-150">Microsoft 365 Defender 포털을 사용하여 테넌트 허용/차단 목록에 차단 URL 항목을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-150">Use the Microsoft 365 Defender portal to create block URL entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="5ede0-151">Microsoft 365 포털에서 정책 **정책** 규칙 & 규칙 테넌트 \>  \>  \> **허용/차단 목록 으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="5ede0-151">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Rules** section \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="5ede0-152">**테넌트 허용/차단 목록** 페이지에서 URL  탭이 선택되어 있는지 확인한 다음 차단 아이콘 ![ 차단 을 ](../../media/m365-cc-sc-create-icon.png) **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="5ede0-152">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click ![Block icon](../../media/m365-cc-sc-create-icon.png) **Block**.</span></span>

3. <span data-ttu-id="5ede0-153">나타나는 **URL 차단** 플라이아웃에서 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-153">In the **Block URLs** flyout that appears, configure the following settings:</span></span>
   - <span data-ttu-id="5ede0-154">**와일드카드가** 있는 URL 추가: 줄당 하나의 URL을 입력하고 최대 20개까지 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-154">**Add URLs with wildcards**: Enter one URL per line, up to a maximum of 20.</span></span> <span data-ttu-id="5ede0-155">URL 항목의 구문에 대한 자세한 내용은 이 문서 부분의 [테넌트 허용/차단](#url-syntax-for-the-tenant-allowblock-list) 목록 섹션에 대한 URL 구문을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5ede0-155">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>
   - <span data-ttu-id="5ede0-156">**만료 안 하세요:** 다음 단계 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-156">**Never expire**: Do one of the following steps:</span></span>
     - <span data-ttu-id="5ede0-157">설정이 꺼져 있는지 확인(토글 해제) 및 제거 사용 상자를 사용하여 항목의 만료 ![ ](../../media/scc-toggle-off.png) 날짜를 지정합니다. </span><span class="sxs-lookup"><span data-stu-id="5ede0-157">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Remove on** box to specify the expiration date for the entries.</span></span>

       <span data-ttu-id="5ede0-158">또는</span><span class="sxs-lookup"><span data-stu-id="5ede0-158">or</span></span>

     - <span data-ttu-id="5ede0-159">토글을 오른쪽으로 이동하여 만료되지 않는 항목을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-159">Move the toggle to the right to configure the entries to never expire:</span></span> ![토글 켬](../../media/scc-toggle-on.png)<span data-ttu-id="5ede0-161">.</span><span class="sxs-lookup"><span data-stu-id="5ede0-161">.</span></span>
   - <span data-ttu-id="5ede0-162">**선택 사항:** 항목에 대한 설명 텍스트를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-162">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="5ede0-163">작업을 마쳤으면 **추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-163">When you're finished, click **Add**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-block-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="5ede0-164">Microsoft 365 Defender 포털을 사용하여 테넌트 허용/차단 목록에 차단 파일 항목을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-164">Use the Microsoft 365 Defender portal to create block file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="5ede0-165">Microsoft 365 포털에서 정책 **정책** 규칙 & 규칙 테넌트 \>  \>  \> **허용/차단 목록 으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="5ede0-165">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Rules** section \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="5ede0-166">**테넌트 허용/차단 목록 페이지에서**  파일 탭을 선택한 다음 차단 아이콘 ![ 차단 을 ](../../media/m365-cc-sc-create-icon.png) **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="5ede0-166">On the **Tenant Allow/Block List** page, select the **Files** tab, and then click ![Block icon](../../media/m365-cc-sc-create-icon.png) **Block**.</span></span>

3. <span data-ttu-id="5ede0-167">파일 **차단** 플라이아웃이 나타나면 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-167">In the **Block files** flyout that appears, configure the following settings:</span></span>
   - <span data-ttu-id="5ede0-168">**파일 해시 추가:** 줄당 SHA256 해시 값 하나(최대 20개)를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-168">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>
   - <span data-ttu-id="5ede0-169">**만료 안 하세요:** 다음 단계 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-169">**Never expire**: Do one of the following steps:</span></span>
     - <span data-ttu-id="5ede0-170">설정이 꺼져 있는지 확인(토글 해제) 및 제거 사용 상자를 사용하여 항목의 만료 ![ ](../../media/scc-toggle-off.png) 날짜를 지정합니다. </span><span class="sxs-lookup"><span data-stu-id="5ede0-170">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Remove on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="5ede0-171">또는</span><span class="sxs-lookup"><span data-stu-id="5ede0-171">or</span></span>

     - <span data-ttu-id="5ede0-172">토글을 오른쪽으로 이동하여 만료되지 않는 항목을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-172">Move the toggle to the right to configure the entries to never expire:</span></span> ![토글 켬](../../media/scc-toggle-on.png)<span data-ttu-id="5ede0-174">.</span><span class="sxs-lookup"><span data-stu-id="5ede0-174">.</span></span>
   - <span data-ttu-id="5ede0-175">**선택 사항:** 항목에 대한 설명 텍스트를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-175">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="5ede0-176">작업을 마쳤으면 **추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-176">When you're finished, click **Add**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="5ede0-177">Microsoft 365 Defender 포털을 사용하여 테넌트 허용/차단 목록에서 스푸핑된 보낸 사람 항목을 만들거나 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-177">Use the Microsoft 365 Defender portal to create allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="5ede0-178">**참고:**</span><span class="sxs-lookup"><span data-stu-id="5ede0-178">**Notes**:</span></span>

- <span data-ttu-id="5ede0-179">_스푸핑된_ 사용자와 도메인  쌍에 정의된 전송 인프라의 조합만 스푸핑을 특별히 허용하거나 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-179">Only the _combination_ of the spoofed user _and_ the sending infrastructure as defined in the domain pair is specifically allowed or blocked from spoofing.</span></span>
- <span data-ttu-id="5ede0-180">도메인 쌍에 대해 허용 또는 차단 항목을 구성하면 해당 도메인 쌍의 메시지가 더 이상 스푸핑 인텔리전스 인사이트에 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-180">When you configure an allow or block entry for a domain pair, messages from that domain pair no longer appear in the spoof intelligence insight.</span></span>
- <span data-ttu-id="5ede0-181">스푸핑된 보낸 사람에 대한 항목은 만료되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-181">Entries for spoofed senders never expire.</span></span>

1. <span data-ttu-id="5ede0-182">Microsoft 365 포털에서 정책 **정책** 규칙 & 규칙 테넌트 \>  \>  \> **허용/차단 목록 으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="5ede0-182">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Rules** section \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="5ede0-183">**테넌트 허용/차단 목록** 페이지에서  스푸핑 탭을 선택한 다음 차단 아이콘 추가를 ![ ](../../media/m365-cc-sc-create-icon.png) **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="5ede0-183">On the **Tenant Allow/Block List** page, select the **Spoofing** tab, and then click ![Block icon](../../media/m365-cc-sc-create-icon.png) **Add**.</span></span>

3. <span data-ttu-id="5ede0-184">나타나는 **새 도메인** 쌍 추가 플라이아웃에서 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-184">In the **Add new domain pairs** flyout that appears, configure the following settings:</span></span>
   - <span data-ttu-id="5ede0-185">**와일드카드를 통해** 새 도메인 쌍 추가: 한 줄에 도메인 쌍을 하나씩 입력하고 최대 20개까지 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-185">**Add new domain pairs with wildcards**: Enter one domain pair per line, up to a maximum of 20.</span></span> <span data-ttu-id="5ede0-186">스푸핑된 보낸 사람 항목에 대한 구문에 대한 자세한 내용은 이 문서 의 부분에 있는 테넌트 [허용/차단](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) 목록 섹션의 스푸핑된 보낸 사람 항목에 대한 도메인 쌍 구문을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5ede0-186">For details about the syntax for spoofed sender entries, see the [Domain pair syntax for spoofed sender entries in the Tenant Allow/Block List](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) section later in this article.</span></span>
   - <span data-ttu-id="5ede0-187">**스푸핑 유형:** 다음 값 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-187">**Spoof type**: Select one of the following values:</span></span>
     - <span data-ttu-id="5ede0-188">**내부:** 스푸핑된 보낸 사람이 조직에 속한 도메인(허용 [도메인)에 있습니다.](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)</span><span class="sxs-lookup"><span data-stu-id="5ede0-188">**Internal**: The spoofed sender is in a domain that belongs to your organization (an [accepted domain](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)).</span></span>
     - <span data-ttu-id="5ede0-189">**외부:** 스푸핑된 보낸 사람이 외부 도메인에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-189">**External**: The spoofed sender is in an external domain.</span></span>
   - <span data-ttu-id="5ede0-190">**작업:** 허용 **또는 차단을** **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5ede0-190">**Action**: Select **Allow** or **Block**.</span></span>

4. <span data-ttu-id="5ede0-191">작업을 마쳤으면 **추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-191">When you're finished, click **Add**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="5ede0-192">Microsoft 365 Defender 포털을 사용하여 테넌트 허용/차단 목록의 항목 보기</span><span class="sxs-lookup"><span data-stu-id="5ede0-192">Use the Microsoft 365 Defender portal to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="5ede0-193">Microsoft 365 포털에서 정책 **정책** 규칙 & 규칙 테넌트 \>  \>  \> **허용/차단 목록 으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="5ede0-193">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Rules** section \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="5ede0-194">원하는 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-194">Select the tab you want.</span></span> <span data-ttu-id="5ede0-195">사용 가능한 열은 선택한 탭에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-195">The columns that are available depend on the tab you selected:</span></span>

   - <span data-ttu-id="5ede0-196">**URL**:</span><span class="sxs-lookup"><span data-stu-id="5ede0-196">**URLs**:</span></span>
     - <span data-ttu-id="5ede0-197">**값:** URL입니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-197">**Value**: The URL.</span></span>
     - <span data-ttu-id="5ede0-198">**작업**: 값 **Block 입니다.**</span><span class="sxs-lookup"><span data-stu-id="5ede0-198">**Action**: The value **Block**.</span></span>
     - <span data-ttu-id="5ede0-199">**마지막 업데이트**</span><span class="sxs-lookup"><span data-stu-id="5ede0-199">**Last updated**</span></span>
     - <span data-ttu-id="5ede0-200">**제거**</span><span class="sxs-lookup"><span data-stu-id="5ede0-200">**Remove on**</span></span>
     - <span data-ttu-id="5ede0-201">**참고**</span><span class="sxs-lookup"><span data-stu-id="5ede0-201">**Notes**</span></span>
   - <span data-ttu-id="5ede0-202">**파일**</span><span class="sxs-lookup"><span data-stu-id="5ede0-202">**Files**</span></span>
     - <span data-ttu-id="5ede0-203">**값:** 파일 해시입니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-203">**Value**: The file hash.</span></span>
     - <span data-ttu-id="5ede0-204">**작업**: 값 **Block 입니다.**</span><span class="sxs-lookup"><span data-stu-id="5ede0-204">**Action**: The value **Block**.</span></span>
     - <span data-ttu-id="5ede0-205">**마지막 업데이트**</span><span class="sxs-lookup"><span data-stu-id="5ede0-205">**Last updated**</span></span>
     - <span data-ttu-id="5ede0-206">**제거**</span><span class="sxs-lookup"><span data-stu-id="5ede0-206">**Remove on**</span></span>
     - <span data-ttu-id="5ede0-207">**참고**</span><span class="sxs-lookup"><span data-stu-id="5ede0-207">**Notes**</span></span>
   - <span data-ttu-id="5ede0-208">**스푸핑**</span><span class="sxs-lookup"><span data-stu-id="5ede0-208">**Spoofing**</span></span>
     - <span data-ttu-id="5ede0-209">**스푸핑된 사용자**</span><span class="sxs-lookup"><span data-stu-id="5ede0-209">**Spoofed user**</span></span>
     - <span data-ttu-id="5ede0-210">**인프라 보내기**</span><span class="sxs-lookup"><span data-stu-id="5ede0-210">**Sending infrastructure**</span></span>
     - <span data-ttu-id="5ede0-211">**스푸핑 유형**: 내부 또는 외부 **값입니다.** </span><span class="sxs-lookup"><span data-stu-id="5ede0-211">**Spoof type**: The value **Internal** or **External**.</span></span>
     - <span data-ttu-id="5ede0-212">**작업**: 값 **Block** 또는 **Allow입니다.**</span><span class="sxs-lookup"><span data-stu-id="5ede0-212">**Action**: The value **Block** or **Allow**.</span></span>

   <span data-ttu-id="5ede0-213">열 제목을 클릭하여 오차 또는 내선 순서로 정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-213">You can click on a column heading to sort in ascending or descending order.</span></span>

   <span data-ttu-id="5ede0-214">그룹을 **클릭하여** 결과를 그룹화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-214">You can click **Group** to group the results.</span></span> <span data-ttu-id="5ede0-215">사용 가능한 값은 선택한 탭에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-215">The values that are available depend on the tab you selected:</span></span>

   - <span data-ttu-id="5ede0-216">**URL:** 작업을 사용하여 결과를 그룹화할 수 **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="5ede0-216">**URLs**: You can group the results by **Action**.</span></span>
   - <span data-ttu-id="5ede0-217">**파일**: 작업을 사용하여 결과를 그룹화할 **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="5ede0-217">**Files**: You can group the results by **Action**.</span></span>
   - <span data-ttu-id="5ede0-218">**스푸핑**: 작업 또는 스푸핑 유형별로 결과를 **그룹화할 수 있습니다.** </span><span class="sxs-lookup"><span data-stu-id="5ede0-218">**Spoofing**: You can group the results by **Action** or **Spoof type**.</span></span>

   <span data-ttu-id="5ede0-219">**검색을** 클릭하고 값의 전체 또는 일부를 입력한 다음 Enter를 눌러 특정 값을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-219">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="5ede0-220">완료되면 검색 아이콘 지우기 ![ 검색 ](../../media/m365-cc-sc-close-icon.png) **지우기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="5ede0-220">When you're finished, click ![Clear search icon](../../media/m365-cc-sc-close-icon.png) **Clear search**.</span></span>

   <span data-ttu-id="5ede0-221">**필터를** 클릭하여 결과를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-221">Click **Filter** to filter the results.</span></span> <span data-ttu-id="5ede0-222">필터 플라이아웃에서  사용할 수 있는 값은 선택한 탭에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-222">The values that are available in **Filter** flyout that appears depend on the tab you selected:</span></span>

   - <span data-ttu-id="5ede0-223">**URL**</span><span class="sxs-lookup"><span data-stu-id="5ede0-223">**URLs**</span></span>
     - <span data-ttu-id="5ede0-224">**작업**</span><span class="sxs-lookup"><span data-stu-id="5ede0-224">**Action**</span></span>
     - <span data-ttu-id="5ede0-225">**만료되지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="5ede0-225">**Never expire**</span></span>
     - <span data-ttu-id="5ede0-226">**마지막으로 업데이트된 날짜**</span><span class="sxs-lookup"><span data-stu-id="5ede0-226">**Last updated date**</span></span>
     - <span data-ttu-id="5ede0-227">**제거**</span><span class="sxs-lookup"><span data-stu-id="5ede0-227">**Remove on**</span></span>
   - <span data-ttu-id="5ede0-228">**파일**</span><span class="sxs-lookup"><span data-stu-id="5ede0-228">**Files**</span></span>
     - <span data-ttu-id="5ede0-229">**작업**</span><span class="sxs-lookup"><span data-stu-id="5ede0-229">**Action**</span></span>
     - <span data-ttu-id="5ede0-230">**만료되지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="5ede0-230">**Never expire**</span></span>
     - <span data-ttu-id="5ede0-231">**마지막 업데이트**</span><span class="sxs-lookup"><span data-stu-id="5ede0-231">**Last updated**</span></span>
     - <span data-ttu-id="5ede0-232">**제거**</span><span class="sxs-lookup"><span data-stu-id="5ede0-232">**Remove on**</span></span>
   - <span data-ttu-id="5ede0-233">**스푸핑**</span><span class="sxs-lookup"><span data-stu-id="5ede0-233">**Spoofing**</span></span>
     - <span data-ttu-id="5ede0-234">**작업**</span><span class="sxs-lookup"><span data-stu-id="5ede0-234">**Action**</span></span>
     - <span data-ttu-id="5ede0-235">**스푸핑 유형**</span><span class="sxs-lookup"><span data-stu-id="5ede0-235">**Spoof type**</span></span>

   <span data-ttu-id="5ede0-236">완료되면 적용을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="5ede0-236">When you're finished, click **Apply**.</span></span> <span data-ttu-id="5ede0-237">기존 필터를 지우려면 **필터를** 클릭하고 나타나는 필터  플라이아웃에서 필터 **지우기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="5ede0-237">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="5ede0-238">Microsoft 365 Defender 포털을 사용하여 테넌트 허용/차단 목록의 항목 수정</span><span class="sxs-lookup"><span data-stu-id="5ede0-238">Use the Microsoft 365 Defender portal to modify entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="5ede0-239">Microsoft 365 포털에서 정책 **정책** 규칙 & 규칙 테넌트 \>  \>  \> **허용/차단 목록 으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="5ede0-239">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Rules** section \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="5ede0-240">수정할 항목 유형이 포함된 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-240">Select the tab that contains the type of entry that you want to modify:</span></span>
   - <span data-ttu-id="5ede0-241">**URL**</span><span class="sxs-lookup"><span data-stu-id="5ede0-241">**URLs**</span></span>
   - <span data-ttu-id="5ede0-242">**파일**</span><span class="sxs-lookup"><span data-stu-id="5ede0-242">**Files**</span></span>
   - <span data-ttu-id="5ede0-243">**스푸핑**</span><span class="sxs-lookup"><span data-stu-id="5ede0-243">**Spoofing**</span></span>

3. <span data-ttu-id="5ede0-244">수정할 항목을 선택하고 편집 아이콘 편집 ![ 을 ](../../media/m365-cc-sc-edit-icon.png) **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="5ede0-244">Select the entry that you want to modify, and then click ![Edit icon](../../media/m365-cc-sc-edit-icon.png) **Edit**.</span></span> <span data-ttu-id="5ede0-245">플라이아웃에서 수정할 수 있는 값은 이전 단계에서 선택한 탭에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-245">The values that you are able to modify in the flyout that appears depend on the tab you selected in the previous step:</span></span>
   - <span data-ttu-id="5ede0-246">**URL**</span><span class="sxs-lookup"><span data-stu-id="5ede0-246">**URLs**</span></span>
     - <span data-ttu-id="5ede0-247">**만료 및/또는** 만료 날짜가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-247">**Never expire** and/or expiration date.</span></span>
     - <span data-ttu-id="5ede0-248">**선택 사항 참고 사항**</span><span class="sxs-lookup"><span data-stu-id="5ede0-248">**Optional note**</span></span>
   - <span data-ttu-id="5ede0-249">**파일**</span><span class="sxs-lookup"><span data-stu-id="5ede0-249">**Files**</span></span>
     - <span data-ttu-id="5ede0-250">**만료 및/또는** 만료 날짜가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-250">**Never expire** and/or expiration date.</span></span>
     - <span data-ttu-id="5ede0-251">**선택 사항 참고 사항**</span><span class="sxs-lookup"><span data-stu-id="5ede0-251">**Optional note**</span></span>
   - <span data-ttu-id="5ede0-252">**스푸핑**</span><span class="sxs-lookup"><span data-stu-id="5ede0-252">**Spoofing**</span></span>
     - <span data-ttu-id="5ede0-253">**작업:** 값을 허용 또는 **차단으로** 변경할 **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="5ede0-253">**Action**: You can change the value to **Allow** or **Block**.</span></span>
4. <span data-ttu-id="5ede0-254">작업을 마쳤으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-254">When you're finished, click **Save**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="5ede0-255">Microsoft 365 Defender 포털을 사용하여 테넌트 허용/차단 목록에서 항목 제거</span><span class="sxs-lookup"><span data-stu-id="5ede0-255">Use the Microsoft 365 Defender portal to remove entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="5ede0-256">Microsoft 365 포털에서 정책 **정책** 규칙 & 규칙 테넌트 \>  \>  \> **허용/차단 목록 으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="5ede0-256">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Rules** section \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="5ede0-257">제거할 항목 유형이 포함된 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-257">Select the tab that contains the type of entry that you want to remove:</span></span>
   - <span data-ttu-id="5ede0-258">**URL**</span><span class="sxs-lookup"><span data-stu-id="5ede0-258">**URLs**</span></span>
   - <span data-ttu-id="5ede0-259">**파일**</span><span class="sxs-lookup"><span data-stu-id="5ede0-259">**Files**</span></span>
   - <span data-ttu-id="5ede0-260">**스푸핑**</span><span class="sxs-lookup"><span data-stu-id="5ede0-260">**Spoofing**</span></span>

3. <span data-ttu-id="5ede0-261">제거할 항목을 선택하고 삭제 아이콘 삭제 ![ 를 ](../../media/m365-cc-sc-delete-icon.png) **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="5ede0-261">Select the entry that you want to remove, and then click ![Delete icon](../../media/m365-cc-sc-delete-icon.png) **Delete**.</span></span>

4. <span data-ttu-id="5ede0-262">나타나는 경고 대화 상자에서 삭제를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="5ede0-262">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="5ede0-263">PowerShell Exchange Online 독립 실행형 EOP PowerShell을 사용하여 테넌트 허용/차단 목록 구성</span><span class="sxs-lookup"><span data-stu-id="5ede0-263">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-block-file-or-url-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="5ede0-264">PowerShell을 사용하여 테넌트 허용/차단 목록에 차단 파일 또는 URL 항목 추가</span><span class="sxs-lookup"><span data-stu-id="5ede0-264">Use PowerShell to add block file or URL entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="5ede0-265">테넌트 허용/차단 목록에서 차단 파일 또는 URL 항목을 추가하기 위해 다음 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-265">To add block file or URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <FileHash | Url> -Block -Entries "Value1","Value2",..."ValueN" <-ExpirationDate Date | -NoExpiration> [-Notes <String>]
```

<span data-ttu-id="5ede0-266">이 예제에서는 만료되지 않는 지정된 파일에 대한 차단 파일 항목을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-266">This example adds a block file entry for the specified files that never expires.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="5ede0-267">이 예제에서는 contoso.com, contoso.com, www.contoso.com 및 하위 xyz.abc.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="5ede0-267">This example adds a block URL entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="5ede0-268">ExpirationDate 또는 NoExpiration 매개 변수를 사용하지 않았기 때문에 항목이 30일 후에 만료됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-268">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

<span data-ttu-id="5ede0-269">구문과 매개 변수에 대한 자세한 내용은 [New-TenantAllowBlockListItems를 참조하십시오.](/powershell/module/exchange/new-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="5ede0-269">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-add-allow-or-block-spoofed-sender-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="5ede0-270">PowerShell을 사용하여 테넌트 허용/차단 목록에 스푸핑된 보낸 사람 항목 추가 또는 차단</span><span class="sxs-lookup"><span data-stu-id="5ede0-270">Use PowerShell to add allow or block spoofed sender entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="5ede0-271">테넌트 허용/차단 목록에 스푸핑된 보낸 사람 항목을 추가하기 위해 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="5ede0-271">To add spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListSpoofItems -SpoofedUser <Domain | EmailAddress | *> -SendingInfrastructure <Domain | IPAddress/24> -SpoofType <External | Internal> -Action <Allow | Block>
```

<span data-ttu-id="5ede0-272">구문과 매개 변수에 대한 자세한 내용은 [New-TenantAllowBlockListSpoofItems를 참조하십시오.](/powershell/module/exchange/new-tenantallowblocklistspoofitems)</span><span class="sxs-lookup"><span data-stu-id="5ede0-272">For detailed syntax and parameter information, see [New-TenantAllowBlockListSpoofItems](/powershell/module/exchange/new-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-view-block-file-or-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="5ede0-273">PowerShell을 사용하여 테넌트 허용/차단 목록에서 차단 파일 또는 URL 항목 보기</span><span class="sxs-lookup"><span data-stu-id="5ede0-273">Use PowerShell to view block file or URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="5ede0-274">테넌트 허용/차단 목록에서 차단 파일 또는 URL 항목을 보고 다음 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-274">To view block file or URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <FileHash | URL> [-Entry <FileHashValue | URLValue>] [<-ExpirationDate Date | -NoExpiration>]
```

<span data-ttu-id="5ede0-275">이 예제에서는 지정한 파일 해시 값에 대한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-275">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="5ede0-276">이 예제에서는 차단된 URL을 모두 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-276">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

<span data-ttu-id="5ede0-277">구문과 매개 변수에 대한 자세한 내용은 [Get-TenantAllowBlockListItems를 참조하십시오.](/powershell/module/exchange/get-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="5ede0-277">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="5ede0-278">PowerShell을 사용하여 테넌트 허용/차단 목록에서 스푸핑된 보낸 사람 항목 보기 또는 차단</span><span class="sxs-lookup"><span data-stu-id="5ede0-278">Use PowerShell to view allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="5ede0-279">테넌트 허용/차단 목록에서 스푸핑된 보낸 사람 항목을 보고 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="5ede0-279">To view spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems [-Action <Allow | Block>] [-SpoofType <External | Internal>
```

<span data-ttu-id="5ede0-280">이 예에서는 테넌트 허용/차단 목록에 있는 스푸핑된 보낸 사람 항목을 모두 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-280">This example returns all spoofed sender entries in the Tenant Allow/Block List.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems
```

<span data-ttu-id="5ede0-281">이 예에서는 내부에 있는 스푸핑된 보낸 사람 항목을 모두 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-281">This example returns all allow spoofed sender entries that are internal.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems -Action Allow -SpoofType Internal
```

<span data-ttu-id="5ede0-282">이 예에서는 외부에 있는 차단된 스푸핑된 보낸 사람 항목을 모두 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-282">This example returns all blocked spoofed sender entries that are external.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems -Action Block -SpoofType External
```

<span data-ttu-id="5ede0-283">구문과 매개 변수에 대한 자세한 내용은 [Get-TenantAllowBlockListSpoofItems를 참조하십시오.](/powershell/module/exchange/get-tenantallowblocklistspoofitems)</span><span class="sxs-lookup"><span data-stu-id="5ede0-283">For detailed syntax and parameter information, see [Get-TenantAllowBlockListSpoofItems](/powershell/module/exchange/get-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-modify-block-file-and-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="5ede0-284">PowerShell을 사용하여 테넌트 허용/차단 목록에서 차단 파일 및 URL 항목 수정</span><span class="sxs-lookup"><span data-stu-id="5ede0-284">Use PowerShell to modify block file and URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="5ede0-285">테넌트 허용/차단 목록에서 차단 파일 및 URL 항목을 수정하려면 다음 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-285">To modify block file and URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN"> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

<span data-ttu-id="5ede0-286">이 예에서는 지정한 블록 URL 항목의 만료 날짜를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-286">This example changes the expiration date of the specified block URL entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate "5/30/2020"
```

<span data-ttu-id="5ede0-287">구문과 매개 변수에 대한 자세한 내용은 [Set-TenantAllowBlockListItems를 참조하십시오.](/powershell/module/exchange/set-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="5ede0-287">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="5ede0-288">PowerShell을 사용하여 테넌트 허용/차단 목록에서 스푸핑된 보낸 사람 항목 허용 또는 차단</span><span class="sxs-lookup"><span data-stu-id="5ede0-288">Use PowerShell to modify allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="5ede0-289">테넌트 허용/차단 목록에서 스푸핑된 보낸 사람 항목을 허용하거나 차단하려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="5ede0-289">To modify allow or block spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN"> -Action <Allow | Block>
```

<span data-ttu-id="5ede0-290">이 예에서는 스푸핑된 보낸 사람 항목을 허용에서 차단으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-290">This example changes spoofed sender entry from allow to block.</span></span>

```powershell
Set-TenantAllowBlockListItems -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -Action Block
```

<span data-ttu-id="5ede0-291">구문과 매개 변수에 대한 자세한 내용은 [Set-TenantAllowBlockListSpoofItems를 참조하십시오.](/powershell/module/exchange/set-tenantallowblocklistspoofitems)</span><span class="sxs-lookup"><span data-stu-id="5ede0-291">For detailed syntax and parameter information, see [Set-TenantAllowBlockListSpoofItems](/powershell/module/exchange/set-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-remove-url-or-file-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="5ede0-292">PowerShell을 사용하여 테넌트 허용/차단 목록에서 URL 또는 파일 항목 제거</span><span class="sxs-lookup"><span data-stu-id="5ede0-292">Use PowerShell to remove URL or file entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="5ede0-293">테넌트 허용/차단 목록에서 파일 및 URL 항목을 제거하려면 다음 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-293">To remove file and URL entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="5ede0-294">이 예에서는 테넌트 허용/차단 목록에서 지정된 차단 URL 항목을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-294">This example removes the specified block URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="5ede0-295">구문과 매개 변수에 대한 자세한 내용은 [Remove-TenantAllowBlockListItems를 참조하십시오.](/powershell/module/exchange/remove-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="5ede0-295">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-allow-or-block-spoofed-sender-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="5ede0-296">PowerShell을 사용하여 테넌트 허용/차단 목록에서 스푸핑된 보낸 사람 항목 허용 또는 차단</span><span class="sxs-lookup"><span data-stu-id="5ede0-296">Use PowerShell to remove allow or block spoofed sender entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="5ede0-297">테넌트 허용/차단 목록에서 스푸핑 보낸 사람 항목을 허용하거나 차단하려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="5ede0-297">To remove allow or block spoof sender entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="5ede0-298">구문과 매개 변수에 대한 자세한 내용은 [Remove-TenantAllowBlockListSpoofItems를 참조하십시오.](/powershell/module/exchange/remove-tenantallowblocklistspoofitems)</span><span class="sxs-lookup"><span data-stu-id="5ede0-298">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListSpoofItems](/powershell/module/exchange/remove-tenantallowblocklistspoofitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="5ede0-299">테넌트 허용/차단 목록에 대한 URL 구문</span><span class="sxs-lookup"><span data-stu-id="5ede0-299">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="5ede0-300">IP4v 및 IPv6 주소는 사용할 수 있지만 TCP/UDP 포트는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-300">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="5ede0-301">파일 이름 확장명은 허용되지 않습니다(예: test.pdf).</span><span class="sxs-lookup"><span data-stu-id="5ede0-301">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="5ede0-302">유니코드는 지원되지 않지만 Punycode는 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-302">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="5ede0-303">다음 명령문이 모두 true이면 호스트 이름을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-303">Hostnames are allowed if all of the following statements are true:</span></span>
  - <span data-ttu-id="5ede0-304">호스트 이름에는 기간이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-304">The hostname contains a period.</span></span>
  - <span data-ttu-id="5ede0-305">기간 왼쪽에 하나 이상의 문자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-305">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="5ede0-306">이 기간의 오른쪽에는 두 개 이상의 문자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-306">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="5ede0-307">예를 들어 `t.co` 허용되거나 `.com` `contoso.` 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-307">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="5ede0-308">하위 경로는 암시적이지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-308">Subpaths are not implied.</span></span>

  <span data-ttu-id="5ede0-309">예를 들어 `contoso.com` 를 포함하지 `contoso.com/a` 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-309">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="5ede0-310">와일드카드(\*)는 다음과 같은 시나리오에서 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-310">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="5ede0-311">하위omain을 지정하려면 왼쪽 와일드카드 다음에 기간이 와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-311">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="5ede0-312">예를 들어 `*.contoso.com` 허용됩니다. `*contoso.com` 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-312">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="5ede0-313">오른쪽 와일드카드는 슬래시(/)를 따라 경로를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-313">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="5ede0-314">예를 들어 `contoso.com/*` 허용되거나 `contoso.com*` `contoso.com/ab*` 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-314">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="5ede0-315">모든 하위 경로는 올바른 와일드카드로 암시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-315">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="5ede0-316">예를 들어 `contoso.com/*` 를 포함하지 `contoso.com/a` 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-316">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="5ede0-317">`*.com*` 가 잘못되었습니다(확인 가능한 도메인이 아니며 오른쪽 와일드카드가 슬래시를 따르지 않습니다).</span><span class="sxs-lookup"><span data-stu-id="5ede0-317">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="5ede0-318">와일드카드는 IP 주소에서 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-318">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="5ede0-319">다음 시나리오에서는 선조(~) 문자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-319">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="5ede0-320">왼쪽 밀기선은 도메인과 모든 하위 도메인을 암시합니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-320">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="5ede0-321">예를 들어 `~contoso.com` 및 `contoso.com` `*.contoso.com` 을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-321">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="5ede0-322">URL 항목이 모든 프로토콜에 적용될 수 있기 때문에 프로토콜(예: , 또는 )이 포함된 URL 항목은 `http://` `https://` `ftp://` 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-322">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="5ede0-323">사용자 이름 또는 암호는 지원되거나 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-323">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="5ede0-324">따옴표(' 또는 ")는 잘못된 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-324">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="5ede0-325">URL에는 가능한 경우 모든 리디렉션이 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-325">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="5ede0-326">URL 입력 시나리오</span><span class="sxs-lookup"><span data-stu-id="5ede0-326">URL entry scenarios</span></span>

<span data-ttu-id="5ede0-327">유효한 URL 항목 및 해당 결과는 다음 섹션에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-327">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="5ede0-328">시나리오: 와일드카드 없음</span><span class="sxs-lookup"><span data-stu-id="5ede0-328">Scenario: No wildcards</span></span>

<span data-ttu-id="5ede0-329">**항목**: `contoso.com`</span><span class="sxs-lookup"><span data-stu-id="5ede0-329">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="5ede0-330">**일치 허용**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="5ede0-330">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="5ede0-331">**일치하지 않는 허용**:</span><span class="sxs-lookup"><span data-stu-id="5ede0-331">**Allow not matched**:</span></span>

  - <span data-ttu-id="5ede0-332">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="5ede0-332">abc-contoso.com</span></span>
  - <span data-ttu-id="5ede0-333">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="5ede0-333">contoso.com/a</span></span>
  - <span data-ttu-id="5ede0-334">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5ede0-334">payroll.contoso.com</span></span>
  - <span data-ttu-id="5ede0-335">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="5ede0-335">test.com/contoso.com</span></span>
  - <span data-ttu-id="5ede0-336">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="5ede0-336">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="5ede0-337">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5ede0-337">www.contoso.com</span></span>
  - <span data-ttu-id="5ede0-338">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="5ede0-338">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="5ede0-339">**블록 일치**:</span><span class="sxs-lookup"><span data-stu-id="5ede0-339">**Block match**:</span></span>

  - <span data-ttu-id="5ede0-340">contoso.com</span><span class="sxs-lookup"><span data-stu-id="5ede0-340">contoso.com</span></span>
  - <span data-ttu-id="5ede0-341">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="5ede0-341">contoso.com/a</span></span>
  - <span data-ttu-id="5ede0-342">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5ede0-342">payroll.contoso.com</span></span>
  - <span data-ttu-id="5ede0-343">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="5ede0-343">test.com/contoso.com</span></span>
  - <span data-ttu-id="5ede0-344">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="5ede0-344">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="5ede0-345">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5ede0-345">www.contoso.com</span></span>
  - <span data-ttu-id="5ede0-346">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="5ede0-346">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="5ede0-347">**블록이 일치하지 않는 경우**: abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="5ede0-347">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="5ede0-348">시나리오: 왼쪽 와일드카드(하위omain)</span><span class="sxs-lookup"><span data-stu-id="5ede0-348">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="5ede0-349">**항목**: `*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="5ede0-349">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="5ede0-350">**일치 및** **차단 일치 허용**:</span><span class="sxs-lookup"><span data-stu-id="5ede0-350">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="5ede0-351">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5ede0-351">www.contoso.com</span></span>
  - <span data-ttu-id="5ede0-352">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5ede0-352">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="5ede0-353">**일치하지 않는 허용** 및 **차단이 일치하지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="5ede0-353">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="5ede0-354">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="5ede0-354">123contoso.com</span></span>
  - <span data-ttu-id="5ede0-355">contoso.com</span><span class="sxs-lookup"><span data-stu-id="5ede0-355">contoso.com</span></span>
  - <span data-ttu-id="5ede0-356">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="5ede0-356">test.com/contoso.com</span></span>
  - <span data-ttu-id="5ede0-357">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="5ede0-357">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="5ede0-358">시나리오: 경로 맨 위에 있는 오른쪽 와일드카드</span><span class="sxs-lookup"><span data-stu-id="5ede0-358">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="5ede0-359">**항목**: `contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="5ede0-359">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="5ede0-360">**일치 및** **차단 일치 허용**:</span><span class="sxs-lookup"><span data-stu-id="5ede0-360">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="5ede0-361">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="5ede0-361">contoso.com/a/b</span></span>
  - <span data-ttu-id="5ede0-362">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="5ede0-362">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="5ede0-363">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="5ede0-363">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="5ede0-364">**일치하지 않는 허용** 및 **차단이 일치하지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="5ede0-364">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="5ede0-365">contoso.com</span><span class="sxs-lookup"><span data-stu-id="5ede0-365">contoso.com</span></span>
  - <span data-ttu-id="5ede0-366">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="5ede0-366">contoso.com/a</span></span>
  - <span data-ttu-id="5ede0-367">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5ede0-367">www.contoso.com</span></span>
  - <span data-ttu-id="5ede0-368">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="5ede0-368">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="5ede0-369">시나리오: 왼쪽 밀기</span><span class="sxs-lookup"><span data-stu-id="5ede0-369">Scenario: Left tilde</span></span>

<span data-ttu-id="5ede0-370">**항목**: `~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="5ede0-370">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="5ede0-371">**일치 및** **차단 일치 허용**:</span><span class="sxs-lookup"><span data-stu-id="5ede0-371">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="5ede0-372">contoso.com</span><span class="sxs-lookup"><span data-stu-id="5ede0-372">contoso.com</span></span>
  - <span data-ttu-id="5ede0-373">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5ede0-373">www.contoso.com</span></span>
  - <span data-ttu-id="5ede0-374">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5ede0-374">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="5ede0-375">**일치하지 않는 허용** 및 **차단이 일치하지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="5ede0-375">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="5ede0-376">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="5ede0-376">123contoso.com</span></span>
  - <span data-ttu-id="5ede0-377">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="5ede0-377">contoso.com/abc</span></span>
  - <span data-ttu-id="5ede0-378">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="5ede0-378">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="5ede0-379">시나리오: 오른쪽 와일드카드 접미사</span><span class="sxs-lookup"><span data-stu-id="5ede0-379">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="5ede0-380">**항목**: `contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="5ede0-380">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="5ede0-381">**일치 및** **차단 일치 허용**:</span><span class="sxs-lookup"><span data-stu-id="5ede0-381">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="5ede0-382">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="5ede0-382">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="5ede0-383">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="5ede0-383">contoso.com/a</span></span>
  - <span data-ttu-id="5ede0-384">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="5ede0-384">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="5ede0-385">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="5ede0-385">contoso.com/ab</span></span>
  - <span data-ttu-id="5ede0-386">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="5ede0-386">contoso.com/b</span></span>
  - <span data-ttu-id="5ede0-387">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="5ede0-387">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="5ede0-388">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="5ede0-388">contoso.com/ba</span></span>

- <span data-ttu-id="5ede0-389">**일치하지 않는 허용** 및 **일치하지 않는** 차단 : contoso.com</span><span class="sxs-lookup"><span data-stu-id="5ede0-389">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="5ede0-390">시나리오: 왼쪽 와일드카드 하위omain 및 오른쪽 와일드카드 접미사</span><span class="sxs-lookup"><span data-stu-id="5ede0-390">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="5ede0-391">**항목**: `*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="5ede0-391">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="5ede0-392">**일치 및** **차단 일치 허용**:</span><span class="sxs-lookup"><span data-stu-id="5ede0-392">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="5ede0-393">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="5ede0-393">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="5ede0-394">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="5ede0-394">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="5ede0-395">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="5ede0-395">www.contoso.com/a</span></span>
  - <span data-ttu-id="5ede0-396">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="5ede0-396">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="5ede0-397">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="5ede0-397">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="5ede0-398">**일치하지 않는 허용** 및 **일치하지 않는** 차단 : contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="5ede0-398">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="5ede0-399">시나리오: 왼쪽 및 오른쪽 밀기</span><span class="sxs-lookup"><span data-stu-id="5ede0-399">Scenario: Left and right tilde</span></span>

<span data-ttu-id="5ede0-400">**항목**: `~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="5ede0-400">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="5ede0-401">**일치 및** **차단 일치 허용**:</span><span class="sxs-lookup"><span data-stu-id="5ede0-401">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="5ede0-402">contoso.com</span><span class="sxs-lookup"><span data-stu-id="5ede0-402">contoso.com</span></span>
  - <span data-ttu-id="5ede0-403">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="5ede0-403">contoso.com/a</span></span>
  - <span data-ttu-id="5ede0-404">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5ede0-404">www.contoso.com</span></span>
  - <span data-ttu-id="5ede0-405">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="5ede0-405">www.contoso.com/b</span></span>
  - <span data-ttu-id="5ede0-406">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5ede0-406">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="5ede0-407">**일치하지 않는 허용** 및 **차단이 일치하지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="5ede0-407">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="5ede0-408">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="5ede0-408">123contoso.com</span></span>
  - <span data-ttu-id="5ede0-409">contoso.org</span><span class="sxs-lookup"><span data-stu-id="5ede0-409">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="5ede0-410">시나리오: IP 주소</span><span class="sxs-lookup"><span data-stu-id="5ede0-410">Scenario: IP address</span></span>

<span data-ttu-id="5ede0-411">**항목**: `1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="5ede0-411">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="5ede0-412">**일치 및** **차단 일치** 허용 : 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="5ede0-412">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="5ede0-413">**일치하지 않는 허용** 및 **차단이 일치하지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="5ede0-413">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="5ede0-414">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="5ede0-414">1.2.3.4/a</span></span>
  - <span data-ttu-id="5ede0-415">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="5ede0-415">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="5ede0-416">오른쪽 와일드카드가 있는 IP 주소</span><span class="sxs-lookup"><span data-stu-id="5ede0-416">IP address with right wildcard</span></span>

<span data-ttu-id="5ede0-417">**항목**: `1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="5ede0-417">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="5ede0-418">**일치 및** **차단 일치 허용**:</span><span class="sxs-lookup"><span data-stu-id="5ede0-418">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="5ede0-419">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="5ede0-419">1.2.3.4/b</span></span>
  - <span data-ttu-id="5ede0-420">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="5ede0-420">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="5ede0-421">잘못된 항목의 예</span><span class="sxs-lookup"><span data-stu-id="5ede0-421">Examples of invalid entries</span></span>

<span data-ttu-id="5ede0-422">다음 항목이 잘못되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-422">The following entries are invalid:</span></span>

- <span data-ttu-id="5ede0-423">**누락되었거나 잘못된 도메인 값**:</span><span class="sxs-lookup"><span data-stu-id="5ede0-423">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="5ede0-424">contoso</span><span class="sxs-lookup"><span data-stu-id="5ede0-424">contoso</span></span>
  - <span data-ttu-id="5ede0-425">\*.contoso.\*</span><span class="sxs-lookup"><span data-stu-id="5ede0-425">\*.contoso.\*</span></span>
  - <span data-ttu-id="5ede0-426">\*.com</span><span class="sxs-lookup"><span data-stu-id="5ede0-426">\*.com</span></span>
  - <span data-ttu-id="5ede0-427">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="5ede0-427">\*.pdf</span></span>

- <span data-ttu-id="5ede0-428">**텍스트의 와일드카드 또는 간격 문자가 없는** 경우 :</span><span class="sxs-lookup"><span data-stu-id="5ede0-428">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="5ede0-429">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="5ede0-429">\*contoso.com</span></span>
  - <span data-ttu-id="5ede0-430">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="5ede0-430">contoso.com\*</span></span>
  - <span data-ttu-id="5ede0-431">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="5ede0-431">\*1.2.3.4</span></span>
  - <span data-ttu-id="5ede0-432">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="5ede0-432">1.2.3.4\*</span></span>
  - <span data-ttu-id="5ede0-433">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="5ede0-433">contoso.com/a\*</span></span>
  - <span data-ttu-id="5ede0-434">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="5ede0-434">contoso.com/ab\*</span></span>

- <span data-ttu-id="5ede0-435">**포트가 있는 IP 주소:**</span><span class="sxs-lookup"><span data-stu-id="5ede0-435">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="5ede0-436">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="5ede0-436">contoso.com:443</span></span>
  - <span data-ttu-id="5ede0-437">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="5ede0-437">abc.contoso.com:25</span></span>

- <span data-ttu-id="5ede0-438">**설명이 없는 와일드카드**:</span><span class="sxs-lookup"><span data-stu-id="5ede0-438">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="5ede0-439">\*.\*</span><span class="sxs-lookup"><span data-stu-id="5ede0-439">\*.\*</span></span>

- <span data-ttu-id="5ede0-440">**중간 와일드카드**:</span><span class="sxs-lookup"><span data-stu-id="5ede0-440">**Middle wildcards**:</span></span>

  - <span data-ttu-id="5ede0-441">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="5ede0-441">conto\*so.com</span></span>
  - <span data-ttu-id="5ede0-442">conto~so.com</span><span class="sxs-lookup"><span data-stu-id="5ede0-442">conto~so.com</span></span>

- <span data-ttu-id="5ede0-443">**이중 와일드카드**</span><span class="sxs-lookup"><span data-stu-id="5ede0-443">**Double wildcards**</span></span>

  - <span data-ttu-id="5ede0-444">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="5ede0-444">contoso.com/\*\*</span></span>
  - <span data-ttu-id="5ede0-445">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="5ede0-445">contoso.com/\*/\*</span></span>

## <a name="domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="5ede0-446">테넌트 허용/차단 목록의 스푸핑된 보낸 사람 항목에 대한 도메인 쌍 구문</span><span class="sxs-lookup"><span data-stu-id="5ede0-446">Domain pair syntax for spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="5ede0-447">테넌트 허용/차단 목록에서 스푸핑된 보낸 사람에 대한 도메인 쌍은 다음 구문을 사용 `<Spoofed user>, <Sending infrastructure>` 합니다. .</span><span class="sxs-lookup"><span data-stu-id="5ede0-447">A domain pair for a spoofed sender in the Tenant Allow/Block List uses the following syntax: `<Spoofed user>, <Sending infrastructure>`.</span></span>

- <span data-ttu-id="5ede0-448">**스푸핑된 사용자:** 이 값은 전자 메일 클라이언트의 시작 상자에 표시되는  스푸핑된 사용자의 전자 메일 주소와 관련됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-448">**Spoofed user**: This value involves the email address of the spoofed user that's displayed in the **From** box in email clients.</span></span> <span data-ttu-id="5ede0-449">이 주소를 `5322.From` 주소라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-449">This address is also known as the `5322.From` address.</span></span> <span data-ttu-id="5ede0-450">사용할 수 있는 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-450">Valid values include:</span></span>
  - <span data-ttu-id="5ede0-451">개별 전자 메일 주소(예: chris@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="5ede0-451">An individual email address (for example, chris@contoso.com).</span></span>
  - <span data-ttu-id="5ede0-452">전자 메일 도메인(예: contoso.com.</span><span class="sxs-lookup"><span data-stu-id="5ede0-452">An email domain (for example, contoso.com).</span></span>
  - <span data-ttu-id="5ede0-453">와일드카드 문자(예: \* ).</span><span class="sxs-lookup"><span data-stu-id="5ede0-453">The wildcard character (for example, \*).</span></span>

- <span data-ttu-id="5ede0-454">**보내는 인프라:** 이 값은 스푸핑된 사용자의 메시지 원본을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-454">**Sending infrastructure**: This value indicates the source of messages from the spoofed user.</span></span> <span data-ttu-id="5ede0-455">사용할 수 있는 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-455">Valid values include:</span></span>
  - <span data-ttu-id="5ede0-456">원본 전자 메일 서버의 IP 주소(예: PTR 레코드)의 역방향 DNS fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="5ede0-456">The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address (for example, fabrikam.com).</span></span>
  - <span data-ttu-id="5ede0-457">원본 IP 주소에 PTR 레코드가 없는 경우 보내는 인프라는 \<source IP\> /24(예: 192.168.100.100/24)로 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-457">If the source IP address has no PTR record, then the sending infrastructure is identified as \<source IP\>/24 (for example, 192.168.100.100/24).</span></span>

<span data-ttu-id="5ede0-458">다음은 스푸핑된 보낸 사람 식별을 위한 유효한 도메인 쌍의 몇 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-458">Here are some examples of valid domain pairs to identify spoofed senders:</span></span>

- `contoso.com, 192.168.100.100/24`
- `chris@contoso.com, fabrikam.com`
- `*, contoso.net`

<span data-ttu-id="5ede0-459">스푸핑된 보낸 사람 항목의 최대 수는 1000개입니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-459">The maximum number of spoofed sender entries is 1000.</span></span>

<span data-ttu-id="5ede0-460">도메인 쌍을 추가하면 스푸핑된 사용자와 보내는 인프라의 조합만 허용하거나 *차단할* 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="5ede0-460">Adding a domain pair only allows or blocks the *combination* of the spoofed user *and* the sending infrastructure.</span></span> <span data-ttu-id="5ede0-461">또한 모든 원본에서 스푸핑된 사용자의 전자 메일을 허용하지 않으며, 스푸핑된 사용자에 대해 보내는 인프라 원본의 전자 메일을 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-461">It does not allow email from the spoofed user from any source, nor does it allow email from the sending infrastructure source for any spoofed user.</span></span> 

<span data-ttu-id="5ede0-462">예를 들어 다음 도메인 쌍에 대해 허용 항목을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-462">For example, you add an allow entry for the following domain pair:</span></span>

- <span data-ttu-id="5ede0-463">**도메인**: gmail.com</span><span class="sxs-lookup"><span data-stu-id="5ede0-463">**Domain**: gmail.com</span></span>
- <span data-ttu-id="5ede0-464">**인프라:** tms.mx.com</span><span class="sxs-lookup"><span data-stu-id="5ede0-464">**Infrastructure**: tms.mx.com</span></span>

<span data-ttu-id="5ede0-465">해당 도메인 및  보내는 인프라 쌍의 메시지만 스푸핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-465">Only messages from that domain *and* sending infrastructure pair are allowed to spoof.</span></span> <span data-ttu-id="5ede0-466">스푸핑을 시도하는 gmail.com 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-466">Other senders attempting to spoof gmail.com aren't allowed.</span></span> <span data-ttu-id="5ede0-467">다른 도메인의 보낸 사람이 보낸 메시지는 tms.mx.com 인텔리전스를 통해 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ede0-467">Messages from senders in other domains originating from tms.mx.com are checked by spoof intelligence.</span></span>
