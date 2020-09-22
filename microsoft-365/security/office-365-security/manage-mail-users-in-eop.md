---
title: 독립 실행형 EOP에서 메일 사용자 관리
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
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: 디렉터리 동기화, EAC 및 PowerShell을 사용 하 여 사용자를 관리 하는 등의 EOP (Exchange Online Protection)에서 메일 사용자를 관리 하는 방법에 대해 알아봅니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 56e6f8955b5993fb4b5064aa92cdde80a4c67ffe
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201786"
---
# <a name="manage-mail-users-in-standalone-eop"></a><span data-ttu-id="c5b63-103">독립 실행형 EOP에서 메일 사용자 관리</span><span class="sxs-lookup"><span data-stu-id="c5b63-103">Manage mail users in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="c5b63-104">Exchange Online 사서함이 없는 독립 실행형 EOP (Exchange Online Protection) 조직에서 메일 사용자는 기본 유형의 사용자 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-104">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, mail users are the fundamental type of user account.</span></span> <span data-ttu-id="c5b63-105">메일 사용자는 독립 실행형 EOP 조직에 계정 자격 증명을 가지 며 사용 권한이 할당 된 리소스에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-105">A mail user has account credentials in your standalone EOP organization, and can access resources (have permissions assigned).</span></span> <span data-ttu-id="c5b63-106">메일 사용자의 전자 메일 주소는 외부 (예: 온-프레미스 전자 메일 환경)입니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-106">A mail user's email address is external (for example, in your on-premises email environment).</span></span>

> [!NOTE]
> <span data-ttu-id="c5b63-107">메일 사용자를 만들 때는 Microsoft 365 관리 센터에서 해당 사용자 계정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-107">When you create a mail user, the corresponding user account is available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="c5b63-108">Microsoft 365 관리 센터에서 사용자 계정을 만드는 경우 해당 계정을 사용 하 여 메일 사용자를 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-108">When you create a user account in the Microsoft 365 admin center, you can't use that account to create a mail user.</span></span>

<span data-ttu-id="c5b63-109">독립 실행형 EOP에서 메일 사용자를 만들고 관리 하는 데 권장 되는 방법은이 항목 뒷부분의 [디렉터리 동기화를 사용 하 여 메일 사용자 관리](#use-directory-synchronization-to-manage-mail-users) 섹션에 설명 된 대로 디렉터리 동기화를 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-109">The recommended method to create and manage mail users in standalone EOP is to use directory synchronization as described in the [Use directory synchronization to manage mail users](#use-directory-synchronization-to-manage-mail-users) section later in this topic.</span></span>

<span data-ttu-id="c5b63-110">사용자 수가 적은 독립 실행형 EOP 조직의 경우이 항목에 설명 된 대로 EAC (Exchange 관리 센터) 또는 독립 실행형 EOP PowerShell에서 메일 사용자를 추가 하 고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-110">For standalone EOP organizations with a small number of users, you can add and manage mail users in the Exchange admin center (EAC) or in standalone EOP PowerShell as described in this topic.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c5b63-111">시작하기 전에 알아야 할 내용</span><span class="sxs-lookup"><span data-stu-id="c5b63-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="c5b63-112">EAC (Exchange 관리 센터)를 열려면 [독립 실행형 EOP에서 exchange 관리 센터](exchange-admin-center-in-exchange-online-protection-eop.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c5b63-112">To open the Exchange admin center (EAC), see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="c5b63-113">독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c5b63-113">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="c5b63-114">EOP PowerShell에서 메일 사용자를 만들 때 제한이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-114">When you create mail users in EOP PowerShell, you might encounter throttling.</span></span> <span data-ttu-id="c5b63-115">또한 EOP PowerShell cmdlet은 일괄 처리 방법을 사용 하 여 명령 결과가 표시 되기까지 몇 분 정도 전파 지연을 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-115">Also, the EOP PowerShell cmdlets use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="c5b63-116">이 절차를 수행하려면 먼저 사용 권한을 할당받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-116">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="c5b63-117">특히 OrganizationManagement (전역 관리자) 및 RecipientManagement 역할 그룹에 할당 되는 메일 받는 사람 만들기 (만들기) 및 메일 받는 사람 (수정) 역할은 기본적으로 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-117">Specifically, you need the Mail Recipient Creation (create) and Mail Recipients (modify) roles, which are assigned to the OrganizationManagement (global admins) and RecipientManagement role groups by default.</span></span> <span data-ttu-id="c5b63-118">자세한 내용은 [권한 독립 실행형 EOP의 사용 권한을](feature-permissions-in-eop.md) 참조 하 고 [EAC를 사용 하 여 역할 그룹의 구성원 목록을 수정](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-118">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="c5b63-119">이 항목의 절차에 적용할 수 있는 바로 가기 키에 대 한 자세한 내용은 [Exchange Online에서 exchange 관리 센터에 대 한 바로 가기 키](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c5b63-119">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="c5b63-120">문제가 있습니까?</span><span class="sxs-lookup"><span data-stu-id="c5b63-120">Having problems?</span></span> <span data-ttu-id="c5b63-121">Exchange 포럼에서 도움을 요청하세요.</span><span class="sxs-lookup"><span data-stu-id="c5b63-121">Ask for help in the Exchange forums.</span></span> <span data-ttu-id="c5b63-122">[Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) 포럼을 방문 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-122">Visit the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-exchange-admin-center-to-manage-mail-users"></a><span data-ttu-id="c5b63-123">Exchange 관리 센터를 사용 하 여 메일 사용자 관리</span><span class="sxs-lookup"><span data-stu-id="c5b63-123">Use the Exchange admin center to manage mail users</span></span>

### <a name="use-the-eac-to-create-mail-users"></a><span data-ttu-id="c5b63-124">EAC를 사용 하 여 메일 사용자 만들기</span><span class="sxs-lookup"><span data-stu-id="c5b63-124">Use the EAC to create mail users</span></span>

1. <span data-ttu-id="c5b63-125">EAC에서 **받는 사람** \> **연락처로** 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-125">In the EAC, go to **Recipients** \> **Contacts**</span></span>

2. <span data-ttu-id="c5b63-126">**새로** ![ 만들기 아이콘 ](../../media/ITPro-EAC-AddIcon.png) 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-126">Click **New** ![New icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="c5b63-127">**새 메일 사용자** 페이지가 열리면 다음 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-127">In the **New mail user** page that opens, configure the following settings.</span></span> <span data-ttu-id="c5b63-128">로 표시 된 설정은 <sup>\*</sup> 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-128">Settings marked with an <sup>\*</sup> are required.</span></span>

   - <span data-ttu-id="c5b63-129">**이름**</span><span class="sxs-lookup"><span data-stu-id="c5b63-129">**First name**</span></span>

   - <span data-ttu-id="c5b63-130">**이니셜**: 사람의 중간 이니셜입니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-130">**Initials**: The person's middle initial.</span></span>

   - <span data-ttu-id="c5b63-131">**성**</span><span class="sxs-lookup"><span data-stu-id="c5b63-131">**Last name**</span></span>

   - <span data-ttu-id="c5b63-132"><sup>\*</sup>**표시 이름**:이 상자에는 기본적으로 **이름**, **이니셜**및 **성** 상자의 값이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-132"><sup>\*</sup>**Display name**: By default, this box shows the values from the **First name**, **Initials**, and **Last name** boxes.</span></span> <span data-ttu-id="c5b63-133">이 값을 그대로 사용 하거나 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-133">You can accept this value or change it.</span></span> <span data-ttu-id="c5b63-134">이 값은 고유 해야 하며 최대 길이는 64 자입니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-134">The value should be unique, and has a maximum length of 64 characters.</span></span>

   - <span data-ttu-id="c5b63-135"><sup>\*</sup>**별칭**: 사용자에 대해 최대 64 문자를 사용 하 여 고유한 별칭을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-135"><sup>\*</sup>**Alias**: Enter a unique alias, using up to 64 characters, for the user</span></span>

   - <span data-ttu-id="c5b63-136">**외부 전자 메일 주소**: 사용자의 전자 메일 주소를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-136">**External email address**: Enter the user's email address.</span></span> <span data-ttu-id="c5b63-137">도메인은 클라우드 기반 조직 외부에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-137">The domain should be external to your cloud-based organization.</span></span>

   - <span data-ttu-id="c5b63-138"><sup>\*</sup>**사용자 ID**: 사용자가 서비스에 로그인 할 때 사용할 계정을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-138"><sup>\*</sup>**User ID**: Enter the account that the person will use to sign in to the service.</span></span> <span data-ttu-id="c5b63-139">사용자 ID는 @ 기호 왼쪽의 사용자 이름 및 오른쪽에 있는 도메인으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-139">The user ID consists of a username on the left side of the at (@) symbol (@) and a domain on the right side.</span></span>

   - <span data-ttu-id="c5b63-140"><sup>\*</sup>**새 암호** 및 <sup>\*</sup> **암호 확인**: 계정 암호를 입력 하 고 다시 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-140"><sup>\*</sup>**New password** and <sup>\*</sup>**Confirm password**: Enter and reenter the account password.</span></span> <span data-ttu-id="c5b63-141">암호가 조직의 암호 길이, 복잡도 및 기록 요구 사항을 따르는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-141">Verify that the password complies with the password length, complexity, and history requirements of your organization.</span></span>

3. <span data-ttu-id="c5b63-142">모든 설정이 끝나면 **저장**을 클릭하여 메일 사용자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-142">When you've finished, click **Save** to create the mail user.</span></span>

### <a name="use-the-eac-to-modify-mail-users"></a><span data-ttu-id="c5b63-143">EAC를 사용 하 여 메일 사용자 수정</span><span class="sxs-lookup"><span data-stu-id="c5b63-143">Use the EAC to modify mail users</span></span>

1. <span data-ttu-id="c5b63-144">EAC에서 **받는 사람** \> **연락처**로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-144">In the EAC, go to **Recipients** \> **Contacts**.</span></span>

2. <span data-ttu-id="c5b63-145">수정할 메일 사용자를 선택 하 고 편집 아이콘 **편집** 을 클릭 ![ ](../../media/ITPro-EAC-AddIcon.png) 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-145">Select the mail user that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

3. <span data-ttu-id="c5b63-146">메일 사용자 속성 페이지가 열리면 다음 탭 중 하나를 클릭 하 여 속성을 보거나 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-146">On the mail user properties page that opens, click one of the following tabs to view or change properties.</span></span>

   <span data-ttu-id="c5b63-147">작업을 마쳤으면 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-147">When you're finished, click **Save**.</span></span>

#### <a name="general"></a><span data-ttu-id="c5b63-148">일반</span><span class="sxs-lookup"><span data-stu-id="c5b63-148">General</span></span>

<span data-ttu-id="c5b63-149">**일반** 탭을 사용 하 여 메일 사용자에 대 한 기본 정보를 보거나 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-149">Use the **General** tab to view or change basic information about the mail user.</span></span>

- <span data-ttu-id="c5b63-150">**이름**</span><span class="sxs-lookup"><span data-stu-id="c5b63-150">**First name**</span></span>

- <span data-ttu-id="c5b63-151">**이니셜**</span><span class="sxs-lookup"><span data-stu-id="c5b63-151">**Initials**</span></span>

- <span data-ttu-id="c5b63-152">**성**</span><span class="sxs-lookup"><span data-stu-id="c5b63-152">**Last name**</span></span>

- <span data-ttu-id="c5b63-153">**표시 이름**:이 이름은 조직의 주소록, 전자 메일의 대상: 및 보낸 사람: 줄 및 EAC의 연락처 목록에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-153">**Display name**: This name appears in your organization's address book, on the To: and From: lines in email, and in the list of contacts in the EAC.</span></span> <span data-ttu-id="c5b63-154">표시 이름 앞뒤에는 빈 공간을 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-154">This name can't contain empty spaces before or after the display name.</span></span>

- <span data-ttu-id="c5b63-155">**사용자 ID**: Microsoft 365의 사용자 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-155">**User ID**: This is the user's account in Microsoft 365.</span></span> <span data-ttu-id="c5b63-156">여기서는이 값을 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-156">You can't modify this value here.</span></span>

#### <a name="contact-information"></a><span data-ttu-id="c5b63-157">연락처 정보</span><span class="sxs-lookup"><span data-stu-id="c5b63-157">Contact information</span></span>

<span data-ttu-id="c5b63-158">사용자의 연락처 정보를 보거나 변경 하려면 **연락처 정보** 탭을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-158">Use the **Contact information** tab to view or change the user's contact information.</span></span> <span data-ttu-id="c5b63-159">이 페이지의 정보는 주소록에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-159">The information on this page is displayed in the address book.</span></span>

- <span data-ttu-id="c5b63-160">**주소**</span><span class="sxs-lookup"><span data-stu-id="c5b63-160">**Street**</span></span>
- <span data-ttu-id="c5b63-161">**구/군/시**</span><span class="sxs-lookup"><span data-stu-id="c5b63-161">**City**</span></span>
- <span data-ttu-id="c5b63-162">**시/도**</span><span class="sxs-lookup"><span data-stu-id="c5b63-162">**State/Province**</span></span>
- <span data-ttu-id="c5b63-163">**우편 번호**</span><span class="sxs-lookup"><span data-stu-id="c5b63-163">**ZIP/Postal code**</span></span>
- <span data-ttu-id="c5b63-164">**국가/지역**</span><span class="sxs-lookup"><span data-stu-id="c5b63-164">**Country/Region**</span></span>
- <span data-ttu-id="c5b63-165">**회사 전화**</span><span class="sxs-lookup"><span data-stu-id="c5b63-165">**Work phone**</span></span>
- <span data-ttu-id="c5b63-166">**휴대폰**</span><span class="sxs-lookup"><span data-stu-id="c5b63-166">**Mobile phone**</span></span>
- <span data-ttu-id="c5b63-167">**팩스**</span><span class="sxs-lookup"><span data-stu-id="c5b63-167">**Fax**</span></span>
- <span data-ttu-id="c5b63-168">**기타 옵션**</span><span class="sxs-lookup"><span data-stu-id="c5b63-168">**More options**</span></span>

  - <span data-ttu-id="c5b63-169">**사무실**</span><span class="sxs-lookup"><span data-stu-id="c5b63-169">**Office**</span></span>
  - <span data-ttu-id="c5b63-170">**집 전화**</span><span class="sxs-lookup"><span data-stu-id="c5b63-170">**Home phone**</span></span>
  - <span data-ttu-id="c5b63-171">**웹 페이지**</span><span class="sxs-lookup"><span data-stu-id="c5b63-171">**Web page**</span></span>
  - <span data-ttu-id="c5b63-172">**참고**</span><span class="sxs-lookup"><span data-stu-id="c5b63-172">**Notes**</span></span>

#### <a name="organization"></a><span data-ttu-id="c5b63-173">조직</span><span class="sxs-lookup"><span data-stu-id="c5b63-173">Organization</span></span>

<span data-ttu-id="c5b63-174">**조직 탭을** 사용 하 여 조직에서 사용자의 역할에 대 한 세부 정보를 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-174">Use the **Organization** tab to record detailed information about the user's role in the organization.</span></span>

- <span data-ttu-id="c5b63-175">**Title**</span><span class="sxs-lookup"><span data-stu-id="c5b63-175">**Title**</span></span>
- <span data-ttu-id="c5b63-176">**Department**</span><span class="sxs-lookup"><span data-stu-id="c5b63-176">**Department**</span></span>
- <span data-ttu-id="c5b63-177">**Company**</span><span class="sxs-lookup"><span data-stu-id="c5b63-177">**Company**</span></span>

### <a name="use-the-eac-to-remove-mail-users"></a><span data-ttu-id="c5b63-178">EAC를 사용 하 여 메일 사용자 제거</span><span class="sxs-lookup"><span data-stu-id="c5b63-178">Use the EAC to remove mail users</span></span>

1. <span data-ttu-id="c5b63-179">EAC에서 **받는 사람** \> **연락처**로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-179">In the EAC, go to **Recipients** \> **Contacts**.</span></span>

2. <span data-ttu-id="c5b63-180">제거할 메일 사용자를 선택한 다음 제거 아이콘 **제거** 를 클릭 ![ ](../../media/ITPro-EAC-RemoveIcon.gif) 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-180">Select the mail user that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

## <a name="use-powershell-to-manage-mail-users"></a><span data-ttu-id="c5b63-181">PowerShell을 사용 하 여 메일 사용자 관리</span><span class="sxs-lookup"><span data-stu-id="c5b63-181">Use PowerShell to manage mail users</span></span>

### <a name="use-standalone-eop-powershell-to-view-mail-users"></a><span data-ttu-id="c5b63-182">독립 실행형 EOP PowerShell을 사용 하 여 메일 사용자 보기</span><span class="sxs-lookup"><span data-stu-id="c5b63-182">Use standalone EOP PowerShell to view mail users</span></span>

<span data-ttu-id="c5b63-183">독립 실행형 EOP PowerShell에 있는 모든 메일 사용자의 요약 목록을 반환 하려면 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-183">To return a summary list of all mail users in standalone EOP PowerShell, run the following command:</span></span>

```powershell
Get-Recipient -RecipientType MailUser -ResultSize unlimited
```

<span data-ttu-id="c5b63-184">특정 메일 사용자에 대 한 자세한 정보를 보려면 \<MailUserIdentity\> 메일 사용자의 이름, 별칭 또는 계정 이름으로 바꾸고 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-184">To view detailed information about a specific mail user, replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following commands:</span></span>

```powershell
Get-Recipient -Identity <MailUserIdentity> | Format-List
```

```powershell
Get-User -Identity <MailUserIdentity> | Format-List
```

<span data-ttu-id="c5b63-185">구문 및 매개 변수에 대 한 자세한 내용은 [get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) and [get-help](https://docs.microsoft.com/powershell/module/exchange/get-user)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c5b63-185">For detailed syntax and parameter information, see [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) and [Get-User](https://docs.microsoft.com/powershell/module/exchange/get-user).</span></span>

### <a name="use-standalone-eop-powershell-to-create-mail-users"></a><span data-ttu-id="c5b63-186">독립 실행형 EOP PowerShell을 사용 하 여 메일 사용자 만들기</span><span class="sxs-lookup"><span data-stu-id="c5b63-186">Use standalone EOP PowerShell to create mail users</span></span>

<span data-ttu-id="c5b63-187">독립 실행형 EOP PowerShell에서 메일 사용자를 만들려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-187">To create mail users in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
New-EOPMailUser -Name "<UniqueName>" -MicrosoftOnlineServicesID <Account> -Password (ConvertTo-SecureString -String '<password>' -AsPlainText -Force) [-Alias <AliasValue>] [-DisplayName "<Display Name>"] [-ExternalEmailAddress <ExternalEmailAddress>] [-FirstName <Text>] [-Initials <Text>] [-LastName <Text>]
```

<span data-ttu-id="c5b63-188">**참고:**</span><span class="sxs-lookup"><span data-stu-id="c5b63-188">**Notes**:</span></span>

- <span data-ttu-id="c5b63-189">_Name_ 매개 변수는 필수 이며, 최대 길이는 64 자 이며 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-189">The _Name_ parameter is required, has a maximum length of 64 characters, and must be unique.</span></span> <span data-ttu-id="c5b63-190">_DisplayName_ 매개 변수를 사용하지 않는 경우에는 _Name_ 매개 변수의 값이 표시 이름에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-190">If you don't use the _DisplayName_ parameter, the value of the _Name_ parameter is used for the display name.</span></span>
- <span data-ttu-id="c5b63-191">_Alias_ 매개 변수를 사용 하지 않으면 _MicrosoftOnlineServicesID_ 매개 변수의 왼쪽이 별칭에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-191">If you don't use the _Alias_ parameter, the left side of the _MicrosoftOnlineServicesID_ parameter is used for the alias.</span></span>
- <span data-ttu-id="c5b63-192">_ExternalEmailAddress_ 매개 변수를 사용 하지 않으면 외부 전자 메일 주소에 _MicrosoftOnlineServicesID_ 값이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-192">If you don't use the _ExternalEmailAddress_ parameter, the _MicrosoftOnlineServicesID_ value is used for the external email address.</span></span>

<span data-ttu-id="c5b63-193">이 예에서는 다음 설정을 사용 하 여 메일 사용자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-193">This example creates a mail user with the following settings:</span></span>

- <span data-ttu-id="c5b63-194">이름은 JeffreyZeng이 고 표시 이름은 Jeffrey Zeng입니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-194">The name is JeffreyZeng and the display name is Jeffrey Zeng.</span></span>
- <span data-ttu-id="c5b63-195">이름은 Jeffrey고 성은 Zeng입니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-195">The first name is Jeffrey and the last name is Zeng.</span></span>
- <span data-ttu-id="c5b63-196">별칭은 jeffreyz입니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-196">The alias is jeffreyz.</span></span>
- <span data-ttu-id="c5b63-197">외부 전자 메일 주소는 jzeng@tailspintoys.com입니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-197">The external email address is jzeng@tailspintoys.com.</span></span>
- <span data-ttu-id="c5b63-198">계정 이름은 jeffreyz@contoso.onmicrosoft.com입니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-198">The account name is jeffreyz@contoso.onmicrosoft.com.</span></span>
- <span data-ttu-id="c5b63-199">암호는 Pa$$word1입니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-199">The password is Pa$$word1.</span></span>

```PowerShell
New-EOPMailUser -Name JeffreyZeng -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force) -ExternalEmailAddress jeffreyz@tailspintoys.com -DisplayName "Jeffrey Zeng" -Alias jeffreyz -FirstName Jeffrey -LastName Zeng
```

<span data-ttu-id="c5b63-200">구문 및 매개 변수에 대 한 자세한 내용은 [New-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/new-eopmailuser)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c5b63-200">For detailed syntax and parameter information, see [New-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/new-eopmailuser).</span></span>

### <a name="use-standalone-eop-powershell-to-modify-mail-users"></a><span data-ttu-id="c5b63-201">독립 실행형 EOP PowerShell을 사용 하 여 메일 사용자 수정</span><span class="sxs-lookup"><span data-stu-id="c5b63-201">Use standalone EOP PowerShell to modify mail users</span></span>

<span data-ttu-id="c5b63-202">독립 실행형 EOP PowerShell에서 기존 메일 사용자를 수정 하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-202">To modify existing mail users in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
Set-EOPMailUser -Identity <MailUserIdentity> [-Alias <Text>] [-DisplayName <Text>] [-EmailAddresses <ProxyAddressCollection>] [-MicrosoftOnlineServicesID <SmtpAddress>]
```

```powershell
Set-EOPUser -Identity <MailUserIdentity> [-City <Text>] [-Company <Text>] [-CountryOrRegion <CountryInfo>] [-Department <Text>] [-Fax <PhoneNumber>] [-FirstName <Text>] [-HomePhone <PhoneNumber>] [-Initials <Text>] [-LastName <Text>] [-MobilePhone <PhoneNumber>] [-Notes <Text>] [-Office <Text>] [-Phone <PhoneNumber>] [-PostalCode <String>] [-StateOrProvince <String>] [-StreetAddress <Tet>] [-Title <Text>] [-WebPage <Text>]
```

<span data-ttu-id="c5b63-203">다음 예에서는 Pilar Pinilla의 외부 전자 메일 주소를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-203">This example sets the external email address for Pilar Pinilla.</span></span>

```PowerShell
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

<span data-ttu-id="c5b63-204">다음 예에서는 모든 메일 사용자의 Company 속성을 Contoso로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-204">This example sets the Company property for all mail users to Contoso.</span></span>

```PowerShell
$Recip = Get-Recipient -RecipientType MailUser -ResultSize unlimited
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}
```

<span data-ttu-id="c5b63-205">구문 및 매개 변수에 대 한 자세한 내용은 [Set-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/set-eopmailuser)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c5b63-205">For detailed syntax and parameter information, see [Set-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/set-eopmailuser).</span></span>

### <a name="use-standalone-eop-powershell-to-remove-mail-users"></a><span data-ttu-id="c5b63-206">독립 실행형 EOP PowerShell을 사용 하 여 메일 사용자 제거</span><span class="sxs-lookup"><span data-stu-id="c5b63-206">Use standalone EOP PowerShell to remove mail users</span></span>

<span data-ttu-id="c5b63-207">독립 실행형 EOP PowerShell에서 메일 사용자를 제거 하려면 \<MailUserIdentity\> 메일 사용자의 이름, 별칭 또는 계정 이름으로 바꾸고 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-207">To remove mail users in standalone EOP PowerShell, replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following command:</span></span>

```PowerShell
Remove-EOPMailUser -Identity <MailUserIdentity\>
```

<span data-ttu-id="c5b63-208">이 예에서는 Jeffrey Zeng의 메일 사용자를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-208">This example removes the mail user for Jeffrey Zeng.</span></span>

```PowerShell
Remove-EOPMailUser -Identity "Jeffrey Zeng"
```

<span data-ttu-id="c5b63-209">구문 및 매개 변수에 대 한 자세한 내용은 [Remove-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/remove-eopmailuser)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c5b63-209">For detailed syntax and parameter information, see [Remove-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/remove-eopmailuser).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="c5b63-210">이 절차가 제대로 수행되었는지 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="c5b63-210">How do you know these procedures worked?</span></span>

<span data-ttu-id="c5b63-211">독립 실행형 EOP에서 메일 사용자를 성공적으로 생성, 수정 또는 제거 했는지 확인 하려면 다음 절차 중 하나를 사용 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c5b63-211">To verify that you've successfully created, modified, or removed mail users in standalone EOP, use any of the following procedures:</span></span>

- <span data-ttu-id="c5b63-212">EAC에서 **받는 사람** \> **연락처**로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-212">In the EAC, go to **Recipients** \> **Contacts**.</span></span> <span data-ttu-id="c5b63-213">메일 사용자가 나열 되어 있거나 나열 되지 않았는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-213">Verify that the mail user is listed (or isn't listed).</span></span> <span data-ttu-id="c5b63-214">메일 사용자를 선택 하 고 세부 정보 창에서 정보를 보거나 편집 아이콘 **편집** ![ 을 클릭 ](../../media/ITPro-EAC-AddIcon.png) 하 여 설정을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-214">Select the mail user and view the information in the Details pane, or click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png) to view the settings.</span></span>

- <span data-ttu-id="c5b63-215">독립 실행형 EOP PowerShell에서 다음 명령을 실행 하 여 메일 사용자가 나열 되어 있거나 나열 되지 않았는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-215">In standalone EOP PowerShell, run the following command to verify the mail user is listed (or isn't listed):</span></span>

  ```powershell
  Get-Recipient -RecipientType MailUser -ResultSize unlimited
  ```

- <span data-ttu-id="c5b63-216">\<MailUserIdentity\>메일 사용자의 이름, 별칭 또는 계정 이름으로 바꾸고 다음 명령을 실행 하 여 설정을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-216">Replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following commands to verify the settings:</span></span>

  ```powershell
  Get-Recipient -Identity <MailUserIdentity> | Format-List
  ```

  ```powershell
  Get-User -Identity <MailUserIdentity> | Format-List
  ```

## <a name="use-directory-synchronization-to-manage-mail-users"></a><span data-ttu-id="c5b63-217">디렉터리 동기화를 사용하여 메일 사용자 관리</span><span class="sxs-lookup"><span data-stu-id="c5b63-217">Use directory synchronization to manage mail users</span></span>

<span data-ttu-id="c5b63-218">독립 실행형 EOP에서는 온-프레미스 Active Directory를 사용 하는 고객에 게 디렉터리 동기화를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-218">In standalone EOP, directory synchronization is available for customers with on-premises Active Directory.</span></span> <span data-ttu-id="c5b63-219">이러한 계정을 azure AD (Active Directory)와 동기화 하 여 계정의 복사본이 클라우드에 저장 되는 것을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-219">You can synchronize those accounts to Azure Active Directory (Azure AD), where copies of the accounts are stored in the cloud.</span></span> <span data-ttu-id="c5b63-220">기존 사용자 계정을 Azure Active Directory에 동기화 하는 경우 EAC (Exchange 관리 센터)의 **받는 사람** 창이 나 독립 실행형 EOP PowerShell에서 해당 사용자를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-220">When you synchronize your existing user accounts to Azure Active Directory, you can view those users in the **Recipients** pane of the Exchange admin center (EAC) or in standalone EOP PowerShell.</span></span>

<span data-ttu-id="c5b63-221">**참고:**</span><span class="sxs-lookup"><span data-stu-id="c5b63-221">**Notes**:</span></span>

- <span data-ttu-id="c5b63-222">디렉터리 동기화를 사용 하 여 받는 사람을 관리 하는 경우에도 Microsoft 365 관리 센터에서 사용자를 추가 및 관리할 수 있지만 온-프레미스 Active Directory와 동기화 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-222">If you use directory synchronization to manage your recipients, you can still add and manage users in the Microsoft 365 admin center, but they will not be synchronized with your on-premises Active Directory.</span></span> <span data-ttu-id="c5b63-223">디렉터리 동기화는 온-프레미스 Active Directory의 받는 사람만 클라우드로 동기화 하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-223">This is because directory synchronization only syncs recipients from your on-premises Active Directory to the cloud.</span></span>

- <span data-ttu-id="c5b63-224">다음 기능을 사용하려면 디렉터리 동기화를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-224">Using directory synchronization is recommended for use with the following features:</span></span>

  - <span data-ttu-id="c5b63-225">**Outlook 수신 허용-보낸 사람 목록 및 수신 거부 목록**: 서비스에 동기화 된 경우 이러한 목록이 서비스의 스팸 필터링 보다 우선 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-225">**Outlook Safe Sender lists and Blocked Sender lists**: When synchronized to the service, these lists will take precedence over spam filtering in the service.</span></span> <span data-ttu-id="c5b63-226">이렇게 하면 개별 보낸 사람 및 도메인 항목을 사용 하 여 사용자의 수신 허용-보낸 사람의 목록 및 수신 거부 목록을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-226">This lets users manage their own Safe Sender list and Blocked Sender list with individual sender and domain entries.</span></span> <span data-ttu-id="c5b63-227">자세한 내용은 [Exchange Online 사서함에 대한 정크 메일 설정 구성하기](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-junk-email-settings-on-exo-mailboxes)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c5b63-227">For more information, see [Configure junk email settings on Exchange Online mailboxes](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-junk-email-settings-on-exo-mailboxes).</span></span>

  - <span data-ttu-id="c5b63-228">**Dbeb (디렉터리 기반 Edge 차단)**: dbeb에 대 한 자세한 내용은 [Use Directory Based edge 차단은 잘못 된 받는 사람에 게 보낸 메시지를 거부](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)합니다 .를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c5b63-228">**Directory Based Edge Blocking (DBEB)**: For more information about DBEB, see [Use Directory Based Edge Blocking to reject messages sent to invalid recipients](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking).</span></span>

  - <span data-ttu-id="c5b63-229">**최종 사용자에 게 격리에 대 한 액세스 권한**: 격리 된 메시지에 액세스 하려면 받는 사람에 게 서비스의 유효한 사용자 ID와 암호가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-229">**End user access to quarantine**: To access their quarantined messages, recipients must have a valid user ID and password in the service.</span></span> <span data-ttu-id="c5b63-230">격리에 대 한 자세한 내용은 [사용자로 격리 된 메시지 찾기 및 릴리스](https://docs.microsoft.com/microsoft-365/security/office-365-security/find-and-release-quarantined-messages-as-a-user)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c5b63-230">For more information about quarantine, see [Find and release quarantined messages as a user](https://docs.microsoft.com/microsoft-365/security/office-365-security/find-and-release-quarantined-messages-as-a-user).</span></span>

  - <span data-ttu-id="c5b63-231">**메일 흐름 규칙 (전송 규칙이 라고도 함)**: 디렉터리 동기화를 사용 하는 경우 기존 Active directory 사용자 및 그룹이 클라우드로 자동 업로드 되 고, 서비스에서 해당 사용자 및/또는 그룹을 수동으로 추가 하지 않고도이를 대상으로 하는 메일 흐름 규칙을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-231">**Mail flow rules (also known as transport rules)**: When you use directory synchronization, your existing Active Directory users and groups are automatically uploaded to the cloud, and you can then create mail flow rules that target specific users and/or groups without having to manually add them in the service.</span></span> <span data-ttu-id="c5b63-232">[동적 메일 그룹](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) 은 디렉터리 동기화를 통해 동기화 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-232">Note that [dynamic distribution groups](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) can't be synchronized via directory synchronization.</span></span>

<span data-ttu-id="c5b63-233">[Azure Active directory를 사용한 하이브리드 id 란?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity)에 설명 된 대로 필요한 사용 권한을 얻고 디렉터리 동기화를 준비 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-233">Get the necessary permissions and prepare for directory synchronization, as described in [What is hybrid identity with Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity).</span></span>

### <a name="synchronize-directories-with-azure-active-directory-connect-aad-connect"></a><span data-ttu-id="c5b63-234">Azure Active Directory Connect를 사용한 디렉터리 동기화 (AAD 연결)</span><span class="sxs-lookup"><span data-stu-id="c5b63-234">Synchronize directories with Azure Active Directory Connect (AAD Connect)</span></span>

1. <span data-ttu-id="c5b63-235">[AZURE AD Connect 동기화: 이해 및 사용자 지정 동기화](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis)에 설명 된 대로 디렉터리 동기화를 활성화 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-235">Activate directory synchronization as described in [Azure AD Connect sync: Understand and customize synchronization](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).</span></span>

2. <span data-ttu-id="c5b63-236">[AZURE AD Connect 필수 구성 요소](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites)에 설명 된 대로 AAD connect를 실행 하는 온-프레미스 컴퓨터를 설치 하 고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-236">Install and configure an on-premises computer to run AAD Connect as described in [Prerequisites for Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites).</span></span>

3. <span data-ttu-id="c5b63-237">[AZURE AD Connect에 사용할 설치 유형을 선택 합니다](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation).</span><span class="sxs-lookup"><span data-stu-id="c5b63-237">[Select which installation type to use for Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation):</span></span>

   - [<span data-ttu-id="c5b63-238">Express</span><span class="sxs-lookup"><span data-stu-id="c5b63-238">Express</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)

   - [<span data-ttu-id="c5b63-239">사용자 지정</span><span class="sxs-lookup"><span data-stu-id="c5b63-239">Custom</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-custom)

   - [<span data-ttu-id="c5b63-240">통과 인증</span><span class="sxs-lookup"><span data-stu-id="c5b63-240">Pass-through authentication</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-quick-start)

> [!IMPORTANT]
> <span data-ttu-id="c5b63-p121">Azure Active Directory 동기화 도구 구성 마법사를 완료하면 Active Directory 포리스트에 **MSOL_AD_SYNC** 계정이 만들어집니다. 이 계정을 사용하여 온-프레미스 Active Directory 정보를 읽고 동기화합니다. 디렉터리 동기화가 정상적으로 작동하도록 하려면 로컬 디렉터리 동기화 서버의 TCP 443이 열려 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-p121">When you finish the Azure Active Directory Sync Tool Configuration Wizard, the **MSOL_AD_SYNC** account is created in your Active Directory forest. This account is used to read and synchronize your on-premises Active Directory information. In order for directory synchronization to work correctly, make sure that TCP 443 on your local directory synchronization server is open.</span></span>

<span data-ttu-id="c5b63-244">동기화를 구성한 후 AAD 연결이 제대로 동기화 되는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-244">After configuring your sync, be sure to verify that AAD Connect is synchronizing correctly.</span></span> <span data-ttu-id="c5b63-245">이렇게 하려면 EAC에서 **받는 사람** \> **연락처**로 이동한 다음 온-프레미스 환경에서 사용자 목록이 올바르게 동기화되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b63-245">In the EAC, go to **Recipients** \> **Contacts** and view that the list of users was correctly synchronized from your on-premises environment.</span></span>
