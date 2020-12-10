---
title: 테넌트 허용/차단 목록에서 허용 및 차단된 URL 관리
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
description: 관리자는 보안 및 준수 센터의 테넌트 허용/차단 목록에서 URL & 수 있습니다.
ms.openlocfilehash: 0fdfa23ba22b240032e7a6888948de180aa0f6ae
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49614967"
---
# <a name="manage-urls-in-the-tenant-allowblock-list"></a><span data-ttu-id="0b12a-103">테넌트 허용/차단 목록의 URL 관리</span><span class="sxs-lookup"><span data-stu-id="0b12a-103">Manage URLs in the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="0b12a-104">이 항목에 설명된 기능은 미리 보기로 제공되어 있으며 변경될 수 있으며 일부 조직에서는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-104">The features described in this topic are in Preview, are subject to change, and are not available in all organizations.</span></span>

<span data-ttu-id="0b12a-105">Exchange Online 사서함이 있는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에서는 EOP 필터링 판정에 동의하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="0b12a-106">예를 들어 좋은 메시지는 나쁜 메시지(가음성)로 표시되거나 잘못된 메시지가 통과(거짓 부정)될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-106">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="0b12a-107">보안 및 규정 준수 센터의 테넌트 허용/차단 & Microsoft 365 필터링 판정을 수동으로 다시우는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-107">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="0b12a-108">테넌트 허용/차단 목록은 메일 흐름 중과 사용자가 클릭할 때 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-108">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="0b12a-109">테넌트 허용/차단 목록에서 허용하거나 차단할 URL을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-109">You can specify URLs to allow or block in the Tenant Allow/Block List.</span></span>

<span data-ttu-id="0b12a-110">이 항목에서는 보안 & 준수 센터 또는 PowerShell(Exchange Online에 사서함이 있는 Microsoft 365 조직용 Exchange Online PowerShell, Exchange Online 사서함이 없는 조직의 독립 실행형 EOP PowerShell)에서 테넌트 허용/차단 목록의 항목을 구성하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-110">This topic describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="0b12a-111">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="0b12a-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="0b12a-112"><https://protection.office.com/>에서 보안 및 준수 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="0b12a-113">테넌트 **허용/차단** 목록 페이지로 직접 이동하기 위해 <https://protection.office.com/tenantAllowBlockList> 다음을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="0b12a-113">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="0b12a-114">사용 가능한 URL 값은 이 항목 부분의 테넌트 [허용/차단 목록 섹션에](#url-syntax-for-the-tenant-allowblock-list) 대한 URL 구문에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-114">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

- <span data-ttu-id="0b12a-115">테넌트 허용/차단 목록에는 URL에 최대 500개 항목이 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-115">The Tenant Allow/Block List allows a maximum of 500 entries for URLs.</span></span>

- <span data-ttu-id="0b12a-116">15분 이내에 항목이 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-116">An entry should be active within 15 minutes.</span></span>

- <span data-ttu-id="0b12a-117">차단 항목은 허용 항목보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-117">Block entries take precedence over allow entries.</span></span>

- <span data-ttu-id="0b12a-118">기본적으로 테넌트 허용/차단 목록의 항목은 30일 후에 만료됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-118">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="0b12a-119">날짜를 지정하거나 만료되지 않는 것으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-119">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="0b12a-120">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0b12a-120">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="0b12a-121">독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0b12a-121">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="0b12a-122">이 문서의 절차를 수행하려면 먼저 보안 및 준수 센터에서 사용 권한을 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-122">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="0b12a-123">테넌트 허용/차단 목록에서 값을 추가하고 제거하려면 **조직** 관리 또는 보안 관리자 역할 그룹의 **구성원이** 되거나 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-123">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="0b12a-124">테넌트 허용/차단 목록에 대한 읽기 전용 액세스 권한을 사용하려면  전역 읽기 또는 보안 읽기 권한이 있는 사용자 역할 그룹의 **구성원이면** 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-124">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="0b12a-125">자세한 내용은 [보안 및 준수 센터의 사용 권한](permissions-in-the-security-and-compliance-center.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0b12a-125">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="0b12a-126">**참고**:</span><span class="sxs-lookup"><span data-stu-id="0b12a-126">**Notes**:</span></span>

  - <span data-ttu-id="0b12a-127">Microsoft 365 관리 센터의 해당 Azure Active Directory 역할에 사용자를 추가하면 사용자에게 보안 및 준수 센터에서 필요한 권한 _및_ Microsoft 365의 다른 기능에 대한 권한이 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-127">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="0b12a-128">자세한 내용은 [관리자 역할 정보](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0b12a-128">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="0b12a-129">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **보기 전용 조직 관리** 역할 그룹에도 기능에 대한 읽기 전용 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-129">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="0b12a-130">보안 및 & 센터를 사용하여 테넌트 허용/차단 목록에 URL 항목 만들기</span><span class="sxs-lookup"><span data-stu-id="0b12a-130">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="0b12a-131">URL 항목의 구문에 대한 자세한 내용은 이 항목 부분의 [테넌트 허용/차단 목록 섹션에](#url-syntax-for-the-tenant-allowblock-list) 대한 URL 구문을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0b12a-131">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

1. <span data-ttu-id="0b12a-132">보안 & 준수 센터에서 위협 **관리** 정책 \>  \> **테넌트 허용/차단 목록으로 이동하십시오.**</span><span class="sxs-lookup"><span data-stu-id="0b12a-132">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="0b12a-133">**테넌트 허용/차단 목록** 페이지에서 **URL** 탭이 선택되어 있는지 확인한 다음 **추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="0b12a-133">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Add**</span></span>

3. <span data-ttu-id="0b12a-134">나타나는 **새 URL** 추가 플라이아웃에서 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-134">In the **Add new URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="0b12a-135">**와일드카드를** 사용하여 URL 추가: 줄당 URL을 하나씩 입력하고 최대 20개까지 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-135">**Add URLs with wildcards**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="0b12a-136">**차단/허용:** 지정한 URL을  허용할지 차단할지 여부를 선택합니다. </span><span class="sxs-lookup"><span data-stu-id="0b12a-136">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified URLs.</span></span>

   - <span data-ttu-id="0b12a-137">**만료 안 하세요.** 다음 단계 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-137">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="0b12a-138">설정이 꺼져 있는지 확인하고(토글 해제) 만료 상자를 사용하여 항목의 만료 ![ ](../../media/scc-toggle-off.png) 날짜를 지정합니다. </span><span class="sxs-lookup"><span data-stu-id="0b12a-138">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="0b12a-139">또는</span><span class="sxs-lookup"><span data-stu-id="0b12a-139">or</span></span>

     - <span data-ttu-id="0b12a-140">토글을 오른쪽으로 이동하여 항목이 만료되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-140">Move the toggle to the right to configure the entries to never expire:</span></span> ![토글 켬](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="0b12a-142">.</span><span class="sxs-lookup"><span data-stu-id="0b12a-142">.</span></span>

   - <span data-ttu-id="0b12a-143">**선택 사항**: 항목에 대한 설명 텍스트를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-143">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="0b12a-144">완료되면 추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="0b12a-144">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="0b12a-145">보안 및 & 센터를 사용하여 테넌트 허용/차단 목록의 항목 보기</span><span class="sxs-lookup"><span data-stu-id="0b12a-145">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="0b12a-146">보안 & 준수 센터에서 위협 **관리** 정책 \>  \> **테넌트 허용/차단 목록으로 이동하십시오.**</span><span class="sxs-lookup"><span data-stu-id="0b12a-146">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="0b12a-147">URL **탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-147">Select the **URLs** tab.</span></span>

<span data-ttu-id="0b12a-148">다음 열 머리 단추를 클릭하여 오차 또는 내선 순서로 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-148">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="0b12a-149">**값**</span><span class="sxs-lookup"><span data-stu-id="0b12a-149">**Value**</span></span>
- <span data-ttu-id="0b12a-150">**작업:** **차단** **또는** 허용.</span><span class="sxs-lookup"><span data-stu-id="0b12a-150">**Action**: **Block** or **Allow**.</span></span>
- <span data-ttu-id="0b12a-151">**마지막 업데이트 날짜**</span><span class="sxs-lookup"><span data-stu-id="0b12a-151">**Last updated date**</span></span>
- <span data-ttu-id="0b12a-152">**만료 날짜**</span><span class="sxs-lookup"><span data-stu-id="0b12a-152">**Expiration date**</span></span>
- <span data-ttu-id="0b12a-153">**참고**</span><span class="sxs-lookup"><span data-stu-id="0b12a-153">**Note**</span></span>

<span data-ttu-id="0b12a-154">그룹을 **클릭하여** 작업(차단  또는 **허용)** 또는 없음으로 항목을 **그룹화합니다.**</span><span class="sxs-lookup"><span data-stu-id="0b12a-154">Click **Group** to group the entries by **Action** (**Block** or **Allow**) or **None**.</span></span>

<span data-ttu-id="0b12a-155">검색을 **클릭하고** 값의 전체 또는 일부를 입력한 다음 Enter를 눌러 특정 값을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-155">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="0b12a-156">완료되면 검색 지우기 **검색 아이콘을** ![ ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-156">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="0b12a-157">필터를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="0b12a-157">Click **Filter**.</span></span> <span data-ttu-id="0b12a-158">필터  플라이아웃이 나타나면 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-158">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="0b12a-159">**작업:** **허용,** **차단** 또는 둘 다를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-159">**Action**: Select **Allow**, **Block** or both.</span></span>

- <span data-ttu-id="0b12a-160">**만료되지 않습니다.**(해제) 또는 ![ ](../../media/scc-toggle-off.png) (토글 ![ 끄기) 를 ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-160">**Never expire**: Select off (![Toggle off](../../media/scc-toggle-off.png)) or on (![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)).</span></span>

- <span data-ttu-id="0b12a-161">**Last updated**: Select a start date **(From),** an end date (**To)** or both.</span><span class="sxs-lookup"><span data-stu-id="0b12a-161">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="0b12a-162">**만료 날짜:** 시작 날짜(시작 **날짜),** 종료 날짜(끝 **날짜)** 또는 둘 다를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-162">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="0b12a-163">완료되면 적용을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="0b12a-163">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="0b12a-164">기존 필터를 지우려면 **필터를** 클릭하고 나타나는 필터  플라이아웃에서 필터 **지우기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="0b12a-164">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="0b12a-165">보안 및 & 센터를 사용하여 테넌트 허용/차단 목록의 항목 수정</span><span class="sxs-lookup"><span data-stu-id="0b12a-165">Use the Security & Compliance Center to modify entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="0b12a-166">URL 값 자체는 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-166">You can't modify the URL value itself.</span></span> <span data-ttu-id="0b12a-167">대신 항목을 삭제하고 다시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-167">Instead, you need to delete the entry and recreate it.</span></span>

1. <span data-ttu-id="0b12a-168">보안 & 준수 센터에서 위협 **관리** 정책 \>  \> **테넌트 허용/차단 목록으로 이동하십시오.**</span><span class="sxs-lookup"><span data-stu-id="0b12a-168">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="0b12a-169">URL **탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-169">Select the **URLs** tab.</span></span>

3. <span data-ttu-id="0b12a-170">수정할 항목을 선택하고 편집  ![ 아이콘을 ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-170">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="0b12a-171">플라이아웃이 나타나면 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-171">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="0b12a-172">**차단/허용:** 허용 **또는 차단을** **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0b12a-172">**Block/Allow**: Select **Allow** or **Block**.</span></span>

   - <span data-ttu-id="0b12a-173">**만료 안 하세요.** 다음 단계 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-173">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="0b12a-174">설정이 꺼져 있는지(토글 해제) 확인란을 사용하여 항목의 만료 날짜를 ![ ](../../media/scc-toggle-off.png) 지정합니다. </span><span class="sxs-lookup"><span data-stu-id="0b12a-174">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

     <span data-ttu-id="0b12a-175">또는</span><span class="sxs-lookup"><span data-stu-id="0b12a-175">or</span></span>

     - <span data-ttu-id="0b12a-176">토글을 오른쪽으로 이동하여 항목이 만료되지 못하도록 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-176">Move the toggle to the right to configure the entry to never expire:</span></span> ![토글 켬](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="0b12a-178">.</span><span class="sxs-lookup"><span data-stu-id="0b12a-178">.</span></span>

   - <span data-ttu-id="0b12a-179">**선택 사항**: 항목에 대한 설명 텍스트를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-179">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="0b12a-180">작업을 마쳤으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-180">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="0b12a-181">보안 및 & 센터를 사용하여 테넌트 허용/차단 목록에서 항목 제거</span><span class="sxs-lookup"><span data-stu-id="0b12a-181">Use the Security & Compliance Center to remove entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="0b12a-182">보안 & 준수 센터에서 위협 **관리** 정책 \>  \> **테넌트 허용/차단 목록으로 이동하십시오.**</span><span class="sxs-lookup"><span data-stu-id="0b12a-182">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="0b12a-183">URL **탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-183">Select the **URLs** tab.</span></span>

3. <span data-ttu-id="0b12a-184">제거할 항목을 선택하고 삭제 **아이콘을** ![ ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-184">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="0b12a-185">나타나는 경고 대화 상자에서 삭제를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="0b12a-185">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="0b12a-186">Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell을 사용하여 테넌트 허용/차단 목록 구성</span><span class="sxs-lookup"><span data-stu-id="0b12a-186">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="0b12a-187">PowerShell을 사용하여 테넌트 허용/차단 목록의 항목 추가</span><span class="sxs-lookup"><span data-stu-id="0b12a-187">Use PowerShell to add entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="0b12a-188">테넌트 허용/차단 목록에 항목을 추가하기 위해 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="0b12a-188">To add entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="0b12a-189">이 예제에서는 contoso.com 및 모든 하위 contoso.com, www.contoso.com 및 하위 xyz.abc.contoso.com URL 블록 항목을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-189">This example adds a URL block entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="0b12a-190">ExpirationDate 또는 NoExpiration 매개 변수를 사용하지 않았기 때문에 항목이 30일 후에 만료됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-190">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

<span data-ttu-id="0b12a-191">구문과 매개 변수에 대한 자세한 내용은 [New-TenantAllowBlockListItems를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="0b12a-191">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="0b12a-192">PowerShell을 사용하여 테넌트 허용/차단 목록의 항목 보기</span><span class="sxs-lookup"><span data-stu-id="0b12a-192">Use PowerShell to view entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="0b12a-193">테넌트 허용/차단 목록의 항목을 표시하기 위해 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="0b12a-193">To view entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url [-Entry <URLValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="0b12a-194">이 예제에서는 차단된 URL을 모두 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-194">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

<span data-ttu-id="0b12a-195">구문과 매개 변수에 대한 자세한 내용은 [Get-TenantAllowBlockListItems를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="0b12a-195">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="0b12a-196">PowerShell을 사용하여 테넌트 허용/차단 목록의 항목 수정</span><span class="sxs-lookup"><span data-stu-id="0b12a-196">Use PowerShell to modify entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="0b12a-197">URL 값 자체는 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-197">You can't modify the URL value itself.</span></span> <span data-ttu-id="0b12a-198">대신 항목을 삭제하고 다시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-198">Instead, you need to delete the entry and recreate it.</span></span>

<span data-ttu-id="0b12a-199">테넌트 허용/차단 목록의 항목을 수정하려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="0b12a-199">To modify entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="0b12a-200">이 예제에서는 지정한 항목의 만료 날짜를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-200">This example changes the expiration date of the specified entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="0b12a-201">구문과 매개 변수에 대한 자세한 내용은 [Set-TenantAllowBlockListItems를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="0b12a-201">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="0b12a-202">PowerShell을 사용하여 테넌트 허용/차단 목록에서 항목 제거</span><span class="sxs-lookup"><span data-stu-id="0b12a-202">Use PowerShell to remove entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="0b12a-203">테넌트 허용/차단 목록에서 항목을 제거하려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="0b12a-203">To remove entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="0b12a-204">이 예에서는 테넌트 허용/차단 목록에서 지정된 URL 항목을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-204">This example removes the specified URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="0b12a-205">구문과 매개 변수에 대한 자세한 내용은 [Remove-TenantAllowBlockListItems를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="0b12a-205">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="0b12a-206">테넌트 허용/차단 목록에 대한 URL 구문</span><span class="sxs-lookup"><span data-stu-id="0b12a-206">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="0b12a-207">IP4v 및 IPv6 주소는 허용되지만 TCP/UDP 포트는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-207">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="0b12a-208">파일 이름 확장명은 허용되지 않습니다(예: test.pdf.</span><span class="sxs-lookup"><span data-stu-id="0b12a-208">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="0b12a-209">유니코드는 지원되지 않지만 Punycode는 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-209">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="0b12a-210">다음 명령문이 모두 true이면 호스트 이름을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-210">Hostnames are allowed if all of the following statements are true:</span></span>

  - <span data-ttu-id="0b12a-211">호스트 이름에 기간이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-211">The hostname contains a period.</span></span>
  - <span data-ttu-id="0b12a-212">기간 왼쪽에 하나 이상의 문자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-212">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="0b12a-213">기간의 오른쪽에 두 개 이상의 문자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-213">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="0b12a-214">예를 들어 허용되거나 `t.co` `.com` 허용되지 `contoso.` 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-214">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="0b12a-215">하위 경로는 암시적이지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-215">Subpaths are not implied.</span></span>

  <span data-ttu-id="0b12a-216">예를 들어 `contoso.com` . `contoso.com/a`</span><span class="sxs-lookup"><span data-stu-id="0b12a-216">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="0b12a-217">와일드카드(\*)는 다음 시나리오에서 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-217">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="0b12a-218">하위omain을 지정하려면 왼쪽 와일드카드 다음에 기간이 와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-218">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="0b12a-219">예를 들어 `*.contoso.com` 허용됩니다. `*contoso.com` 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-219">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="0b12a-220">오른쪽 와일드카드는 슬래시(/)를 따라 경로를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-220">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="0b12a-221">예를 들어 허용되거나 `contoso.com/*` `contoso.com*` 허용되지 `contoso.com/ab*` 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-221">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="0b12a-222">모든 하위 경로는 오른쪽 와일드카드로 암시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-222">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="0b12a-223">예를 들어 `contoso.com/*` . `contoso.com/a`</span><span class="sxs-lookup"><span data-stu-id="0b12a-223">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="0b12a-224">`*.com*` 가 잘못되었습니다(확인 가능한 도메인이 아니며 오른쪽 와일드카드가 슬래시를 따르지 않습니다).</span><span class="sxs-lookup"><span data-stu-id="0b12a-224">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="0b12a-225">와일드카드는 IP 주소에서 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-225">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="0b12a-226">다음과 같은 시나리오에서 선조(~) 문자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-226">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="0b12a-227">왼쪽 누적은 도메인 및 모든 하위 도메인을 암시합니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-227">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="0b12a-228">예를 들어 `~contoso.com` 다음을 `contoso.com` `*.contoso.com` 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-228">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="0b12a-229">URL 항목은 모든 프로토콜에 적용될 수 있기 때문에 프로토콜(예: 또는 )이 포함된 URL 항목은 `http://` `https://` `ftp://` 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-229">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="0b12a-230">사용자 이름 또는 암호는 지원되거나 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-230">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="0b12a-231">따옴표(' 또는 ")는 잘못된 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-231">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="0b12a-232">URL에는 가능한 경우 모든 리디렉션이 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-232">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="0b12a-233">URL 입력 시나리오</span><span class="sxs-lookup"><span data-stu-id="0b12a-233">URL entry scenarios</span></span>

<span data-ttu-id="0b12a-234">유효한 URL 항목 및 해당 결과는 다음 섹션에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-234">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="0b12a-235">시나리오: 와일드카드 없음</span><span class="sxs-lookup"><span data-stu-id="0b12a-235">Scenario: No wildcards</span></span>

<span data-ttu-id="0b12a-236">**항목:**`contoso.com`</span><span class="sxs-lookup"><span data-stu-id="0b12a-236">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="0b12a-237">**일치 허용**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="0b12a-237">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="0b12a-238">**일치하지 않는 경우:**</span><span class="sxs-lookup"><span data-stu-id="0b12a-238">**Allow not matched**:</span></span>

  - <span data-ttu-id="0b12a-239">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="0b12a-239">abc-contoso.com</span></span>
  - <span data-ttu-id="0b12a-240">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="0b12a-240">contoso.com/a</span></span>
  - <span data-ttu-id="0b12a-241">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0b12a-241">payroll.contoso.com</span></span>
  - <span data-ttu-id="0b12a-242">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="0b12a-242">test.com/contoso.com</span></span>
  - <span data-ttu-id="0b12a-243">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="0b12a-243">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="0b12a-244">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0b12a-244">www.contoso.com</span></span>
  - <span data-ttu-id="0b12a-245">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="0b12a-245">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="0b12a-246">**블록 일치**:</span><span class="sxs-lookup"><span data-stu-id="0b12a-246">**Block match**:</span></span>

  - <span data-ttu-id="0b12a-247">contoso.com</span><span class="sxs-lookup"><span data-stu-id="0b12a-247">contoso.com</span></span>
  - <span data-ttu-id="0b12a-248">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="0b12a-248">contoso.com/a</span></span>
  - <span data-ttu-id="0b12a-249">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0b12a-249">payroll.contoso.com</span></span>
  - <span data-ttu-id="0b12a-250">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="0b12a-250">test.com/contoso.com</span></span>
  - <span data-ttu-id="0b12a-251">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="0b12a-251">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="0b12a-252">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0b12a-252">www.contoso.com</span></span>
  - <span data-ttu-id="0b12a-253">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="0b12a-253">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="0b12a-254">**블록이 일치하지 않는 경우**: abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="0b12a-254">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="0b12a-255">시나리오: 왼쪽 와일드카드(하위omain)</span><span class="sxs-lookup"><span data-stu-id="0b12a-255">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="0b12a-256">**항목:**`*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="0b12a-256">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="0b12a-257">**일치 및** **차단 일치 허용**:</span><span class="sxs-lookup"><span data-stu-id="0b12a-257">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="0b12a-258">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0b12a-258">www.contoso.com</span></span>
  - <span data-ttu-id="0b12a-259">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0b12a-259">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="0b12a-260">**일치하지 않는 허용** 및 **차단이 일치하지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="0b12a-260">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="0b12a-261">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="0b12a-261">123contoso.com</span></span>
  - <span data-ttu-id="0b12a-262">contoso.com</span><span class="sxs-lookup"><span data-stu-id="0b12a-262">contoso.com</span></span>
  - <span data-ttu-id="0b12a-263">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="0b12a-263">test.com/contoso.com</span></span>
  - <span data-ttu-id="0b12a-264">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="0b12a-264">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="0b12a-265">시나리오: 경로 맨 위에 있는 오른쪽 와일드카드</span><span class="sxs-lookup"><span data-stu-id="0b12a-265">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="0b12a-266">**항목:**`contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="0b12a-266">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="0b12a-267">**일치 및** **차단 일치 허용**:</span><span class="sxs-lookup"><span data-stu-id="0b12a-267">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="0b12a-268">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="0b12a-268">contoso.com/a/b</span></span>
  - <span data-ttu-id="0b12a-269">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="0b12a-269">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="0b12a-270">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="0b12a-270">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="0b12a-271">**일치하지 않는 허용** 및 **차단이 일치하지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="0b12a-271">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="0b12a-272">contoso.com</span><span class="sxs-lookup"><span data-stu-id="0b12a-272">contoso.com</span></span>
  - <span data-ttu-id="0b12a-273">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="0b12a-273">contoso.com/a</span></span>
  - <span data-ttu-id="0b12a-274">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0b12a-274">www.contoso.com</span></span>
  - <span data-ttu-id="0b12a-275">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="0b12a-275">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="0b12a-276">시나리오: 왼쪽으로 밀기</span><span class="sxs-lookup"><span data-stu-id="0b12a-276">Scenario: Left tilde</span></span>

<span data-ttu-id="0b12a-277">**항목:**`~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="0b12a-277">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="0b12a-278">**일치 및** **차단 일치 허용**:</span><span class="sxs-lookup"><span data-stu-id="0b12a-278">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="0b12a-279">contoso.com</span><span class="sxs-lookup"><span data-stu-id="0b12a-279">contoso.com</span></span>
  - <span data-ttu-id="0b12a-280">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0b12a-280">www.contoso.com</span></span>
  - <span data-ttu-id="0b12a-281">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0b12a-281">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="0b12a-282">**일치하지 않는 허용** 및 **차단이 일치하지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="0b12a-282">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="0b12a-283">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="0b12a-283">123contoso.com</span></span>
  - <span data-ttu-id="0b12a-284">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="0b12a-284">contoso.com/abc</span></span>
  - <span data-ttu-id="0b12a-285">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="0b12a-285">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="0b12a-286">시나리오: 오른쪽 와일드카드 접미사</span><span class="sxs-lookup"><span data-stu-id="0b12a-286">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="0b12a-287">**항목:**`contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="0b12a-287">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="0b12a-288">**일치 및** **차단 일치 허용**:</span><span class="sxs-lookup"><span data-stu-id="0b12a-288">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="0b12a-289">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="0b12a-289">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="0b12a-290">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="0b12a-290">contoso.com/a</span></span>
  - <span data-ttu-id="0b12a-291">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="0b12a-291">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="0b12a-292">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="0b12a-292">contoso.com/ab</span></span>
  - <span data-ttu-id="0b12a-293">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="0b12a-293">contoso.com/b</span></span>
  - <span data-ttu-id="0b12a-294">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="0b12a-294">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="0b12a-295">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="0b12a-295">contoso.com/ba</span></span>

- <span data-ttu-id="0b12a-296">**일치하지 않는 허용** 및 **일치하지 않는** 차단 : contoso.com</span><span class="sxs-lookup"><span data-stu-id="0b12a-296">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="0b12a-297">시나리오: 왼쪽 와일드카드 하위omain 및 오른쪽 와일드카드 접미사</span><span class="sxs-lookup"><span data-stu-id="0b12a-297">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="0b12a-298">**항목:**`*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="0b12a-298">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="0b12a-299">**일치 및** **차단 일치 허용**:</span><span class="sxs-lookup"><span data-stu-id="0b12a-299">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="0b12a-300">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="0b12a-300">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="0b12a-301">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="0b12a-301">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="0b12a-302">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="0b12a-302">www.contoso.com/a</span></span>
  - <span data-ttu-id="0b12a-303">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="0b12a-303">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="0b12a-304">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="0b12a-304">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="0b12a-305">**일치하지 않는 허용** 및 **일치하지 않는** 차단 : contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="0b12a-305">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="0b12a-306">시나리오: 왼쪽 및 오른쪽 바른 바른 선</span><span class="sxs-lookup"><span data-stu-id="0b12a-306">Scenario: Left and right tilde</span></span>

<span data-ttu-id="0b12a-307">**항목:**`~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="0b12a-307">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="0b12a-308">**일치 및** **차단 일치 허용**:</span><span class="sxs-lookup"><span data-stu-id="0b12a-308">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="0b12a-309">contoso.com</span><span class="sxs-lookup"><span data-stu-id="0b12a-309">contoso.com</span></span>
  - <span data-ttu-id="0b12a-310">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="0b12a-310">contoso.com/a</span></span>
  - <span data-ttu-id="0b12a-311">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0b12a-311">www.contoso.com</span></span>
  - <span data-ttu-id="0b12a-312">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="0b12a-312">www.contoso.com/b</span></span>
  - <span data-ttu-id="0b12a-313">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0b12a-313">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="0b12a-314">**일치하지 않는 허용** 및 **차단이 일치하지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="0b12a-314">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="0b12a-315">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="0b12a-315">123contoso.com</span></span>
  - <span data-ttu-id="0b12a-316">contoso.org</span><span class="sxs-lookup"><span data-stu-id="0b12a-316">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="0b12a-317">시나리오: IP 주소</span><span class="sxs-lookup"><span data-stu-id="0b12a-317">Scenario: IP address</span></span>

<span data-ttu-id="0b12a-318">**항목:**`1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="0b12a-318">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="0b12a-319">**일치 및** **차단 일치** 허용 : 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="0b12a-319">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="0b12a-320">**일치하지 않는 허용** 및 **차단이 일치하지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="0b12a-320">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="0b12a-321">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="0b12a-321">1.2.3.4/a</span></span>
  - <span data-ttu-id="0b12a-322">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="0b12a-322">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="0b12a-323">오른쪽 와일드카드가 있는 IP 주소</span><span class="sxs-lookup"><span data-stu-id="0b12a-323">IP address with right wildcard</span></span>

<span data-ttu-id="0b12a-324">**항목:**`1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="0b12a-324">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="0b12a-325">**일치 및** **차단 일치 허용**:</span><span class="sxs-lookup"><span data-stu-id="0b12a-325">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="0b12a-326">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="0b12a-326">1.2.3.4/b</span></span>
  - <span data-ttu-id="0b12a-327">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="0b12a-327">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="0b12a-328">잘못된 항목의 예</span><span class="sxs-lookup"><span data-stu-id="0b12a-328">Examples of invalid entries</span></span>

<span data-ttu-id="0b12a-329">유효하지 않은 항목은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0b12a-329">The following entries are invalid:</span></span>

- <span data-ttu-id="0b12a-330">**누락되었거나 잘못된 도메인 값:**</span><span class="sxs-lookup"><span data-stu-id="0b12a-330">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="0b12a-331">contoso</span><span class="sxs-lookup"><span data-stu-id="0b12a-331">contoso</span></span>
  - <span data-ttu-id="0b12a-332">\*.contoso.\*</span><span class="sxs-lookup"><span data-stu-id="0b12a-332">\*.contoso.\*</span></span>
  - <span data-ttu-id="0b12a-333">\*.com</span><span class="sxs-lookup"><span data-stu-id="0b12a-333">\*.com</span></span>
  - <span data-ttu-id="0b12a-334">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="0b12a-334">\*.pdf</span></span>

- <span data-ttu-id="0b12a-335">**텍스트의 와일드카드:**</span><span class="sxs-lookup"><span data-stu-id="0b12a-335">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="0b12a-336">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="0b12a-336">\*contoso.com</span></span>
  - <span data-ttu-id="0b12a-337">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="0b12a-337">contoso.com\*</span></span>
  - <span data-ttu-id="0b12a-338">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="0b12a-338">\*1.2.3.4</span></span>
  - <span data-ttu-id="0b12a-339">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="0b12a-339">1.2.3.4\*</span></span>
  - <span data-ttu-id="0b12a-340">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="0b12a-340">contoso.com/a\*</span></span>
  - <span data-ttu-id="0b12a-341">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="0b12a-341">contoso.com/ab\*</span></span>

- <span data-ttu-id="0b12a-342">**포트가 있는 IP 주소:**</span><span class="sxs-lookup"><span data-stu-id="0b12a-342">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="0b12a-343">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="0b12a-343">contoso.com:443</span></span>
  - <span data-ttu-id="0b12a-344">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="0b12a-344">abc.contoso.com:25</span></span>

- <span data-ttu-id="0b12a-345">**설명하지 않는 와일드카드:**</span><span class="sxs-lookup"><span data-stu-id="0b12a-345">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="0b12a-346">\*.\*</span><span class="sxs-lookup"><span data-stu-id="0b12a-346">\*.\*</span></span>

- <span data-ttu-id="0b12a-347">**중간 와일드카드**:</span><span class="sxs-lookup"><span data-stu-id="0b12a-347">**Middle wildcards**:</span></span>

  - <span data-ttu-id="0b12a-348">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="0b12a-348">conto\*so.com</span></span>
  - <span data-ttu-id="0b12a-349">conto~so.com</span><span class="sxs-lookup"><span data-stu-id="0b12a-349">conto~so.com</span></span>

- <span data-ttu-id="0b12a-350">**이중 와일드카드**</span><span class="sxs-lookup"><span data-stu-id="0b12a-350">**Double wildcards**</span></span>

  - <span data-ttu-id="0b12a-351">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="0b12a-351">contoso.com/\*\*</span></span>
  - <span data-ttu-id="0b12a-352">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="0b12a-352">contoso.com/\*/\*</span></span>
