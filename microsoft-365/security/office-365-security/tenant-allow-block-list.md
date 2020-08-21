---
title: 테넌트 허용/차단 목록에서 허용되고 차단된 URL 관리
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 관리자는 보안 및 준수 센터의 테넌트 허용/차단 목록에서 URL 항목을 구성하는 방법을 & 있습니다.
ms.openlocfilehash: 888a96f23daf2cf47847466ad4080f310be7f9b4
ms.sourcegitcommit: 260bbb93bbda62db9e88c021ccccfa75ac39a32e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/21/2020
ms.locfileid: "46845945"
---
# <a name="manage-urls-in-the-tenant-allowblock-list"></a><span data-ttu-id="61a6f-103">테넌트 허용/차단 목록의 URL 관리</span><span class="sxs-lookup"><span data-stu-id="61a6f-103">Manage URLs in the Tenant Allow/Block List</span></span>

> [!NOTE]
> <span data-ttu-id="61a6f-104">이 항목에서 설명하는 기능은 미리 보기에 제공되고 변경될 수 있고 일부 조직에서는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-104">The features described in this topic are in Preview, are subject to change, and are not available in all organizations.</span></span>

<span data-ttu-id="61a6f-105">Exchange Online 사서함이 있는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에서는 EOP 필터링 통계에 이를 집계할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="61a6f-106">예를 들어 좋은 메시지는 좋은 메시지(가양성)로 표시되거나 부정(거짓 부정)으로 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-106">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="61a6f-107">보안 센터의 테넌트 허용/차단 & 목록은 Microsoft 365 필터링 결과를 수동으로 재정의하는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-107">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="61a6f-108">테넌트 허용/차단 목록은 메일 흐름도 진행되는 동안 또는 사용자가 클릭할 때 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-108">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="61a6f-109">테넌트 허용/차단 목록에서 허용하거나 차단할 URL을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-109">You can specify URLs to allow or block in the Tenant Allow/Block List.</span></span>

<span data-ttu-id="61a6f-110">이 항목에서는 보안 & 규정 준수 센터 또는 PowerShell(Exchange Online 사서함을 사용하는 Microsoft 365 조직의 Exchange Online PowerShell, Exchange Online 사서함이 없는 조직의 경우 독립 실행형 EOP PowerShell)의 테넌트 허용/차단 목록의 항목을 구성하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-110">This topic describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="61a6f-111">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="61a6f-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="61a6f-112"><https://protection.office.com/>에서 보안 및 준수 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="61a6f-113">테넌트 **허용/차단 목록 페이지로 직접 이동하려면** 다음을 사용합니다. <https://protection.office.com/tenantAllowBlockList></span><span class="sxs-lookup"><span data-stu-id="61a6f-113">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="61a6f-114">사용 가능한 URL 값은 이 항목 뒷부분의 [테넌트 허용/차단 목록 섹션에 대한 URL](#url-syntax-for-the-tenant-allowblock-list) 구문에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-114">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

- <span data-ttu-id="61a6f-115">테넌트 허용/차단 목록을 통해 URL에 최대 500개의 항목을 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-115">The Tenant Allow/Block List allows a maximum of 500 entries for URLs.</span></span>

- <span data-ttu-id="61a6f-116">15분 내에 항목을 활성화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-116">An entry should be active within 15 minutes.</span></span>

- <span data-ttu-id="61a6f-117">차단 항목은 허용 항목보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-117">Block entries take precedence over allow entries.</span></span>

- <span data-ttu-id="61a6f-118">기본적으로 테넌트 허용/차단 목록의 항목은 30일 후에 만료됩니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-118">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="61a6f-119">날짜를 지정하거나 만료되지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-119">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="61a6f-120">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="61a6f-120">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="61a6f-121">독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="61a6f-121">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="61a6f-122">이 항목의 절차를 수행하려면 먼저 사용 권한을 할당받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-122">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="61a6f-123">테넌트 허용/차단 목록에서 값을 추가하거나 제거하려면 다음 역할 그룹 중 하나의 구성원이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-123">To add and remove values from the Tenant Allow/Block List, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="61a6f-124">[보안 및 준수 센터](permissions-in-the-security-and-compliance-center.md)의 **조직 관리** 또는 **보안 관리자**</span><span class="sxs-lookup"><span data-stu-id="61a6f-124">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="61a6f-125">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **조직 관리** 및 **예방 조치 관리**</span><span class="sxs-lookup"><span data-stu-id="61a6f-125">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="61a6f-126">테넌트 허용/차단 목록에 대한 읽기 전용 액세스를 위해서는 다음 역할 그룹 중 하나의 구성원이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-126">For read-only access to the Tenant Allow/Block List, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="61a6f-127">[보안 및 준수 센터](permissions-in-the-security-and-compliance-center.md)의 **보안 읽기**</span><span class="sxs-lookup"><span data-stu-id="61a6f-127">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="61a6f-128">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **보기 전용 조직 관리**</span><span class="sxs-lookup"><span data-stu-id="61a6f-128">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="61a6f-129">보안 센터 보안 & 사용하여 테넌트 허용/차단 목록에 URL 항목 만들기</span><span class="sxs-lookup"><span data-stu-id="61a6f-129">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="61a6f-130">URL 항목에 대한 구문에 대한 자세한 내용은 이 항목 [뒷부분의 테넌트 허용/차단 목록 섹션에 대한 URL](#url-syntax-for-the-tenant-allowblock-list) 구문을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="61a6f-130">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

1. <span data-ttu-id="61a6f-131">보안 센터 보안 & 위협 관리 정책 테넌트 **Threat management** \> **Policy** \> **허용/차단 목록으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="61a6f-131">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="61a6f-132">테넌트 **허용/차단 목록 페이지에서** URL 탭이 **선택되어 있는지** 확인하고 다음 추가를 클릭합니다. **Add**</span><span class="sxs-lookup"><span data-stu-id="61a6f-132">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Add**</span></span>

3. <span data-ttu-id="61a6f-133">표시되는 새 **URL 플라이아웃** 추가에서 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-133">In the **Add new URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="61a6f-134">**와일드카드로 URL 추가:** 한 줄당 한 URL을, 최대 20개까지 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-134">**Add URLs with wildcards**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="61a6f-135">**차단/허용:** 지정한 URL을 **허용할지 또는** **차단할지를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-135">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified URLs.</span></span>

   - <span data-ttu-id="61a6f-136">**만료 되지 않음:** 다음 단계 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-136">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="61a6f-137">설정이 ![ 꺼짐(토글 해제)되어 있는지 확인하고 상자 ](../../media/scc-toggle-off.png) 상기에 따라 항목에 대한 만료 날짜를 지정합니다. **Expires on**</span><span class="sxs-lookup"><span data-stu-id="61a6f-137">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="61a6f-138">또는</span><span class="sxs-lookup"><span data-stu-id="61a6f-138">or</span></span>

     - <span data-ttu-id="61a6f-139">토글을 오른쪽으로 이동하여 만료되지 않도록 항목을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-139">Move the toggle to the right to configure the entries to never expire:</span></span> ![토글 켬](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="61a6f-141">.</span><span class="sxs-lookup"><span data-stu-id="61a6f-141">.</span></span>

   - <span data-ttu-id="61a6f-142">**선택 사항:** 항목에 대한 설명 텍스트를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-142">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="61a6f-143">작업을 마치면 추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="61a6f-143">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="61a6f-144">보안 센터 보안 & 사용하여 테넌트 허용/차단 목록에서 항목 보기</span><span class="sxs-lookup"><span data-stu-id="61a6f-144">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="61a6f-145">보안 센터 보안 & 위협 관리 정책 테넌트 **Threat management** \> **Policy** \> **허용/차단 목록으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="61a6f-145">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="61a6f-146">URL **탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-146">Select the **URLs** tab.</span></span>

<span data-ttu-id="61a6f-147">다음 열 머리글을 클릭하여 오름차순 또는 오름차순으로 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-147">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="61a6f-148">**값**</span><span class="sxs-lookup"><span data-stu-id="61a6f-148">**Value**</span></span>
- <span data-ttu-id="61a6f-149">**작업:** **차단 또는** **허용**.</span><span class="sxs-lookup"><span data-stu-id="61a6f-149">**Action**: **Block** or **Allow**.</span></span>
- <span data-ttu-id="61a6f-150">**마지막 업데이트 날짜**</span><span class="sxs-lookup"><span data-stu-id="61a6f-150">**Last updated date**</span></span>
- <span data-ttu-id="61a6f-151">**만료 날짜**</span><span class="sxs-lookup"><span data-stu-id="61a6f-151">**Expiration date**</span></span>
- <span data-ttu-id="61a6f-152">**참고**</span><span class="sxs-lookup"><span data-stu-id="61a6f-152">**Note**</span></span>

<span data-ttu-id="61a6f-153">그룹을 **클릭하여** 작업(차단 또는 **허용)** **또는** **없음으로 항목을** **그룹화합니다.**</span><span class="sxs-lookup"><span data-stu-id="61a6f-153">Click **Group** to group the entries by **Action** (**Block** or **Allow**) or **None**.</span></span>

<span data-ttu-id="61a6f-154">검색을 **클릭하고**모든 값을 입력한 다음 Enter 키를 눌러 특정 값을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-154">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="61a6f-155">Finish you're finished, click **Clear search** ![ clear search ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) icon.</span><span class="sxs-lookup"><span data-stu-id="61a6f-155">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="61a6f-156">필터를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="61a6f-156">Click **Filter**.</span></span> <span data-ttu-id="61a6f-157">표시되는 **필터** 플라이아웃에서 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-157">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="61a6f-158">**작업:** **허용선택, 차단** **또는** 둘 다를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-158">**Action**: Select **Allow**, **Block** or both.</span></span>

- <span data-ttu-id="61a6f-159">**만료 안 됨:** 설정(토글 ![ ](../../media/scc-toggle-off.png) 해제) 또는 켜기(토글)입니다. ![ ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)</span><span class="sxs-lookup"><span data-stu-id="61a6f-159">**Never expire**: Select off (![Toggle off](../../media/scc-toggle-off.png)) or on (![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)).</span></span>

- <span data-ttu-id="61a6f-160">**마지막 업데이트됨**: 시작 날짜**선택(시작 날짜)** 및 끝 날짜(끝**날짜) 또는**두 가지 모두를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-160">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="61a6f-161">**만료 날짜: 시작 날짜**선택(시작**날짜)** 및 종료 날짜(끝 날짜)**또는 둘**다를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-161">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="61a6f-162">작업을 마치면 "적용"을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="61a6f-162">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="61a6f-163">기존 필터를 지우려면 **필터를 클릭한 다음 필터**플라이아웃에서 필터 지우기를 **클릭합니다.** **Filter**</span><span class="sxs-lookup"><span data-stu-id="61a6f-163">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="61a6f-164">보안 설정 준수 & 센터를 사용하여 테넌트 허용/차단 목록의 항목 수정</span><span class="sxs-lookup"><span data-stu-id="61a6f-164">Use the Security & Compliance Center to modify entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="61a6f-165">URL 값은 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-165">You can't modify the URL value itself.</span></span> <span data-ttu-id="61a6f-166">대신 항목을 삭제하여 다시 만들어해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-166">Instead, you need to delete the entry and recreate it.</span></span>

1. <span data-ttu-id="61a6f-167">보안 센터 보안 & 위협 관리 정책 테넌트 **Threat management** \> **Policy** \> **허용/차단 목록으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="61a6f-167">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="61a6f-168">URL **탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-168">Select the **URLs** tab.</span></span>

3. <span data-ttu-id="61a6f-169">수정할 항목을 선택하고 편집 아이콘을 **Edit** ![ ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-169">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="61a6f-170">플라이아웃이 나타나면 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-170">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="61a6f-171">**차단/허용:** 허용 **또는** 차단 **선택.**</span><span class="sxs-lookup"><span data-stu-id="61a6f-171">**Block/Allow**: Select **Allow** or **Block**.</span></span>

   - <span data-ttu-id="61a6f-172">**만료 되지 않음:** 다음 단계 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-172">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="61a6f-173">설정이 ![ 꺼짐(토글 해제)되어 있는지 확인하고 상자 상입기를 사용하여 ](../../media/scc-toggle-off.png) 항목의 만료 날짜를 지정합니다. **Expires on**</span><span class="sxs-lookup"><span data-stu-id="61a6f-173">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

     <span data-ttu-id="61a6f-174">또는</span><span class="sxs-lookup"><span data-stu-id="61a6f-174">or</span></span>

     - <span data-ttu-id="61a6f-175">토글을 오른쪽으로 이동하여 만료되지 않도록 항목을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-175">Move the toggle to the right to configure the entry to never expire:</span></span> ![토글 켬](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="61a6f-177">.</span><span class="sxs-lookup"><span data-stu-id="61a6f-177">.</span></span>

   - <span data-ttu-id="61a6f-178">**선택 사항**사항: 항목에 대한 설명 텍스트를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-178">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="61a6f-179">작업을 마쳤으면 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-179">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="61a6f-180">보안 그룹 규정 & 사용하여 테넌트 허용/차단 목록에서 항목 제거</span><span class="sxs-lookup"><span data-stu-id="61a6f-180">Use the Security & Compliance Center to remove entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="61a6f-181">보안 센터 보안 & 위협 관리 정책 테넌트 **Threat management** \> **Policy** \> **허용/차단 목록으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="61a6f-181">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="61a6f-182">URL **탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-182">Select the **URLs** tab.</span></span>

3. <span data-ttu-id="61a6f-183">제거할 항목을 선택한 다음 삭제 아이콘을 **Delete** ![ ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-183">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="61a6f-184">표시되는 경고 대화 상자에서 \*\* 삭제\*\*를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-184">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="61a6f-185">Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell을 사용하여 테넌트 허용/차단 목록 구성</span><span class="sxs-lookup"><span data-stu-id="61a6f-185">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="61a6f-186">PowerShell을 사용하여 테넌트 허용/차단 목록에서 항목 추가</span><span class="sxs-lookup"><span data-stu-id="61a6f-186">Use PowerShell to add entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="61a6f-187">테넌트 허용/차단 목록에 항목을 추가하려면 다음 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-187">To add entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="61a6f-188">이 예에서는 연결 로그 및 모든 하위 contoso.com(예: 검색, www.contoso.com 및 www.contoso.com)에 contoso.com 대한 URL www.contoso.com 하나xyz.abc.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="61a6f-188">This example adds a URL block entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="61a6f-189">만료 날짜 또는 NoExpiration 매개 변수를 사용하지 않기 때문에 해당 항목은 30일 후 만료됩니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-189">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

<span data-ttu-id="61a6f-190">구문과 매개 변수에 대한 자세한 내용은 [New-TenantAllowBlockListItems를 참조하세요.](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="61a6f-190">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="61a6f-191">PowerShell을 사용하여 테넌트 허용/차단 목록에서 항목 보기</span><span class="sxs-lookup"><span data-stu-id="61a6f-191">Use PowerShell to view entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="61a6f-192">테넌트 허용/차단 목록에서 항목을 확인하려면 다음 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-192">To view entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url [-Entry <URLValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="61a6f-193">이 예제에서는 차단된 모든 URL을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-193">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

<span data-ttu-id="61a6f-194">구문과 매개 변수에 대한 자세한 내용은 [Get-TenantAllowBlockListItems를 참조하세요.](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="61a6f-194">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="61a6f-195">PowerShell을 사용하여 테넌트 허용/차단 목록의 항목 수정</span><span class="sxs-lookup"><span data-stu-id="61a6f-195">Use PowerShell to modify entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="61a6f-196">URL 값은 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-196">You can't modify the URL value itself.</span></span> <span data-ttu-id="61a6f-197">대신 항목을 삭제하여 다시 만들어해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-197">Instead, you need to delete the entry and recreate it.</span></span>

<span data-ttu-id="61a6f-198">테넌트 허용/차단 목록에서 항목을 수정하려면 다음 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-198">To modify entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="61a6f-199">다음은 지정한 항목의 만료 날짜를 변경하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-199">This example changes the expiration date of the specified entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="61a6f-200">구문과 매개 변수에 대한 자세한 내용은 [Set-TenantAllowBlockListItems를 참조하세요.](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="61a6f-200">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="61a6f-201">PowerShell을 사용하여 테넌트 허용/차단 목록에서 항목 제거</span><span class="sxs-lookup"><span data-stu-id="61a6f-201">Use PowerShell to remove entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="61a6f-202">테넌트 허용/차단 목록에서 항목을 제거하려면 다음 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-202">To remove entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="61a6f-203">이 예에서는 테넌트 허용/차단 목록에서 지정된 URL 항목을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-203">This example removes the specified URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="61a6f-204">구문과 매개 변수에 대한 자세한 내용은 [Remove-TenantAllowBlockListItems를 참조하세요.](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="61a6f-204">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="61a6f-205">테넌트 허용/차단 목록에 대한 URL 구문</span><span class="sxs-lookup"><span data-stu-id="61a6f-205">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="61a6f-206">IP4v 및 IPv6 주소는 허용되지만 TCP/UDP 포트는 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-206">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="61a6f-207">파일 이름 확장명은 허용되지 않습니다(예: test.pdf).</span><span class="sxs-lookup"><span data-stu-id="61a6f-207">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="61a6f-208">유니코드는 지원되지 않지만 Punycode는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-208">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="61a6f-209">다음 설명이 모두 참인 경우 호스트 이름을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-209">Hostnames are allowed if all of the following statements are true:</span></span>

  - <span data-ttu-id="61a6f-210">호스트 이름에 마침표가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-210">The hostname contains a period.</span></span>
  - <span data-ttu-id="61a6f-211">기계의 왼쪽에 문자가 하나 이상 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-211">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="61a6f-212">마침표의 오른쪽에 두 자 이상이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-212">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="61a6f-213">예를 들어 `t.co` 허용되는지 또는 `.com` `contoso.` 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-213">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="61a6f-214">하위 경로는 암시적이지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-214">Subpaths are not implied.</span></span>

  <span data-ttu-id="61a6f-215">예를 들어 `contoso.com` 포함하지 `contoso.com/a` 않습니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-215">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="61a6f-216">다음과 같은 시나리오에서 와일드카드(\*)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-216">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="61a6f-217">왼쪽 와일드카드 다음에 기간이 오도록 하여 하위 도메인을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-217">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="61a6f-218">예를 들어 `*.contoso.com` 허용되지 `*contoso.com` 만나고 허용되지 않음</span><span class="sxs-lookup"><span data-stu-id="61a6f-218">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="61a6f-219">오른쪽 와일드카드는 경로를 지정하기 위해 Slash(/)를 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-219">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="61a6f-220">예를 들어 `contoso.com/*` 허용되는지 또는 `contoso.com*` `contoso.com/ab*` 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-220">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="61a6f-221">일부 하위 경로는 오른쪽 와일드카드의 암시적이 지나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-221">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="61a6f-222">예를 들어 `contoso.com/*` 포함하지 `contoso.com/a` 않습니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-222">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="61a6f-223">`*.com*` 값이 잘못되었습니다. 확인 가능한 도메인이 아다는 것은 발밝기가 되지만 오른쪽 와일드카드가 전달(forward slash)을 따르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-223">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="61a6f-224">IP 주소에서는 와일드카드를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-224">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="61a6f-225">다음과 같은 시나리오에서 는 자동데(~) 문자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-225">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="61a6f-226">왼쪽과 같은 설명은 도메인 및 모든 하위 도메인을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-226">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="61a6f-227">예를 `~contoso.com` `contoso.com` 들어 `*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="61a6f-227">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="61a6f-228">URL 항목이 모든 프로토콜에 적용되므로 `http://` 이러한 `https://` 프로토콜(예: `ftp://` 또는)을 포함하는 URL 항목이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-228">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="61a6f-229">사용자 이름 또는 암호는 지원되지 않거나 암호가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-229">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="61a6f-230">따로 바따(' 또는 ")는 잘못된 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-230">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="61a6f-231">URL에는 가능한 경우 모든 리디렉션이 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-231">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="61a6f-232">URL 항목 시나리오</span><span class="sxs-lookup"><span data-stu-id="61a6f-232">URL entry scenarios</span></span>

<span data-ttu-id="61a6f-233">다음 섹션에서는 유효한 URL 항목과 해당 결과에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-233">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="61a6f-234">시나리오: 와일드카드 없음</span><span class="sxs-lookup"><span data-stu-id="61a6f-234">Scenario: No wildcards</span></span>

<span data-ttu-id="61a6f-235">**항목:**`contoso.com`</span><span class="sxs-lookup"><span data-stu-id="61a6f-235">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="61a6f-236">**Allow match**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="61a6f-236">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="61a6f-237">**일치하지 않음**:</span><span class="sxs-lookup"><span data-stu-id="61a6f-237">**Allow not matched**:</span></span>

  - <span data-ttu-id="61a6f-238">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="61a6f-238">abc-contoso.com</span></span>
  - <span data-ttu-id="61a6f-239">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="61a6f-239">contoso.com/a</span></span>
  - <span data-ttu-id="61a6f-240">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="61a6f-240">payroll.contoso.com</span></span>
  - <span data-ttu-id="61a6f-241">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="61a6f-241">test.com/contoso.com</span></span>
  - <span data-ttu-id="61a6f-242">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="61a6f-242">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="61a6f-243">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="61a6f-243">www.contoso.com</span></span>
  - <span data-ttu-id="61a6f-244">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="61a6f-244">www.contoso.com/q=a@contoso.com</span></span>
  
- <span data-ttu-id="61a6f-245">**차단 일치**:</span><span class="sxs-lookup"><span data-stu-id="61a6f-245">**Block match**:</span></span>

  - <span data-ttu-id="61a6f-246">contoso.com</span><span class="sxs-lookup"><span data-stu-id="61a6f-246">contoso.com</span></span>
  - <span data-ttu-id="61a6f-247">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="61a6f-247">contoso.com/a</span></span>
  - <span data-ttu-id="61a6f-248">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="61a6f-248">payroll.contoso.com</span></span>
  - <span data-ttu-id="61a6f-249">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="61a6f-249">test.com/contoso.com</span></span>
  - <span data-ttu-id="61a6f-250">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="61a6f-250">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="61a6f-251">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="61a6f-251">www.contoso.com</span></span>
  - <span data-ttu-id="61a6f-252">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="61a6f-252">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="61a6f-253">**차단과 일치하지 않는**: abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="61a6f-253">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="61a6f-254">시나리오: 왼쪽 와일드카드(하위 도메인)</span><span class="sxs-lookup"><span data-stu-id="61a6f-254">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="61a6f-255">**항목:**`*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="61a6f-255">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="61a6f-256">**일치 및** 차단 **일치 허용**:</span><span class="sxs-lookup"><span data-stu-id="61a6f-256">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="61a6f-257">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="61a6f-257">www.contoso.com</span></span>
  - <span data-ttu-id="61a6f-258">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="61a6f-258">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="61a6f-259">**일치하지 않음 및 차단이** **일치하지 않음:**</span><span class="sxs-lookup"><span data-stu-id="61a6f-259">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="61a6f-260">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="61a6f-260">123contoso.com</span></span>
  - <span data-ttu-id="61a6f-261">contoso.com</span><span class="sxs-lookup"><span data-stu-id="61a6f-261">contoso.com</span></span>
  - <span data-ttu-id="61a6f-262">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="61a6f-262">test.com/contoso.com</span></span>
  - <span data-ttu-id="61a6f-263">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="61a6f-263">www.contoso.com/abc</span></span>
  
#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="61a6f-264">시나리오: 경로의 위쪽와 일드카드 오른쪽</span><span class="sxs-lookup"><span data-stu-id="61a6f-264">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="61a6f-265">**항목:**`contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="61a6f-265">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="61a6f-266">**일치 및** 차단 **일치 허용**:</span><span class="sxs-lookup"><span data-stu-id="61a6f-266">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="61a6f-267">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="61a6f-267">contoso.com/a/b</span></span>
  - <span data-ttu-id="61a6f-268">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="61a6f-268">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="61a6f-269">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="61a6f-269">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="61a6f-270">**일치하지 않음 및 차단이** **일치하지 않음:**</span><span class="sxs-lookup"><span data-stu-id="61a6f-270">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="61a6f-271">contoso.com</span><span class="sxs-lookup"><span data-stu-id="61a6f-271">contoso.com</span></span>
  - <span data-ttu-id="61a6f-272">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="61a6f-272">contoso.com/a</span></span>
  - <span data-ttu-id="61a6f-273">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="61a6f-273">www.contoso.com</span></span>
  - <span data-ttu-id="61a6f-274">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="61a6f-274">www.contoso.com/q=a@contoso.com</span></span>
  
#### <a name="scenario-left-tilde"></a><span data-ttu-id="61a6f-275">시나리오: 왼쪽 자동열드</span><span class="sxs-lookup"><span data-stu-id="61a6f-275">Scenario: Left tilde</span></span>

<span data-ttu-id="61a6f-276">**항목:**`~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="61a6f-276">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="61a6f-277">**일치 및** 차단 **일치 허용**:</span><span class="sxs-lookup"><span data-stu-id="61a6f-277">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="61a6f-278">contoso.com</span><span class="sxs-lookup"><span data-stu-id="61a6f-278">contoso.com</span></span>
  - <span data-ttu-id="61a6f-279">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="61a6f-279">www.contoso.com</span></span>
  - <span data-ttu-id="61a6f-280">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="61a6f-280">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="61a6f-281">**일치하지 않음 및 차단이** **일치하지 않음:**</span><span class="sxs-lookup"><span data-stu-id="61a6f-281">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="61a6f-282">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="61a6f-282">123contoso.com</span></span>
  - <span data-ttu-id="61a6f-283">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="61a6f-283">contoso.com/abc</span></span>
  - <span data-ttu-id="61a6f-284">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="61a6f-284">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="61a6f-285">시나리오: 오른쪽 와일드카드 접미사</span><span class="sxs-lookup"><span data-stu-id="61a6f-285">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="61a6f-286">**항목:**`contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="61a6f-286">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="61a6f-287">**일치 및** 차단 **일치 허용**:</span><span class="sxs-lookup"><span data-stu-id="61a6f-287">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="61a6f-288">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="61a6f-288">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="61a6f-289">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="61a6f-289">contoso.com/a</span></span>
  - <span data-ttu-id="61a6f-290">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="61a6f-290">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="61a6f-291">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="61a6f-291">contoso.com/ab</span></span>
  - <span data-ttu-id="61a6f-292">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="61a6f-292">contoso.com/b</span></span>
  - <span data-ttu-id="61a6f-293">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="61a6f-293">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="61a6f-294">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="61a6f-294">contoso.com/ba</span></span>

- <span data-ttu-id="61a6f-295">**일치하지 않음 및** **차단이 일치하지 않음:** contoso.com</span><span class="sxs-lookup"><span data-stu-id="61a6f-295">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="61a6f-296">시나리오: 왼쪽 와일드카드 하위 도메인 및 오른쪽 와일드카드 접미사</span><span class="sxs-lookup"><span data-stu-id="61a6f-296">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="61a6f-297">**항목:**`*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="61a6f-297">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="61a6f-298">**일치 및** 차단 **일치 허용**:</span><span class="sxs-lookup"><span data-stu-id="61a6f-298">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="61a6f-299">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="61a6f-299">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="61a6f-300">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="61a6f-300">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="61a6f-301">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="61a6f-301">www.contoso.com/a</span></span>
  - <span data-ttu-id="61a6f-302">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="61a6f-302">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="61a6f-303">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="61a6f-303">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="61a6f-304">**일치하지 않음 및** **차단이 일치하지 않음:** contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="61a6f-304">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="61a6f-305">시나리오: 왼쪽 및 오른쪽 가로 표시</span><span class="sxs-lookup"><span data-stu-id="61a6f-305">Scenario: Left and right tilde</span></span>

<span data-ttu-id="61a6f-306">**항목:**`~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="61a6f-306">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="61a6f-307">**일치 및** 차단 **일치 허용**:</span><span class="sxs-lookup"><span data-stu-id="61a6f-307">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="61a6f-308">contoso.com</span><span class="sxs-lookup"><span data-stu-id="61a6f-308">contoso.com</span></span>
  - <span data-ttu-id="61a6f-309">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="61a6f-309">contoso.com/a</span></span>
  - <span data-ttu-id="61a6f-310">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="61a6f-310">www.contoso.com</span></span>
  - <span data-ttu-id="61a6f-311">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="61a6f-311">www.contoso.com/b</span></span>
  - <span data-ttu-id="61a6f-312">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="61a6f-312">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="61a6f-313">**일치하지 않음 및 차단이** **일치하지 않음:**</span><span class="sxs-lookup"><span data-stu-id="61a6f-313">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="61a6f-314">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="61a6f-314">123contoso.com</span></span>
  - <span data-ttu-id="61a6f-315">contoso.org</span><span class="sxs-lookup"><span data-stu-id="61a6f-315">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="61a6f-316">시나리오: IP 주소</span><span class="sxs-lookup"><span data-stu-id="61a6f-316">Scenario: IP address</span></span>

<span data-ttu-id="61a6f-317">**항목:**`1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="61a6f-317">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="61a6f-318">**일치 및** **차단 일치 허용**: 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="61a6f-318">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="61a6f-319">**일치하지 않음 및 차단이** **일치하지 않음:**</span><span class="sxs-lookup"><span data-stu-id="61a6f-319">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="61a6f-320">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="61a6f-320">1.2.3.4/a</span></span>
  - <span data-ttu-id="61a6f-321">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="61a6f-321">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="61a6f-322">오른쪽 와일드카드를 사용한 IP 주소</span><span class="sxs-lookup"><span data-stu-id="61a6f-322">IP address with right wildcard</span></span>

<span data-ttu-id="61a6f-323">**항목:**`1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="61a6f-323">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="61a6f-324">**일치 및** 차단 **일치 허용**:</span><span class="sxs-lookup"><span data-stu-id="61a6f-324">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="61a6f-325">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="61a6f-325">1.2.3.4/b</span></span>
  - <span data-ttu-id="61a6f-326">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="61a6f-326">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="61a6f-327">잘못된 항목의 예</span><span class="sxs-lookup"><span data-stu-id="61a6f-327">Examples of invalid entries</span></span>

<span data-ttu-id="61a6f-328">다음 항목은 유효하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="61a6f-328">The following entries are invalid:</span></span>

- <span data-ttu-id="61a6f-329">**누락되어 있거나 잘못된 도메인 값:**</span><span class="sxs-lookup"><span data-stu-id="61a6f-329">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="61a6f-330">contoso</span><span class="sxs-lookup"><span data-stu-id="61a6f-330">contoso</span></span>
  - <span data-ttu-id="61a6f-331">\*.contoso.\*</span><span class="sxs-lookup"><span data-stu-id="61a6f-331">\*.contoso.\*</span></span>
  - <span data-ttu-id="61a6f-332">\*.com</span><span class="sxs-lookup"><span data-stu-id="61a6f-332">\*.com</span></span>
  - <span data-ttu-id="61a6f-333">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="61a6f-333">\*.pdf</span></span>

- <span data-ttu-id="61a6f-334">**텍스트또는 간격 지시 문자 없는 와일드카드:**</span><span class="sxs-lookup"><span data-stu-id="61a6f-334">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="61a6f-335">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="61a6f-335">\*contoso.com</span></span>
  - <span data-ttu-id="61a6f-336">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="61a6f-336">contoso.com\*</span></span>
  - <span data-ttu-id="61a6f-337">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="61a6f-337">\*1.2.3.4</span></span>
  - <span data-ttu-id="61a6f-338">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="61a6f-338">1.2.3.4\*</span></span>
  - <span data-ttu-id="61a6f-339">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="61a6f-339">contoso.com/a\*</span></span>
  - <span data-ttu-id="61a6f-340">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="61a6f-340">contoso.com/ab\*</span></span>

- <span data-ttu-id="61a6f-341">**포트를 사용한 IP 주소:**</span><span class="sxs-lookup"><span data-stu-id="61a6f-341">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="61a6f-342">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="61a6f-342">contoso.com:443</span></span>
  - <span data-ttu-id="61a6f-343">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="61a6f-343">abc.contoso.com:25</span></span>

- <span data-ttu-id="61a6f-344">**설명이 없는 와일드카드:**</span><span class="sxs-lookup"><span data-stu-id="61a6f-344">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="61a6f-345">\*.\*</span><span class="sxs-lookup"><span data-stu-id="61a6f-345">\*.\*</span></span>

- <span data-ttu-id="61a6f-346">**중간 와일드카드:**</span><span class="sxs-lookup"><span data-stu-id="61a6f-346">**Middle wildcards**:</span></span>

  - <span data-ttu-id="61a6f-347">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="61a6f-347">conto\*so.com</span></span>
  - <span data-ttu-id="61a6f-348">conto~so.com</span><span class="sxs-lookup"><span data-stu-id="61a6f-348">conto~so.com</span></span>

- <span data-ttu-id="61a6f-349">**이중 와일드카드**</span><span class="sxs-lookup"><span data-stu-id="61a6f-349">**Double wildcards**</span></span>

  - <span data-ttu-id="61a6f-350">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="61a6f-350">contoso.com/\*\*</span></span>
  - <span data-ttu-id="61a6f-351">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="61a6f-351">contoso.com/\*/\*</span></span>
