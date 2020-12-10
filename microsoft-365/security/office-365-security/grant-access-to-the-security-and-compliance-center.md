---
title: 사용자에게 보안 및 준수 센터에 대한 액세스 권한 부여
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
f1_keywords:
- ms.o365.cc.PermissionsHelp
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 2cfce2c8-20c5-47f9-afc4-24b059c1bd76
description: 사용자는 보안 또는 규정 준수 기능을 관리하기 전에 Microsoft 365 보안 & 규정 준수 센터에서 사용 권한을 할당해야 합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1bf8da85a0e090a9d74934ea5084f547d6a8794f
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616611"
---
# <a name="give-users-access-to-the-security--compliance-center"></a><span data-ttu-id="e76ee-103">사용자에게 보안 및 준수 센터에 대한 액세스 권한 부여</span><span class="sxs-lookup"><span data-stu-id="e76ee-103">Give users access to the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="e76ee-104">사용자는 보안 또는 규정 준수 & 관리하기 전에 보안 및 규정 준수 센터에서 사용 권한을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e76ee-104">Users need to be assigned permissions in the Security & Compliance Center before they can manage any of its security or compliance features.</span></span> <span data-ttu-id="e76ee-105">Security & 준수 센터에서 OrganizationManagement 역할 그룹의 전역 관리자 또는 구성원으로 이러한 권한을 사용자에게 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e76ee-105">As a global admin or member of the OrganizationManagement role group in the Security & Compliance Center, you can give these permissions to users.</span></span> <span data-ttu-id="e76ee-106">사용자는 액세스 권한을 부여 받은 보안 또는 규정 준수 기능만 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e76ee-106">Users will only be able to manage the security or compliance features that you give them access to.</span></span>

<span data-ttu-id="e76ee-107">Security & 준수 센터에서 사용자에게 부여할 수 있는 다양한 사용 권한에 대한 자세한 내용은 보안 및 준수 센터에서 & [있습니다.](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="e76ee-107">For more information about the different permissions you can give to users in the Security & Compliance Center, check out [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e76ee-108">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="e76ee-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e76ee-109">이 문서의 단계를 완료하려면 전역 관리자 또는 Security & 준수 센터에서 OrganizationManagement 역할 그룹의 구성원이 되거나,</span><span class="sxs-lookup"><span data-stu-id="e76ee-109">You need to be a global admin, or a member of the OrganizationManagement role group in the Security & Compliance Center, to complete the steps in this article.</span></span>

- <span data-ttu-id="e76ee-110">Security & 준수 센터의 역할 그룹은 Exchange Online의 역할 그룹과 이름이 유사할 수 있지만 동일하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e76ee-110">Role groups for the Security & Compliance Center might have similar names to the role groups in Exchange Online, but they're not the same.</span></span>

- <span data-ttu-id="e76ee-111">역할 그룹 구성원은 Exchange Online과 Security & 공유되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e76ee-111">Role group memberships aren't shared between Exchange Online and the Security & Compliance Center.</span></span>

- <span data-ttu-id="e76ee-112">AOBO(관리 위임된 액세스 권한) 권한이 있는 DAP(위임된 액세스 권한) 파트너는 보안 및 준수 센터에 & 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e76ee-112">Delegated Access Permission (DAP) partners with Administer On Behalf Of (AOBO) permissions can't access the Security & Compliance Center.</span></span>

## <a name="use-the-security--compliance-center-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="e76ee-113">보안 및 & 준수 센터를 사용하여 다른 사용자에게 보안 및 준수 센터에 & 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="e76ee-113">Use the Security & Compliance Center to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="e76ee-114">에서 보안 & 준수 센터를 연 다음 사용 <https://protection.office.com> **권한으로 이동 합니다.**</span><span class="sxs-lookup"><span data-stu-id="e76ee-114">Open the Security & Compliance Center at <https://protection.office.com> and then go to **Permissions**.</span></span> <span data-ttu-id="e76ee-115">사용 권한 탭으로 직접 **이동하려면** 을 을 <https://protection.office.com/permissions> 열습니다.</span><span class="sxs-lookup"><span data-stu-id="e76ee-115">To go directly to the **Permissions** tab, open <https://protection.office.com/permissions>.</span></span>

2. <span data-ttu-id="e76ee-116">역할 그룹 목록에서 역할 그룹을 선택한 다음  편집 ![ 아이콘을 ](../../media/O365-MDM-CreatePolicy-EditIcon.gif) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e76ee-116">From the list of role groups, choose the role group, and then click **Edit** ![Edit icon](../../media/O365-MDM-CreatePolicy-EditIcon.gif).</span></span>

3. <span data-ttu-id="e76ee-117">구성원 아래의 역할 그룹의 속성 페이지에서 아이콘 추가를 클릭하고 추가할 사용자의 이름을 ![ ](../../media/ITPro-EAC-AddIcon.gif) 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e76ee-117">In the role group's properties page under **Members**, click **Add**![Add Icon](../../media/ITPro-EAC-AddIcon.gif) and select the name of the user (or users) you want to add.</span></span>

4. <span data-ttu-id="e76ee-118">역할 그룹에 **\>** 추가할 모든 사용자를 선택한 경우 추가 기능을 클릭한 다음 **확인을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="e76ee-118">When you've selected all of the users you want to add to the role group, click **add-\>** and then **OK**.</span></span>

5. <span data-ttu-id="e76ee-119">작업을 마쳤으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e76ee-119">When you're finished, click **Save**.</span></span>

## <a name="use-security--compliance-center-powershell-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="e76ee-120">보안 & 준수 센터 PowerShell을 사용하여 다른 사용자에게 보안 및 준수 센터에 & 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="e76ee-120">Use Security & Compliance Center PowerShell to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="e76ee-121">[보안 및 준수 센터 PowerShell에 연결하기](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)</span><span class="sxs-lookup"><span data-stu-id="e76ee-121">[Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="e76ee-122">다음 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e76ee-122">Use the following syntax:</span></span>

   ```powershell
   Add-RoleGroupMember -Identity <RoleGroup> -Member <UserIdentity>

   - _Identity_ is the role group.
   - _Member_ is the user or universal security group (USG). You can specify only one member at a time.

   This example adds MatildaS to the Organization Management role group.

   ```PowerShell
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

<span data-ttu-id="e76ee-123">구문과 매개 변수에 대한 자세한 내용은 [Add-RoleGroupMember를 참조합니다.](https://docs.microsoft.com/powershell/module/exchange/add-rolegroupmember)</span><span class="sxs-lookup"><span data-stu-id="e76ee-123">For detailed syntax and parameter issues, see [Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/add-rolegroupmember)</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="e76ee-124">작동 여부는 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="e76ee-124">How do you know this worked?</span></span>

<span data-ttu-id="e76ee-125">보안 및 준수 센터에 대한 액세스 권한이 & 확인을 위해 다음 단계 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="e76ee-125">To verify that you've successfully granted access to the Security & Compliance Center, do either of the following steps:</span></span>

- <span data-ttu-id="e76ee-126">보안 & 준수 센터에서 사용 권한으로 이동하여 역할 그룹을 선택합니다. </span><span class="sxs-lookup"><span data-stu-id="e76ee-126">In the Security & Compliance Center, go to **Permissions** and select the role group.</span></span> <span data-ttu-id="e76ee-127">열 수 있는 세부 정보 플라이아웃에서 역할 그룹의 구성원을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e76ee-127">In the details flyout that opens, verify the members of the role group.</span></span>

- <span data-ttu-id="e76ee-128">보안 & 준수 센터 PowerShell에서 역할 그룹의 이름으로 바꾸고 \<RoleGroupName\> 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e76ee-128">In Security & Compliance Center PowerShell, replace \<RoleGroupName\> with the name of the role group, and run the following command:</span></span>

  ```powershell
  Get-RoleGroupMember -Identity "<RoleGroupName>"
  ```

  <span data-ttu-id="e76ee-129">구문과 매개 변수에 대한 자세한 내용은 [Get-RoleGroupMember를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember)</span><span class="sxs-lookup"><span data-stu-id="e76ee-129">For detailed syntax and parameter information, see [Get-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember).</span></span>
