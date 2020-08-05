---
title: 테 넌 트 허용/차단 목록에서 허용 및 차단 된 Url 관리
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
description: 관리자는 보안 & 준수 센터의 테 넌 트 허용/차단 목록에서 URL 항목을 구성 하는 방법을 확인할 수 있습니다.
ms.openlocfilehash: 5ff34cca922f18a015bd9da847facc8177cf8790
ms.sourcegitcommit: 89178b8f20d59ca88cfca303a13062b91fbeae9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/04/2020
ms.locfileid: "46552553"
---
# <a name="manage-urls-in-the-tenant-allowblock-list"></a><span data-ttu-id="14cf3-103">테 넌 트 허용/차단 목록에서 Url 관리</span><span class="sxs-lookup"><span data-stu-id="14cf3-103">Manage URLs in the Tenant Allow/Block List</span></span>

> [!NOTE]
> <span data-ttu-id="14cf3-104">이 항목에서 설명 하는 기능은 미리 보기에 있으며, 변경 될 수 있으며, 일부 조직에서는 제공 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-104">The features described in this topic are in Preview, are subject to change, and are not available in all organizations.</span></span>

<span data-ttu-id="14cf3-105">Exchange online 사서함을 사용 하지 않는 exchange Online 또는 독립 실행형 EOP (Exchange Online Protection) 조직의 사서함이 있는 Microsoft 365 조직에서는 EOP 필터링 결과에 동의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="14cf3-106">예를 들어 좋은 메시지는 불량 (가양성)으로 표시 되거나 잘못 된 메시지 (가양성)를 통해 허용 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-106">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="14cf3-107">보안 & 준수 센터의 테 넌 트 허용/차단 목록에서는 Microsoft 365 필터링 verdicts를 수동으로 다시 정의할 수 있는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-107">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="14cf3-108">메일 흐름 중 및 사용자가 클릭 했을 때의 테 넌 트 허용/차단 목록이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-108">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="14cf3-109">테 넌 트 허용/차단 목록에서 허용 하거나 차단할 Url을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-109">You can specify URLs to allow or block in the Tenant Allow/Block List.</span></span>

<span data-ttu-id="14cf3-110">이 항목에서는 보안 & 준수 센터 또는 PowerShell (exchange online 사서함이 없는 조직에 대해 exchange Online의 사서함이 있는 Microsoft 365 조 직의 경우 Exchange online PowerShell)의 테 넌 트 허용/차단 목록에서 항목을 구성 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-110">This topic describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="14cf3-111">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="14cf3-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="14cf3-112"><https://protection.office.com/>에서 보안 및 준수 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="14cf3-113">**테 넌 트 허용/차단 목록** 페이지로 바로 이동 하려면를 사용 <https://protection.office.com/tenantAllowBlockList> 합니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-113">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="14cf3-114">사용 가능한 URL 값은이 항목 뒷부분의 [테 넌 트 허용/차단 목록 섹션에 대 한 URL 구문](#url-syntax-for-the-tenant-allowblock-list) 에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-114">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

- <span data-ttu-id="14cf3-115">테 넌 트 허용/차단 목록에서 URLss에 대해 최대 500 항목을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-115">The Tenant Allow/Block List allows a maximum of 500 entries for URLss.</span></span>

- <span data-ttu-id="14cf3-116">15 분 내에 항목을 활성화 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-116">An entry should be active within 15 minutes.</span></span>

- <span data-ttu-id="14cf3-117">차단 항목은 허용 항목 보다 우선적으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-117">Block entries take precedence over allow entries.</span></span>

- <span data-ttu-id="14cf3-118">기본적으로 테 넌 트 허용/차단 목록의 항목은 30 일 후에 만료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-118">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="14cf3-119">날짜를 지정 하거나 만료 되지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-119">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="14cf3-120">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="14cf3-120">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="14cf3-121">독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="14cf3-121">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="14cf3-122">이 항목의 절차를 수행하려면 먼저 사용 권한을 할당받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-122">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="14cf3-123">테 넌 트 허용/차단 목록에서 값을 추가 및 제거 하려면 다음 역할 그룹 중 하나의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-123">To add and remove values from the Tenant Allow/Block List, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="14cf3-124">[보안 및 준수 센터](permissions-in-the-security-and-compliance-center.md)의 **조직 관리** 또는 **보안 관리자**</span><span class="sxs-lookup"><span data-stu-id="14cf3-124">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="14cf3-125">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **조직 관리** 및 **예방 조치 관리**</span><span class="sxs-lookup"><span data-stu-id="14cf3-125">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="14cf3-126">테 넌 트 허용/차단 목록에 대 한 읽기 전용 액세스를 위해서는 다음 역할 그룹 중 하나의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-126">For read-only access to the Tenant Allow/Block List, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="14cf3-127">[보안 및 준수 센터](permissions-in-the-security-and-compliance-center.md)의 **보안 읽기**</span><span class="sxs-lookup"><span data-stu-id="14cf3-127">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="14cf3-128">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **보기 전용 조직 관리**</span><span class="sxs-lookup"><span data-stu-id="14cf3-128">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="14cf3-129">보안 & 준수 센터를 사용 하 여 테 넌 트 허용/차단 목록에 URL 항목 만들기</span><span class="sxs-lookup"><span data-stu-id="14cf3-129">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="14cf3-130">URL 항목의 구문에 대 한 자세한 내용은이 항목 뒷부분의 [테 넌 트 허용/차단 목록 섹션에 대 한 URL 구문을](#url-syntax-for-the-tenant-allowblock-list) 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="14cf3-130">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

1. <span data-ttu-id="14cf3-131">보안 & 준수 센터에서 **위협 관리** \> **정책** \> **테 넌 트 허용/차단 목록**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-131">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="14cf3-132">**테 넌 트 허용/차단 목록** 페이지에서 **url** 탭이 선택 되어 있는지 확인 한 다음 **추가** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-132">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Add**</span></span>

3. <span data-ttu-id="14cf3-133">**새 Url 추가** 플라이 아웃이 나타나면 다음 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-133">In the **Add new URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="14cf3-134">**와일드 카드를 사용 하 여 Url 추가**: 한 줄당 url을 하나씩 입력 합니다 (최대 20 개).</span><span class="sxs-lookup"><span data-stu-id="14cf3-134">**Add URLs with wildcards**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="14cf3-135">**차단/허용**: 지정 된 Url을 **허용** 하거나 **차단할지** 여부를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-135">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified URLs.</span></span>

   - <span data-ttu-id="14cf3-136">사용 **기간 제한 없음**: 다음 단계 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-136">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="14cf3-137">설정이 꺼져 있는지 ( ![ 토글 해제)를 확인 하 ](../../media/scc-toggle-off.png) 고 **만료** 날짜 상자를 사용 하 여 항목의 만료일을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-137">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="14cf3-138">또는</span><span class="sxs-lookup"><span data-stu-id="14cf3-138">or</span></span>

     - <span data-ttu-id="14cf3-139">오른쪽으로 토글을 이동 하 여 만료 되지 않도록 항목을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-139">Move the toggle to the right to configure the entries to never expire:</span></span> ![토글 켬](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="14cf3-141">.</span><span class="sxs-lookup"><span data-stu-id="14cf3-141">.</span></span>

   - <span data-ttu-id="14cf3-142">**선택 사항**: 항목에 대 한 설명 텍스트를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-142">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="14cf3-143">작업이 완료 되 면 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-143">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="14cf3-144">보안 & 준수 센터를 사용 하 여 테 넌 트 허용/차단 목록의 항목 보기</span><span class="sxs-lookup"><span data-stu-id="14cf3-144">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="14cf3-145">보안 & 준수 센터에서 **위협 관리** \> **정책** \> **테 넌 트 허용/차단 목록**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-145">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="14cf3-146">**Url** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-146">Select the **URLs** tab.</span></span>

<span data-ttu-id="14cf3-147">다음 열 머리글을 클릭 하 여 오름차순 또는 내림차순으로 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-147">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="14cf3-148">**값**</span><span class="sxs-lookup"><span data-stu-id="14cf3-148">**Value**</span></span>
- <span data-ttu-id="14cf3-149">**작업**: **차단** 또는 **허용**합니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-149">**Action**: **Block** or **Allow**.</span></span>
- <span data-ttu-id="14cf3-150">**마지막 업데이트 날짜**</span><span class="sxs-lookup"><span data-stu-id="14cf3-150">**Last updated date**</span></span>
- <span data-ttu-id="14cf3-151">**만료 날짜**</span><span class="sxs-lookup"><span data-stu-id="14cf3-151">**Expiration date**</span></span>
- <span data-ttu-id="14cf3-152">**참고**</span><span class="sxs-lookup"><span data-stu-id="14cf3-152">**Note**</span></span>

<span data-ttu-id="14cf3-153">**그룹** 을 클릭 하 여 **작업** (**차단** 또는 **허용**)을 기준으로 항목을 그룹화 하거나 **아무 것도**선택 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-153">Click **Group** to group the entries by **Action** (**Block** or **Allow**) or **None**.</span></span>

<span data-ttu-id="14cf3-154">**검색**을 클릭 하 고 값의 일부나 전체를 입력 한 다음 enter 키를 눌러 특정 값을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-154">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="14cf3-155">작업이 끝나면 검색 지우기 검색 아이콘 **을 클릭** ![ ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) 합니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-155">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="14cf3-156">**필터**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-156">Click **Filter**.</span></span> <span data-ttu-id="14cf3-157">**필터** 플라이 아웃이 나타나면 다음 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-157">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="14cf3-158">**작업**: **Allow**, **Block** 또는 both를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-158">**Action**: Select **Allow**, **Block** or both.</span></span>

- <span data-ttu-id="14cf3-159">사용 **기간 제한 없음**: 해제 (설정 ![ /해제 ](../../media/scc-toggle-off.png) ) 또는 설정 ( ![ 토글 켜기)을 선택 ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) 합니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-159">**Never expire**: Select off (![Toggle off](../../media/scc-toggle-off.png)) or on (![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)).</span></span>

- <span data-ttu-id="14cf3-160">**마지막 업데이트**: 시작 날짜 (**원본**), 종료 날짜 (**대상**) 또는 두 가지 모두를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-160">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="14cf3-161">**만료 날짜**: 시작 날짜 (**From**), 종료 날짜 (**대상**) 또는 둘 다를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-161">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="14cf3-162">작업이 완료 되 면 **적용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-162">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="14cf3-163">기존 필터를 지우려면 **필터**를 클릭 하 고 **필터** 플라이 아웃이 나타나면 **필터 해제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-163">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="14cf3-164">보안 & 준수 센터를 사용 하 여 테 넌 트 허용/차단 목록의 항목 수정</span><span class="sxs-lookup"><span data-stu-id="14cf3-164">Use the Security & Compliance Center to modify entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="14cf3-165">URL 값 자체는 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-165">You can't modify the URL value itself.</span></span> <span data-ttu-id="14cf3-166">대신 항목을 삭제 하 고 다시 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-166">Instead, you need to delete the entry and recreate it.</span></span>

1. <span data-ttu-id="14cf3-167">보안 & 준수 센터에서 **위협 관리** \> **정책** \> **테 넌 트 허용/차단 목록**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-167">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="14cf3-168">**Url** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-168">Select the **URLs** tab.</span></span>

3. <span data-ttu-id="14cf3-169">수정 하려는 항목을 선택 하 고 편집 아이콘 편집을 클릭 **Edit** ![ ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) 합니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-169">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="14cf3-170">플라이 아웃이 나타나면 다음 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-170">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="14cf3-171">**차단/허용**: **허용** 또는 **차단**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-171">**Block/Allow**: Select **Allow** or **Block**.</span></span>

   - <span data-ttu-id="14cf3-172">사용 **기간 제한 없음**: 다음 단계 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-172">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="14cf3-173">설정이 꺼져 있는지 ( ![ 토글 해제)를 확인 하 ](../../media/scc-toggle-off.png) 고 **만료** 날짜 상자를 사용 하 여 항목의 만료일을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-173">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

     <span data-ttu-id="14cf3-174">또는</span><span class="sxs-lookup"><span data-stu-id="14cf3-174">or</span></span>

     - <span data-ttu-id="14cf3-175">오른쪽으로 토글을 이동 하 여 항목이 만료 되지 않도록 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-175">Move the toggle to the right to configure the entry to never expire:</span></span> ![토글 켬](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="14cf3-177">.</span><span class="sxs-lookup"><span data-stu-id="14cf3-177">.</span></span>

   - <span data-ttu-id="14cf3-178">**선택 사항**: 항목에 대 한 설명 텍스트를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-178">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="14cf3-179">작업을 마쳤으면 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-179">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="14cf3-180">보안 & 준수 센터를 사용 하 여 테 넌 트 허용/차단 목록에서 항목 제거</span><span class="sxs-lookup"><span data-stu-id="14cf3-180">Use the Security & Compliance Center to remove entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="14cf3-181">보안 & 준수 센터에서 **위협 관리** \> **정책** \> **테 넌 트 허용/차단 목록**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-181">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="14cf3-182">**Url** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-182">Select the **URLs** tab.</span></span>

3. <span data-ttu-id="14cf3-183">제거할 항목을 선택한 다음 삭제 아이콘 **삭제** 를 클릭 ![ ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) 합니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-183">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="14cf3-184">경고 대화 상자가 나타나면 **삭제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-184">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="14cf3-185">Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell을 사용 하 여 테 넌 트 허용/차단 목록을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-185">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="14cf3-186">PowerShell을 사용 하 여 테 넌 트 허용/차단 목록에 항목 추가</span><span class="sxs-lookup"><span data-stu-id="14cf3-186">Use PowerShell to add entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="14cf3-187">테 넌 트 허용/차단 목록에 항목을 추가 하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-187">To add entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="14cf3-188">이 예에서는 contoso.com 및 모든 하위 도메인 (예: contoso.com, www.contoso.com 및 xyz.abc.contoso.com)에 대 한 URL 블록 항목을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-188">This example adds a URL block entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="14cf3-189">ExpirationDate 또는 NoExpiration 매개 변수를 사용 하지 않았으므로 30 일 후에 항목이 만료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-189">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

<span data-ttu-id="14cf3-190">구문과 매개 변수에 대 한 자세한 내용은 [TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="14cf3-190">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="14cf3-191">PowerShell을 사용 하 여 테 넌 트 허용/차단 목록의 항목 보기</span><span class="sxs-lookup"><span data-stu-id="14cf3-191">Use PowerShell to view entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="14cf3-192">테 넌 트 허용/차단 목록의 항목을 보려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-192">To view entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url [-Entry <URLValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="14cf3-193">이 예에서는 차단 된 모든 Url을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-193">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

<span data-ttu-id="14cf3-194">구문과 매개 변수에 대 한 자세한 내용은 [TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="14cf3-194">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="14cf3-195">PowerShell을 사용 하 여 테 넌 트 허용/차단 목록의 항목 수정</span><span class="sxs-lookup"><span data-stu-id="14cf3-195">Use PowerShell to modify entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="14cf3-196">URL 값 자체는 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-196">You can't modify the URL value itself.</span></span> <span data-ttu-id="14cf3-197">대신 항목을 삭제 하 고 다시 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-197">Instead, you need to delete the entry and recreate it.</span></span>

<span data-ttu-id="14cf3-198">테 넌 트 허용/차단 목록의 항목을 수정 하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-198">To modify entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="14cf3-199">다음은 지정 된 항목의 만료 날짜를 변경 하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-199">This example changes the expiration date of the specified entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="14cf3-200">구문 및 매개 변수에 대 한 자세한 내용은 [TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="14cf3-200">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="14cf3-201">PowerShell을 사용 하 여 테 넌 트 허용/차단 목록에서 항목 제거</span><span class="sxs-lookup"><span data-stu-id="14cf3-201">Use PowerShell to remove entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="14cf3-202">테 넌 트 허용/차단 목록에서 항목을 제거 하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-202">To remove entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="14cf3-203">이 예에서는 테 넌 트 허용/차단 목록에서 지정 된 URL 항목을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-203">This example removes the specified URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="14cf3-204">구문과 매개 변수에 대 한 자세한 내용은 [TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="14cf3-204">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="14cf3-205">테 넌 트 허용/차단 목록에 대 한 URL 구문</span><span class="sxs-lookup"><span data-stu-id="14cf3-205">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="14cf3-206">IP4v 및 IPv6 주소를 사용할 수 있지만 TCP/UDP 포트는 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-206">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="14cf3-207">파일 이름 확장명은 허용 되지 않습니다 (예: test.pdf).</span><span class="sxs-lookup"><span data-stu-id="14cf3-207">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="14cf3-208">유니코드는 지원 되지 않지만, Punycode는입니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-208">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="14cf3-209">다음의 모든 조건에 해당 하는 경우에는 호스트 이름이 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-209">Hostnames are allowed if all of the following statements are true:</span></span>

  - <span data-ttu-id="14cf3-210">호스트 이름에 마침표가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-210">The hostname contains a period.</span></span>
  - <span data-ttu-id="14cf3-211">마침표 왼쪽에 문자가 하나 이상 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-211">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="14cf3-212">마침표 오른쪽에 2 개 이상의 문자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-212">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="14cf3-213">예를 들어, `t.co` 허용 `.com` 되지 않거나 `contoso.` 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-213">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="14cf3-214">하위 경로는 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-214">Subpaths are not implied.</span></span>

  <span data-ttu-id="14cf3-215">예를 들어에 `contoso.com` 는가 포함 되지 않습니다 `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="14cf3-215">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="14cf3-216">다음과 같은 시나리오에서는 와일드 카드 (\*)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-216">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="14cf3-217">하위 도메인을 지정 하려면 left 와일드 카드 다음에 마침표가와 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-217">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="14cf3-218">예를 들어, 허용 `*.contoso.com` `*contoso.com` 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-218">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="14cf3-219">경로를 지정 하려면 오른쪽 와일드 카드는 슬래시 (/) 다음에와 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-219">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="14cf3-220">예를 들어, `contoso.com/*` 허용 `contoso.com*` 되지 않거나 `contoso.com/ab*` 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-220">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="14cf3-221">모든 서브 경로는 오른쪽 와일드 카드에서 암시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-221">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="14cf3-222">예를 들어에 `contoso.com/*` 는가 포함 되지 않습니다 `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="14cf3-222">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="14cf3-223">`*.com*`잘못 되었습니다 (확인할 수 있는 도메인이 아님, 올바른 와일드 카드가 슬래시 다음에 없음).</span><span class="sxs-lookup"><span data-stu-id="14cf3-223">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="14cf3-224">IP 주소에는 와일드 카드를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-224">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="14cf3-225">물결표 (~) 문자는 다음과 같은 시나리오에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-225">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="14cf3-226">왼쪽 물결표는 도메인과 모든 하위 도메인을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-226">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="14cf3-227">예를 `~contoso.com` 들어 `contoso.com` and를 포함 `*.contoso.com` 합니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-227">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="14cf3-228">`http://` `https://` `ftp://` Url 항목은 모든 프로토콜에 적용 되므로 프로토콜 (예:, 또는)을 포함 하는 url 항목은 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-228">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="14cf3-229">사용자 이름 또는 암호는 지원 되지 않거나 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-229">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="14cf3-230">따옴표 (' 또는 ")는 잘못 된 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-230">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="14cf3-231">URL에는 가능한 모든 리디렉션이 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-231">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="14cf3-232">URL 입력 시나리오</span><span class="sxs-lookup"><span data-stu-id="14cf3-232">URL entry scenarios</span></span>

<span data-ttu-id="14cf3-233">유효한 URL 항목 및 결과는 다음 섹션에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-233">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="14cf3-234">시나리오: 와일드 카드 없음</span><span class="sxs-lookup"><span data-stu-id="14cf3-234">Scenario: No wildcards</span></span>

<span data-ttu-id="14cf3-235">**항목**:`contoso.com`</span><span class="sxs-lookup"><span data-stu-id="14cf3-235">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="14cf3-236">**일치 허용**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="14cf3-236">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="14cf3-237">**일치 하지 않는 항목 허용**:</span><span class="sxs-lookup"><span data-stu-id="14cf3-237">**Allow not matched**:</span></span>

  - <span data-ttu-id="14cf3-238">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="14cf3-238">abc-contoso.com</span></span>
  - <span data-ttu-id="14cf3-239">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="14cf3-239">contoso.com/a</span></span>
  - <span data-ttu-id="14cf3-240">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="14cf3-240">payroll.contoso.com</span></span>
  - <span data-ttu-id="14cf3-241">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="14cf3-241">test.com/contoso.com</span></span>
  - <span data-ttu-id="14cf3-242">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="14cf3-242">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="14cf3-243">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="14cf3-243">www.contoso.com</span></span>
  - <span data-ttu-id="14cf3-244">www. .com/q = a@contoso</span><span class="sxs-lookup"><span data-stu-id="14cf3-244">www.contoso.com/q=a@contoso.com</span></span>
  
- <span data-ttu-id="14cf3-245">**일치 블록**:</span><span class="sxs-lookup"><span data-stu-id="14cf3-245">**Block match**:</span></span>

  - <span data-ttu-id="14cf3-246">contoso.com</span><span class="sxs-lookup"><span data-stu-id="14cf3-246">contoso.com</span></span>
  - <span data-ttu-id="14cf3-247">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="14cf3-247">contoso.com/a</span></span>
  - <span data-ttu-id="14cf3-248">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="14cf3-248">payroll.contoso.com</span></span>
  - <span data-ttu-id="14cf3-249">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="14cf3-249">test.com/contoso.com</span></span>
  - <span data-ttu-id="14cf3-250">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="14cf3-250">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="14cf3-251">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="14cf3-251">www.contoso.com</span></span>
  - <span data-ttu-id="14cf3-252">www. .com/q = a@contoso</span><span class="sxs-lookup"><span data-stu-id="14cf3-252">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="14cf3-253">**일치 하지 않는 블록**: abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="14cf3-253">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="14cf3-254">시나리오: Left 와일드 카드 (하위 도메인)</span><span class="sxs-lookup"><span data-stu-id="14cf3-254">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="14cf3-255">**항목**:`*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="14cf3-255">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="14cf3-256">**일치 허용** 및 **일치 차단**:</span><span class="sxs-lookup"><span data-stu-id="14cf3-256">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="14cf3-257">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="14cf3-257">www.contoso.com</span></span>
  - <span data-ttu-id="14cf3-258">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="14cf3-258">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="14cf3-259">**일치 하지 않는** 항목과 **일치**하는 블록 허용:</span><span class="sxs-lookup"><span data-stu-id="14cf3-259">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="14cf3-260">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="14cf3-260">123contoso.com</span></span>
  - <span data-ttu-id="14cf3-261">contoso.com</span><span class="sxs-lookup"><span data-stu-id="14cf3-261">contoso.com</span></span>
  - <span data-ttu-id="14cf3-262">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="14cf3-262">test.com/contoso.com</span></span>
  - <span data-ttu-id="14cf3-263">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="14cf3-263">www.contoso.com/abc</span></span>
  
#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="14cf3-264">시나리오: 경로 맨 위의 오른쪽 와일드 카드</span><span class="sxs-lookup"><span data-stu-id="14cf3-264">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="14cf3-265">**항목**:`contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="14cf3-265">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="14cf3-266">**일치 허용** 및 **일치 차단**:</span><span class="sxs-lookup"><span data-stu-id="14cf3-266">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="14cf3-267">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="14cf3-267">contoso.com/a/b</span></span>
  - <span data-ttu-id="14cf3-268">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="14cf3-268">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="14cf3-269">contoso/a/? q = joe@t .com</span><span class="sxs-lookup"><span data-stu-id="14cf3-269">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="14cf3-270">**일치 하지 않는** 항목과 **일치**하는 블록 허용:</span><span class="sxs-lookup"><span data-stu-id="14cf3-270">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="14cf3-271">contoso.com</span><span class="sxs-lookup"><span data-stu-id="14cf3-271">contoso.com</span></span>
  - <span data-ttu-id="14cf3-272">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="14cf3-272">contoso.com/a</span></span>
  - <span data-ttu-id="14cf3-273">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="14cf3-273">www.contoso.com</span></span>
  - <span data-ttu-id="14cf3-274">www. .com/q = a@contoso</span><span class="sxs-lookup"><span data-stu-id="14cf3-274">www.contoso.com/q=a@contoso.com</span></span>
  
#### <a name="scenario-left-tilde"></a><span data-ttu-id="14cf3-275">시나리오: 왼쪽 물결표</span><span class="sxs-lookup"><span data-stu-id="14cf3-275">Scenario: Left tilde</span></span>

<span data-ttu-id="14cf3-276">**항목**:`~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="14cf3-276">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="14cf3-277">**일치 허용** 및 **일치 차단**:</span><span class="sxs-lookup"><span data-stu-id="14cf3-277">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="14cf3-278">contoso.com</span><span class="sxs-lookup"><span data-stu-id="14cf3-278">contoso.com</span></span>
  - <span data-ttu-id="14cf3-279">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="14cf3-279">www.contoso.com</span></span>
  - <span data-ttu-id="14cf3-280">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="14cf3-280">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="14cf3-281">**일치 하지 않는** 항목과 **일치**하는 블록 허용:</span><span class="sxs-lookup"><span data-stu-id="14cf3-281">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="14cf3-282">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="14cf3-282">123contoso.com</span></span>
  - <span data-ttu-id="14cf3-283">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="14cf3-283">contoso.com/abc</span></span>
  - <span data-ttu-id="14cf3-284">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="14cf3-284">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="14cf3-285">시나리오: 오른쪽 와일드 카드 접미사</span><span class="sxs-lookup"><span data-stu-id="14cf3-285">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="14cf3-286">**항목**:`contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="14cf3-286">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="14cf3-287">**일치 허용** 및 **일치 차단**:</span><span class="sxs-lookup"><span data-stu-id="14cf3-287">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="14cf3-288">contoso/? q = whatever@fabrikam</span><span class="sxs-lookup"><span data-stu-id="14cf3-288">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="14cf3-289">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="14cf3-289">contoso.com/a</span></span>
  - <span data-ttu-id="14cf3-290">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="14cf3-290">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="14cf3-291">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="14cf3-291">contoso.com/ab</span></span>
  - <span data-ttu-id="14cf3-292">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="14cf3-292">contoso.com/b</span></span>
  - <span data-ttu-id="14cf3-293">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="14cf3-293">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="14cf3-294">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="14cf3-294">contoso.com/ba</span></span>

- <span data-ttu-id="14cf3-295">**일치 하지 않음** 및 **일치**하는 블록 허용: contoso.com</span><span class="sxs-lookup"><span data-stu-id="14cf3-295">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="14cf3-296">시나리오: Left 와일드 카드 하위 도메인 및 오른쪽 와일드 카드 접미사</span><span class="sxs-lookup"><span data-stu-id="14cf3-296">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="14cf3-297">**항목**:`*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="14cf3-297">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="14cf3-298">**일치 허용** 및 **일치 차단**:</span><span class="sxs-lookup"><span data-stu-id="14cf3-298">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="14cf3-299">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="14cf3-299">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="14cf3-300">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="14cf3-300">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="14cf3-301">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="14cf3-301">www.contoso.com/a</span></span>
  - <span data-ttu-id="14cf3-302">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="14cf3-302">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="14cf3-303">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="14cf3-303">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="14cf3-304">**일치 하지 않음** 및 **일치**하는 블록 허용: contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="14cf3-304">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="14cf3-305">시나리오: 왼쪽과 오른쪽 물결표</span><span class="sxs-lookup"><span data-stu-id="14cf3-305">Scenario: Left and right tilde</span></span>

<span data-ttu-id="14cf3-306">**항목**:`~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="14cf3-306">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="14cf3-307">**일치 허용** 및 **일치 차단**:</span><span class="sxs-lookup"><span data-stu-id="14cf3-307">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="14cf3-308">contoso.com</span><span class="sxs-lookup"><span data-stu-id="14cf3-308">contoso.com</span></span>
  - <span data-ttu-id="14cf3-309">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="14cf3-309">contoso.com/a</span></span>
  - <span data-ttu-id="14cf3-310">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="14cf3-310">www.contoso.com</span></span>
  - <span data-ttu-id="14cf3-311">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="14cf3-311">www.contoso.com/b</span></span>
  - <span data-ttu-id="14cf3-312">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="14cf3-312">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="14cf3-313">**일치 하지 않는** 항목과 **일치**하는 블록 허용:</span><span class="sxs-lookup"><span data-stu-id="14cf3-313">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="14cf3-314">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="14cf3-314">123contoso.com</span></span>
  - <span data-ttu-id="14cf3-315">contoso.org</span><span class="sxs-lookup"><span data-stu-id="14cf3-315">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="14cf3-316">시나리오: IP 주소</span><span class="sxs-lookup"><span data-stu-id="14cf3-316">Scenario: IP address</span></span>

<span data-ttu-id="14cf3-317">**항목**:`1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="14cf3-317">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="14cf3-318">**일치 허용** 및 **일치 차단**: 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="14cf3-318">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="14cf3-319">**일치 하지 않는** 항목과 **일치**하는 블록 허용:</span><span class="sxs-lookup"><span data-stu-id="14cf3-319">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="14cf3-320">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="14cf3-320">1.2.3.4/a</span></span>
  - <span data-ttu-id="14cf3-321">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="14cf3-321">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="14cf3-322">오른쪽 와일드 카드를 사용한 IP 주소</span><span class="sxs-lookup"><span data-stu-id="14cf3-322">IP address with right wildcard</span></span>

<span data-ttu-id="14cf3-323">**항목**:`1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="14cf3-323">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="14cf3-324">**일치 허용** 및 **일치 차단**:</span><span class="sxs-lookup"><span data-stu-id="14cf3-324">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="14cf3-325">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="14cf3-325">1.2.3.4/b</span></span>
  - <span data-ttu-id="14cf3-326">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="14cf3-326">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="14cf3-327">잘못 된 항목의 예</span><span class="sxs-lookup"><span data-stu-id="14cf3-327">Examples of invalid entries</span></span>

<span data-ttu-id="14cf3-328">다음 항목은 유효 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14cf3-328">The following entries are invalid:</span></span>

- <span data-ttu-id="14cf3-329">**누락 되었거나 잘못 된 도메인 값**:</span><span class="sxs-lookup"><span data-stu-id="14cf3-329">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="14cf3-330">극동</span><span class="sxs-lookup"><span data-stu-id="14cf3-330">contoso</span></span>
  - <span data-ttu-id="14cf3-331">\*극동.\*</span><span class="sxs-lookup"><span data-stu-id="14cf3-331">\*.contoso.\*</span></span>
  - <span data-ttu-id="14cf3-332">\*.com</span><span class="sxs-lookup"><span data-stu-id="14cf3-332">\*.com</span></span>
  - <span data-ttu-id="14cf3-333">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="14cf3-333">\*.pdf</span></span>

- <span data-ttu-id="14cf3-334">**텍스트에 와일드 카드 사용 또는 공백 문자 없는**경우:</span><span class="sxs-lookup"><span data-stu-id="14cf3-334">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="14cf3-335">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="14cf3-335">\*contoso.com</span></span>
  - <span data-ttu-id="14cf3-336">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="14cf3-336">contoso.com\*</span></span>
  - <span data-ttu-id="14cf3-337">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="14cf3-337">\*1.2.3.4</span></span>
  - <span data-ttu-id="14cf3-338">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="14cf3-338">1.2.3.4\*</span></span>
  - <span data-ttu-id="14cf3-339">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="14cf3-339">contoso.com/a\*</span></span>
  - <span data-ttu-id="14cf3-340">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="14cf3-340">contoso.com/ab\*</span></span>

- <span data-ttu-id="14cf3-341">**포트를 포함 하는 IP 주소**:</span><span class="sxs-lookup"><span data-stu-id="14cf3-341">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="14cf3-342">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="14cf3-342">contoso.com:443</span></span>
  - <span data-ttu-id="14cf3-343">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="14cf3-343">abc.contoso.com:25</span></span>

- <span data-ttu-id="14cf3-344">**설명적이 아닌 와일드 카드**:</span><span class="sxs-lookup"><span data-stu-id="14cf3-344">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="14cf3-345">\*.\*</span><span class="sxs-lookup"><span data-stu-id="14cf3-345">\*.\*</span></span>

- <span data-ttu-id="14cf3-346">**중간 와일드 카드**:</span><span class="sxs-lookup"><span data-stu-id="14cf3-346">**Middle wildcards**:</span></span>

  - <span data-ttu-id="14cf3-347">\*so.com</span><span class="sxs-lookup"><span data-stu-id="14cf3-347">conto\*so.com</span></span>
  - <span data-ttu-id="14cf3-348">~ ~ .com</span><span class="sxs-lookup"><span data-stu-id="14cf3-348">conto~so.com</span></span>

- <span data-ttu-id="14cf3-349">**이중 와일드 카드**</span><span class="sxs-lookup"><span data-stu-id="14cf3-349">**Double wildcards**</span></span>

  - <span data-ttu-id="14cf3-350">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="14cf3-350">contoso.com/\*\*</span></span>
  - <span data-ttu-id="14cf3-351">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="14cf3-351">contoso.com/\*/\*</span></span>
