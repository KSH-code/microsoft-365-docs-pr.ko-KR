---
title: 무제한 보관 사용 - 관리자 도움말
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: e2a789f2-9962-4960-9fd4-a00aa063559e
description: '관리자: Exchange Online 사서함에 대해 무제한 저장소를 제공하는 자동 확장 보관을 사용하도록 설정하는 방법을 배워야 합니다. 전체 조직 또는 특정 사용자에 대해 자동 확장 보관을 사용하도록 설정할 수 있습니다.'
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 237e3032b21f6fe0d3a97d2ae41c527e500fb2e0
ms.sourcegitcommit: 7d4aa58ae9fc893825b6e648fa3f072c3ac59628
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2021
ms.locfileid: "49790086"
---
# <a name="enable-unlimited-archiving---admin-help"></a><span data-ttu-id="d2414-104">무제한 보관 사용 - 관리자 도움말</span><span class="sxs-lookup"><span data-stu-id="d2414-104">Enable unlimited archiving - Admin Help</span></span>

<span data-ttu-id="d2414-105">Exchange Online 자동 확장 보관 기능을 사용하여 보관 사서함에 대해 무제한 저장소 공간을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2414-105">You can use the Exchange Online auto-expanding archiving feature to enable unlimited storage space for archive mailboxes.</span></span> <span data-ttu-id="d2414-106">자동 확장 보관이 켜져 있는 경우 저장소 제한에 도달하면 사용자의 보관 사서함에 추가 저장소 공간이 자동으로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2414-106">When auto-expanding archiving is turned on, additional storage space is automatically added to a user's archive mailbox when it approaches the storage limit.</span></span> <span data-ttu-id="d2414-107">그 결과 사서함 저장소 용량에 제한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2414-107">The result is unlimited mailbox storage capacity.</span></span> <span data-ttu-id="d2414-108">조직의 모든 사용자 또는 특정 사용자에 대해 자동 확장 보관을 켜도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2414-108">You can turn on auto-expanding archiving for everyone in your organization or just for specific users.</span></span> <span data-ttu-id="d2414-109">자동 확장 보관에 대한 자세한 내용은 [Office 365의](unlimited-archiving.md)무제한 보관 개요를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d2414-109">For more information about auto-expanding archiving, see [Overview of unlimited archiving in Office 365](unlimited-archiving.md).</span></span>

## <a name="before-you-enable-auto-expanding-archiving"></a><span data-ttu-id="d2414-110">자동 확장 보관을 사용하도록 설정하기 전에</span><span class="sxs-lookup"><span data-stu-id="d2414-110">Before you enable auto-expanding archiving</span></span>

- <span data-ttu-id="d2414-111">전체 조직 또는 특정 사용자에 대해 자동 확장 보관을 사용하도록 설정하려면 조직의 전역 관리자 또는 Exchange Online 조직에서 Organization Management 역할 그룹의 구성원이 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2414-111">You have to be a global administrator in your organization or a member of the Organization Management role group in your Exchange Online organization to enable auto-expanding archiving for your entire organization or for specific users.</span></span> <span data-ttu-id="d2414-112">또는 Mail Recipients 역할이 할당된 역할 그룹의 구성원이 되어 특정 사용자에 대해 자동 확장 보관을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2414-112">Alternately, you have to be a member of a role group that's assigned the Mail Recipients role to enable auto-expanding archiving for specific users.</span></span>

- <span data-ttu-id="d2414-113">자동 확장 보관을 사용하려면 먼저 사용자의 보관 사서함을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2414-113">A user's archive mailbox has to be enabled before you can enable auto-expanding archiving.</span></span> <span data-ttu-id="d2414-114">보관 사서함을 사용하도록 설정하려면 사용자에게 Exchange Online 계획 2 라이선스가 할당되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2414-114">A user must be assigned an Exchange Online Plan 2 license to enable the archive mailbox.</span></span> <span data-ttu-id="d2414-115">사용자에게 Exchange Online 계획 1 라이선스가 할당된 경우 보관 사서함을 사용하도록 설정하려면 별도의 Exchange Online Archiving 라이선스를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2414-115">If a user is assigned an Exchange Online Plan 1 license, you would have to assign them a separate Exchange Online Archiving license to enable their archive mailbox.</span></span> <span data-ttu-id="d2414-116">보안 및 준수 센터에서 보관 [사서함 & 참조.](enable-archive-mailboxes.md)</span><span class="sxs-lookup"><span data-stu-id="d2414-116">See [Enable archive mailboxes in the Security & Compliance Center](enable-archive-mailboxes.md).</span></span>

- <span data-ttu-id="d2414-117">PowerShell을 사용하여 보관 사서함을 사용하도록 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2414-117">You can also use PowerShell to enable archive mailboxes.</span></span> <span data-ttu-id="d2414-118">조직의 [모든](#more-information) 사용자에 대해 보관 사서함을 사용하도록 설정하는 데 사용할 수 있는 PowerShell 명령의 예는 추가 정보 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d2414-118">See the [More information](#more-information) section for an example of the PowerShell command that you can use to enable archive mailboxes for all users in your organization.</span></span>

- <span data-ttu-id="d2414-119">자동 확장 보관 기능은 공유 사서함도 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="d2414-119">Auto-expanding archiving also supports shared mailboxes.</span></span> <span data-ttu-id="d2414-120">공유 사서함에 대해 보관 사서함을 사용하도록 설정하려면 Exchange Online 계획 2 라이선스 또는 Exchange Online 계획 1 라이선스와 Exchange Online Archiving 라이선스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d2414-120">To enable the archive for a shared mailbox, an Exchange Online Plan 2 license or an Exchange Online Plan 1 license with an Exchange Online Archiving license is required.</span></span>

- <span data-ttu-id="d2414-121">Exchange 관리 센터 또는 보안 & 준수 센터를 사용하여 자동 확장 보관을 사용하도록 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2414-121">You can't use the Exchange admin center or the Security & Compliance Center to enable auto-expanding archiving.</span></span> <span data-ttu-id="d2414-122">Exchange Online PowerShell을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2414-122">You have to use Exchange Online PowerShell.</span></span> <span data-ttu-id="d2414-123">원격 PowerShell을 사용하여 Exchange Online 조직에 연결하기 위해 [Exchange Online PowerShell에 연결합니다.](https://go.microsoft.com/fwlink/p/?linkid=396554)</span><span class="sxs-lookup"><span data-stu-id="d2414-123">To connect to your Exchange Online organization using remote PowerShell, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

## <a name="enable-auto-expanding-archiving-for-your-entire-organization"></a><span data-ttu-id="d2414-124">전체 조직에 대해 자동 확장 보관 사용</span><span class="sxs-lookup"><span data-stu-id="d2414-124">Enable auto-expanding archiving for your entire organization</span></span>

<span data-ttu-id="d2414-125">전체 조직에 대해 자동 확장 보관을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2414-125">You can enable auto-expanding archiving for your entire organization.</span></span> <span data-ttu-id="d2414-126">이 기능을 설정하면 기존 사용자 사서함 및 새로 만든 사용자 사서함에 대해 자동 확장 보관이 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2414-126">After you turn it on, auto-expanding archiving will be enabled for existing user mailboxes and for new user mailboxes that are created.</span></span> <span data-ttu-id="d2414-127">사용자 사서함을 만들 때 자동 확장 보관 기능이 새 사용자 사서함에 대해 작동하도록 사용자의 기본 보관 사서함을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2414-127">When you create user mailboxes, be sure to enable the user's main archive mailbox so the auto-expanding archiving feature works for the new user mailbox.</span></span>
  
1. [<span data-ttu-id="d2414-128">Exchange Online PowerShell에 연결</span><span class="sxs-lookup"><span data-stu-id="d2414-128">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?linkid=396554)

2. <span data-ttu-id="d2414-129">Exchange Online PowerShell에서 다음 명령을 실행하여 전체 조직에 대해 자동 확장 보관을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2414-129">Run the following command in Exchange Online PowerShell to enable auto-expanding archiving for your entire organization.</span></span>

    ```powershell
    Set-OrganizationConfig -AutoExpandingArchive
    ```

## <a name="enable-auto-expanding-archiving-for-specific-users"></a><span data-ttu-id="d2414-130">특정 사용자에 대해 자동 확장 보관 사용</span><span class="sxs-lookup"><span data-stu-id="d2414-130">Enable auto-expanding archiving for specific users</span></span>

<span data-ttu-id="d2414-131">조직의 모든 사용자에 대해 자동 확장 보관을 사용하도록 설정하는 대신 특정 사용자에 대해만 보관을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2414-131">Instead of enabling auto-expanding archiving for every user in your organization, you can enable it only for specific users.</span></span> <span data-ttu-id="d2414-132">일부 사용자만 대용량 보관 저장소 용량을 필요로 할 수 있기 때문에 이 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2414-132">You might do this because only some users might have a need for a large archive storage capacity.</span></span>
  
<span data-ttu-id="d2414-133">특정 사용자 및 사용자의 사서함에 대해 자동 확장 보관을 사용하도록 설정하거나 보존 정책에 할당하면 다음과 같은 두 가지 구성이 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2414-133">When you enable auto-expanding archiving for a specific user and the user's mailbox in on hold or assigned to a retention policy, the following two configurations changes are made:</span></span>
  
- <span data-ttu-id="d2414-134">사용자의 기본 보관 사서함에 대한 저장소 할당량은 10GB(100GB에서 110GB)로 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="d2414-134">The storage quota for the user's primary archive mailbox is increased by 10 GB (from 100 GB to 110 GB).</span></span> <span data-ttu-id="d2414-135">보관 경고 할당량도 10GB(90GB에서 100GB)로 늘어났습니다.</span><span class="sxs-lookup"><span data-stu-id="d2414-135">The archive warning quota is also increased by 10 GB (from 90 GB to 100 GB).</span></span>

- <span data-ttu-id="d2414-136">사용자의 기본 사서함에 있는 복구 가능한 항목 폴더의 저장소 할당량은 10GB(또한 100GB에서 110GB)로 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="d2414-136">The storage quota for the Recoverable Items folder in the user's primary mailbox is increased by 10 GB (also from 100 GB to 110 GB).</span></span> <span data-ttu-id="d2414-137">복구 가능한 항목 경고 할당량도 10GB(90GB에서 100GB)로 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="d2414-137">The Recoverable Items warning quota is also increased by 10 GB (from 90 GB to 100 GB).</span></span> <span data-ttu-id="d2414-138">이러한 변경 내용은 보류된 사서함 또는 보존 정책에 할당된 경우만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2414-138">These changes are applicable only if the mailbox in on hold or assigned to a retention policy.</span></span>

<span data-ttu-id="d2414-139">이 추가 공간은 자동 확장 보관이 프로비전되기 전에 발생할 수 있는 저장소 문제를 방지하기 위해 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2414-139">This additional space is added to prevent any storage issues that may occur before the auto-expanding archive is provisioned.</span></span> <span data-ttu-id="d2414-140">이전  *섹션에서*  설명한 바와 같이 전체 조직에 대해 자동 확장 보관을 사용하도록 설정하면 추가 저장소 공간이 추가되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2414-140">Additional storage space  *is not*  added when you enable auto-expanding archiving for your entire organization, as described in the previous section.</span></span>
  
1. [<span data-ttu-id="d2414-141">Exchange Online PowerShell에 연결</span><span class="sxs-lookup"><span data-stu-id="d2414-141">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?linkid=396554)

2. <span data-ttu-id="d2414-142">Exchange Online PowerShell에서 다음 명령을 실행하여 특정 사용자에 대해 자동 확장 보관을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2414-142">Run the following command in Exchange Online PowerShell to enable auto-expanding archiving for a specific user.</span></span> <span data-ttu-id="d2414-143">앞서 설명한 것 처럼 사용자의 보관 사서함 (주 보관)을 사용 하도록 설정 해야 해당 사용자에 대 한 자동 확장 보관을 하도록 설정 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2414-143">As previously explained, the user's archive mailbox (main archive) must be enabled before you can turn on auto-expanding archiving for that user.</span></span>

    ```powershell
    Enable-Mailbox <user mailbox> -AutoExpandingArchive
    ```

> [!IMPORTANT]
> <span data-ttu-id="d2414-144">Exchange 하이브리드 배포에서는 **Enable-Mailbox -AutoExpandingArchive** 명령을 사용하여 기본 사서함이 On-premises에 있으며 보관 사서함이 클라우드 기반인 특정 사용자에 대해 자동 확장 보관을 사용하도록 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2414-144">In an Exchange hybrid deployment, you can't use the **Enable-Mailbox -AutoExpandingArchive** command to enable auto-expanding archiving for a specific user whose primary mailbox is on-premises and whose archive mailbox is cloud-based.</span></span> <span data-ttu-id="d2414-145">Exchange 하이브리드 배포에서 클라우드 기반 보관 사서함에 대해 자동 확장 보관을 사용하도록 설정하려면 Exchange Online PowerShell에서 **Set-OrganizationConfig -AutoExpandingArchive** 명령을 실행하여 전체 조직에 대해 자동 확장 보관을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2414-145">To enable auto-expanding archiving for cloud-based archive mailboxes in an Exchange hybrid deployment, you have to run the **Set-OrganizationConfig -AutoExpandingArchive** command in Exchange Online PowerShell to enable auto-expanding archiving for the entire organization.</span></span> <span data-ttu-id="d2414-146">사용자의 기본 사서함과 보관 사서함이 모두 클라우드 기반인 경우 **Enable-Mailbox -AutoExpandingArchive** 명령을 사용하여 해당 특정 사용자에 대해 자동 확장 보관을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2414-146">If a user's primary and archive mailboxes are both cloud-based, then you can use the **Enable-Mailbox -AutoExpandingArchive** command to enable auto-expanding archiving for that specific user.</span></span>
  
## <a name="verify-that-auto-expanding-archiving-is-enabled"></a><span data-ttu-id="d2414-147">자동 확장 보관이 사용하도록 설정되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="d2414-147">Verify that auto-expanding archiving is enabled</span></span>

<span data-ttu-id="d2414-148">조직에 대해 자동 확장 보관이 사용하도록 설정되어 있는지 확인하기 위해 Exchange Online PowerShell에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d2414-148">To verify that auto-expanding archiving is enabled for your organization, run the following command in Exchange Online PowerShell.</span></span>

```powershell
Get-OrganizationConfig | FL AutoExpandingArchiveEnabled
```

<span data-ttu-id="d2414-149">값은 자동 확장 보관이 조직에 대해 사용하도록 설정되어 있는  `True` 경우를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d2414-149">A value of  `True` indicates that auto-expanding archiving is enabled for the organization.</span></span> 
  
<span data-ttu-id="d2414-150">특정 사용자에 대해 자동 확장 보관이 사용하도록 설정되어 있는지 확인하기 위해 Exchange Online PowerShell에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d2414-150">To verify that auto-expanding archiving is enabled for a specific user, run the following command in Exchange Online PowerShell.</span></span>
  
```powershell
Get-Mailbox <user mailbox> | FL AutoExpandingArchiveEnabled
```

<span data-ttu-id="d2414-151">값은 사용자에 대해 자동 확장 보관이 사용하도록 설정되어 있는  `True` 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d2414-151">A value of  `True` indicates that auto-expanding archiving is enabled for the user.</span></span> 
  
<span data-ttu-id="d2414-152">자동 확장 보관을 사용하도록 설정한 후 다음에 유의하십시오.</span><span class="sxs-lookup"><span data-stu-id="d2414-152">Keep the following things in mind after you enable auto-expanding archiving:</span></span>
  
- <span data-ttu-id="d2414-153">**Set-OrganizationConfig -AutoExpandingArchive** 명령을 실행하여 조직에 대해 자동 확장 보관을 사용하도록 설정하는 경우 개별 사서함에서 **Enable-Mailbox -AutoExpandingArchive를** 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2414-153">If you run the **Set-OrganizationConfig -AutoExpandingArchive** command to enable auto-expanding archiving for your organization, you don't have to run the **Enable-Mailbox -AutoExpandingArchive** on individual mailboxes.</span></span> <span data-ttu-id="d2414-154">조직에 대해 자동 확장 보관을 사용하도록 설정하기 위해 **Set-OrganizationConfig** cmdlet을 실행해도 사용자 사서함의  *AutoExpandingArchiveEnabled*  속성은 변경되지 `True` 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2414-154">Running the **Set-OrganizationConfig** cmdlet to enable auto-expanding archiving for your organization doesn't change the  *AutoExpandingArchiveEnabled*  property on user mailboxes to `True`.</span></span>

- <span data-ttu-id="d2414-155">마찬가지로 자동 확장 보관을 사용하도록 설정하면  *ArchiveQuota*  및  *ArchiveWarningQuota*  사서함 속성의 값이 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2414-155">Similarly, the values for the  *ArchiveQuota*  and  *ArchiveWarningQuota*  mailbox properties aren't changed when you enable auto-expanding archiving.</span></span> <span data-ttu-id="d2414-156">실제로 사용자 사서함에 대해 자동 확장 보관을 사용하도록 설정하고  *AutoExpandingArchiveEnabled*  속성을 설정하면  `True`  *ArchiveQuota*  및  *ArchiveWarningQuota*  속성은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2414-156">In fact, when you enable auto-expanding archiving for a user mailbox and the  *AutoExpandingArchiveEnabled*  property is set to  `True`, the  *ArchiveQuota*  and  *ArchiveWarningQuota*  properties are ignored.</span></span> <span data-ttu-id="d2414-157">사용자의 사서함에 대해 자동 확장 보관을 사용하도록 설정한 후 이러한 사서함 속성의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d2414-157">Here's an example of these mailbox properties after auto-expanding archiving is enabled for a user's mailbox.</span></span> 

    ![자동 확장 보관을 사용하도록 설정하면 ArchiveQuota 및 ArchiveWarningQuota 속성이 무시됩니다.](../media/6a1c1b69-5c4c-4267-aac8-53577667f03e.png)

## <a name="more-information"></a><span data-ttu-id="d2414-159">추가 정보</span><span class="sxs-lookup"><span data-stu-id="d2414-159">More information</span></span>

- <span data-ttu-id="d2414-160">PowerShell을 사용하여 보관 사서함을 사용하도록 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2414-160">You can also use PowerShell to enable archive mailboxes.</span></span> <span data-ttu-id="d2414-161">예를 들어 Exchange Online PowerShell에서 다음 명령을 실행하여 보관 사서함을 아직 사용하도록 설정하지 않은 모든 사용자에 대해 보관 사서함을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2414-161">For example, you can run the following command in Exchange Online PowerShell to enable archive mailboxes for all users whose archive mailbox isn't already enabled.</span></span>

    ```powershell
    Get-Mailbox -Filter {ArchiveStatus -Eq "None" -AND RecipientTypeDetails -eq "UserMailbox"} | Enable-Mailbox -Archive
    ```

- <span data-ttu-id="d2414-162">조직 또는 특정 사용자에 대해 자동 확장 보관을 켜면 보관 사서함(복구 가능한 항목 폴더 포함)이 90GB에 도달하면 보관 사서함이 자동 확장 보관함으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2414-162">After you turn on auto-expanding archiving for your organization or for a specific user, an archive mailbox is converted to an auto-expanding archive when the archive mailbox (including the Recoverable Items folder) reaches 90 GB.</span></span> <span data-ttu-id="d2414-163">추가 저장소 공간을 프로비전하는 데 최대 30일이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2414-163">It can take up to 30 days for the additional storage space to be provisioned.</span></span>

- <span data-ttu-id="d2414-164">자동 확장 보관을 켜면 보관을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2414-164">After you turn on auto-expanding archiving, it can't be turned off.</span></span>

- <span data-ttu-id="d2414-165">자동 확장 보관은 Exchange 하이브리드 배포에서 클라우드 기반 보관 사서함에 대해 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2414-165">Auto-expanding archiving is supported for cloud-based archive mailboxes in an Exchange hybrid deployment for users who have an on-premises primary mailbox.</span></span> <span data-ttu-id="d2414-166">그러나 클라우드 기반 보관 사서함에 대해 자동 확장 보관을 사용하도록 설정한 후 사서함을 다시 보관하는 오프보드를 On-premises Exchange 조직에 오프보드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2414-166">However, after auto-expanding archiving is enabled for a cloud-based archive mailbox, you can't off-board that archive mailbox back to the on-premises Exchange organization.</span></span> <span data-ttu-id="d2414-167">자동 확장 보관은 모든 버전의 사서함에 대해 지원되지 Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="d2414-167">Auto-expanding archiving isn't supported for on-premises mailboxes in any version of Exchange Server.</span></span>

- <span data-ttu-id="d2414-168">사용자가 보관 사서함의 추가 저장소 영역에 있는 항목에 액세스하는 데 사용할 수 있는 Outlook 클라이언트 목록은 무제한 보관 개요의 [](unlimited-archiving.md#outlook-requirements-for-accessing-items-in-an-auto-expanded-archive)"자동 확장 보관함의 항목에 액세스하기 위한 Outlook 요구 사항" 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d2414-168">For a list of Outlook clients that users can use to access items in the additional storage area in their archive mailbox, see the "Outlook requirements for accessing items in an auto-expanded archive" section in [Overview of unlimited archiving](unlimited-archiving.md#outlook-requirements-for-accessing-items-in-an-auto-expanded-archive).</span></span>

- <span data-ttu-id="d2414-169">앞서 설명한처럼 **Enable-Mailbox -AutoExpandingArchive** 명령을 실행할 때 사용자의 기본 보관 사서함의 저장소 할당량(사서함이 보류된 경우 복구 가능한 항목 폴더)에 10GB가 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2414-169">As previously explained, 10 GB is added to the storage quota of the user's primary archive mailbox (and to the Recoverable Items folder if the mailbox is on hold) when you run the **Enable-Mailbox -AutoExpandingArchive** command.</span></span> <span data-ttu-id="d2414-170">이렇게 하면 자동 확장 저장소 공간이 프로비전될 때까지(최대 30일까지 걸릴 수 있는) 추가 저장소가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2414-170">This provides additional storage until the auto-expanded storage space is provisioned (which can take up to 30 days).</span></span> <span data-ttu-id="d2414-171">이 추가 저장소 공간은 **Set-OrganizationConfig -AutoExpandingArchive를** 실행하여 조직의 모든 사서함에 대해 자동 확장 보관을 사용하도록 설정할 때 추가되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2414-171">This additional storage space isn't added when you run the **Set-OrganizationConfig -AutoExpandingArchive** to enable auto-expanding archiving for all mailboxes in your organization.</span></span> <span data-ttu-id="d2414-172">전체 조직에 대해 자동 확장 보관을 사용하도록 설정했지만 특정 사용자에 대해 10GB의 저장소 공간을 더 추가해야 하는 경우 해당 사서함에서 **Enable-Mailbox -AutoExpandingArchive** 명령을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2414-172">If you enabled auto-expanding archiving for the entire organization, but need to add the additional 10 GB of storage space for a specific user, you can run the **Enable-Mailbox -AutoExpandingArchive** command on that mailbox.</span></span> <span data-ttu-id="d2414-173">자동 확장 보관이 이미 사용하도록 설정되어 있지만 추가 저장소 공간이 사서함에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2414-173">You will receive an error saying that auto-expanding archiving has already been enabled, but the additional storage space will be added to the mailbox.</span></span>

- <span data-ttu-id="d2414-174">관리자가 저장소 할당량을 조정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2414-174">Administrators can't adjust the storage quota.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d2414-175">자동 확장 보관은 하루당 1GB를 초과하지 않는 증가율의 개별 사용자 또는 공유 사서함에 사용되는 사서함에만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2414-175">Auto-expanding archiving is only supported for mailboxes used for individual users or shared mailboxes with a growth rate that doesn't exceed 1 GB per day.</span></span> <span data-ttu-id="d2414-176">보관 목적으로 저널링, 전송 규칙 또는 자동 전달 규칙을 사용하여 메시지를 보관 사서함으로 복사할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2414-176">Using journaling, transport rules, or auto-forwarding rules to copy messages to an archive mailbox for the purposes of archiving is not permitted.</span></span> <span data-ttu-id="d2414-177">사용자의 보관 사서함은 해당 사용자만을 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d2414-177">A user's archive mailbox is intended for just that user.</span></span> <span data-ttu-id="d2414-178">Microsoft는 사용자의 보관 사서함이 다른 사용자의 보관 데이터를 저장하는 데 사용되는 경우 또는 부적절한 사용의 경우 무제한 보관을 거부할 권리가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2414-178">Microsoft reserves the right to deny unlimited archiving in instances where a user's archive mailbox is used to store archive data for other users or in other cases of inappropriate use.</span></span>
