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
ms.openlocfilehash: 103ddc9aa0858f9203582ac07a655fd7f5506cf3
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587590"
---
# <a name="manage-the-tenant-allowblock-list"></a><span data-ttu-id="7f509-103">테넌트 허용/차단 목록 관리</span><span class="sxs-lookup"><span data-stu-id="7f509-103">Manage the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="7f509-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="7f509-104">**Applies to**</span></span>
- [<span data-ttu-id="7f509-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="7f509-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="7f509-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="7f509-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="7f509-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7f509-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="7f509-108">현재는 **테넌트** 허용/차단 목록에서 허용된 항목을 구성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-108">You can't **configure** allowed items in the Tenant Allow/Block List at this time.</span></span>

<span data-ttu-id="7f509-109">Exchange Online 사서함이 있는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에서는 EOP 필터링 판정에 동의하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-109">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="7f509-110">예를 들어 양호한 메시지는 나쁜 메시지(가음성)로 표시되거나 잘못된 메시지가 통과(거짓 부정)로 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-110">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="7f509-111">보안 및 준수 센터의 테넌트 허용/차단 & Microsoft 365 필터링 판정을 수동으로 다시 설정하는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-111">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="7f509-112">테넌트 허용/차단 목록은 메일 흐름 중과 사용자가 클릭할 때 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-112">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="7f509-113">항상 차단할 URL 또는 파일을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-113">You can specify URLs or files to always block.</span></span>

<span data-ttu-id="7f509-114">이 문서에서는 보안 & 준수 센터 또는 PowerShell(Exchange Online에 사서함이 있는 Microsoft 365 조직의 경우 Exchange Online PowerShell, Exchange Online 사서함이 없는 조직의 경우 독립 실행형 EOP PowerShell)에서 테넌트 허용/차단 목록의 항목을 구성하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-114">This article describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="7f509-115">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="7f509-115">What do you need to know before you begin?</span></span>

- <span data-ttu-id="7f509-116"><https://protection.office.com/>에서 보안 및 준수 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-116">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="7f509-117">테넌트 **허용/차단 목록 페이지로 직접 이동하기** 위해 를 <https://protection.office.com/tenantAllowBlockList> 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="7f509-117">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="7f509-118">파일의 SHA256 해시 값을 사용하여 파일을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-118">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="7f509-119">Windows에서 파일의 SHA256 해시 값을 찾으면 명령 프롬프트에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-119">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="7f509-120">값의 예로는 를 들 수 `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-120">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="7f509-121">pHash(지각 해시) 값은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-121">Perceptual hash (pHash) values are not supported.</span></span>

- <span data-ttu-id="7f509-122">사용 가능한 URL 값은 이 문서 부분의 [테넌트 허용/차단](#url-syntax-for-the-tenant-allowblock-list) 목록 섹션에 대한 URL 구문에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-122">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="7f509-123">테넌트 허용/차단 목록을 사용하면 URL에 대해 최대 500개 항목과 파일 해시의 항목 500개가 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-123">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="7f509-124">각 항목의 최대 문자 수는 다음입니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-124">The maximum number of characters for each entry is:</span></span>
  - <span data-ttu-id="7f509-125">파일 해시 = 64</span><span class="sxs-lookup"><span data-stu-id="7f509-125">File hashes = 64</span></span>
  - <span data-ttu-id="7f509-126">URL = 250</span><span class="sxs-lookup"><span data-stu-id="7f509-126">URL = 250</span></span>

- <span data-ttu-id="7f509-127">항목이 30분 이내에 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-127">An entry should be active within 30 minutes.</span></span>

- <span data-ttu-id="7f509-128">기본적으로 테넌트 허용/차단 목록의 항목은 30일 후에 만료됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-128">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="7f509-129">날짜를 지정하거나 만료되지 않는 날짜로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-129">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="7f509-130">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7f509-130">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="7f509-131">독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7f509-131">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="7f509-132">이 게시물의 절차를 수행하려면 먼저 **Exchange Online** 에서 사용 권한을 할당받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-132">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="7f509-133">테넌트 허용/차단 목록에서 값을 추가 및 제거하려면 조직  관리 또는 보안 관리자 역할 그룹의 **구성원이** 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-133">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="7f509-134">테넌트 허용/차단 목록에 대한 읽기 전용 액세스의 경우 전역  읽기 사용자 또는 보안 읽기 권한이 있는 역할 그룹의 **구성원이** 되거나 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-134">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="7f509-135">자세한 내용은 [Exchange Online의 사용 권한](/exchange/permissions-exo/permissions-exo)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7f509-135">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  > 
  > - <span data-ttu-id="7f509-136">Microsoft 365 관리 센터의 해당 Azure Active Directory 역할에 사용자를 추가하면 사용자에게 필요한 권한 _및_ Microsoft 365의 다른 기능에 대한 권한이 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-136">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="7f509-137">자세한 내용은 [관리자 역할 정보](../../admin/add-users/about-admin-roles.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7f509-137">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  > - <span data-ttu-id="7f509-138">[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups)의 **보기 전용 조직 관리** 역할 그룹에도 기능에 대한 읽기 전용 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-138">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="7f509-139">보안 및 & 센터를 사용하여 테넌트 허용/차단 목록에 URL 항목 만들기</span><span class="sxs-lookup"><span data-stu-id="7f509-139">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="7f509-140">URL 항목의 구문에 대한 자세한 내용은 이 문서 부분의 [테넌트 허용/차단](#url-syntax-for-the-tenant-allowblock-list) 목록 섹션에 대한 URL 구문을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7f509-140">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

1. <span data-ttu-id="7f509-141">보안 및 & 센터에서 위협 **관리** 정책 \>  \> **테넌트 허용/차단 목록으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="7f509-141">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="7f509-142">**테넌트 허용/차단 목록** 페이지에서 URL  탭이 선택되어 있는지 확인한 다음 **차단을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="7f509-142">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Block**</span></span>

3. <span data-ttu-id="7f509-143">나타나는 **URL 차단** 플라이아웃에서 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-143">In the **Block URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="7f509-144">**차단할 URL 추가:** 줄당 하나의 URL을 입력하고 최대 20개까지 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-144">**Add URLs to block**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="7f509-145">**만료 안 하세요:** 다음 단계 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-145">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="7f509-146">설정이 꺼져 있는지 확인하고(토글 해제) 만료 날짜 상자를 사용하여 항목의 만료 ![ ](../../media/scc-toggle-off.png) 날짜를 지정합니다. </span><span class="sxs-lookup"><span data-stu-id="7f509-146">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

       <span data-ttu-id="7f509-147">또는</span><span class="sxs-lookup"><span data-stu-id="7f509-147">or</span></span>

     - <span data-ttu-id="7f509-148">토글을 오른쪽으로 이동하여 만료되지 않는 항목을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-148">Move the toggle to the right to configure the entries to never expire:</span></span> ![토글 켬](../../media/scc-toggle-on.png)<span data-ttu-id="7f509-150">.</span><span class="sxs-lookup"><span data-stu-id="7f509-150">.</span></span>

   - <span data-ttu-id="7f509-151">**선택 사항:** 항목에 대한 설명 텍스트를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-151">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="7f509-152">작업을 마쳤으면 **추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-152">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="7f509-153">보안 및 & 센터를 사용하여 테넌트 허용/차단 목록에 파일 항목 만들기</span><span class="sxs-lookup"><span data-stu-id="7f509-153">Use the Security & Compliance Center to create file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="7f509-154">보안 및 & 센터에서 위협 **관리** 정책 \>  \> **테넌트 허용/차단 목록으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="7f509-154">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="7f509-155">**테넌트 허용/차단 목록** 페이지에서  파일 탭을 선택한 다음 차단을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="7f509-155">On the **Tenant Allow/Block List** page, select **Files** tab, and then click **Block**.</span></span>

3. <span data-ttu-id="7f509-156">**플라이아웃을 차단할** 파일 추가에서 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-156">In the **Add files to block** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="7f509-157">**파일 해시 추가:** 줄당 SHA256 해시 값 하나(최대 20개)를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-157">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="7f509-158">**만료 안 하세요:** 다음 단계 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-158">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="7f509-159">설정이 꺼져 있는지 확인하고(토글 해제) 만료 날짜 상자를 사용하여 항목의 만료 ![ ](../../media/scc-toggle-off.png) 날짜를 지정합니다. </span><span class="sxs-lookup"><span data-stu-id="7f509-159">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="7f509-160">또는</span><span class="sxs-lookup"><span data-stu-id="7f509-160">or</span></span>

     - <span data-ttu-id="7f509-161">토글을 오른쪽으로 이동하여 만료되지 않는 항목을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-161">Move the toggle to the right to configure the entries to never expire:</span></span> ![토글 켬](../../media/scc-toggle-on.png)<span data-ttu-id="7f509-163">.</span><span class="sxs-lookup"><span data-stu-id="7f509-163">.</span></span>

   - <span data-ttu-id="7f509-164">**선택 사항:** 항목에 대한 설명 텍스트를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-164">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="7f509-165">작업을 마쳤으면 **추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-165">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="7f509-166">보안 및 & 센터를 사용하여 테넌트 허용/차단 목록의 항목 보기</span><span class="sxs-lookup"><span data-stu-id="7f509-166">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="7f509-167">보안 및 & 센터에서 위협 **관리** 정책 \>  \> **테넌트 허용/차단 목록으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="7f509-167">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="7f509-168">URL **탭 또는** 파일 **탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-168">Select the **URLs** tab or the **Files** tab.</span></span>

<span data-ttu-id="7f509-169">다음 열 제목을 클릭하여 오차 또는 내선 순서로 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-169">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="7f509-170">**값:** URL 또는 파일 해시입니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-170">**Value**: The URL or the file hash.</span></span>
- <span data-ttu-id="7f509-171">**마지막으로 업데이트된 날짜**</span><span class="sxs-lookup"><span data-stu-id="7f509-171">**Last updated date**</span></span>
- <span data-ttu-id="7f509-172">**만료 날짜**</span><span class="sxs-lookup"><span data-stu-id="7f509-172">**Expiration date**</span></span>
- <span data-ttu-id="7f509-173">**참고**</span><span class="sxs-lookup"><span data-stu-id="7f509-173">**Note**</span></span>

<span data-ttu-id="7f509-174">**검색을** 클릭하고 값의 전체 또는 일부를 입력한 다음 Enter를 눌러 특정 값을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-174">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="7f509-175">완료되면 검색 지우기 **검색** ![ 아이콘 지우기 를 ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-175">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="7f509-176">필터 **를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="7f509-176">Click **Filter**.</span></span> <span data-ttu-id="7f509-177">나타나는 **필터** 플라이아웃에서 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-177">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="7f509-178">**만료 안 하게:** 해제 선택: 해제 ![ 또는 ](../../media/scc-toggle-off.png) 으로 전환: ![ 을 토글합니다. ](../../media/scc-toggle-on.png)</span><span class="sxs-lookup"><span data-stu-id="7f509-178">**Never expire**: Select off: ![Toggle off](../../media/scc-toggle-off.png) or on: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

- <span data-ttu-id="7f509-179">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span><span class="sxs-lookup"><span data-stu-id="7f509-179">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="7f509-180">**만료 날짜:** 시작 날짜(**시작** 날짜 ), 종료 날짜(**To**) 또는 둘 다를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-180">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="7f509-181">완료되면 적용을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="7f509-181">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="7f509-182">기존 필터를 지우려면 **필터를** 클릭하고 나타나는 필터  플라이아웃에서 필터 **지우기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="7f509-182">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-block-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="7f509-183">보안 및 & 센터를 사용하여 테넌트 허용/차단 목록의 차단 항목 수정</span><span class="sxs-lookup"><span data-stu-id="7f509-183">Use the Security & Compliance Center to modify block entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="7f509-184">항목 내의 기존 차단된 URL 또는 파일 값은 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-184">You can't modify the existing blocked URL or file values within an entry.</span></span> <span data-ttu-id="7f509-185">이러한 값을 수정하려면 항목을 삭제하고 다시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-185">To modify these values, you need to delete and recreate the entry.</span></span>

1. <span data-ttu-id="7f509-186">보안 및 & 센터에서 위협 **관리** 정책 \>  \> **테넌트 허용/차단 목록으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="7f509-186">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="7f509-187">URL **탭 또는** 파일 **탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-187">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="7f509-188">수정할 차단 항목을 선택하고 편집 편집 아이콘  ![ 을 ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-188">Select the block entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="7f509-189">플라이아웃이 나타나면 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-189">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="7f509-190">**만료 안 하세요:** 다음 단계 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-190">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="7f509-191">설정이 꺼져 있는지 확인하고(토글 해제) 만료 날짜 상자를 사용하여 항목의 만료 ![ ](../../media/scc-toggle-off.png) 날짜를 지정합니다. </span><span class="sxs-lookup"><span data-stu-id="7f509-191">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

       <span data-ttu-id="7f509-192">또는</span><span class="sxs-lookup"><span data-stu-id="7f509-192">or</span></span>

     - <span data-ttu-id="7f509-193">토글을 오른쪽으로 이동하여 항목이 만료되지 않는 것으로 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-193">Move the toggle to the right to configure the entry to never expire:</span></span> ![토글 켬](../../media/scc-toggle-on.png)<span data-ttu-id="7f509-195">.</span><span class="sxs-lookup"><span data-stu-id="7f509-195">.</span></span>

   - <span data-ttu-id="7f509-196">**선택 사항:** 항목에 대한 설명 텍스트를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-196">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="7f509-197">작업을 마쳤으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-197">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-block-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="7f509-198">보안 및 & 센터를 사용하여 테넌트 허용/차단 목록에서 차단 항목 제거</span><span class="sxs-lookup"><span data-stu-id="7f509-198">Use the Security & Compliance Center to remove block entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="7f509-199">보안 및 & 센터에서 위협 **관리** 정책 \>  \> **테넌트 허용/차단 목록으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="7f509-199">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="7f509-200">URL **탭 또는** 파일 **탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-200">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="7f509-201">제거할 차단 항목을 선택한 다음 삭제 삭제 아이콘 **을** ![ ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-201">Select the block entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="7f509-202">나타나는 경고 대화 상자에서 삭제를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="7f509-202">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="7f509-203">Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell을 사용하여 테넌트 허용/차단 목록 구성</span><span class="sxs-lookup"><span data-stu-id="7f509-203">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-block-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="7f509-204">PowerShell을 사용하여 테넌트 허용/차단 목록에 차단 항목 추가</span><span class="sxs-lookup"><span data-stu-id="7f509-204">Use PowerShell to add block entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="7f509-205">테넌트 허용/차단 목록에서 차단 항목을 추가하기 위해 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="7f509-205">To add block entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <Url | FileHash> -Block -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="7f509-206">이 예제에서는 contoso.com, contoso.com, www.contoso.com 및 하위 xyz.abc.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="7f509-206">This example adds a block URL entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="7f509-207">ExpirationDate 또는 NoExpiration 매개 변수를 사용하지 않았기 때문에 항목이 30일 후에 만료됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-207">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

<span data-ttu-id="7f509-208">이 예제에서는 만료되지 않는 지정된 파일에 대한 차단 파일 항목을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-208">This example adds a block file entry for the specified files that never expires.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="7f509-209">구문과 매개 변수에 대한 자세한 내용은 [New-TenantAllowBlockListItems를 참조하십시오.](/powershell/module/exchange/new-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="7f509-209">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="7f509-210">PowerShell을 사용하여 테넌트 허용/차단 목록의 항목 보기</span><span class="sxs-lookup"><span data-stu-id="7f509-210">Use PowerShell to view entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="7f509-211">테넌트 허용/차단 목록의 항목을 표시하기 위해 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="7f509-211">To view entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <Url | FileHash> [-Entry <URLValue | FileHashValue>] [-Block] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="7f509-212">이 예제에서는 차단된 URL을 모두 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-212">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

<span data-ttu-id="7f509-213">이 예제에서는 지정한 파일 해시 값에 대한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-213">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="7f509-214">구문과 매개 변수에 대한 자세한 내용은 [Get-TenantAllowBlockListItems를 참조하십시오.](/powershell/module/exchange/get-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="7f509-214">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-block-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="7f509-215">PowerShell을 사용하여 테넌트 허용/차단 목록에서 차단 항목 수정</span><span class="sxs-lookup"><span data-stu-id="7f509-215">Use PowerShell to modify block entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="7f509-216">차단 항목 내에 있는 기존 URL 또는 파일 값은 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-216">You can't modify the existing URL or file values within a block entry.</span></span> <span data-ttu-id="7f509-217">이러한 값을 수정하려면 항목을 삭제하고 다시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-217">To modify these values, you need to delete and recreate the entry.</span></span>

<span data-ttu-id="7f509-218">테넌트 허용/차단 목록에서 차단 항목을 수정하려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="7f509-218">To modify block entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN"> [-Block] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="7f509-219">이 예제에서는 지정한 블록 항목의 만료 날짜를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-219">This example changes the expiration date of the specified block entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="7f509-220">구문과 매개 변수에 대한 자세한 내용은 [Set-TenantAllowBlockListItems를 참조하십시오.](/powershell/module/exchange/set-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="7f509-220">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-block-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="7f509-221">PowerShell을 사용하여 테넌트 허용/차단 목록에서 차단 항목 제거</span><span class="sxs-lookup"><span data-stu-id="7f509-221">Use PowerShell to remove block entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="7f509-222">테넌트 허용/차단 목록에서 차단 항목을 제거하려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="7f509-222">To remove block entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="7f509-223">이 예에서는 테넌트 허용/차단 목록에서 지정된 차단 URL 항목을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-223">This example removes the specified block URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="7f509-224">구문과 매개 변수에 대한 자세한 내용은 [Remove-TenantAllowBlockListItems를 참조하십시오.](/powershell/module/exchange/remove-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="7f509-224">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="7f509-225">테넌트 허용/차단 목록에 대한 URL 구문</span><span class="sxs-lookup"><span data-stu-id="7f509-225">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="7f509-226">IP4v 및 IPv6 주소는 사용할 수 있지만 TCP/UDP 포트는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-226">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="7f509-227">파일 이름 확장명은 허용되지 않습니다(예: test.pdf).</span><span class="sxs-lookup"><span data-stu-id="7f509-227">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="7f509-228">유니코드는 지원되지 않지만 Punycode는 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-228">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="7f509-229">다음 명령문이 모두 true이면 호스트 이름을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-229">Hostnames are allowed if all of the following statements are true:</span></span>
  - <span data-ttu-id="7f509-230">호스트 이름에는 기간이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-230">The hostname contains a period.</span></span>
  - <span data-ttu-id="7f509-231">기간 왼쪽에 하나 이상의 문자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-231">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="7f509-232">이 기간의 오른쪽에는 두 개 이상의 문자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-232">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="7f509-233">예를 들어 `t.co` 허용되거나 `.com` `contoso.` 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-233">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="7f509-234">하위 경로는 암시적이지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-234">Subpaths are not implied.</span></span>

  <span data-ttu-id="7f509-235">예를 들어 `contoso.com` 를 포함하지 `contoso.com/a` 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-235">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="7f509-236">와일드카드(\*)는 다음과 같은 시나리오에서 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-236">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="7f509-237">하위omain을 지정하려면 왼쪽 와일드카드 다음에 기간이 와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-237">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="7f509-238">예를 들어 `*.contoso.com` 허용됩니다. `*contoso.com` 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-238">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="7f509-239">오른쪽 와일드카드는 슬래시(/)를 따라 경로를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-239">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="7f509-240">예를 들어 `contoso.com/*` 허용되거나 `contoso.com*` `contoso.com/ab*` 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-240">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="7f509-241">모든 하위 경로는 올바른 와일드카드로 암시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-241">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="7f509-242">예를 들어 `contoso.com/*` 를 포함하지 `contoso.com/a` 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-242">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="7f509-243">`*.com*` 가 잘못되었습니다(확인 가능한 도메인이 아니며 오른쪽 와일드카드가 슬래시를 따르지 않습니다).</span><span class="sxs-lookup"><span data-stu-id="7f509-243">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="7f509-244">와일드카드는 IP 주소에서 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-244">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="7f509-245">다음 시나리오에서는 선조(~) 문자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-245">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="7f509-246">왼쪽 밀기선은 도메인과 모든 하위 도메인을 암시합니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-246">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="7f509-247">예를 들어 `~contoso.com` 및 `contoso.com` `*.contoso.com` 을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-247">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="7f509-248">URL 항목이 모든 프로토콜에 적용될 수 있기 때문에 프로토콜(예: , 또는 )이 포함된 URL 항목은 `http://` `https://` `ftp://` 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-248">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="7f509-249">사용자 이름 또는 암호는 지원되거나 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-249">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="7f509-250">따옴표(' 또는 ")는 잘못된 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-250">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="7f509-251">URL에는 가능한 경우 모든 리디렉션이 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-251">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="7f509-252">URL 입력 시나리오</span><span class="sxs-lookup"><span data-stu-id="7f509-252">URL entry scenarios</span></span>

<span data-ttu-id="7f509-253">유효한 URL 항목 및 해당 결과는 다음 섹션에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-253">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="7f509-254">시나리오: 와일드카드 없음</span><span class="sxs-lookup"><span data-stu-id="7f509-254">Scenario: No wildcards</span></span>

<span data-ttu-id="7f509-255">**항목**: `contoso.com`</span><span class="sxs-lookup"><span data-stu-id="7f509-255">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="7f509-256">**일치 허용**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="7f509-256">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="7f509-257">**일치하지 않는 허용**:</span><span class="sxs-lookup"><span data-stu-id="7f509-257">**Allow not matched**:</span></span>

  - <span data-ttu-id="7f509-258">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="7f509-258">abc-contoso.com</span></span>
  - <span data-ttu-id="7f509-259">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="7f509-259">contoso.com/a</span></span>
  - <span data-ttu-id="7f509-260">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7f509-260">payroll.contoso.com</span></span>
  - <span data-ttu-id="7f509-261">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="7f509-261">test.com/contoso.com</span></span>
  - <span data-ttu-id="7f509-262">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="7f509-262">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="7f509-263">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7f509-263">www.contoso.com</span></span>
  - <span data-ttu-id="7f509-264">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="7f509-264">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="7f509-265">**블록 일치**:</span><span class="sxs-lookup"><span data-stu-id="7f509-265">**Block match**:</span></span>

  - <span data-ttu-id="7f509-266">contoso.com</span><span class="sxs-lookup"><span data-stu-id="7f509-266">contoso.com</span></span>
  - <span data-ttu-id="7f509-267">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="7f509-267">contoso.com/a</span></span>
  - <span data-ttu-id="7f509-268">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7f509-268">payroll.contoso.com</span></span>
  - <span data-ttu-id="7f509-269">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="7f509-269">test.com/contoso.com</span></span>
  - <span data-ttu-id="7f509-270">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="7f509-270">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="7f509-271">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7f509-271">www.contoso.com</span></span>
  - <span data-ttu-id="7f509-272">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="7f509-272">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="7f509-273">**블록이 일치하지 않는 경우**: abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="7f509-273">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="7f509-274">시나리오: 왼쪽 와일드카드(하위omain)</span><span class="sxs-lookup"><span data-stu-id="7f509-274">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="7f509-275">**항목**: `*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="7f509-275">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="7f509-276">**일치 및** **차단 일치 허용**:</span><span class="sxs-lookup"><span data-stu-id="7f509-276">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="7f509-277">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7f509-277">www.contoso.com</span></span>
  - <span data-ttu-id="7f509-278">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7f509-278">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="7f509-279">**일치하지 않는 허용** 및 **차단이 일치하지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="7f509-279">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="7f509-280">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="7f509-280">123contoso.com</span></span>
  - <span data-ttu-id="7f509-281">contoso.com</span><span class="sxs-lookup"><span data-stu-id="7f509-281">contoso.com</span></span>
  - <span data-ttu-id="7f509-282">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="7f509-282">test.com/contoso.com</span></span>
  - <span data-ttu-id="7f509-283">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="7f509-283">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="7f509-284">시나리오: 경로 맨 위에 있는 오른쪽 와일드카드</span><span class="sxs-lookup"><span data-stu-id="7f509-284">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="7f509-285">**항목**: `contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="7f509-285">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="7f509-286">**일치 및** **차단 일치 허용**:</span><span class="sxs-lookup"><span data-stu-id="7f509-286">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="7f509-287">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="7f509-287">contoso.com/a/b</span></span>
  - <span data-ttu-id="7f509-288">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="7f509-288">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="7f509-289">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="7f509-289">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="7f509-290">**일치하지 않는 허용** 및 **차단이 일치하지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="7f509-290">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="7f509-291">contoso.com</span><span class="sxs-lookup"><span data-stu-id="7f509-291">contoso.com</span></span>
  - <span data-ttu-id="7f509-292">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="7f509-292">contoso.com/a</span></span>
  - <span data-ttu-id="7f509-293">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7f509-293">www.contoso.com</span></span>
  - <span data-ttu-id="7f509-294">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="7f509-294">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="7f509-295">시나리오: 왼쪽 밀기</span><span class="sxs-lookup"><span data-stu-id="7f509-295">Scenario: Left tilde</span></span>

<span data-ttu-id="7f509-296">**항목**: `~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="7f509-296">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="7f509-297">**일치 및** **차단 일치 허용**:</span><span class="sxs-lookup"><span data-stu-id="7f509-297">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="7f509-298">contoso.com</span><span class="sxs-lookup"><span data-stu-id="7f509-298">contoso.com</span></span>
  - <span data-ttu-id="7f509-299">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7f509-299">www.contoso.com</span></span>
  - <span data-ttu-id="7f509-300">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7f509-300">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="7f509-301">**일치하지 않는 허용** 및 **차단이 일치하지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="7f509-301">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="7f509-302">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="7f509-302">123contoso.com</span></span>
  - <span data-ttu-id="7f509-303">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="7f509-303">contoso.com/abc</span></span>
  - <span data-ttu-id="7f509-304">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="7f509-304">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="7f509-305">시나리오: 오른쪽 와일드카드 접미사</span><span class="sxs-lookup"><span data-stu-id="7f509-305">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="7f509-306">**항목**: `contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="7f509-306">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="7f509-307">**일치 및** **차단 일치 허용**:</span><span class="sxs-lookup"><span data-stu-id="7f509-307">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="7f509-308">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="7f509-308">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="7f509-309">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="7f509-309">contoso.com/a</span></span>
  - <span data-ttu-id="7f509-310">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="7f509-310">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="7f509-311">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="7f509-311">contoso.com/ab</span></span>
  - <span data-ttu-id="7f509-312">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="7f509-312">contoso.com/b</span></span>
  - <span data-ttu-id="7f509-313">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="7f509-313">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="7f509-314">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="7f509-314">contoso.com/ba</span></span>

- <span data-ttu-id="7f509-315">**일치하지 않는 허용** 및 **일치하지 않는** 차단 : contoso.com</span><span class="sxs-lookup"><span data-stu-id="7f509-315">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="7f509-316">시나리오: 왼쪽 와일드카드 하위omain 및 오른쪽 와일드카드 접미사</span><span class="sxs-lookup"><span data-stu-id="7f509-316">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="7f509-317">**항목**: `*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="7f509-317">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="7f509-318">**일치 및** **차단 일치 허용**:</span><span class="sxs-lookup"><span data-stu-id="7f509-318">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="7f509-319">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="7f509-319">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="7f509-320">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="7f509-320">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="7f509-321">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="7f509-321">www.contoso.com/a</span></span>
  - <span data-ttu-id="7f509-322">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="7f509-322">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="7f509-323">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="7f509-323">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="7f509-324">**일치하지 않는 허용** 및 **일치하지 않는** 차단 : contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="7f509-324">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="7f509-325">시나리오: 왼쪽 및 오른쪽 밀기</span><span class="sxs-lookup"><span data-stu-id="7f509-325">Scenario: Left and right tilde</span></span>

<span data-ttu-id="7f509-326">**항목**: `~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="7f509-326">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="7f509-327">**일치 및** **차단 일치 허용**:</span><span class="sxs-lookup"><span data-stu-id="7f509-327">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="7f509-328">contoso.com</span><span class="sxs-lookup"><span data-stu-id="7f509-328">contoso.com</span></span>
  - <span data-ttu-id="7f509-329">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="7f509-329">contoso.com/a</span></span>
  - <span data-ttu-id="7f509-330">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7f509-330">www.contoso.com</span></span>
  - <span data-ttu-id="7f509-331">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="7f509-331">www.contoso.com/b</span></span>
  - <span data-ttu-id="7f509-332">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7f509-332">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="7f509-333">**일치하지 않는 허용** 및 **차단이 일치하지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="7f509-333">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="7f509-334">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="7f509-334">123contoso.com</span></span>
  - <span data-ttu-id="7f509-335">contoso.org</span><span class="sxs-lookup"><span data-stu-id="7f509-335">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="7f509-336">시나리오: IP 주소</span><span class="sxs-lookup"><span data-stu-id="7f509-336">Scenario: IP address</span></span>

<span data-ttu-id="7f509-337">**항목**: `1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="7f509-337">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="7f509-338">**일치 및** **차단 일치** 허용 : 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="7f509-338">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="7f509-339">**일치하지 않는 허용** 및 **차단이 일치하지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="7f509-339">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="7f509-340">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="7f509-340">1.2.3.4/a</span></span>
  - <span data-ttu-id="7f509-341">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="7f509-341">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="7f509-342">오른쪽 와일드카드가 있는 IP 주소</span><span class="sxs-lookup"><span data-stu-id="7f509-342">IP address with right wildcard</span></span>

<span data-ttu-id="7f509-343">**항목**: `1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="7f509-343">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="7f509-344">**일치 및** **차단 일치 허용**:</span><span class="sxs-lookup"><span data-stu-id="7f509-344">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="7f509-345">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="7f509-345">1.2.3.4/b</span></span>
  - <span data-ttu-id="7f509-346">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="7f509-346">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="7f509-347">잘못된 항목의 예</span><span class="sxs-lookup"><span data-stu-id="7f509-347">Examples of invalid entries</span></span>

<span data-ttu-id="7f509-348">다음 항목이 잘못되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7f509-348">The following entries are invalid:</span></span>

- <span data-ttu-id="7f509-349">**누락되었거나 잘못된 도메인 값**:</span><span class="sxs-lookup"><span data-stu-id="7f509-349">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="7f509-350">contoso</span><span class="sxs-lookup"><span data-stu-id="7f509-350">contoso</span></span>
  - <span data-ttu-id="7f509-351">\*.contoso.\*</span><span class="sxs-lookup"><span data-stu-id="7f509-351">\*.contoso.\*</span></span>
  - <span data-ttu-id="7f509-352">\*.com</span><span class="sxs-lookup"><span data-stu-id="7f509-352">\*.com</span></span>
  - <span data-ttu-id="7f509-353">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="7f509-353">\*.pdf</span></span>

- <span data-ttu-id="7f509-354">**텍스트의 와일드카드 또는 간격 문자가 없는** 경우 :</span><span class="sxs-lookup"><span data-stu-id="7f509-354">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="7f509-355">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="7f509-355">\*contoso.com</span></span>
  - <span data-ttu-id="7f509-356">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="7f509-356">contoso.com\*</span></span>
  - <span data-ttu-id="7f509-357">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="7f509-357">\*1.2.3.4</span></span>
  - <span data-ttu-id="7f509-358">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="7f509-358">1.2.3.4\*</span></span>
  - <span data-ttu-id="7f509-359">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="7f509-359">contoso.com/a\*</span></span>
  - <span data-ttu-id="7f509-360">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="7f509-360">contoso.com/ab\*</span></span>

- <span data-ttu-id="7f509-361">**포트가 있는 IP 주소:**</span><span class="sxs-lookup"><span data-stu-id="7f509-361">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="7f509-362">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="7f509-362">contoso.com:443</span></span>
  - <span data-ttu-id="7f509-363">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="7f509-363">abc.contoso.com:25</span></span>

- <span data-ttu-id="7f509-364">**설명이 없는 와일드카드**:</span><span class="sxs-lookup"><span data-stu-id="7f509-364">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="7f509-365">\*.\*</span><span class="sxs-lookup"><span data-stu-id="7f509-365">\*.\*</span></span>

- <span data-ttu-id="7f509-366">**중간 와일드카드**:</span><span class="sxs-lookup"><span data-stu-id="7f509-366">**Middle wildcards**:</span></span>

  - <span data-ttu-id="7f509-367">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="7f509-367">conto\*so.com</span></span>
  - <span data-ttu-id="7f509-368">conto~so.com</span><span class="sxs-lookup"><span data-stu-id="7f509-368">conto~so.com</span></span>

- <span data-ttu-id="7f509-369">**이중 와일드카드**</span><span class="sxs-lookup"><span data-stu-id="7f509-369">**Double wildcards**</span></span>

  - <span data-ttu-id="7f509-370">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="7f509-370">contoso.com/\*\*</span></span>
  - <span data-ttu-id="7f509-371">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="7f509-371">contoso.com/\*/\*</span></span>
