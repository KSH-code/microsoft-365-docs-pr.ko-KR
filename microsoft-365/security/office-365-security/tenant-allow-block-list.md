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
ms.openlocfilehash: 20e460f4e93f7b87faaead8b87ba561224e38938
ms.sourcegitcommit: babbba2b5bf69fd3facde2905ec024b753dcd1b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "50515211"
---
# <a name="manage-the-tenant-allowblock-list"></a><span data-ttu-id="f74af-103">테넌트 허용/차단 목록 관리</span><span class="sxs-lookup"><span data-stu-id="f74af-103">Manage the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f74af-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="f74af-104">**Applies to**</span></span>
- [<span data-ttu-id="f74af-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="f74af-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="f74af-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="f74af-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="f74af-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f74af-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

> [!NOTE]
>
> <span data-ttu-id="f74af-108">이 문서에 설명된 기능은 미리 보기에 있으며 변경될 수 있으며 일부 조직에서는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-108">The features described in this article are in Preview, are subject to change, and are not available in all organizations.</span></span>
>
> <span data-ttu-id="f74af-109">현재는 **테넌트** 허용/차단 목록에서 허용된 항목을 구성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-109">You can't **configure** allowed items in the Tenant Allow/Block List at this time.</span></span>

<span data-ttu-id="f74af-110">Exchange Online 사서함이 있는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에서는 EOP 필터링 판정에 동의하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-110">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="f74af-111">예를 들어 양호한 메시지는 나쁜 메시지(가음성)로 표시되거나 잘못된 메시지가 통과(거짓 부정)로 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-111">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="f74af-112">보안 및 준수 센터의 테넌트 허용/차단 & Microsoft 365 필터링 판정을 수동으로 다시 설정하는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-112">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="f74af-113">테넌트 허용/차단 목록은 메일 흐름 중과 사용자가 클릭할 때 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-113">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="f74af-114">항상 차단할 URL 또는 파일을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-114">You can specify URLs or files to always block.</span></span>

<span data-ttu-id="f74af-115">이 문서에서는 보안 & 준수 센터 또는 PowerShell(Exchange Online에 사서함이 있는 Microsoft 365 조직의 경우 Exchange Online PowerShell, Exchange Online 사서함이 없는 조직의 경우 독립 실행형 EOP PowerShell)에서 테넌트 허용/차단 목록의 항목을 구성하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-115">This article describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f74af-116">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="f74af-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f74af-117"><https://protection.office.com/>에서 보안 및 준수 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-117">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="f74af-118">테넌트 **허용/차단 목록 페이지로 직접 이동하기** 위해 를 <https://protection.office.com/tenantAllowBlockList> 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="f74af-118">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="f74af-119">파일의 SHA256 해시 값을 사용하여 파일을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-119">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="f74af-120">Windows에서 파일의 SHA256 해시 값을 찾으면 명령 프롬프트에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-120">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="f74af-121">값의 예로는 를 들 수 `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-121">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="f74af-122">pHash(지각 해시) 값은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-122">Perceptual hash (pHash) values are not supported.</span></span>

- <span data-ttu-id="f74af-123">사용 가능한 URL 값은 이 문서 부분의 [테넌트 허용/차단](#url-syntax-for-the-tenant-allowblock-list) 목록 섹션에 대한 URL 구문에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-123">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="f74af-124">테넌트 허용/차단 목록을 사용하면 URL에 대해 최대 500개 항목과 파일 해시의 항목 500개가 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-124">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="f74af-125">각 항목의 최대 문자 수는 다음입니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-125">The maximum number of characters for each entry is:</span></span>
  - <span data-ttu-id="f74af-126">파일 해시 = 64</span><span class="sxs-lookup"><span data-stu-id="f74af-126">File hashes = 64</span></span>
  - <span data-ttu-id="f74af-127">URL = 250</span><span class="sxs-lookup"><span data-stu-id="f74af-127">URL = 250</span></span>

- <span data-ttu-id="f74af-128">항목이 30분 이내에 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-128">An entry should be active within 30 minutes.</span></span>

- <span data-ttu-id="f74af-129">기본적으로 테넌트 허용/차단 목록의 항목은 30일 후에 만료됩니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-129">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="f74af-130">날짜를 지정하거나 만료되지 않는 날짜로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-130">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="f74af-131">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f74af-131">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="f74af-132">독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f74af-132">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="f74af-133">이 게시물의 절차를 수행하려면 먼저 **Exchange Online** 에서 사용 권한을 할당받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-133">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="f74af-134">테넌트 허용/차단 목록에서 값을 추가 및 제거하려면 조직  관리 또는 보안 관리자 역할 그룹의 **구성원이** 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-134">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="f74af-135">테넌트 허용/차단 목록에 대한 읽기 전용 액세스의 경우 전역  읽기 사용자 또는 보안 읽기 권한이 있는 역할 그룹의 **구성원이** 되거나 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-135">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="f74af-136">자세한 내용은 [Exchange Online의 사용 권한](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f74af-136">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  > 
  > - <span data-ttu-id="f74af-137">Microsoft 365 관리 센터의 해당 Azure Active Directory 역할에 사용자를 추가하면 사용자에게 필요한 권한 _및_ Microsoft 365의 다른 기능에 대한 권한이 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-137">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="f74af-138">자세한 내용은 [관리자 역할 정보](../../admin/add-users/about-admin-roles.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f74af-138">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  > - <span data-ttu-id="f74af-139">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **보기 전용 조직 관리** 역할 그룹에도 기능에 대한 읽기 전용 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-139">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="f74af-140">보안 및 & 센터를 사용하여 테넌트 허용/차단 목록에 URL 항목 만들기</span><span class="sxs-lookup"><span data-stu-id="f74af-140">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="f74af-141">URL 항목의 구문에 대한 자세한 내용은 이 문서 부분의 [테넌트 허용/차단](#url-syntax-for-the-tenant-allowblock-list) 목록 섹션에 대한 URL 구문을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f74af-141">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

1. <span data-ttu-id="f74af-142">보안 및 & 센터에서 위협 **관리** 정책 \>  \> **테넌트 허용/차단 목록으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="f74af-142">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="f74af-143">**테넌트 허용/차단 목록** 페이지에서 URL  탭이 선택되어 있는지 확인한 다음 **차단을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f74af-143">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Block**</span></span>

3. <span data-ttu-id="f74af-144">나타나는 **URL 차단** 플라이아웃에서 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-144">In the **Block URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="f74af-145">**차단할 URL 추가:** 줄당 하나의 URL을 입력하고 최대 20개까지 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-145">**Add URLs to block**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="f74af-146">**만료 안 하세요:** 다음 단계 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-146">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="f74af-147">설정이 꺼져 있는지 확인하고(토글 해제) 만료 날짜 상자를 사용하여 항목의 만료 ![ ](../../media/scc-toggle-off.png) 날짜를 지정합니다. </span><span class="sxs-lookup"><span data-stu-id="f74af-147">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

       <span data-ttu-id="f74af-148">또는</span><span class="sxs-lookup"><span data-stu-id="f74af-148">or</span></span>

     - <span data-ttu-id="f74af-149">토글을 오른쪽으로 이동하여 만료되지 않는 항목을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-149">Move the toggle to the right to configure the entries to never expire:</span></span> ![토글 켬](../../media/scc-toggle-on.png)<span data-ttu-id="f74af-151">.</span><span class="sxs-lookup"><span data-stu-id="f74af-151">.</span></span>

   - <span data-ttu-id="f74af-152">**선택 사항:** 항목에 대한 설명 텍스트를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-152">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="f74af-153">작업을 마쳤으면 **추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-153">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="f74af-154">보안 및 & 센터를 사용하여 테넌트 허용/차단 목록에 파일 항목 만들기</span><span class="sxs-lookup"><span data-stu-id="f74af-154">Use the Security & Compliance Center to create file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="f74af-155">보안 및 & 센터에서 위협 **관리** 정책 \>  \> **테넌트 허용/차단 목록으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="f74af-155">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="f74af-156">**테넌트 허용/차단 목록** 페이지에서  파일 탭을 선택한 다음 차단을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f74af-156">On the **Tenant Allow/Block List** page, select **Files** tab, and then click **Block**.</span></span>

3. <span data-ttu-id="f74af-157">**플라이아웃을 차단할** 파일 추가에서 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-157">In the **Add files to block** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="f74af-158">**파일 해시 추가:** 줄당 SHA256 해시 값 하나(최대 20개)를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-158">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="f74af-159">**만료 안 하세요:** 다음 단계 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-159">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="f74af-160">설정이 꺼져 있는지 확인하고(토글 해제) 만료 날짜 상자를 사용하여 항목의 만료 ![ ](../../media/scc-toggle-off.png) 날짜를 지정합니다. </span><span class="sxs-lookup"><span data-stu-id="f74af-160">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="f74af-161">또는</span><span class="sxs-lookup"><span data-stu-id="f74af-161">or</span></span>

     - <span data-ttu-id="f74af-162">토글을 오른쪽으로 이동하여 만료되지 않는 항목을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-162">Move the toggle to the right to configure the entries to never expire:</span></span> ![토글 켬](../../media/scc-toggle-on.png)<span data-ttu-id="f74af-164">.</span><span class="sxs-lookup"><span data-stu-id="f74af-164">.</span></span>

   - <span data-ttu-id="f74af-165">**선택 사항:** 항목에 대한 설명 텍스트를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-165">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="f74af-166">작업을 마쳤으면 **추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-166">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="f74af-167">보안 및 & 센터를 사용하여 테넌트 허용/차단 목록의 항목 보기</span><span class="sxs-lookup"><span data-stu-id="f74af-167">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="f74af-168">보안 및 & 센터에서 위협 **관리** 정책 \>  \> **테넌트 허용/차단 목록으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="f74af-168">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="f74af-169">URL **탭 또는** 파일 **탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-169">Select the **URLs** tab or the **Files** tab.</span></span>

<span data-ttu-id="f74af-170">다음 열 제목을 클릭하여 오차 또는 내선 순서로 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-170">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="f74af-171">**값:** URL 또는 파일 해시입니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-171">**Value**: The URL or the file hash.</span></span>
- <span data-ttu-id="f74af-172">**마지막으로 업데이트된 날짜**</span><span class="sxs-lookup"><span data-stu-id="f74af-172">**Last updated date**</span></span>
- <span data-ttu-id="f74af-173">**만료 날짜**</span><span class="sxs-lookup"><span data-stu-id="f74af-173">**Expiration date**</span></span>
- <span data-ttu-id="f74af-174">**참고**</span><span class="sxs-lookup"><span data-stu-id="f74af-174">**Note**</span></span>

<span data-ttu-id="f74af-175">**검색을** 클릭하고 값의 전체 또는 일부를 입력한 다음 Enter를 눌러 특정 값을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-175">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="f74af-176">완료되면 검색 지우기 **검색** ![ 아이콘 지우기 를 ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-176">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="f74af-177">필터 **를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f74af-177">Click **Filter**.</span></span> <span data-ttu-id="f74af-178">나타나는 **필터** 플라이아웃에서 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-178">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="f74af-179">**만료 안 하게:** 해제 선택: 해제 ![ 또는 ](../../media/scc-toggle-off.png) 으로 전환: ![ 을 토글합니다. ](../../media/scc-toggle-on.png)</span><span class="sxs-lookup"><span data-stu-id="f74af-179">**Never expire**: Select off: ![Toggle off](../../media/scc-toggle-off.png) or on: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

- <span data-ttu-id="f74af-180">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span><span class="sxs-lookup"><span data-stu-id="f74af-180">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="f74af-181">**만료 날짜:** 시작 날짜(**시작** 날짜 ), 종료 날짜(**To**) 또는 둘 다를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-181">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="f74af-182">완료되면 적용을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f74af-182">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="f74af-183">기존 필터를 지우려면 **필터를** 클릭하고 나타나는 필터  플라이아웃에서 필터 **지우기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f74af-183">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-block-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="f74af-184">보안 및 & 센터를 사용하여 테넌트 허용/차단 목록의 차단 항목 수정</span><span class="sxs-lookup"><span data-stu-id="f74af-184">Use the Security & Compliance Center to modify block entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="f74af-185">항목 내의 기존 차단된 URL 또는 파일 값은 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-185">You can't modify the existing blocked URL or file values within an entry.</span></span> <span data-ttu-id="f74af-186">이러한 값을 수정하려면 항목을 삭제하고 다시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-186">To modify these values, you need to delete and recreate the entry.</span></span>

1. <span data-ttu-id="f74af-187">보안 및 & 센터에서 위협 **관리** 정책 \>  \> **테넌트 허용/차단 목록으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="f74af-187">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="f74af-188">URL **탭 또는** 파일 **탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-188">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="f74af-189">수정할 차단 항목을 선택하고 편집 편집 아이콘  ![ 을 ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-189">Select the block entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="f74af-190">플라이아웃이 나타나면 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-190">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="f74af-191">**만료 안 하세요:** 다음 단계 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-191">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="f74af-192">설정이 꺼져 있는지 확인하고(토글 해제) 만료 날짜 상자를 사용하여 항목의 만료 ![ ](../../media/scc-toggle-off.png) 날짜를 지정합니다. </span><span class="sxs-lookup"><span data-stu-id="f74af-192">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

       <span data-ttu-id="f74af-193">또는</span><span class="sxs-lookup"><span data-stu-id="f74af-193">or</span></span>

     - <span data-ttu-id="f74af-194">토글을 오른쪽으로 이동하여 항목이 만료되지 않는 것으로 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-194">Move the toggle to the right to configure the entry to never expire:</span></span> ![토글 켬](../../media/scc-toggle-on.png)<span data-ttu-id="f74af-196">.</span><span class="sxs-lookup"><span data-stu-id="f74af-196">.</span></span>

   - <span data-ttu-id="f74af-197">**선택 사항:** 항목에 대한 설명 텍스트를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-197">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="f74af-198">작업을 마쳤으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-198">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-block-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="f74af-199">보안 및 & 센터를 사용하여 테넌트 허용/차단 목록에서 차단 항목 제거</span><span class="sxs-lookup"><span data-stu-id="f74af-199">Use the Security & Compliance Center to remove block entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="f74af-200">보안 및 & 센터에서 위협 **관리** 정책 \>  \> **테넌트 허용/차단 목록으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="f74af-200">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="f74af-201">URL **탭 또는** 파일 **탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-201">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="f74af-202">제거할 차단 항목을 선택한 다음 삭제 삭제 아이콘 **을** ![ ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-202">Select the block entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="f74af-203">나타나는 경고 대화 상자에서 삭제를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f74af-203">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="f74af-204">Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell을 사용하여 테넌트 허용/차단 목록 구성</span><span class="sxs-lookup"><span data-stu-id="f74af-204">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-block-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="f74af-205">PowerShell을 사용하여 테넌트 허용/차단 목록에 차단 항목 추가</span><span class="sxs-lookup"><span data-stu-id="f74af-205">Use PowerShell to add block entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="f74af-206">테넌트 허용/차단 목록에서 차단 항목을 추가하기 위해 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="f74af-206">To add block entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <Url | FileHash> -Block -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="f74af-207">이 예제에서는 contoso.com, contoso.com, www.contoso.com 및 하위 xyz.abc.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="f74af-207">This example adds a block URL entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="f74af-208">ExpirationDate 또는 NoExpiration 매개 변수를 사용하지 않았기 때문에 항목이 30일 후에 만료됩니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-208">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

<span data-ttu-id="f74af-209">이 예제에서는 만료되지 않는 지정된 파일에 대한 차단 파일 항목을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-209">This example adds a block file entry for the specified files that never expires.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="f74af-210">구문과 매개 변수에 대한 자세한 내용은 [New-TenantAllowBlockListItems를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="f74af-210">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="f74af-211">PowerShell을 사용하여 테넌트 허용/차단 목록의 항목 보기</span><span class="sxs-lookup"><span data-stu-id="f74af-211">Use PowerShell to view entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="f74af-212">테넌트 허용/차단 목록의 항목을 표시하기 위해 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="f74af-212">To view entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <Url | FileHash> [-Entry <URLValue | FileHashValue>] [-Block] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="f74af-213">이 예제에서는 차단된 URL을 모두 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-213">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

<span data-ttu-id="f74af-214">이 예제에서는 지정한 파일 해시 값에 대한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-214">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="f74af-215">구문과 매개 변수에 대한 자세한 내용은 [Get-TenantAllowBlockListItems를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="f74af-215">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-block-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="f74af-216">PowerShell을 사용하여 테넌트 허용/차단 목록에서 차단 항목 수정</span><span class="sxs-lookup"><span data-stu-id="f74af-216">Use PowerShell to modify block entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="f74af-217">차단 항목 내에 있는 기존 URL 또는 파일 값은 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-217">You can't modify the existing URL or file values within a block entry.</span></span> <span data-ttu-id="f74af-218">이러한 값을 수정하려면 항목을 삭제하고 다시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-218">To modify these values, you need to delete and recreate the entry.</span></span>

<span data-ttu-id="f74af-219">테넌트 허용/차단 목록에서 차단 항목을 수정하려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="f74af-219">To modify block entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN"> [-Block] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="f74af-220">이 예제에서는 지정한 블록 항목의 만료 날짜를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-220">This example changes the expiration date of the specified block entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="f74af-221">구문과 매개 변수에 대한 자세한 내용은 [Set-TenantAllowBlockListItems를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="f74af-221">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-block-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="f74af-222">PowerShell을 사용하여 테넌트 허용/차단 목록에서 차단 항목 제거</span><span class="sxs-lookup"><span data-stu-id="f74af-222">Use PowerShell to remove block entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="f74af-223">테넌트 허용/차단 목록에서 차단 항목을 제거하려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="f74af-223">To remove block entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="f74af-224">이 예에서는 테넌트 허용/차단 목록에서 지정된 차단 URL 항목을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-224">This example removes the specified block URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="f74af-225">구문과 매개 변수에 대한 자세한 내용은 [Remove-TenantAllowBlockListItems를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="f74af-225">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="f74af-226">테넌트 허용/차단 목록에 대한 URL 구문</span><span class="sxs-lookup"><span data-stu-id="f74af-226">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="f74af-227">IP4v 및 IPv6 주소는 사용할 수 있지만 TCP/UDP 포트는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-227">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="f74af-228">파일 이름 확장명은 허용되지 않습니다(예: test.pdf).</span><span class="sxs-lookup"><span data-stu-id="f74af-228">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="f74af-229">유니코드는 지원되지 않지만 Punycode는 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-229">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="f74af-230">다음 명령문이 모두 true이면 호스트 이름을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-230">Hostnames are allowed if all of the following statements are true:</span></span>
  - <span data-ttu-id="f74af-231">호스트 이름에는 기간이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-231">The hostname contains a period.</span></span>
  - <span data-ttu-id="f74af-232">기간 왼쪽에 하나 이상의 문자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-232">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="f74af-233">이 기간의 오른쪽에는 두 개 이상의 문자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-233">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="f74af-234">예를 들어 `t.co` 허용되거나 `.com` `contoso.` 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-234">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="f74af-235">하위 경로는 암시적이지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-235">Subpaths are not implied.</span></span>

  <span data-ttu-id="f74af-236">예를 들어 `contoso.com` 를 포함하지 `contoso.com/a` 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-236">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="f74af-237">와일드카드(\*)는 다음과 같은 시나리오에서 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-237">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="f74af-238">하위omain을 지정하려면 왼쪽 와일드카드 다음에 기간이 와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-238">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="f74af-239">예를 들어 `*.contoso.com` 허용됩니다. `*contoso.com` 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-239">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="f74af-240">오른쪽 와일드카드는 슬래시(/)를 따라 경로를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-240">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="f74af-241">예를 들어 `contoso.com/*` 허용되거나 `contoso.com*` `contoso.com/ab*` 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-241">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="f74af-242">모든 하위 경로는 올바른 와일드카드로 암시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-242">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="f74af-243">예를 들어 `contoso.com/*` 를 포함하지 `contoso.com/a` 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-243">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="f74af-244">`*.com*` 가 잘못되었습니다(확인 가능한 도메인이 아니며 오른쪽 와일드카드가 슬래시를 따르지 않습니다).</span><span class="sxs-lookup"><span data-stu-id="f74af-244">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="f74af-245">와일드카드는 IP 주소에서 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-245">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="f74af-246">다음 시나리오에서는 선조(~) 문자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-246">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="f74af-247">왼쪽 밀기선은 도메인과 모든 하위 도메인을 암시합니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-247">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="f74af-248">예를 들어 `~contoso.com` 및 `contoso.com` `*.contoso.com` 을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-248">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="f74af-249">URL 항목이 모든 프로토콜에 적용될 수 있기 때문에 프로토콜(예: , 또는 )이 포함된 URL 항목은 `http://` `https://` `ftp://` 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-249">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="f74af-250">사용자 이름 또는 암호는 지원되거나 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-250">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="f74af-251">따옴표(' 또는 ")는 잘못된 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-251">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="f74af-252">URL에는 가능한 경우 모든 리디렉션이 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-252">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="f74af-253">URL 입력 시나리오</span><span class="sxs-lookup"><span data-stu-id="f74af-253">URL entry scenarios</span></span>

<span data-ttu-id="f74af-254">유효한 URL 항목 및 해당 결과는 다음 섹션에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-254">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="f74af-255">시나리오: 와일드카드 없음</span><span class="sxs-lookup"><span data-stu-id="f74af-255">Scenario: No wildcards</span></span>

<span data-ttu-id="f74af-256">**항목**: `contoso.com`</span><span class="sxs-lookup"><span data-stu-id="f74af-256">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="f74af-257">**일치 허용**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="f74af-257">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="f74af-258">**일치하지 않는 허용**:</span><span class="sxs-lookup"><span data-stu-id="f74af-258">**Allow not matched**:</span></span>

  - <span data-ttu-id="f74af-259">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="f74af-259">abc-contoso.com</span></span>
  - <span data-ttu-id="f74af-260">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="f74af-260">contoso.com/a</span></span>
  - <span data-ttu-id="f74af-261">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f74af-261">payroll.contoso.com</span></span>
  - <span data-ttu-id="f74af-262">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="f74af-262">test.com/contoso.com</span></span>
  - <span data-ttu-id="f74af-263">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="f74af-263">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="f74af-264">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f74af-264">www.contoso.com</span></span>
  - <span data-ttu-id="f74af-265">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="f74af-265">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="f74af-266">**블록 일치**:</span><span class="sxs-lookup"><span data-stu-id="f74af-266">**Block match**:</span></span>

  - <span data-ttu-id="f74af-267">contoso.com</span><span class="sxs-lookup"><span data-stu-id="f74af-267">contoso.com</span></span>
  - <span data-ttu-id="f74af-268">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="f74af-268">contoso.com/a</span></span>
  - <span data-ttu-id="f74af-269">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f74af-269">payroll.contoso.com</span></span>
  - <span data-ttu-id="f74af-270">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="f74af-270">test.com/contoso.com</span></span>
  - <span data-ttu-id="f74af-271">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="f74af-271">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="f74af-272">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f74af-272">www.contoso.com</span></span>
  - <span data-ttu-id="f74af-273">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="f74af-273">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="f74af-274">**블록이 일치하지 않는 경우**: abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="f74af-274">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="f74af-275">시나리오: 왼쪽 와일드카드(하위omain)</span><span class="sxs-lookup"><span data-stu-id="f74af-275">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="f74af-276">**항목**: `*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="f74af-276">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="f74af-277">**일치 및** **차단 일치 허용**:</span><span class="sxs-lookup"><span data-stu-id="f74af-277">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="f74af-278">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f74af-278">www.contoso.com</span></span>
  - <span data-ttu-id="f74af-279">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f74af-279">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="f74af-280">**일치하지 않는 허용** 및 **차단이 일치하지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="f74af-280">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="f74af-281">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="f74af-281">123contoso.com</span></span>
  - <span data-ttu-id="f74af-282">contoso.com</span><span class="sxs-lookup"><span data-stu-id="f74af-282">contoso.com</span></span>
  - <span data-ttu-id="f74af-283">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="f74af-283">test.com/contoso.com</span></span>
  - <span data-ttu-id="f74af-284">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="f74af-284">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="f74af-285">시나리오: 경로 맨 위에 있는 오른쪽 와일드카드</span><span class="sxs-lookup"><span data-stu-id="f74af-285">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="f74af-286">**항목**: `contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="f74af-286">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="f74af-287">**일치 및** **차단 일치 허용**:</span><span class="sxs-lookup"><span data-stu-id="f74af-287">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="f74af-288">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="f74af-288">contoso.com/a/b</span></span>
  - <span data-ttu-id="f74af-289">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="f74af-289">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="f74af-290">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="f74af-290">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="f74af-291">**일치하지 않는 허용** 및 **차단이 일치하지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="f74af-291">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="f74af-292">contoso.com</span><span class="sxs-lookup"><span data-stu-id="f74af-292">contoso.com</span></span>
  - <span data-ttu-id="f74af-293">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="f74af-293">contoso.com/a</span></span>
  - <span data-ttu-id="f74af-294">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f74af-294">www.contoso.com</span></span>
  - <span data-ttu-id="f74af-295">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="f74af-295">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="f74af-296">시나리오: 왼쪽 밀기</span><span class="sxs-lookup"><span data-stu-id="f74af-296">Scenario: Left tilde</span></span>

<span data-ttu-id="f74af-297">**항목**: `~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="f74af-297">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="f74af-298">**일치 및** **차단 일치 허용**:</span><span class="sxs-lookup"><span data-stu-id="f74af-298">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="f74af-299">contoso.com</span><span class="sxs-lookup"><span data-stu-id="f74af-299">contoso.com</span></span>
  - <span data-ttu-id="f74af-300">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f74af-300">www.contoso.com</span></span>
  - <span data-ttu-id="f74af-301">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f74af-301">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="f74af-302">**일치하지 않는 허용** 및 **차단이 일치하지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="f74af-302">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="f74af-303">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="f74af-303">123contoso.com</span></span>
  - <span data-ttu-id="f74af-304">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="f74af-304">contoso.com/abc</span></span>
  - <span data-ttu-id="f74af-305">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="f74af-305">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="f74af-306">시나리오: 오른쪽 와일드카드 접미사</span><span class="sxs-lookup"><span data-stu-id="f74af-306">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="f74af-307">**항목**: `contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="f74af-307">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="f74af-308">**일치 및** **차단 일치 허용**:</span><span class="sxs-lookup"><span data-stu-id="f74af-308">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="f74af-309">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="f74af-309">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="f74af-310">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="f74af-310">contoso.com/a</span></span>
  - <span data-ttu-id="f74af-311">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="f74af-311">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="f74af-312">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="f74af-312">contoso.com/ab</span></span>
  - <span data-ttu-id="f74af-313">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="f74af-313">contoso.com/b</span></span>
  - <span data-ttu-id="f74af-314">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="f74af-314">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="f74af-315">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="f74af-315">contoso.com/ba</span></span>

- <span data-ttu-id="f74af-316">**일치하지 않는 허용** 및 **일치하지 않는** 차단 : contoso.com</span><span class="sxs-lookup"><span data-stu-id="f74af-316">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="f74af-317">시나리오: 왼쪽 와일드카드 하위omain 및 오른쪽 와일드카드 접미사</span><span class="sxs-lookup"><span data-stu-id="f74af-317">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="f74af-318">**항목**: `*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="f74af-318">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="f74af-319">**일치 및** **차단 일치 허용**:</span><span class="sxs-lookup"><span data-stu-id="f74af-319">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="f74af-320">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="f74af-320">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="f74af-321">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="f74af-321">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="f74af-322">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="f74af-322">www.contoso.com/a</span></span>
  - <span data-ttu-id="f74af-323">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="f74af-323">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="f74af-324">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="f74af-324">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="f74af-325">**일치하지 않는 허용** 및 **일치하지 않는** 차단 : contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="f74af-325">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="f74af-326">시나리오: 왼쪽 및 오른쪽 밀기</span><span class="sxs-lookup"><span data-stu-id="f74af-326">Scenario: Left and right tilde</span></span>

<span data-ttu-id="f74af-327">**항목**: `~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="f74af-327">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="f74af-328">**일치 및** **차단 일치 허용**:</span><span class="sxs-lookup"><span data-stu-id="f74af-328">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="f74af-329">contoso.com</span><span class="sxs-lookup"><span data-stu-id="f74af-329">contoso.com</span></span>
  - <span data-ttu-id="f74af-330">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="f74af-330">contoso.com/a</span></span>
  - <span data-ttu-id="f74af-331">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f74af-331">www.contoso.com</span></span>
  - <span data-ttu-id="f74af-332">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="f74af-332">www.contoso.com/b</span></span>
  - <span data-ttu-id="f74af-333">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f74af-333">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="f74af-334">**일치하지 않는 허용** 및 **차단이 일치하지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="f74af-334">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="f74af-335">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="f74af-335">123contoso.com</span></span>
  - <span data-ttu-id="f74af-336">contoso.org</span><span class="sxs-lookup"><span data-stu-id="f74af-336">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="f74af-337">시나리오: IP 주소</span><span class="sxs-lookup"><span data-stu-id="f74af-337">Scenario: IP address</span></span>

<span data-ttu-id="f74af-338">**항목**: `1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="f74af-338">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="f74af-339">**일치 및** **차단 일치** 허용 : 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="f74af-339">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="f74af-340">**일치하지 않는 허용** 및 **차단이 일치하지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="f74af-340">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="f74af-341">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="f74af-341">1.2.3.4/a</span></span>
  - <span data-ttu-id="f74af-342">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="f74af-342">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="f74af-343">오른쪽 와일드카드가 있는 IP 주소</span><span class="sxs-lookup"><span data-stu-id="f74af-343">IP address with right wildcard</span></span>

<span data-ttu-id="f74af-344">**항목**: `1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="f74af-344">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="f74af-345">**일치 및** **차단 일치 허용**:</span><span class="sxs-lookup"><span data-stu-id="f74af-345">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="f74af-346">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="f74af-346">1.2.3.4/b</span></span>
  - <span data-ttu-id="f74af-347">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="f74af-347">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="f74af-348">잘못된 항목의 예</span><span class="sxs-lookup"><span data-stu-id="f74af-348">Examples of invalid entries</span></span>

<span data-ttu-id="f74af-349">다음 항목이 잘못되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f74af-349">The following entries are invalid:</span></span>

- <span data-ttu-id="f74af-350">**누락되었거나 잘못된 도메인 값**:</span><span class="sxs-lookup"><span data-stu-id="f74af-350">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="f74af-351">contoso</span><span class="sxs-lookup"><span data-stu-id="f74af-351">contoso</span></span>
  - <span data-ttu-id="f74af-352">\*.contoso.\*</span><span class="sxs-lookup"><span data-stu-id="f74af-352">\*.contoso.\*</span></span>
  - <span data-ttu-id="f74af-353">\*.com</span><span class="sxs-lookup"><span data-stu-id="f74af-353">\*.com</span></span>
  - <span data-ttu-id="f74af-354">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="f74af-354">\*.pdf</span></span>

- <span data-ttu-id="f74af-355">**텍스트의 와일드카드 또는 간격 문자가 없는** 경우 :</span><span class="sxs-lookup"><span data-stu-id="f74af-355">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="f74af-356">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="f74af-356">\*contoso.com</span></span>
  - <span data-ttu-id="f74af-357">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="f74af-357">contoso.com\*</span></span>
  - <span data-ttu-id="f74af-358">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="f74af-358">\*1.2.3.4</span></span>
  - <span data-ttu-id="f74af-359">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="f74af-359">1.2.3.4\*</span></span>
  - <span data-ttu-id="f74af-360">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="f74af-360">contoso.com/a\*</span></span>
  - <span data-ttu-id="f74af-361">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="f74af-361">contoso.com/ab\*</span></span>

- <span data-ttu-id="f74af-362">**포트가 있는 IP 주소:**</span><span class="sxs-lookup"><span data-stu-id="f74af-362">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="f74af-363">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="f74af-363">contoso.com:443</span></span>
  - <span data-ttu-id="f74af-364">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="f74af-364">abc.contoso.com:25</span></span>

- <span data-ttu-id="f74af-365">**설명이 없는 와일드카드**:</span><span class="sxs-lookup"><span data-stu-id="f74af-365">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="f74af-366">\*.\*</span><span class="sxs-lookup"><span data-stu-id="f74af-366">\*.\*</span></span>

- <span data-ttu-id="f74af-367">**중간 와일드카드**:</span><span class="sxs-lookup"><span data-stu-id="f74af-367">**Middle wildcards**:</span></span>

  - <span data-ttu-id="f74af-368">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="f74af-368">conto\*so.com</span></span>
  - <span data-ttu-id="f74af-369">conto~so.com</span><span class="sxs-lookup"><span data-stu-id="f74af-369">conto~so.com</span></span>

- <span data-ttu-id="f74af-370">**이중 와일드카드**</span><span class="sxs-lookup"><span data-stu-id="f74af-370">**Double wildcards**</span></span>

  - <span data-ttu-id="f74af-371">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="f74af-371">contoso.com/\*\*</span></span>
  - <span data-ttu-id="f74af-372">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="f74af-372">contoso.com/\*/\*</span></span>
