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
ms.openlocfilehash: 250b6223ffe663e0cd950069a3c3c7827b4aa57b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290168"
---
# <a name="manage-the-tenant-allowblock-list"></a><span data-ttu-id="625b2-103">테넌트 허용/차단 목록 관리</span><span class="sxs-lookup"><span data-stu-id="625b2-103">Manage the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="625b2-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="625b2-104">**Applies to**</span></span>
- [<span data-ttu-id="625b2-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="625b2-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="625b2-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="625b2-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="625b2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="625b2-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

> [!NOTE]
>
> <span data-ttu-id="625b2-108">이 문서에 설명된 기능은 미리 보기로 제공되어 있으며 변경될 수 있으며 일부 조직에서는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-108">The features described in this article are in Preview, are subject to change, and are not available in all organizations.</span></span>
>
> <span data-ttu-id="625b2-109">현재는 **테넌트** 허용/차단 목록에서 허용된 항목을 구성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-109">You can't **configure** allowed items in the Tenant Allow/Block List at this time.</span></span>

<span data-ttu-id="625b2-110">Exchange Online 사서함이 있는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에서는 EOP 필터링 판정에 동의하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-110">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="625b2-111">예를 들어 좋은 메시지는 나쁜 메시지(가음성)로 표시되거나 잘못된 메시지가 통과(거짓 부정)될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-111">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="625b2-112">보안 및 규정 준수 센터의 테넌트 허용/차단 & Microsoft 365 필터링 판정을 수동으로 다시우는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-112">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="625b2-113">테넌트 허용/차단 목록은 메일 흐름 중과 사용자가 클릭할 때 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-113">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="625b2-114">URL 또는 파일을 항상 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-114">You can specify URLs or files to always block.</span></span>

<span data-ttu-id="625b2-115">이 문서에서는 보안 & 준수 센터 또는 PowerShell(Exchange Online에 사서함이 있는 Microsoft 365 조직용 Exchange Online PowerShell, Exchange Online 사서함이 없는 조직의 독립 실행형 EOP PowerShell)에서 테넌트 허용/차단 목록의 항목을 구성하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-115">This article describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="625b2-116">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="625b2-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="625b2-117"><https://protection.office.com/>에서 보안 및 준수 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-117">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="625b2-118">테넌트 **허용/차단** 목록 페이지로 직접 이동하기 위해 <https://protection.office.com/tenantAllowBlockList> 다음을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="625b2-118">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="625b2-119">파일의 SHA256 해시 값을 사용하여 파일을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-119">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="625b2-120">Windows에서 파일의 SHA256 해시 값을 찾으면 명령 프롬프트에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-120">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```dos
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="625b2-121">값의 예는 `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-121">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="625b2-122">pHash(지각 해시) 값은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-122">Perceptual hash (pHash) values are not supported.</span></span>

- <span data-ttu-id="625b2-123">사용 가능한 URL 값은 이 문서 부분의 [테넌트 허용/차단 목록 섹션에](#url-syntax-for-the-tenant-allowblock-list) 대한 URL 구문에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-123">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="625b2-124">테넌트 허용/차단 목록에서는 URL에 대해 최대 500개 항목을 허용하고 파일 해시의 항목은 500개까지 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-124">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="625b2-125">15분 이내에 항목이 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-125">An entry should be active within 15 minutes.</span></span>

- <span data-ttu-id="625b2-126">기본적으로 테넌트 허용/차단 목록의 항목은 30일 후에 만료됩니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-126">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="625b2-127">날짜를 지정하거나 만료되지 않는 것으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-127">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="625b2-128">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="625b2-128">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="625b2-129">독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="625b2-129">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="625b2-130">이 문서의 절차를 수행하려면 먼저 보안 및 준수 센터에서 사용 권한을 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-130">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="625b2-131">테넌트 허용/차단 목록에서 값을 추가하고 제거하려면 **조직** 관리 또는 보안 관리자 역할 그룹의 **구성원이** 되거나 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-131">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="625b2-132">테넌트 허용/차단 목록에 대한 읽기 전용 액세스 권한을 사용하려면  전역 읽기 또는 보안 읽기 권한이 있는 사용자 역할 그룹의 **구성원이면** 됩니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-132">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="625b2-133">자세한 내용은 [보안 및 준수 센터의 사용 권한](permissions-in-the-security-and-compliance-center.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="625b2-133">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="625b2-134">**참고**:</span><span class="sxs-lookup"><span data-stu-id="625b2-134">**Notes**:</span></span>

  - <span data-ttu-id="625b2-135">Microsoft 365 관리 센터의 해당 Azure Active Directory 역할에 사용자를 추가하면 사용자에게 보안 및 준수 센터에서 필요한 권한 _및_ Microsoft 365의 다른 기능에 대한 권한이 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-135">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="625b2-136">자세한 내용은 [관리자 역할 정보](../../admin/add-users/about-admin-roles.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="625b2-136">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="625b2-137">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **보기 전용 조직 관리** 역할 그룹에도 기능에 대한 읽기 전용 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-137">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="625b2-138">보안 및 & 센터를 사용하여 테넌트 허용/차단 목록에 URL 항목 만들기</span><span class="sxs-lookup"><span data-stu-id="625b2-138">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="625b2-139">URL 항목의 구문에 대한 자세한 내용은 이 문서 부분의 [테넌트 허용/차단 목록 섹션에](#url-syntax-for-the-tenant-allowblock-list) 대한 URL 구문을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="625b2-139">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

1. <span data-ttu-id="625b2-140">보안 & 준수 센터에서 위협 **관리** 정책 \>  \> **테넌트 허용/차단 목록으로 이동하십시오.**</span><span class="sxs-lookup"><span data-stu-id="625b2-140">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="625b2-141">**테넌트 허용/차단 목록** 페이지에서 **URL** 탭이 선택되어 있는지 확인한 다음 **차단을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="625b2-141">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Block**</span></span>

3. <span data-ttu-id="625b2-142">나타나는 **차단 URL** 플라이아웃에서 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-142">In the **Block URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="625b2-143">**차단할 URL** 추가: 한 줄당 하나의 URL을 입력하고 최대 20개까지 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-143">**Add URLs to block**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="625b2-144">**만료 안 하세요.** 다음 단계 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-144">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="625b2-145">설정이 꺼져 있는지 확인하고(토글 해제) 만료 상자를 사용하여 항목의 만료 ![ ](../../media/scc-toggle-off.png) 날짜를 지정합니다. </span><span class="sxs-lookup"><span data-stu-id="625b2-145">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="625b2-146">또는</span><span class="sxs-lookup"><span data-stu-id="625b2-146">or</span></span>

     - <span data-ttu-id="625b2-147">토글을 오른쪽으로 이동하여 항목이 만료되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-147">Move the toggle to the right to configure the entries to never expire:</span></span> ![토글 켬](../../media/scc-toggle-on.png)<span data-ttu-id="625b2-149">.</span><span class="sxs-lookup"><span data-stu-id="625b2-149">.</span></span>

   - <span data-ttu-id="625b2-150">**선택 사항**: 항목에 대한 설명 텍스트를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-150">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="625b2-151">작업을 마쳤으면 **추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-151">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="625b2-152">보안 및 & 센터를 사용하여 테넌트 허용/차단 목록에 파일 항목 만들기</span><span class="sxs-lookup"><span data-stu-id="625b2-152">Use the Security & Compliance Center to create file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="625b2-153">보안 & 준수 센터에서 위협 **관리** 정책 \>  \> **테넌트 허용/차단 목록으로 이동하십시오.**</span><span class="sxs-lookup"><span data-stu-id="625b2-153">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="625b2-154">**테넌트 허용/차단 목록** 페이지에서 파일 탭을 **선택한** 다음 차단을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="625b2-154">On the **Tenant Allow/Block List** page, select **Files** tab, and then click **Block**.</span></span>

3. <span data-ttu-id="625b2-155">**플라이아웃이 나타나지도록 차단할** 파일 추가에서 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-155">In the **Add files to block** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="625b2-156">**파일 해시** 추가: 줄당 SHA256 해시 값 하나(최대 20개)를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-156">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="625b2-157">**만료 안 하세요.** 다음 단계 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-157">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="625b2-158">설정이 꺼져 있는지 확인하고(토글 해제) 만료 상자를 사용하여 항목의 만료 ![ ](../../media/scc-toggle-off.png) 날짜를 지정합니다. </span><span class="sxs-lookup"><span data-stu-id="625b2-158">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="625b2-159">또는</span><span class="sxs-lookup"><span data-stu-id="625b2-159">or</span></span>

     - <span data-ttu-id="625b2-160">토글을 오른쪽으로 이동하여 항목이 만료되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-160">Move the toggle to the right to configure the entries to never expire:</span></span> ![토글 켬](../../media/scc-toggle-on.png)<span data-ttu-id="625b2-162">.</span><span class="sxs-lookup"><span data-stu-id="625b2-162">.</span></span>

   - <span data-ttu-id="625b2-163">**선택 사항**: 항목에 대한 설명 텍스트를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-163">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="625b2-164">작업을 마쳤으면 **추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-164">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="625b2-165">보안 및 & 센터를 사용하여 테넌트 허용/차단 목록의 항목 보기</span><span class="sxs-lookup"><span data-stu-id="625b2-165">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="625b2-166">보안 & 준수 센터에서 위협 **관리** 정책 \>  \> **테넌트 허용/차단 목록으로 이동하십시오.**</span><span class="sxs-lookup"><span data-stu-id="625b2-166">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="625b2-167">URL 탭 **또는** 파일 **탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-167">Select the **URLs** tab or the **Files** tab.</span></span>

<span data-ttu-id="625b2-168">다음 열 머리 단추를 클릭하여 오차 또는 내선 순서로 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-168">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="625b2-169">**값:** URL 또는 파일 해시입니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-169">**Value**: The URL or the file hash.</span></span>
- <span data-ttu-id="625b2-170">**마지막 업데이트 날짜**</span><span class="sxs-lookup"><span data-stu-id="625b2-170">**Last updated date**</span></span>
- <span data-ttu-id="625b2-171">**만료 날짜**</span><span class="sxs-lookup"><span data-stu-id="625b2-171">**Expiration date**</span></span>
- <span data-ttu-id="625b2-172">**참고**</span><span class="sxs-lookup"><span data-stu-id="625b2-172">**Note**</span></span>

<span data-ttu-id="625b2-173">검색을 **클릭하고** 값의 전체 또는 일부를 입력한 다음 Enter를 눌러 특정 값을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-173">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="625b2-174">완료되면 검색 지우기 **검색 아이콘을** ![ ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-174">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="625b2-175">필터를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="625b2-175">Click **Filter**.</span></span> <span data-ttu-id="625b2-176">필터  플라이아웃이 나타나면 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-176">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="625b2-177">**만료 안 하게:** 해제 선택: 해제 ![ 또는 ](../../media/scc-toggle-off.png) 끄기: ![ 토글 ](../../media/scc-toggle-on.png)</span><span class="sxs-lookup"><span data-stu-id="625b2-177">**Never expire**: Select off: ![Toggle off](../../media/scc-toggle-off.png) or on: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

- <span data-ttu-id="625b2-178">**Last updated**: Select a start date **(From),** an end date (**To)** or both.</span><span class="sxs-lookup"><span data-stu-id="625b2-178">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="625b2-179">**만료 날짜:** 시작 날짜(시작 **날짜),** 종료 날짜(끝 **날짜)** 또는 둘 다를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-179">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="625b2-180">완료되면 적용을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="625b2-180">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="625b2-181">기존 필터를 지우려면 **필터를** 클릭하고 나타나는 필터  플라이아웃에서 필터 **지우기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="625b2-181">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-block-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="625b2-182">보안 및 & 센터를 사용하여 테넌트 허용/차단 목록의 차단 항목 수정</span><span class="sxs-lookup"><span data-stu-id="625b2-182">Use the Security & Compliance Center to modify block entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="625b2-183">항목 내의 기존 차단된 URL 또는 파일 값은 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-183">You can't modify the existing blocked URL or file values within an entry.</span></span> <span data-ttu-id="625b2-184">이러한 값을 수정하려면 항목을 삭제하고 다시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-184">To modify these values, you need to delete and recreate the entry.</span></span>

1. <span data-ttu-id="625b2-185">보안 & 준수 센터에서 위협 **관리** 정책 \>  \> **테넌트 허용/차단 목록으로 이동하십시오.**</span><span class="sxs-lookup"><span data-stu-id="625b2-185">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="625b2-186">URL 탭 **또는** 파일 **탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-186">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="625b2-187">수정할 차단 항목을 선택하고 편집  ![ 아이콘을 ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-187">Select the block entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="625b2-188">플라이아웃이 나타나면 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-188">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="625b2-189">**만료 안 하세요.** 다음 단계 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-189">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="625b2-190">설정이 꺼져 있는지(토글 해제) 확인란을 사용하여 항목의 만료 날짜를 ![ ](../../media/scc-toggle-off.png) 지정합니다. </span><span class="sxs-lookup"><span data-stu-id="625b2-190">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

     <span data-ttu-id="625b2-191">또는</span><span class="sxs-lookup"><span data-stu-id="625b2-191">or</span></span>

     - <span data-ttu-id="625b2-192">토글을 오른쪽으로 이동하여 항목이 만료되지 못하도록 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-192">Move the toggle to the right to configure the entry to never expire:</span></span> ![토글 켬](../../media/scc-toggle-on.png)<span data-ttu-id="625b2-194">.</span><span class="sxs-lookup"><span data-stu-id="625b2-194">.</span></span>

   - <span data-ttu-id="625b2-195">**선택 사항**: 항목에 대한 설명 텍스트를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-195">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="625b2-196">작업을 마쳤으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-196">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-block-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="625b2-197">보안 및 & 센터를 사용하여 테넌트 허용/차단 목록에서 차단 항목 제거</span><span class="sxs-lookup"><span data-stu-id="625b2-197">Use the Security & Compliance Center to remove block entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="625b2-198">보안 & 준수 센터에서 위협 **관리** 정책 \>  \> **테넌트 허용/차단 목록으로 이동하십시오.**</span><span class="sxs-lookup"><span data-stu-id="625b2-198">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="625b2-199">URL 탭 **또는** 파일 **탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-199">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="625b2-200">제거할 차단 항목을 선택하고 삭제 **아이콘을** ![ ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-200">Select the block entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="625b2-201">나타나는 경고 대화 상자에서 삭제를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="625b2-201">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="625b2-202">Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell을 사용하여 테넌트 허용/차단 목록 구성</span><span class="sxs-lookup"><span data-stu-id="625b2-202">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-block-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="625b2-203">PowerShell을 사용하여 테넌트 허용/차단 목록에 차단 항목 추가</span><span class="sxs-lookup"><span data-stu-id="625b2-203">Use PowerShell to add block entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="625b2-204">테넌트 허용/차단 목록에 차단 항목을 추가하기 위해 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="625b2-204">To add block entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <Url | FileHash> -Block -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="625b2-205">이 예에서는 contoso.com 및 모든 하위 contoso.com, www.contoso.com 및 하위 xyz.abc.contoso.com에 대한 차단 URL 항목을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-205">This example adds a block URL entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="625b2-206">ExpirationDate 또는 NoExpiration 매개 변수를 사용하지 않았기 때문에 항목이 30일 후에 만료됩니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-206">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType Url -Block -Entries ~contoso.com
```

<span data-ttu-id="625b2-207">이 예제에서는 만료되지 않는 지정된 파일에 대한 차단 파일 항목을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-207">This example adds a block file entry for the specified files that never expires.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="625b2-208">구문과 매개 변수에 대한 자세한 내용은 [New-TenantAllowBlockListItems를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="625b2-208">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="625b2-209">PowerShell을 사용하여 테넌트 허용/차단 목록의 항목 보기</span><span class="sxs-lookup"><span data-stu-id="625b2-209">Use PowerShell to view entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="625b2-210">테넌트 허용/차단 목록의 항목을 표시하기 위해 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="625b2-210">To view entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <Url | FileHash> [-Entry <URLValue | FileHashValue>] [-Block] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="625b2-211">이 예제에서는 차단된 URL을 모두 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-211">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

<span data-ttu-id="625b2-212">이 예제에서는 지정한 파일 해시 값에 대한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-212">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="625b2-213">구문과 매개 변수에 대한 자세한 내용은 [Get-TenantAllowBlockListItems를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="625b2-213">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-block-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="625b2-214">PowerShell을 사용하여 테넌트 허용/차단 목록의 차단 항목 수정</span><span class="sxs-lookup"><span data-stu-id="625b2-214">Use PowerShell to modify block entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="625b2-215">차단 항목 내에서는 기존 URL 또는 파일 값을 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-215">You can't modify the existing URL or file values within a block entry.</span></span> <span data-ttu-id="625b2-216">이러한 값을 수정하려면 항목을 삭제하고 다시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-216">To modify these values, you need to delete and recreate the entry.</span></span>

<span data-ttu-id="625b2-217">테넌트 허용/차단 목록에서 차단 항목을 수정하려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="625b2-217">To modify block entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN"> [-Block] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="625b2-218">이 예제에서는 지정한 블록 항목의 만료 날짜를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-218">This example changes the expiration date of the specified block entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="625b2-219">구문과 매개 변수에 대한 자세한 내용은 [Set-TenantAllowBlockListItems를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="625b2-219">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-block-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="625b2-220">PowerShell을 사용하여 테넌트 허용/차단 목록에서 차단 항목 제거</span><span class="sxs-lookup"><span data-stu-id="625b2-220">Use PowerShell to remove block entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="625b2-221">테넌트 허용/차단 목록에서 차단 항목을 제거하려면 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="625b2-221">To remove block entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="625b2-222">이 예에서는 테넌트 허용/차단 목록에서 지정된 차단 URL 항목을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-222">This example removes the specified block URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="625b2-223">구문과 매개 변수에 대한 자세한 내용은 [Remove-TenantAllowBlockListItems를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="625b2-223">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="625b2-224">테넌트 허용/차단 목록에 대한 URL 구문</span><span class="sxs-lookup"><span data-stu-id="625b2-224">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="625b2-225">IP4v 및 IPv6 주소는 허용되지만 TCP/UDP 포트는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-225">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="625b2-226">파일 이름 확장명은 허용되지 않습니다(예: test.pdf.</span><span class="sxs-lookup"><span data-stu-id="625b2-226">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="625b2-227">유니코드는 지원되지 않지만 Punycode는 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-227">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="625b2-228">다음 명령문이 모두 true이면 호스트 이름을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-228">Hostnames are allowed if all of the following statements are true:</span></span>
  - <span data-ttu-id="625b2-229">호스트 이름에 기간이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-229">The hostname contains a period.</span></span>
  - <span data-ttu-id="625b2-230">기간 왼쪽에 하나 이상의 문자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-230">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="625b2-231">기간의 오른쪽에 두 개 이상의 문자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-231">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="625b2-232">예를 들어 허용되거나 `t.co` `.com` 허용되지 `contoso.` 않습니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-232">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="625b2-233">하위 경로는 암시적이지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-233">Subpaths are not implied.</span></span>

  <span data-ttu-id="625b2-234">예를 들어 `contoso.com` . `contoso.com/a`</span><span class="sxs-lookup"><span data-stu-id="625b2-234">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="625b2-235">와일드카드(\*)는 다음 시나리오에서 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-235">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="625b2-236">하위omain을 지정하려면 왼쪽 와일드카드 다음에 기간이 와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-236">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="625b2-237">예를 들어 `*.contoso.com` 허용됩니다. `*contoso.com` 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-237">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="625b2-238">오른쪽 와일드카드는 슬래시(/)를 따라 경로를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-238">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="625b2-239">예를 들어 허용되거나 `contoso.com/*` `contoso.com*` 허용되지 `contoso.com/ab*` 않습니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-239">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="625b2-240">모든 하위 경로는 오른쪽 와일드카드로 암시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-240">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="625b2-241">예를 들어 `contoso.com/*` . `contoso.com/a`</span><span class="sxs-lookup"><span data-stu-id="625b2-241">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="625b2-242">`*.com*` 가 잘못되었습니다(확인 가능한 도메인이 아니며 오른쪽 와일드카드가 슬래시를 따르지 않습니다).</span><span class="sxs-lookup"><span data-stu-id="625b2-242">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="625b2-243">와일드카드는 IP 주소에서 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-243">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="625b2-244">다음과 같은 시나리오에서 선조(~) 문자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-244">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="625b2-245">왼쪽 누적은 도메인 및 모든 하위 도메인을 암시합니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-245">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="625b2-246">예를 들어 `~contoso.com` 다음을 `contoso.com` `*.contoso.com` 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-246">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="625b2-247">URL 항목은 모든 프로토콜에 적용될 수 있기 때문에 프로토콜(예: 또는 )을 포함하는 URL 항목은 `http://` `https://` `ftp://` 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-247">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="625b2-248">사용자 이름 또는 암호는 지원되거나 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-248">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="625b2-249">따옴표(' 또는 ")는 잘못된 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-249">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="625b2-250">URL에는 가능한 경우 모든 리디렉션이 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-250">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="625b2-251">URL 입력 시나리오</span><span class="sxs-lookup"><span data-stu-id="625b2-251">URL entry scenarios</span></span>

<span data-ttu-id="625b2-252">유효한 URL 항목 및 해당 결과는 다음 섹션에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-252">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="625b2-253">시나리오: 와일드카드 없음</span><span class="sxs-lookup"><span data-stu-id="625b2-253">Scenario: No wildcards</span></span>

<span data-ttu-id="625b2-254">**항목:**`contoso.com`</span><span class="sxs-lookup"><span data-stu-id="625b2-254">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="625b2-255">**일치 허용**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="625b2-255">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="625b2-256">**일치하지 않는 경우:**</span><span class="sxs-lookup"><span data-stu-id="625b2-256">**Allow not matched**:</span></span>

  - <span data-ttu-id="625b2-257">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="625b2-257">abc-contoso.com</span></span>
  - <span data-ttu-id="625b2-258">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="625b2-258">contoso.com/a</span></span>
  - <span data-ttu-id="625b2-259">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="625b2-259">payroll.contoso.com</span></span>
  - <span data-ttu-id="625b2-260">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="625b2-260">test.com/contoso.com</span></span>
  - <span data-ttu-id="625b2-261">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="625b2-261">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="625b2-262">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="625b2-262">www.contoso.com</span></span>
  - <span data-ttu-id="625b2-263">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="625b2-263">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="625b2-264">**블록 일치**:</span><span class="sxs-lookup"><span data-stu-id="625b2-264">**Block match**:</span></span>

  - <span data-ttu-id="625b2-265">contoso.com</span><span class="sxs-lookup"><span data-stu-id="625b2-265">contoso.com</span></span>
  - <span data-ttu-id="625b2-266">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="625b2-266">contoso.com/a</span></span>
  - <span data-ttu-id="625b2-267">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="625b2-267">payroll.contoso.com</span></span>
  - <span data-ttu-id="625b2-268">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="625b2-268">test.com/contoso.com</span></span>
  - <span data-ttu-id="625b2-269">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="625b2-269">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="625b2-270">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="625b2-270">www.contoso.com</span></span>
  - <span data-ttu-id="625b2-271">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="625b2-271">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="625b2-272">**블록이 일치하지 않는 경우**: abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="625b2-272">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="625b2-273">시나리오: 왼쪽 와일드카드(하위omain)</span><span class="sxs-lookup"><span data-stu-id="625b2-273">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="625b2-274">**항목:**`*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="625b2-274">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="625b2-275">**일치 및** **차단 일치 허용**:</span><span class="sxs-lookup"><span data-stu-id="625b2-275">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="625b2-276">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="625b2-276">www.contoso.com</span></span>
  - <span data-ttu-id="625b2-277">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="625b2-277">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="625b2-278">**일치하지 않는 허용** 및 **차단이 일치하지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="625b2-278">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="625b2-279">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="625b2-279">123contoso.com</span></span>
  - <span data-ttu-id="625b2-280">contoso.com</span><span class="sxs-lookup"><span data-stu-id="625b2-280">contoso.com</span></span>
  - <span data-ttu-id="625b2-281">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="625b2-281">test.com/contoso.com</span></span>
  - <span data-ttu-id="625b2-282">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="625b2-282">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="625b2-283">시나리오: 경로 맨 위에 있는 오른쪽 와일드카드</span><span class="sxs-lookup"><span data-stu-id="625b2-283">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="625b2-284">**항목:**`contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="625b2-284">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="625b2-285">**일치 및** **차단 일치 허용**:</span><span class="sxs-lookup"><span data-stu-id="625b2-285">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="625b2-286">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="625b2-286">contoso.com/a/b</span></span>
  - <span data-ttu-id="625b2-287">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="625b2-287">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="625b2-288">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="625b2-288">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="625b2-289">**일치하지 않는 허용** 및 **차단이 일치하지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="625b2-289">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="625b2-290">contoso.com</span><span class="sxs-lookup"><span data-stu-id="625b2-290">contoso.com</span></span>
  - <span data-ttu-id="625b2-291">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="625b2-291">contoso.com/a</span></span>
  - <span data-ttu-id="625b2-292">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="625b2-292">www.contoso.com</span></span>
  - <span data-ttu-id="625b2-293">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="625b2-293">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="625b2-294">시나리오: 왼쪽 누적</span><span class="sxs-lookup"><span data-stu-id="625b2-294">Scenario: Left tilde</span></span>

<span data-ttu-id="625b2-295">**항목:**`~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="625b2-295">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="625b2-296">**일치 및** **차단 일치 허용**:</span><span class="sxs-lookup"><span data-stu-id="625b2-296">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="625b2-297">contoso.com</span><span class="sxs-lookup"><span data-stu-id="625b2-297">contoso.com</span></span>
  - <span data-ttu-id="625b2-298">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="625b2-298">www.contoso.com</span></span>
  - <span data-ttu-id="625b2-299">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="625b2-299">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="625b2-300">**일치하지 않는 허용** 및 **차단이 일치하지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="625b2-300">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="625b2-301">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="625b2-301">123contoso.com</span></span>
  - <span data-ttu-id="625b2-302">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="625b2-302">contoso.com/abc</span></span>
  - <span data-ttu-id="625b2-303">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="625b2-303">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="625b2-304">시나리오: 오른쪽 와일드카드 접미사</span><span class="sxs-lookup"><span data-stu-id="625b2-304">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="625b2-305">**항목:**`contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="625b2-305">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="625b2-306">**일치 및** **차단 일치 허용**:</span><span class="sxs-lookup"><span data-stu-id="625b2-306">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="625b2-307">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="625b2-307">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="625b2-308">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="625b2-308">contoso.com/a</span></span>
  - <span data-ttu-id="625b2-309">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="625b2-309">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="625b2-310">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="625b2-310">contoso.com/ab</span></span>
  - <span data-ttu-id="625b2-311">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="625b2-311">contoso.com/b</span></span>
  - <span data-ttu-id="625b2-312">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="625b2-312">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="625b2-313">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="625b2-313">contoso.com/ba</span></span>

- <span data-ttu-id="625b2-314">**일치하지 않는 허용** 및 **일치하지 않는** 차단 : contoso.com</span><span class="sxs-lookup"><span data-stu-id="625b2-314">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="625b2-315">시나리오: 왼쪽 와일드카드 하위omain 및 오른쪽 와일드카드 접미사</span><span class="sxs-lookup"><span data-stu-id="625b2-315">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="625b2-316">**항목:**`*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="625b2-316">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="625b2-317">**일치 및** **차단 일치 허용**:</span><span class="sxs-lookup"><span data-stu-id="625b2-317">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="625b2-318">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="625b2-318">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="625b2-319">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="625b2-319">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="625b2-320">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="625b2-320">www.contoso.com/a</span></span>
  - <span data-ttu-id="625b2-321">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="625b2-321">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="625b2-322">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="625b2-322">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="625b2-323">**일치하지 않는 허용** 및 **일치하지 않는** 차단 : contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="625b2-323">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="625b2-324">시나리오: 왼쪽 및 오른쪽 바른 바스</span><span class="sxs-lookup"><span data-stu-id="625b2-324">Scenario: Left and right tilde</span></span>

<span data-ttu-id="625b2-325">**항목:**`~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="625b2-325">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="625b2-326">**일치 및** **차단 일치 허용**:</span><span class="sxs-lookup"><span data-stu-id="625b2-326">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="625b2-327">contoso.com</span><span class="sxs-lookup"><span data-stu-id="625b2-327">contoso.com</span></span>
  - <span data-ttu-id="625b2-328">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="625b2-328">contoso.com/a</span></span>
  - <span data-ttu-id="625b2-329">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="625b2-329">www.contoso.com</span></span>
  - <span data-ttu-id="625b2-330">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="625b2-330">www.contoso.com/b</span></span>
  - <span data-ttu-id="625b2-331">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="625b2-331">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="625b2-332">**일치하지 않는 허용** 및 **차단이 일치하지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="625b2-332">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="625b2-333">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="625b2-333">123contoso.com</span></span>
  - <span data-ttu-id="625b2-334">contoso.org</span><span class="sxs-lookup"><span data-stu-id="625b2-334">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="625b2-335">시나리오: IP 주소</span><span class="sxs-lookup"><span data-stu-id="625b2-335">Scenario: IP address</span></span>

<span data-ttu-id="625b2-336">**항목:**`1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="625b2-336">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="625b2-337">**일치 및** **차단 일치** 허용 : 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="625b2-337">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="625b2-338">**일치하지 않는 허용** 및 **차단이 일치하지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="625b2-338">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="625b2-339">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="625b2-339">1.2.3.4/a</span></span>
  - <span data-ttu-id="625b2-340">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="625b2-340">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="625b2-341">오른쪽 와일드카드가 있는 IP 주소</span><span class="sxs-lookup"><span data-stu-id="625b2-341">IP address with right wildcard</span></span>

<span data-ttu-id="625b2-342">**항목:**`1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="625b2-342">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="625b2-343">**일치 및** **차단 일치 허용**:</span><span class="sxs-lookup"><span data-stu-id="625b2-343">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="625b2-344">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="625b2-344">1.2.3.4/b</span></span>
  - <span data-ttu-id="625b2-345">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="625b2-345">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="625b2-346">잘못된 항목의 예</span><span class="sxs-lookup"><span data-stu-id="625b2-346">Examples of invalid entries</span></span>

<span data-ttu-id="625b2-347">유효하지 않은 항목은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="625b2-347">The following entries are invalid:</span></span>

- <span data-ttu-id="625b2-348">**누락되었거나 잘못된 도메인 값:**</span><span class="sxs-lookup"><span data-stu-id="625b2-348">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="625b2-349">contoso</span><span class="sxs-lookup"><span data-stu-id="625b2-349">contoso</span></span>
  - <span data-ttu-id="625b2-350">\*.contoso.\*</span><span class="sxs-lookup"><span data-stu-id="625b2-350">\*.contoso.\*</span></span>
  - <span data-ttu-id="625b2-351">\*.com</span><span class="sxs-lookup"><span data-stu-id="625b2-351">\*.com</span></span>
  - <span data-ttu-id="625b2-352">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="625b2-352">\*.pdf</span></span>

- <span data-ttu-id="625b2-353">**텍스트의 와일드카드:**</span><span class="sxs-lookup"><span data-stu-id="625b2-353">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="625b2-354">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="625b2-354">\*contoso.com</span></span>
  - <span data-ttu-id="625b2-355">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="625b2-355">contoso.com\*</span></span>
  - <span data-ttu-id="625b2-356">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="625b2-356">\*1.2.3.4</span></span>
  - <span data-ttu-id="625b2-357">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="625b2-357">1.2.3.4\*</span></span>
  - <span data-ttu-id="625b2-358">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="625b2-358">contoso.com/a\*</span></span>
  - <span data-ttu-id="625b2-359">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="625b2-359">contoso.com/ab\*</span></span>

- <span data-ttu-id="625b2-360">**포트가 있는 IP 주소:**</span><span class="sxs-lookup"><span data-stu-id="625b2-360">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="625b2-361">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="625b2-361">contoso.com:443</span></span>
  - <span data-ttu-id="625b2-362">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="625b2-362">abc.contoso.com:25</span></span>

- <span data-ttu-id="625b2-363">**설명하지 않는 와일드카드:**</span><span class="sxs-lookup"><span data-stu-id="625b2-363">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="625b2-364">\*.\*</span><span class="sxs-lookup"><span data-stu-id="625b2-364">\*.\*</span></span>

- <span data-ttu-id="625b2-365">**중간 와일드카드**:</span><span class="sxs-lookup"><span data-stu-id="625b2-365">**Middle wildcards**:</span></span>

  - <span data-ttu-id="625b2-366">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="625b2-366">conto\*so.com</span></span>
  - <span data-ttu-id="625b2-367">conto~so.com</span><span class="sxs-lookup"><span data-stu-id="625b2-367">conto~so.com</span></span>

- <span data-ttu-id="625b2-368">**이중 와일드카드**</span><span class="sxs-lookup"><span data-stu-id="625b2-368">**Double wildcards**</span></span>

  - <span data-ttu-id="625b2-369">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="625b2-369">contoso.com/\*\*</span></span>
  - <span data-ttu-id="625b2-370">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="625b2-370">contoso.com/\*/\*</span></span>
