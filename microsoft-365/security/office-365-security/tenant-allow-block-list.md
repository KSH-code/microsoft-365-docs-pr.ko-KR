---
title: 테 넌 트 허용/차단 목록에서 허용 및 차단 되는 Url 및 파일 관리
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 관리자는 보안 & 준수 센터의 테 넌 트 허용/차단 목록에서 URL 및 파일 항목을 구성 하는 방법을 알아봅니다.
ms.openlocfilehash: db34abf28b5ead8106eb0b1447052d63072b2da3
ms.sourcegitcommit: 41eb898143286755cd36df9f7e769de641263d73
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/23/2020
ms.locfileid: "45391569"
---
# <a name="manage-urls-and-files-in-the-tenant-allowblock-list"></a><span data-ttu-id="76311-103">테넌트 허용/차단 목록의 URL과 파일 관리</span><span class="sxs-lookup"><span data-stu-id="76311-103">Manage URLs and files in the Tenant Allow/Block List</span></span>

> [!NOTE]
> <span data-ttu-id="76311-104">이 항목에서 설명 하는 기능은 미리 보기에 있으며, 변경 될 수 있으며, 일부 조직에서는 제공 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="76311-104">The features described in this topic are in Preview, are subject to change, and are not available in all organizations.</span></span>

<span data-ttu-id="76311-105">Exchange online 사서함을 사용 하지 않는 exchange Online 또는 독립 실행형 EOP (Exchange Online Protection) 조직의 사서함이 있는 Microsoft 365 조직에서는 EOP 필터링 결과에 동의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="76311-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="76311-106">예를 들어 좋은 메시지는 불량 (가양성)으로 표시 되거나 잘못 된 메시지 (가양성)를 통해 허용 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76311-106">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="76311-107">보안 & 준수 센터의 테 넌 트 허용/차단 목록에서는 Microsoft 365 필터링 verdicts를 수동으로 다시 정의할 수 있는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="76311-107">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="76311-108">메일 흐름 중 및 사용자가 클릭 했을 때의 테 넌 트 허용/차단 목록이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="76311-108">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="76311-109">테 넌 트 허용/차단 목록에서 허용 하거나 차단할 Url 및 파일을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76311-109">You can specify URLs and files to allow or block in the Tenant Allow/Block List.</span></span>

<span data-ttu-id="76311-110">이 항목에서는 보안 & 준수 센터 또는 PowerShell (exchange online 사서함이 없는 조직에 대해 exchange Online의 사서함이 있는 Microsoft 365 조 직의 경우 Exchange online PowerShell)의 테 넌 트 허용/차단 목록에서 항목을 구성 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="76311-110">This topic describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="76311-111">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="76311-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="76311-112"><https://protection.office.com/>에서 보안 및 준수 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="76311-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="76311-113">**테 넌 트 허용/차단 목록** 페이지로 바로 이동 하려면를 사용 <https://protection.office.com/tenantAllowBlockList> 합니다.</span><span class="sxs-lookup"><span data-stu-id="76311-113">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="76311-114">파일의 SHA256 해시 값을 사용 하 여 파일을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="76311-114">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="76311-115">Windows에서 파일의 SHA256 해시 값을 찾으려면 명령 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="76311-115">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```dos
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="76311-116">예를 들면 값은 `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` 입니다.</span><span class="sxs-lookup"><span data-stu-id="76311-116">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="76311-117">PHash (가시 범위 해시) 값은 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="76311-117">Perceptual hash (pHash) values are not allowed.</span></span>

- <span data-ttu-id="76311-118">사용 가능한 URL 값은이 항목 뒷부분의 [테 넌 트 허용/차단 목록 섹션에 대 한 URL 구문](#url-syntax-for-the-tenant-allowblock-list) 에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76311-118">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

- <span data-ttu-id="76311-119">테 넌 트 허용/차단 목록에서 Url에 대해 최대 500 항목을 허용 하 고 파일 해시에 대해 500 항목을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76311-119">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="76311-120">15 분 내에 항목을 활성화 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76311-120">An entry should be active within 15 minutes.</span></span>

- <span data-ttu-id="76311-121">차단 항목은 허용 항목 보다 우선적으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="76311-121">Block entries take precedence over allow entries.</span></span>

- <span data-ttu-id="76311-122">기본적으로 테 넌 트 허용/차단 목록의 항목은 30 일 후에 만료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="76311-122">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="76311-123">날짜를 지정 하거나 만료 되지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76311-123">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="76311-124">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="76311-124">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="76311-125">독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="76311-125">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="76311-126">이 항목의 절차를 수행하려면 먼저 사용 권한을 할당받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76311-126">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="76311-127">테 넌 트 허용/차단 목록에서 값을 추가 및 제거 하려면 다음 역할 그룹 중 하나의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76311-127">To add and remove values from the Tenant Allow/Block List, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="76311-128">[보안 및 준수 센터](permissions-in-the-security-and-compliance-center.md)의 **조직 관리** 또는 **보안 관리자**</span><span class="sxs-lookup"><span data-stu-id="76311-128">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="76311-129">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **조직 관리** 및 **예방 조치 관리**</span><span class="sxs-lookup"><span data-stu-id="76311-129">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="76311-130">테 넌 트 허용/차단 목록에 대 한 읽기 전용 액세스를 위해서는 다음 역할 그룹 중 하나의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76311-130">For read-only access to the Tenant Allow/Block List, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="76311-131">[보안 및 준수 센터](permissions-in-the-security-and-compliance-center.md)의 **보안 읽기**</span><span class="sxs-lookup"><span data-stu-id="76311-131">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="76311-132">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **보기 전용 조직 관리**</span><span class="sxs-lookup"><span data-stu-id="76311-132">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="76311-133">보안 & 준수 센터를 사용 하 여 테 넌 트 허용/차단 목록에 URL 항목 만들기</span><span class="sxs-lookup"><span data-stu-id="76311-133">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="76311-134">URL 항목의 구문에 대 한 자세한 내용은이 항목 뒷부분의 [테 넌 트 허용/차단 목록 섹션에 대 한 URL 구문을](#url-syntax-for-the-tenant-allowblock-list) 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="76311-134">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

1. <span data-ttu-id="76311-135">보안 & 준수 센터에서 **위협 관리** \> **정책** \> **테 넌 트 허용/차단 목록**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="76311-135">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="76311-136">**테 넌 트 허용/차단 목록** 페이지에서 **url** 탭이 선택 되어 있는지 확인 한 다음 **추가** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="76311-136">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Add**</span></span>

3. <span data-ttu-id="76311-137">**새 Url 추가** 플라이 아웃이 나타나면 다음 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="76311-137">In the **Add new URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="76311-138">**와일드 카드를 사용 하 여 Url 추가**: 한 줄당 url을 하나씩 입력 합니다 (최대 20 개).</span><span class="sxs-lookup"><span data-stu-id="76311-138">**Add URLs with wildcards**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="76311-139">**차단/허용**: 지정 된 Url을 **허용** 하거나 **차단할지** 여부를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="76311-139">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified URLs.</span></span>

   - <span data-ttu-id="76311-140">사용 **기간 제한 없음**: 다음 단계 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="76311-140">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="76311-141">설정이 꺼져 있는지 ( ![ 토글 해제)를 확인 하 ](../../media/scc-toggle-off.png) 고 **만료** 날짜 상자를 사용 하 여 항목의 만료일을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="76311-141">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="76311-142">또는</span><span class="sxs-lookup"><span data-stu-id="76311-142">or</span></span>

     - <span data-ttu-id="76311-143">오른쪽으로 토글을 이동 하 여 만료 되지 않도록 항목을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="76311-143">Move the toggle to the right to configure the entries to never expire:</span></span> ![토글 켬](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="76311-145">.</span><span class="sxs-lookup"><span data-stu-id="76311-145">.</span></span>

   - <span data-ttu-id="76311-146">**선택 사항**: 항목에 대 한 설명 텍스트를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="76311-146">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="76311-147">작업이 완료 되 면 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="76311-147">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="76311-148">보안 & 준수 센터를 사용 하 여 테 넌 트 허용/차단 목록에 파일 항목 만들기</span><span class="sxs-lookup"><span data-stu-id="76311-148">Use the Security & Compliance Center to create file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="76311-149">보안 & 준수 센터에서 **위협 관리** \> **정책** \> **테 넌 트 허용/차단 목록**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="76311-149">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="76311-150">**테 넌 트 허용/차단 목록** 페이지에서 **파일** 탭을 선택 하 고 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="76311-150">On the **Tenant Allow/Block List** page, select **Files** tab, and then click **Add**.</span></span>

3. <span data-ttu-id="76311-151">**새 파일** 플라이 아웃 추가 표시 되 면 다음 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="76311-151">In the **Add new files** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="76311-152">**파일 해시 추가**: 줄당 최대 20 개까지 한 줄에 하나씩 SHA256 해시 값을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="76311-152">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="76311-153">**차단/허용**: 지정 된 파일을 **허용할지** 아니면 **차단할지** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="76311-153">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified files.</span></span>

   - <span data-ttu-id="76311-154">사용 **기간 제한 없음**: 다음 단계 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="76311-154">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="76311-155">설정이 꺼져 있는지 ( ![ 토글 해제)를 확인 하 ](../../media/scc-toggle-off.png) 고 **만료** 날짜 상자를 사용 하 여 항목의 만료일을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="76311-155">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="76311-156">또는</span><span class="sxs-lookup"><span data-stu-id="76311-156">or</span></span>

     - <span data-ttu-id="76311-157">오른쪽으로 토글을 이동 하 여 만료 되지 않도록 항목을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="76311-157">Move the toggle to the right to configure the entries to never expire:</span></span> ![토글 켬](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="76311-159">.</span><span class="sxs-lookup"><span data-stu-id="76311-159">.</span></span>

   - <span data-ttu-id="76311-160">**선택 사항**: 항목에 대 한 설명 텍스트를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="76311-160">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="76311-161">작업이 완료 되 면 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="76311-161">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="76311-162">보안 & 준수 센터를 사용 하 여 테 넌 트 허용/차단 목록의 URL 및 파일 항목 보기</span><span class="sxs-lookup"><span data-stu-id="76311-162">Use the Security & Compliance Center to view URL and file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="76311-163">보안 & 준수 센터에서 **위협 관리** \> **정책** \> **테 넌 트 허용/차단 목록**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="76311-163">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="76311-164">**Url** 탭 또는 **파일** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="76311-164">Select the **URLs** tab or the **Files** tab.</span></span>

<span data-ttu-id="76311-165">다음 열 머리글을 클릭 하 여 오름차순 또는 내림차순으로 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="76311-165">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="76311-166">**값**: URL 또는 파일 해시입니다.</span><span class="sxs-lookup"><span data-stu-id="76311-166">**Value**: The URL or the file hash.</span></span>
- <span data-ttu-id="76311-167">**작업**: **차단** 또는 **허용**합니다.</span><span class="sxs-lookup"><span data-stu-id="76311-167">**Action**: **Block** or **Allow**.</span></span>
- <span data-ttu-id="76311-168">**마지막 업데이트 날짜**</span><span class="sxs-lookup"><span data-stu-id="76311-168">**Last updated date**</span></span>
- <span data-ttu-id="76311-169">**만료 날짜**</span><span class="sxs-lookup"><span data-stu-id="76311-169">**Expiration date**</span></span>
- <span data-ttu-id="76311-170">**참고**</span><span class="sxs-lookup"><span data-stu-id="76311-170">**Note**</span></span>

<span data-ttu-id="76311-171">**그룹** 을 클릭 하 여 **작업** (**차단** 또는 **허용**)을 기준으로 항목을 그룹화 하거나 **아무 것도**선택 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="76311-171">Click **Group** to group the entries by **Action** (**Block** or **Allow**) or **None**.</span></span>

<span data-ttu-id="76311-172">**검색**을 클릭 하 고 URL 또는 파일 값의 일부나 전체를 입력 한 다음 enter 키를 눌러 특정 값을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="76311-172">Click **Search**, enter all or part of a URL or file value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="76311-173">작업이 끝나면 검색 지우기 검색 아이콘 **을 클릭** ![ ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) 합니다.</span><span class="sxs-lookup"><span data-stu-id="76311-173">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="76311-174">**필터**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="76311-174">Click **Filter**.</span></span> <span data-ttu-id="76311-175">**필터** 플라이 아웃이 나타나면 다음 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="76311-175">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="76311-176">**작업**: **Allow**, **Block** 또는 both를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="76311-176">**Action**: Select **Allow**, **Block** or both.</span></span>

- <span data-ttu-id="76311-177">사용 **기간 제한 없음**: 해제 (설정 ![ /해제 ](../../media/scc-toggle-off.png) ) 또는 설정 ( ![ 토글 켜기)을 선택 ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) 합니다.</span><span class="sxs-lookup"><span data-stu-id="76311-177">**Never expire**: Select off (![Toggle off](../../media/scc-toggle-off.png)) or on (![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)).</span></span>

- <span data-ttu-id="76311-178">**마지막 업데이트**: 시작 날짜 (**원본**), 종료 날짜 (**대상**) 또는 두 가지 모두를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="76311-178">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="76311-179">**만료 날짜**: 시작 날짜 (**From**), 종료 날짜 (**대상**) 또는 둘 다를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="76311-179">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="76311-180">작업이 완료 되 면 **적용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="76311-180">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="76311-181">기존 필터를 지우려면 **필터**를 클릭 하 고 **필터** 플라이 아웃이 나타나면 **필터 해제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="76311-181">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="76311-182">보안 & 준수 센터를 사용 하 여 테 넌 트 허용/차단 목록의 URL 및 파일 항목 수정</span><span class="sxs-lookup"><span data-stu-id="76311-182">Use the Security & Compliance Center to modify URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="76311-183">URL 또는 파일 값 자체는 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="76311-183">You can't modify the URL or file value itself.</span></span> <span data-ttu-id="76311-184">대신 항목을 삭제 하 고 다시 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76311-184">Instead, you need to delete the entry and recreate it.</span></span>

1. <span data-ttu-id="76311-185">보안 & 준수 센터에서 **위협 관리** \> **정책** \> **테 넌 트 허용/차단 목록**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="76311-185">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="76311-186">**Url** 탭 또는 **파일** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="76311-186">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="76311-187">수정 하려는 항목을 선택 하 고 편집 아이콘 편집을 클릭 **Edit** ![ ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) 합니다.</span><span class="sxs-lookup"><span data-stu-id="76311-187">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="76311-188">플라이 아웃이 나타나면 다음 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="76311-188">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="76311-189">**차단/허용**: **허용** 또는 **차단**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="76311-189">**Block/Allow**: Select **Allow** or **Block**.</span></span>

   - <span data-ttu-id="76311-190">사용 **기간 제한 없음**: 다음 단계 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="76311-190">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="76311-191">설정이 꺼져 있는지 ( ![ 토글 해제)를 확인 하 ](../../media/scc-toggle-off.png) 고 **만료** 날짜 상자를 사용 하 여 항목의 만료일을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="76311-191">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

     <span data-ttu-id="76311-192">또는</span><span class="sxs-lookup"><span data-stu-id="76311-192">or</span></span>

     - <span data-ttu-id="76311-193">오른쪽으로 토글을 이동 하 여 항목이 만료 되지 않도록 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="76311-193">Move the toggle to the right to configure the entry to never expire:</span></span> ![토글 켬](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="76311-195">.</span><span class="sxs-lookup"><span data-stu-id="76311-195">.</span></span>

   - <span data-ttu-id="76311-196">**선택 사항**: 항목에 대 한 설명 텍스트를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="76311-196">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="76311-197">작업을 마쳤으면 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="76311-197">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-url-and-file-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="76311-198">보안 & 준수 센터를 사용 하 여 테 넌 트 허용/차단 목록에서 URL 및 파일 항목 제거</span><span class="sxs-lookup"><span data-stu-id="76311-198">Use the Security & Compliance Center to remove URL and file entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="76311-199">보안 & 준수 센터에서 **위협 관리** \> **정책** \> **테 넌 트 허용/차단 목록**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="76311-199">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="76311-200">**Url** 탭 또는 **파일** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="76311-200">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="76311-201">제거할 항목을 선택한 다음 삭제 아이콘 **삭제** 를 클릭 ![ ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) 합니다.</span><span class="sxs-lookup"><span data-stu-id="76311-201">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="76311-202">경고 대화 상자가 나타나면 **삭제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="76311-202">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="76311-203">Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell을 사용 하 여 테 넌 트 허용/차단 목록을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="76311-203">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="76311-204">PowerShell을 사용 하 여 테 넌 트 허용/차단 목록에 URL 및 파일 항목 추가</span><span class="sxs-lookup"><span data-stu-id="76311-204">Use PowerShell to add URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="76311-205">테 넌 트 허용/차단 목록에 URL 및 파일 항목을 추가 하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="76311-205">To add URL and file entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <Url | FileHash> -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="76311-206">이 예에서는 contoso.com 및 모든 하위 도메인 (예: contoso.com, www.contoso.com 및 xyz.abc.contoso.com)에 대 한 URL 블록 항목을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="76311-206">This example adds a URL block entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="76311-207">ExpirationDate 또는 NoExpiration 매개 변수를 사용 하지 않았으므로 30 일 후에 항목이 만료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="76311-207">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Action Allow -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="76311-208">이 예에서는 지정 된 파일에 대해 만료 되지 않는 파일을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="76311-208">This example adds a file allow entry for the specified files that never expires.</span></span>

<span data-ttu-id="76311-209">구문과 매개 변수에 대 한 자세한 내용은 [TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="76311-209">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="76311-210">PowerShell을 사용 하 여 테 넌 트 허용/차단 목록에서 URL 및 파일 항목 보기</span><span class="sxs-lookup"><span data-stu-id="76311-210">Use PowerShell to view URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="76311-211">테 넌 트 허용/차단 목록에서 URL 및 파일 항목을 보려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="76311-211">To view URL and file entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <Url | FileHash> [-Entry <URLValue | FileHashValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="76311-212">이 예에서는 차단 된 모든 Url을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="76311-212">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

<span data-ttu-id="76311-213">이 예제에서는 지정 된 파일 해시 값에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="76311-213">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="76311-214">구문과 매개 변수에 대 한 자세한 내용은 [TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="76311-214">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="76311-215">PowerShell을 사용 하 여 테 넌 트 허용/차단 목록에서 URL 및 파일 항목 수정</span><span class="sxs-lookup"><span data-stu-id="76311-215">Use PowerShell to modify URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="76311-216">URL 또는 파일 값 자체는 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="76311-216">You can't modify the URL or file value itself.</span></span> <span data-ttu-id="76311-217">대신 항목을 삭제 하 고 다시 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76311-217">Instead, you need to delete the entry and recreate it.</span></span>

<span data-ttu-id="76311-218">테 넌 트 허용/차단 목록에서 URL 및 파일 항목을 수정 하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="76311-218">To modify URL and file entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="76311-219">다음은 지정 된 항목의 만료 날짜를 변경 하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="76311-219">This example changes the expiration date of the specified entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="76311-220">구문 및 매개 변수에 대 한 자세한 내용은 [TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="76311-220">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-url-and-file-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="76311-221">PowerShell을 사용 하 여 테 넌 트 허용/차단 목록에서 URL 및 파일 항목 제거</span><span class="sxs-lookup"><span data-stu-id="76311-221">Use PowerShell to remove URL and file entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="76311-222">테 넌 트 허용/차단 목록에서 URL 및 파일 항목을 제거 하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="76311-222">To remove URL and file entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="76311-223">이 예에서는 테 넌 트 허용/차단 목록에서 지정 된 URL 항목을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="76311-223">This example removes the specified URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="76311-224">구문과 매개 변수에 대 한 자세한 내용은 [TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="76311-224">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="76311-225">테 넌 트 허용/차단 목록에 대 한 URL 구문</span><span class="sxs-lookup"><span data-stu-id="76311-225">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="76311-226">IP4v 및 IPv6 주소를 사용할 수 있지만 TCP/UDP 포트는 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="76311-226">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="76311-227">파일 이름 확장명은 허용 되지 않습니다 (예: test.pdf).</span><span class="sxs-lookup"><span data-stu-id="76311-227">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="76311-228">유니코드는 지원 되지 않지만, Punycode는입니다.</span><span class="sxs-lookup"><span data-stu-id="76311-228">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="76311-229">다음의 모든 조건에 해당 하는 경우에는 호스트 이름이 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="76311-229">Hostnames are allowed if all of the following statements are true:</span></span>

  - <span data-ttu-id="76311-230">호스트 이름에 마침표가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76311-230">The hostname contains a period.</span></span>
  - <span data-ttu-id="76311-231">마침표 왼쪽에 문자가 하나 이상 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76311-231">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="76311-232">마침표 오른쪽에 2 개 이상의 문자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76311-232">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="76311-233">예를 들어, `t.co` 허용 `.com` 되지 않거나 `contoso.` 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="76311-233">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="76311-234">하위 경로는 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="76311-234">Subpaths are not implied.</span></span>

  <span data-ttu-id="76311-235">예를 들어에 `contoso.com` 는가 포함 되지 않습니다 `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="76311-235">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="76311-236">다음과 같은 시나리오에서는 와일드 카드 (\*)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76311-236">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="76311-237">하위 도메인을 지정 하려면 left 와일드 카드 다음에 마침표가와 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76311-237">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="76311-238">예를 들어, 허용 `*.contoso.com` `*contoso.com` 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="76311-238">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="76311-239">경로를 지정 하려면 오른쪽 와일드 카드는 슬래시 (/) 다음에와 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76311-239">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="76311-240">예를 들어, `contoso.com/*` 허용 `contoso.com*` 되지 않거나 `contoso.com/ab*` 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="76311-240">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="76311-241">모든 서브 경로는 오른쪽 와일드 카드에서 암시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="76311-241">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="76311-242">예를 들어에 `contoso.com/*` 는가 포함 되지 않습니다 `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="76311-242">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="76311-243">`*.com*`잘못 되었습니다 (확인할 수 있는 도메인이 아님, 올바른 와일드 카드가 슬래시 다음에 없음).</span><span class="sxs-lookup"><span data-stu-id="76311-243">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="76311-244">IP 주소에는 와일드 카드를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="76311-244">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="76311-245">물결표 (~) 문자는 다음과 같은 시나리오에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76311-245">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="76311-246">왼쪽 물결표는 도메인과 모든 하위 도메인을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="76311-246">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="76311-247">예를 `~contoso.com` 들어 `contoso.com` and를 포함 `*.contoso.com` 합니다.</span><span class="sxs-lookup"><span data-stu-id="76311-247">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="76311-248">`http://` `https://` `ftp://` Url 항목은 모든 프로토콜에 적용 되므로 프로토콜 (예:, 또는)을 포함 하는 url 항목은 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="76311-248">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="76311-249">사용자 이름 또는 암호는 지원 되지 않거나 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="76311-249">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="76311-250">따옴표 (' 또는 ")는 잘못 된 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="76311-250">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="76311-251">URL에는 가능한 모든 리디렉션이 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76311-251">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="76311-252">URL 입력 시나리오</span><span class="sxs-lookup"><span data-stu-id="76311-252">URL entry scenarios</span></span>

<span data-ttu-id="76311-253">유효한 URL 항목 및 결과는 다음 섹션에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76311-253">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="76311-254">시나리오: 와일드 카드 없음</span><span class="sxs-lookup"><span data-stu-id="76311-254">Scenario: No wildcards</span></span>

<span data-ttu-id="76311-255">**항목**:`contoso.com`</span><span class="sxs-lookup"><span data-stu-id="76311-255">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="76311-256">**일치 허용**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="76311-256">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="76311-257">**일치 하지 않는 항목 허용**:</span><span class="sxs-lookup"><span data-stu-id="76311-257">**Allow not matched**:</span></span>

  - <span data-ttu-id="76311-258">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="76311-258">abc-contoso.com</span></span>
  - <span data-ttu-id="76311-259">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="76311-259">contoso.com/a</span></span>
  - <span data-ttu-id="76311-260">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="76311-260">payroll.contoso.com</span></span>
  - <span data-ttu-id="76311-261">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="76311-261">test.com/contoso.com</span></span>
  - <span data-ttu-id="76311-262">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="76311-262">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="76311-263">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="76311-263">www.contoso.com</span></span>
  - <span data-ttu-id="76311-264">www. .com/q = a@contoso</span><span class="sxs-lookup"><span data-stu-id="76311-264">www.contoso.com/q=a@contoso.com</span></span>
  
- <span data-ttu-id="76311-265">**일치 블록**:</span><span class="sxs-lookup"><span data-stu-id="76311-265">**Block match**:</span></span>

  - <span data-ttu-id="76311-266">contoso.com</span><span class="sxs-lookup"><span data-stu-id="76311-266">contoso.com</span></span>
  - <span data-ttu-id="76311-267">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="76311-267">contoso.com/a</span></span>
  - <span data-ttu-id="76311-268">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="76311-268">payroll.contoso.com</span></span>
  - <span data-ttu-id="76311-269">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="76311-269">test.com/contoso.com</span></span>
  - <span data-ttu-id="76311-270">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="76311-270">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="76311-271">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="76311-271">www.contoso.com</span></span>
  - <span data-ttu-id="76311-272">www. .com/q = a@contoso</span><span class="sxs-lookup"><span data-stu-id="76311-272">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="76311-273">**일치 하지 않는 블록**: abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="76311-273">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="76311-274">시나리오: Left 와일드 카드 (하위 도메인)</span><span class="sxs-lookup"><span data-stu-id="76311-274">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="76311-275">**항목**:`*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="76311-275">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="76311-276">**일치 허용** 및 **일치 차단**:</span><span class="sxs-lookup"><span data-stu-id="76311-276">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="76311-277">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="76311-277">www.contoso.com</span></span>
  - <span data-ttu-id="76311-278">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="76311-278">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="76311-279">**일치 하지 않는** 항목과 **일치**하는 블록 허용:</span><span class="sxs-lookup"><span data-stu-id="76311-279">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="76311-280">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="76311-280">123contoso.com</span></span>
  - <span data-ttu-id="76311-281">contoso.com</span><span class="sxs-lookup"><span data-stu-id="76311-281">contoso.com</span></span>
  - <span data-ttu-id="76311-282">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="76311-282">test.com/contoso.com</span></span>
  - <span data-ttu-id="76311-283">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="76311-283">www.contoso.com/abc</span></span>
  
#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="76311-284">시나리오: 경로 맨 위의 오른쪽 와일드 카드</span><span class="sxs-lookup"><span data-stu-id="76311-284">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="76311-285">**항목**:`contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="76311-285">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="76311-286">**일치 허용** 및 **일치 차단**:</span><span class="sxs-lookup"><span data-stu-id="76311-286">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="76311-287">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="76311-287">contoso.com/a/b</span></span>
  - <span data-ttu-id="76311-288">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="76311-288">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="76311-289">contoso/a/? q = joe@t .com</span><span class="sxs-lookup"><span data-stu-id="76311-289">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="76311-290">**일치 하지 않는** 항목과 **일치**하는 블록 허용:</span><span class="sxs-lookup"><span data-stu-id="76311-290">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="76311-291">contoso.com</span><span class="sxs-lookup"><span data-stu-id="76311-291">contoso.com</span></span>
  - <span data-ttu-id="76311-292">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="76311-292">contoso.com/a</span></span>
  - <span data-ttu-id="76311-293">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="76311-293">www.contoso.com</span></span>
  - <span data-ttu-id="76311-294">www. .com/q = a@contoso</span><span class="sxs-lookup"><span data-stu-id="76311-294">www.contoso.com/q=a@contoso.com</span></span>
  
#### <a name="scenario-left-tilde"></a><span data-ttu-id="76311-295">시나리오: 왼쪽 물결표</span><span class="sxs-lookup"><span data-stu-id="76311-295">Scenario: Left tilde</span></span>

<span data-ttu-id="76311-296">**항목**:`~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="76311-296">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="76311-297">**일치 허용** 및 **일치 차단**:</span><span class="sxs-lookup"><span data-stu-id="76311-297">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="76311-298">contoso.com</span><span class="sxs-lookup"><span data-stu-id="76311-298">contoso.com</span></span>
  - <span data-ttu-id="76311-299">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="76311-299">www.contoso.com</span></span>
  - <span data-ttu-id="76311-300">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="76311-300">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="76311-301">**일치 하지 않는** 항목과 **일치**하는 블록 허용:</span><span class="sxs-lookup"><span data-stu-id="76311-301">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="76311-302">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="76311-302">123contoso.com</span></span>
  - <span data-ttu-id="76311-303">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="76311-303">contoso.com/abc</span></span>
  - <span data-ttu-id="76311-304">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="76311-304">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="76311-305">시나리오: 오른쪽 와일드 카드 접미사</span><span class="sxs-lookup"><span data-stu-id="76311-305">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="76311-306">**항목**:`contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="76311-306">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="76311-307">**일치 허용** 및 **일치 차단**:</span><span class="sxs-lookup"><span data-stu-id="76311-307">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="76311-308">contoso/? q = whatever@fabrikam</span><span class="sxs-lookup"><span data-stu-id="76311-308">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="76311-309">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="76311-309">contoso.com/a</span></span>
  - <span data-ttu-id="76311-310">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="76311-310">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="76311-311">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="76311-311">contoso.com/ab</span></span>
  - <span data-ttu-id="76311-312">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="76311-312">contoso.com/b</span></span>
  - <span data-ttu-id="76311-313">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="76311-313">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="76311-314">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="76311-314">contoso.com/ba</span></span>

- <span data-ttu-id="76311-315">**일치 하지 않음** 및 **일치**하는 블록 허용: contoso.com</span><span class="sxs-lookup"><span data-stu-id="76311-315">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="76311-316">시나리오: Left 와일드 카드 하위 도메인 및 오른쪽 와일드 카드 접미사</span><span class="sxs-lookup"><span data-stu-id="76311-316">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="76311-317">**항목**:`*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="76311-317">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="76311-318">**일치 허용** 및 **일치 차단**:</span><span class="sxs-lookup"><span data-stu-id="76311-318">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="76311-319">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="76311-319">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="76311-320">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="76311-320">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="76311-321">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="76311-321">www.contoso.com/a</span></span>
  - <span data-ttu-id="76311-322">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="76311-322">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="76311-323">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="76311-323">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="76311-324">**일치 하지 않음** 및 **일치**하는 블록 허용: contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="76311-324">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="76311-325">시나리오: 왼쪽과 오른쪽 물결표</span><span class="sxs-lookup"><span data-stu-id="76311-325">Scenario: Left and right tilde</span></span>

<span data-ttu-id="76311-326">**항목**:`~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="76311-326">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="76311-327">**일치 허용** 및 **일치 차단**:</span><span class="sxs-lookup"><span data-stu-id="76311-327">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="76311-328">contoso.com</span><span class="sxs-lookup"><span data-stu-id="76311-328">contoso.com</span></span>
  - <span data-ttu-id="76311-329">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="76311-329">contoso.com/a</span></span>
  - <span data-ttu-id="76311-330">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="76311-330">www.contoso.com</span></span>
  - <span data-ttu-id="76311-331">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="76311-331">www.contoso.com/b</span></span>
  - <span data-ttu-id="76311-332">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="76311-332">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="76311-333">**일치 하지 않는** 항목과 **일치**하는 블록 허용:</span><span class="sxs-lookup"><span data-stu-id="76311-333">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="76311-334">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="76311-334">123contoso.com</span></span>
  - <span data-ttu-id="76311-335">contoso.org</span><span class="sxs-lookup"><span data-stu-id="76311-335">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="76311-336">시나리오: IP 주소</span><span class="sxs-lookup"><span data-stu-id="76311-336">Scenario: IP address</span></span>

<span data-ttu-id="76311-337">**항목**:`1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="76311-337">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="76311-338">**일치 허용** 및 **일치 차단**: 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="76311-338">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="76311-339">**일치 하지 않는** 항목과 **일치**하는 블록 허용:</span><span class="sxs-lookup"><span data-stu-id="76311-339">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="76311-340">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="76311-340">1.2.3.4/a</span></span>
  - <span data-ttu-id="76311-341">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="76311-341">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="76311-342">오른쪽 와일드 카드를 사용한 IP 주소</span><span class="sxs-lookup"><span data-stu-id="76311-342">IP address with right wildcard</span></span>

<span data-ttu-id="76311-343">**항목**:`1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="76311-343">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="76311-344">**일치 허용** 및 **일치 차단**:</span><span class="sxs-lookup"><span data-stu-id="76311-344">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="76311-345">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="76311-345">1.2.3.4/b</span></span>
  - <span data-ttu-id="76311-346">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="76311-346">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="76311-347">잘못 된 항목의 예</span><span class="sxs-lookup"><span data-stu-id="76311-347">Examples of invalid entries</span></span>

<span data-ttu-id="76311-348">다음 항목은 유효 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="76311-348">The following entries are invalid:</span></span>

- <span data-ttu-id="76311-349">**누락 되었거나 잘못 된 도메인 값**:</span><span class="sxs-lookup"><span data-stu-id="76311-349">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="76311-350">극동</span><span class="sxs-lookup"><span data-stu-id="76311-350">contoso</span></span>
  - <span data-ttu-id="76311-351">\*극동.\*</span><span class="sxs-lookup"><span data-stu-id="76311-351">\*.contoso.\*</span></span>
  - <span data-ttu-id="76311-352">\*.com</span><span class="sxs-lookup"><span data-stu-id="76311-352">\*.com</span></span>
  - <span data-ttu-id="76311-353">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="76311-353">\*.pdf</span></span>

- <span data-ttu-id="76311-354">**텍스트에 와일드 카드 사용 또는 공백 문자 없는**경우:</span><span class="sxs-lookup"><span data-stu-id="76311-354">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="76311-355">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="76311-355">\*contoso.com</span></span>
  - <span data-ttu-id="76311-356">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="76311-356">contoso.com\*</span></span>
  - <span data-ttu-id="76311-357">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="76311-357">\*1.2.3.4</span></span>
  - <span data-ttu-id="76311-358">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="76311-358">1.2.3.4\*</span></span>
  - <span data-ttu-id="76311-359">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="76311-359">contoso.com/a\*</span></span>
  - <span data-ttu-id="76311-360">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="76311-360">contoso.com/ab\*</span></span>

- <span data-ttu-id="76311-361">**포트를 포함 하는 IP 주소**:</span><span class="sxs-lookup"><span data-stu-id="76311-361">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="76311-362">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="76311-362">contoso.com:443</span></span>
  - <span data-ttu-id="76311-363">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="76311-363">abc.contoso.com:25</span></span>

- <span data-ttu-id="76311-364">**설명적이 아닌 와일드 카드**:</span><span class="sxs-lookup"><span data-stu-id="76311-364">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="76311-365">\*.\*</span><span class="sxs-lookup"><span data-stu-id="76311-365">\*.\*</span></span>

- <span data-ttu-id="76311-366">**중간 와일드 카드**:</span><span class="sxs-lookup"><span data-stu-id="76311-366">**Middle wildcards**:</span></span>

  - <span data-ttu-id="76311-367">\*so.com</span><span class="sxs-lookup"><span data-stu-id="76311-367">conto\*so.com</span></span>
  - <span data-ttu-id="76311-368">~ ~ .com</span><span class="sxs-lookup"><span data-stu-id="76311-368">conto~so.com</span></span>

- <span data-ttu-id="76311-369">**이중 와일드 카드**</span><span class="sxs-lookup"><span data-stu-id="76311-369">**Double wildcards**</span></span>

  - <span data-ttu-id="76311-370">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="76311-370">contoso.com/\*\*</span></span>
  - <span data-ttu-id="76311-371">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="76311-371">contoso.com/\*/\*</span></span>
