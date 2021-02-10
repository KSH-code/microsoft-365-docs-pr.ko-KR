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
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: 디렉터리 동기화, EAC 및 PowerShell을 사용하여 사용자를 관리하는 방법을 포함하여 EOP(Exchange Online Protection)에서 메일 사용자를 관리하는 방법에 대해 자세히 알아보십시오.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 34edafea7567da04094ea386d469d3d27937eee5
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166396"
---
# <a name="manage-mail-users-in-standalone-eop"></a><span data-ttu-id="13e0d-103">독립 실행형 EOP에서 메일 사용자 관리</span><span class="sxs-lookup"><span data-stu-id="13e0d-103">Manage mail users in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="13e0d-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="13e0d-104">**Applies to**</span></span>
-  [<span data-ttu-id="13e0d-105">Exchange Online Protection 독립 실행형</span><span class="sxs-lookup"><span data-stu-id="13e0d-105">Exchange Online Protection standalone</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)

<span data-ttu-id="13e0d-106">Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에서 메일 사용자는 기본 유형의 사용자 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="13e0d-106">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, mail users are the fundamental type of user account.</span></span> <span data-ttu-id="13e0d-107">메일 사용자는 독립 실행형 EOP 조직에 계정 자격 증명을 가지며 리소스에 액세스할 수 있습니다(사용 권한이 할당되어 있습니다).</span><span class="sxs-lookup"><span data-stu-id="13e0d-107">A mail user has account credentials in your standalone EOP organization, and can access resources (have permissions assigned).</span></span> <span data-ttu-id="13e0d-108">메일 사용자의 전자 메일 주소가 외부(예: 전자 메일 환경의 경우)입니다.</span><span class="sxs-lookup"><span data-stu-id="13e0d-108">A mail user's email address is external (for example, in your on-premises email environment).</span></span>

> [!NOTE]
> <span data-ttu-id="13e0d-109">메일 사용자를 만들면 Microsoft 365 관리 센터에서 해당 사용자 계정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13e0d-109">When you create a mail user, the corresponding user account is available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="13e0d-110">Microsoft 365 관리 센터에서 사용자 계정을 만들 때 해당 계정을 사용하여 메일 사용자를 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="13e0d-110">When you create a user account in the Microsoft 365 admin center, you can't use that account to create a mail user.</span></span>

<span data-ttu-id="13e0d-111">독립 실행형 EOP에서 메일 사용자를 만들고 관리하는 권장 방법은 디렉터리 동기화 [](#use-directory-synchronization-to-manage-mail-users) 사용에 설명된 바와 같이 디렉터리 동기화를 사용하여 이 문서의 부분에 있는 메일 사용자 관리 섹션을 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="13e0d-111">The recommended method to create and manage mail users in standalone EOP is to use directory synchronization as described in the [Use directory synchronization to manage mail users](#use-directory-synchronization-to-manage-mail-users) section later in this article.</span></span>

<span data-ttu-id="13e0d-112">사용자가 적은 독립 실행형 EOP 조직의 경우 이 문서에 설명된 바와 같이 EAC(Exchange 관리 센터) 또는 독립 실행형 EOP PowerShell에서 메일 사용자를 추가하고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13e0d-112">For standalone EOP organizations with a small number of users, you can add and manage mail users in the Exchange admin center (EAC) or in standalone EOP PowerShell as described in this article.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="13e0d-113">시작하기 전에 알아야 할 사항은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="13e0d-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="13e0d-114">EAC(Exchange 관리 센터)를 열하려면 독립 실행형 [EOP에서 Exchange 관리 센터를 참조하세요.](exchange-admin-center-in-exchange-online-protection-eop.md)</span><span class="sxs-lookup"><span data-stu-id="13e0d-114">To open the Exchange admin center (EAC), see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="13e0d-115">독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="13e0d-115">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="13e0d-116">EOP PowerShell에서 메일 사용자를 만들 때 스로틀이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13e0d-116">When you create mail users in EOP PowerShell, you might encounter throttling.</span></span> <span data-ttu-id="13e0d-117">또한 EOP PowerShell cmdlet은 일괄 처리 방법을 사용하여 명령 결과가 표시되기 몇 분 전에 전파 지연이 발생하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="13e0d-117">Also, the EOP PowerShell cmdlets use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="13e0d-118">이 문서의 절차를 수행하려면 먼저 Exchange Online Protection에서 사용 권한을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="13e0d-118">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="13e0d-119">특히 조직 관리(전역 관리자) 및 받는 사람 관리 역할 그룹에 기본적으로 할당되는  **Mail Recipient Creation(만들기)** 및 **메일** 받는 사람(수정) 역할이 필요합니다. </span><span class="sxs-lookup"><span data-stu-id="13e0d-119">Specifically, you need the **Mail Recipient Creation** (create) and **Mail Recipients** (modify) roles, which are assigned to the **Organization Management** (global admins) and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="13e0d-120">자세한 내용은 독립 실행형 [EOP의](feature-permissions-in-eop.md) 사용 권한을 참조하고 EAC를 사용하여 역할 그룹의 구성원 목록을 [수정합니다.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)</span><span class="sxs-lookup"><span data-stu-id="13e0d-120">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="13e0d-121">이 문서의 절차에 적용할 수 있는 바로 가기 키에 대한 자세한 내용은 [Exchange Online의 Exchange](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)관리 센터에 대한 바로 가기 키를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="13e0d-121">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="13e0d-122">문제가 있습니까?</span><span class="sxs-lookup"><span data-stu-id="13e0d-122">Having problems?</span></span> <span data-ttu-id="13e0d-123">Exchange 포럼에서 도움을 요청하세요.</span><span class="sxs-lookup"><span data-stu-id="13e0d-123">Ask for help in the Exchange forums.</span></span> <span data-ttu-id="13e0d-124">Exchange [Online Protection 포럼을 방문하세요.](https://go.microsoft.com/fwlink/p/?linkId=285351)</span><span class="sxs-lookup"><span data-stu-id="13e0d-124">Visit the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-exchange-admin-center-to-manage-mail-users"></a><span data-ttu-id="13e0d-125">Exchange 관리 센터를 사용하여 메일 사용자 관리</span><span class="sxs-lookup"><span data-stu-id="13e0d-125">Use the Exchange admin center to manage mail users</span></span>

### <a name="use-the-eac-to-create-mail-users"></a><span data-ttu-id="13e0d-126">EAC를 사용하여 메일 사용자 만들기</span><span class="sxs-lookup"><span data-stu-id="13e0d-126">Use the EAC to create mail users</span></span>

1. <span data-ttu-id="13e0d-127">EAC에서 받는 사람  \> **연락처로 이동**</span><span class="sxs-lookup"><span data-stu-id="13e0d-127">In the EAC, go to **Recipients** \> **Contacts**</span></span>

2. <span data-ttu-id="13e0d-128">새로 **추가** ![ ](../../media/ITPro-EAC-AddIcon.png) 아이콘을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="13e0d-128">Click **New** ![New icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="13e0d-129">새 메일 **사용자** 페이지가 열리면 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="13e0d-129">In the **New mail user** page that opens, configure the following settings.</span></span> <span data-ttu-id="13e0d-130">필수 설정으로 표시된 <sup>\*</sup> 설정이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="13e0d-130">Settings marked with an <sup>\*</sup> are required.</span></span>

   - <span data-ttu-id="13e0d-131">**이름**</span><span class="sxs-lookup"><span data-stu-id="13e0d-131">**First name**</span></span>

   - <span data-ttu-id="13e0d-132">**이니셜**: 사람의 중간 이니셜입니다.</span><span class="sxs-lookup"><span data-stu-id="13e0d-132">**Initials**: The person's middle initial.</span></span>

   - <span data-ttu-id="13e0d-133">**성**</span><span class="sxs-lookup"><span data-stu-id="13e0d-133">**Last name**</span></span>

   - <span data-ttu-id="13e0d-134"><sup>\*</sup>**표시 이름:** 기본적으로 이 상자에는 **이름,** 이니셜 및 성 상자의 **값이** 표시됩니다. </span><span class="sxs-lookup"><span data-stu-id="13e0d-134"><sup>\*</sup>**Display name**: By default, this box shows the values from the **First name**, **Initials**, and **Last name** boxes.</span></span> <span data-ttu-id="13e0d-135">이 값을 수락하거나 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13e0d-135">You can accept this value or change it.</span></span> <span data-ttu-id="13e0d-136">값은 고유해야 하며 최대 길이는 64자입니다.</span><span class="sxs-lookup"><span data-stu-id="13e0d-136">The value should be unique, and has a maximum length of 64 characters.</span></span>

   - <span data-ttu-id="13e0d-137"><sup>\*</sup>**별칭:** 사용자에 대해 최대 64자를 사용하여 고유한 별칭 입력</span><span class="sxs-lookup"><span data-stu-id="13e0d-137"><sup>\*</sup>**Alias**: Enter a unique alias, using up to 64 characters, for the user</span></span>

   - <span data-ttu-id="13e0d-138">**외부 전자 메일 주소:** 사용자의 전자 메일 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="13e0d-138">**External email address**: Enter the user's email address.</span></span> <span data-ttu-id="13e0d-139">도메인은 클라우드 기반 조직 외부에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13e0d-139">The domain should be external to your cloud-based organization.</span></span>

   - <span data-ttu-id="13e0d-140"><sup>\*</sup>**사용자 ID:** 사용자가 서비스에 로그인하는 데 사용할 계정을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="13e0d-140"><sup>\*</sup>**User ID**: Enter the account that the person will use to sign in to the service.</span></span> <span data-ttu-id="13e0d-141">사용자 ID는 @(@) 기호 왼쪽의 사용자 이름과 오른쪽에 있는 도메인으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="13e0d-141">The user ID consists of a username on the left side of the at (@) symbol (@) and a domain on the right side.</span></span>

   - <span data-ttu-id="13e0d-142"><sup>\*</sup>**새 암호** 및 <sup>\*</sup> **암호 확인:** 계정 암호를 입력하고 다시 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="13e0d-142"><sup>\*</sup>**New password** and <sup>\*</sup>**Confirm password**: Enter and reenter the account password.</span></span> <span data-ttu-id="13e0d-143">암호가 조직의 암호 길이, 복잡성 및 기록 요구 사항을 준수하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="13e0d-143">Verify that the password complies with the password length, complexity, and history requirements of your organization.</span></span>

3. <span data-ttu-id="13e0d-144">모든 설정이 끝나면 **저장** 을 클릭하여 메일 사용자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="13e0d-144">When you've finished, click **Save** to create the mail user.</span></span>

### <a name="use-the-eac-to-modify-mail-users"></a><span data-ttu-id="13e0d-145">EAC를 사용하여 메일 사용자 수정</span><span class="sxs-lookup"><span data-stu-id="13e0d-145">Use the EAC to modify mail users</span></span>

1. <span data-ttu-id="13e0d-146">EAC에서 **받는 사람** \> **연락처** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="13e0d-146">In the EAC, go to **Recipients** \> **Contacts**.</span></span>

2. <span data-ttu-id="13e0d-147">수정할 메일 사용자를 선택하고 편집  ![ 아이콘을 ](../../media/ITPro-EAC-AddIcon.png) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="13e0d-147">Select the mail user that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

3. <span data-ttu-id="13e0d-148">열 수 있는 메일 사용자 속성 페이지에서 다음 탭 중 하나를 클릭하여 속성을 보거나 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="13e0d-148">On the mail user properties page that opens, click one of the following tabs to view or change properties.</span></span>

   <span data-ttu-id="13e0d-149">작업을 마쳤으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="13e0d-149">When you're finished, click **Save**.</span></span>

#### <a name="general"></a><span data-ttu-id="13e0d-150">일반 사항</span><span class="sxs-lookup"><span data-stu-id="13e0d-150">General</span></span>

<span data-ttu-id="13e0d-151">일반 **탭을** 사용하여 메일 사용자에 대한 기본 정보를 보거나 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="13e0d-151">Use the **General** tab to view or change basic information about the mail user.</span></span>

- <span data-ttu-id="13e0d-152">**이름**</span><span class="sxs-lookup"><span data-stu-id="13e0d-152">**First name**</span></span>

- <span data-ttu-id="13e0d-153">**이니셜**</span><span class="sxs-lookup"><span data-stu-id="13e0d-153">**Initials**</span></span>

- <span data-ttu-id="13e0d-154">**성**</span><span class="sxs-lookup"><span data-stu-id="13e0d-154">**Last name**</span></span>

- <span data-ttu-id="13e0d-155">**표시 이름:** 이 이름은 조직의 주소 책, 전자 메일의 To: 및 From: 줄 및 EAC의 연락처 목록에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="13e0d-155">**Display name**: This name appears in your organization's address book, on the To: and From: lines in email, and in the list of contacts in the EAC.</span></span> <span data-ttu-id="13e0d-156">표시 이름 앞뒤에는 빈 공간을 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="13e0d-156">This name can't contain empty spaces before or after the display name.</span></span>

- <span data-ttu-id="13e0d-157">**사용자 ID:** Microsoft 365의 사용자 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="13e0d-157">**User ID**: This is the user's account in Microsoft 365.</span></span> <span data-ttu-id="13e0d-158">여기서는 이 값을 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="13e0d-158">You can't modify this value here.</span></span>

#### <a name="contact-information"></a><span data-ttu-id="13e0d-159">연락처 정보</span><span class="sxs-lookup"><span data-stu-id="13e0d-159">Contact information</span></span>

<span data-ttu-id="13e0d-160">연락처 정보 **탭을** 사용하여 사용자의 연락처 정보를 보거나 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="13e0d-160">Use the **Contact information** tab to view or change the user's contact information.</span></span> <span data-ttu-id="13e0d-161">이 페이지의 정보는 주소록에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="13e0d-161">The information on this page is displayed in the address book.</span></span>

- <span data-ttu-id="13e0d-162">**Street**</span><span class="sxs-lookup"><span data-stu-id="13e0d-162">**Street**</span></span>
- <span data-ttu-id="13e0d-163">**구/군/시**</span><span class="sxs-lookup"><span data-stu-id="13e0d-163">**City**</span></span>
- <span data-ttu-id="13e0d-164">**시/도**</span><span class="sxs-lookup"><span data-stu-id="13e0d-164">**State/Province**</span></span>
- <span data-ttu-id="13e0d-165">**우편 번호**</span><span class="sxs-lookup"><span data-stu-id="13e0d-165">**ZIP/Postal code**</span></span>
- <span data-ttu-id="13e0d-166">**국가/지역**</span><span class="sxs-lookup"><span data-stu-id="13e0d-166">**Country/Region**</span></span>
- <span data-ttu-id="13e0d-167">**회사 전화**</span><span class="sxs-lookup"><span data-stu-id="13e0d-167">**Work phone**</span></span>
- <span data-ttu-id="13e0d-168">**휴대폰**</span><span class="sxs-lookup"><span data-stu-id="13e0d-168">**Mobile phone**</span></span>
- <span data-ttu-id="13e0d-169">**팩스**</span><span class="sxs-lookup"><span data-stu-id="13e0d-169">**Fax**</span></span>
- <span data-ttu-id="13e0d-170">**기타 옵션**</span><span class="sxs-lookup"><span data-stu-id="13e0d-170">**More options**</span></span>

  - <span data-ttu-id="13e0d-171">**사무실**</span><span class="sxs-lookup"><span data-stu-id="13e0d-171">**Office**</span></span>
  - <span data-ttu-id="13e0d-172">**집 전화**</span><span class="sxs-lookup"><span data-stu-id="13e0d-172">**Home phone**</span></span>
  - <span data-ttu-id="13e0d-173">**웹 페이지**</span><span class="sxs-lookup"><span data-stu-id="13e0d-173">**Web page**</span></span>
  - <span data-ttu-id="13e0d-174">**참고**</span><span class="sxs-lookup"><span data-stu-id="13e0d-174">**Notes**</span></span>

#### <a name="organization"></a><span data-ttu-id="13e0d-175">조직</span><span class="sxs-lookup"><span data-stu-id="13e0d-175">Organization</span></span>

<span data-ttu-id="13e0d-176">조직 **탭을** 사용하여 조직에서 사용자 역할에 대한 자세한 정보를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="13e0d-176">Use the **Organization** tab to record detailed information about the user's role in the organization.</span></span>

- <span data-ttu-id="13e0d-177">**Title**</span><span class="sxs-lookup"><span data-stu-id="13e0d-177">**Title**</span></span>
- <span data-ttu-id="13e0d-178">**Department**</span><span class="sxs-lookup"><span data-stu-id="13e0d-178">**Department**</span></span>
- <span data-ttu-id="13e0d-179">**Company**</span><span class="sxs-lookup"><span data-stu-id="13e0d-179">**Company**</span></span>

### <a name="use-the-eac-to-remove-mail-users"></a><span data-ttu-id="13e0d-180">EAC를 사용하여 메일 사용자 제거</span><span class="sxs-lookup"><span data-stu-id="13e0d-180">Use the EAC to remove mail users</span></span>

1. <span data-ttu-id="13e0d-181">EAC에서 **받는 사람** \> **연락처** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="13e0d-181">In the EAC, go to **Recipients** \> **Contacts**.</span></span>

2. <span data-ttu-id="13e0d-182">제거할 메일 사용자를 선택하고 **제거** ![ 아이콘을 ](../../media/ITPro-EAC-RemoveIcon.gif) 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="13e0d-182">Select the mail user that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

## <a name="use-powershell-to-manage-mail-users"></a><span data-ttu-id="13e0d-183">PowerShell을 사용하여 메일 사용자 관리</span><span class="sxs-lookup"><span data-stu-id="13e0d-183">Use PowerShell to manage mail users</span></span>

### <a name="use-standalone-eop-powershell-to-view-mail-users"></a><span data-ttu-id="13e0d-184">독립 실행형 EOP PowerShell을 사용하여 메일 사용자 보기</span><span class="sxs-lookup"><span data-stu-id="13e0d-184">Use standalone EOP PowerShell to view mail users</span></span>

<span data-ttu-id="13e0d-185">독립 실행형 EOP PowerShell에서 모든 메일 사용자의 요약 목록을 반환하기 위해 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="13e0d-185">To return a summary list of all mail users in standalone EOP PowerShell, run the following command:</span></span>

```powershell
Get-Recipient -RecipientType MailUser -ResultSize unlimited
```

<span data-ttu-id="13e0d-186">특정 메일 사용자에 대한 자세한 정보를 확인하려면 메일 사용자의 이름, 별칭 또는 계정 이름으로 바꾸고 다음 명령을 \<MailUserIdentity\> 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="13e0d-186">To view detailed information about a specific mail user, replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following commands:</span></span>

```powershell
Get-Recipient -Identity <MailUserIdentity> | Format-List
```

```powershell
Get-User -Identity <MailUserIdentity> | Format-List
```

<span data-ttu-id="13e0d-187">구문과 매개 변수에 대한 자세한 내용은 [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) 및 [Get-User](https://docs.microsoft.com/powershell/module/exchange/get-user)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="13e0d-187">For detailed syntax and parameter information, see [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) and [Get-User](https://docs.microsoft.com/powershell/module/exchange/get-user).</span></span>

### <a name="use-standalone-eop-powershell-to-create-mail-users"></a><span data-ttu-id="13e0d-188">독립 실행형 EOP PowerShell을 사용하여 메일 사용자 만들기</span><span class="sxs-lookup"><span data-stu-id="13e0d-188">Use standalone EOP PowerShell to create mail users</span></span>

<span data-ttu-id="13e0d-189">독립 실행형 EOP PowerShell에서 메일 사용자를 만들 경우 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="13e0d-189">To create mail users in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
New-EOPMailUser -Name "<UniqueName>" -MicrosoftOnlineServicesID <Account> -Password (ConvertTo-SecureString -String '<password>' -AsPlainText -Force) [-Alias <AliasValue>] [-DisplayName "<Display Name>"] [-ExternalEmailAddress <ExternalEmailAddress>] [-FirstName <Text>] [-Initials <Text>] [-LastName <Text>]
```

<span data-ttu-id="13e0d-190">**참고**:</span><span class="sxs-lookup"><span data-stu-id="13e0d-190">**Notes**:</span></span>

- <span data-ttu-id="13e0d-191">_Name_ 매개 변수는 필수 매개 변수로, 최대 길이는 64자입니다.</span><span class="sxs-lookup"><span data-stu-id="13e0d-191">The _Name_ parameter is required, has a maximum length of 64 characters, and must be unique.</span></span> <span data-ttu-id="13e0d-192">_DisplayName_ 매개 변수를 사용하지 않는 경우에는 _Name_ 매개 변수의 값이 표시 이름에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="13e0d-192">If you don't use the _DisplayName_ parameter, the value of the _Name_ parameter is used for the display name.</span></span>
- <span data-ttu-id="13e0d-193">별칭 매개 변수를  사용하지 않는 경우 _MicrosoftOnlineServicesID_ 매개 변수의 왼쪽이 별칭에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="13e0d-193">If you don't use the _Alias_ parameter, the left side of the _MicrosoftOnlineServicesID_ parameter is used for the alias.</span></span>
- <span data-ttu-id="13e0d-194">_ExternalEmailAddress_ 매개 변수를 사용하지 않는 경우 외부 전자 메일 주소에 _MicrosoftOnlineServicesID_ 값이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="13e0d-194">If you don't use the _ExternalEmailAddress_ parameter, the _MicrosoftOnlineServicesID_ value is used for the external email address.</span></span>

<span data-ttu-id="13e0d-195">이 예에서는 다음 설정을 사용하여 메일 사용자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="13e0d-195">This example creates a mail user with the following settings:</span></span>

- <span data-ttu-id="13e0d-196">이름은 JeffreyZeng, 표시 이름은 Jeffrey Zeng입니다.</span><span class="sxs-lookup"><span data-stu-id="13e0d-196">The name is JeffreyZeng and the display name is Jeffrey Zeng.</span></span>
- <span data-ttu-id="13e0d-197">이름은 Jeffrey고 성은 Zeng입니다.</span><span class="sxs-lookup"><span data-stu-id="13e0d-197">The first name is Jeffrey and the last name is Zeng.</span></span>
- <span data-ttu-id="13e0d-198">별칭은 jeffreyz입니다.</span><span class="sxs-lookup"><span data-stu-id="13e0d-198">The alias is jeffreyz.</span></span>
- <span data-ttu-id="13e0d-199">외부 전자 메일 주소는 jzeng@tailspintoys.com입니다.</span><span class="sxs-lookup"><span data-stu-id="13e0d-199">The external email address is jzeng@tailspintoys.com.</span></span>
- <span data-ttu-id="13e0d-200">계정 이름이 jeffreyz@contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="13e0d-200">The account name is jeffreyz@contoso.onmicrosoft.com.</span></span>
- <span data-ttu-id="13e0d-201">암호는 Pa$$word1입니다.</span><span class="sxs-lookup"><span data-stu-id="13e0d-201">The password is Pa$$word1.</span></span>

```PowerShell
New-EOPMailUser -Name JeffreyZeng -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force) -ExternalEmailAddress jeffreyz@tailspintoys.com -DisplayName "Jeffrey Zeng" -Alias jeffreyz -FirstName Jeffrey -LastName Zeng
```

<span data-ttu-id="13e0d-202">구문과 매개 변수에 대한 자세한 내용은 [New-EOPMailUser를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/new-eopmailuser)</span><span class="sxs-lookup"><span data-stu-id="13e0d-202">For detailed syntax and parameter information, see [New-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/new-eopmailuser).</span></span>

### <a name="use-standalone-eop-powershell-to-modify-mail-users"></a><span data-ttu-id="13e0d-203">독립 실행형 EOP PowerShell을 사용하여 메일 사용자 수정</span><span class="sxs-lookup"><span data-stu-id="13e0d-203">Use standalone EOP PowerShell to modify mail users</span></span>

<span data-ttu-id="13e0d-204">독립 실행형 EOP PowerShell에서 기존 메일 사용자를 수정하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="13e0d-204">To modify existing mail users in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
Set-EOPMailUser -Identity <MailUserIdentity> [-Alias <Text>] [-DisplayName <Text>] [-EmailAddresses <ProxyAddressCollection>] [-MicrosoftOnlineServicesID <SmtpAddress>]
```

```powershell
Set-EOPUser -Identity <MailUserIdentity> [-City <Text>] [-Company <Text>] [-CountryOrRegion <CountryInfo>] [-Department <Text>] [-Fax <PhoneNumber>] [-FirstName <Text>] [-HomePhone <PhoneNumber>] [-Initials <Text>] [-LastName <Text>] [-MobilePhone <PhoneNumber>] [-Notes <Text>] [-Office <Text>] [-Phone <PhoneNumber>] [-PostalCode <String>] [-StateOrProvince <String>] [-StreetAddress <Tet>] [-Title <Text>] [-WebPage <Text>]
```

<span data-ttu-id="13e0d-205">다음 예에서는 Pilar Pinilla의 외부 전자 메일 주소를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="13e0d-205">This example sets the external email address for Pilar Pinilla.</span></span>

```PowerShell
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

<span data-ttu-id="13e0d-206">다음 예에서는 모든 메일 사용자의 Company 속성을 Contoso로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="13e0d-206">This example sets the Company property for all mail users to Contoso.</span></span>

```PowerShell
$Recip = Get-Recipient -RecipientType MailUser -ResultSize unlimited
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}
```

<span data-ttu-id="13e0d-207">구문과 매개 변수에 대한 자세한 내용은 [Set-EOPMailUser를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/set-eopmailuser)</span><span class="sxs-lookup"><span data-stu-id="13e0d-207">For detailed syntax and parameter information, see [Set-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/set-eopmailuser).</span></span>

### <a name="use-standalone-eop-powershell-to-remove-mail-users"></a><span data-ttu-id="13e0d-208">독립 실행형 EOP PowerShell을 사용하여 메일 사용자 제거</span><span class="sxs-lookup"><span data-stu-id="13e0d-208">Use standalone EOP PowerShell to remove mail users</span></span>

<span data-ttu-id="13e0d-209">독립 실행형 EOP PowerShell에서 메일 사용자를 제거하려면 메일 사용자의 이름, 별칭 또는 계정 이름으로 바꾸고 다음 \<MailUserIdentity\> 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="13e0d-209">To remove mail users in standalone EOP PowerShell, replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following command:</span></span>

```PowerShell
Remove-EOPMailUser -Identity <MailUserIdentity\>
```

<span data-ttu-id="13e0d-210">이 예에서는 Jeffrey Zeng의 메일 사용자를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="13e0d-210">This example removes the mail user for Jeffrey Zeng.</span></span>

```PowerShell
Remove-EOPMailUser -Identity "Jeffrey Zeng"
```

<span data-ttu-id="13e0d-211">구문과 매개 변수에 대한 자세한 내용은 [Remove-EOPMailUser를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/remove-eopmailuser)</span><span class="sxs-lookup"><span data-stu-id="13e0d-211">For detailed syntax and parameter information, see [Remove-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/remove-eopmailuser).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="13e0d-212">이 절차가 제대로 수행되었는지 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="13e0d-212">How do you know these procedures worked?</span></span>

<span data-ttu-id="13e0d-213">독립 실행형 EOP에서 메일 사용자를 성공적으로 만들거나 수정 또는 제거한 경우 다음 절차 중 원하는 절차를 수행하십시오.</span><span class="sxs-lookup"><span data-stu-id="13e0d-213">To verify that you've successfully created, modified, or removed mail users in standalone EOP, use any of the following procedures:</span></span>

- <span data-ttu-id="13e0d-214">EAC에서 **받는 사람** \> **연락처** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="13e0d-214">In the EAC, go to **Recipients** \> **Contacts**.</span></span> <span data-ttu-id="13e0d-215">메일 사용자가 나열되어 있는지 또는 목록에 없는지 확인</span><span class="sxs-lookup"><span data-stu-id="13e0d-215">Verify that the mail user is listed (or isn't listed).</span></span> <span data-ttu-id="13e0d-216">메일 사용자를 선택하고 세부 정보 창에서 정보를 보거나  편집 아이콘을 클릭하여 설정을 ![ ](../../media/ITPro-EAC-AddIcon.png) 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="13e0d-216">Select the mail user and view the information in the Details pane, or click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png) to view the settings.</span></span>

- <span data-ttu-id="13e0d-217">독립 실행형 EOP PowerShell에서 다음 명령을 실행하여 메일 사용자가 나열되어 있는지(또는 목록에 없는지) 확인</span><span class="sxs-lookup"><span data-stu-id="13e0d-217">In standalone EOP PowerShell, run the following command to verify the mail user is listed (or isn't listed):</span></span>

  ```powershell
  Get-Recipient -RecipientType MailUser -ResultSize unlimited
  ```

- <span data-ttu-id="13e0d-218">메일 사용자의 이름, 별칭 또는 계정 이름으로 바꾸고 다음 명령을 실행하여 설정을 \<MailUserIdentity\> 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="13e0d-218">Replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following commands to verify the settings:</span></span>

  ```powershell
  Get-Recipient -Identity <MailUserIdentity> | Format-List
  ```

  ```powershell
  Get-User -Identity <MailUserIdentity> | Format-List
  ```

## <a name="use-directory-synchronization-to-manage-mail-users"></a><span data-ttu-id="13e0d-219">디렉터리 동기화를 사용하여 메일 사용자 관리</span><span class="sxs-lookup"><span data-stu-id="13e0d-219">Use directory synchronization to manage mail users</span></span>

<span data-ttu-id="13e0d-220">독립 실행형 EOP에서는 Exchange Active Directory가 있는 고객이 디렉터리 동기화를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13e0d-220">In standalone EOP, directory synchronization is available for customers with on-premises Active Directory.</span></span> <span data-ttu-id="13e0d-221">계정의 복사본이 클라우드에 저장되는 Azure AD(Azure Active Directory)에 해당 계정을 동기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13e0d-221">You can synchronize those accounts to Azure Active Directory (Azure AD), where copies of the accounts are stored in the cloud.</span></span> <span data-ttu-id="13e0d-222">기존 사용자 계정을 Azure Active Directory와 동기화할 때 EAC(Exchange 관리 센터)의 받는 사람 창 또는 독립 실행형 EOP PowerShell에서 해당 사용자를 볼 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="13e0d-222">When you synchronize your existing user accounts to Azure Active Directory, you can view those users in the **Recipients** pane of the Exchange admin center (EAC) or in standalone EOP PowerShell.</span></span>

<span data-ttu-id="13e0d-223">**참고**:</span><span class="sxs-lookup"><span data-stu-id="13e0d-223">**Notes**:</span></span>

- <span data-ttu-id="13e0d-224">디렉터리 동기화를 사용하여 받는 사람을 관리하는 경우 Microsoft 365 관리 센터에서 사용자를 추가하고 관리할 수 있지만 이러한 사용자는 사용자와 동기화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="13e0d-224">If you use directory synchronization to manage your recipients, you can still add and manage users in the Microsoft 365 admin center, but they will not be synchronized with your on-premises Active Directory.</span></span> <span data-ttu-id="13e0d-225">이는 디렉터리 동기화가 클라우드로의 받는 사람만 동기화하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="13e0d-225">This is because directory synchronization only syncs recipients from your on-premises Active Directory to the cloud.</span></span>

- <span data-ttu-id="13e0d-226">다음 기능을 사용하려면 디렉터리 동기화를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="13e0d-226">Using directory synchronization is recommended for use with the following features:</span></span>

  - <span data-ttu-id="13e0d-227">**Outlook 수신 - 보낸** 사람 목록 및 수신 차단된 보낸 사람 목록: 서비스에 동기화할 때 이러한 목록이 서비스의 스팸 필터링보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="13e0d-227">**Outlook Safe Sender lists and Blocked Sender lists**: When synchronized to the service, these lists will take precedence over spam filtering in the service.</span></span> <span data-ttu-id="13e0d-228">이를 통해 사용자는 개별 보낸 사람 및 도메인 항목으로 자신의 수신 -보낸 사람 목록 및 수신 차단된 보낸 사람 목록을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13e0d-228">This lets users manage their own Safe Sender list and Blocked Sender list with individual sender and domain entries.</span></span> <span data-ttu-id="13e0d-229">자세한 내용은 [Exchange Online 사서함에 대한 정크 메일 설정 구성하기](configure-junk-email-settings-on-exo-mailboxes.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="13e0d-229">For more information, see [Configure junk email settings on Exchange Online mailboxes](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

  - <span data-ttu-id="13e0d-230">**DBEB(디렉터리** 기반 Edge 차단) : DBEB에 대한 자세한 내용은 디렉터리 기반 Edge 차단을 사용하여 잘못된 받는 사람에게 보낸 메시지를 [거부합니다.](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)</span><span class="sxs-lookup"><span data-stu-id="13e0d-230">**Directory Based Edge Blocking (DBEB)**: For more information about DBEB, see [Use Directory Based Edge Blocking to reject messages sent to invalid recipients](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking).</span></span>

  - <span data-ttu-id="13e0d-231">**최종 사용자에** 대한 인증 액세스: 받는 사람이 해당 메시지에 액세스하려면 서비스에서 유효한 사용자 ID와 암호가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="13e0d-231">**End user access to quarantine**: To access their quarantined messages, recipients must have a valid user ID and password in the service.</span></span> <span data-ttu-id="13e0d-232">Quarantine에 대한 자세한 내용은 사용자로 고지된 메시지 찾기 및 [릴리스를 참조하세요.](find-and-release-quarantined-messages-as-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="13e0d-232">For more information about quarantine, see [Find and release quarantined messages as a user](find-and-release-quarantined-messages-as-a-user.md).</span></span>

  - <span data-ttu-id="13e0d-233">**메일 흐름 규칙(전송** 규칙) : 디렉터리 동기화를 사용하는 경우 기존 Active Directory 사용자 및 그룹이 클라우드에 자동으로 업로드되며, 그런 다음 서비스에 수동으로 추가할 필요 없이 특정 사용자 및/또는 그룹을 대상으로 하는 메일 흐름 규칙을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13e0d-233">**Mail flow rules (also known as transport rules)**: When you use directory synchronization, your existing Active Directory users and groups are automatically uploaded to the cloud, and you can then create mail flow rules that target specific users and/or groups without having to manually add them in the service.</span></span> <span data-ttu-id="13e0d-234">동적 메일 [그룹은](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) 디렉터리 동기화를 통해 동기화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="13e0d-234">Note that [dynamic distribution groups](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) can't be synchronized via directory synchronization.</span></span>

<span data-ttu-id="13e0d-235">Azure Active Directory의 하이브리드 ID란? 설명에 따라 필요한 사용 권한을 얻고 디렉터리 [동기화를 준비합니다.](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity)</span><span class="sxs-lookup"><span data-stu-id="13e0d-235">Get the necessary permissions and prepare for directory synchronization, as described in [What is hybrid identity with Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity).</span></span>

### <a name="synchronize-directories-with-azure-active-directory-connect-aad-connect"></a><span data-ttu-id="13e0d-236">Azure Active Directory Connect(AAD Connect)와 디렉터리 동기화</span><span class="sxs-lookup"><span data-stu-id="13e0d-236">Synchronize directories with Azure Active Directory Connect (AAD Connect)</span></span>

1. <span data-ttu-id="13e0d-237">Azure AD Connect 동기화에 설명된 대로 디렉터리 동기화 활성화: 동기화 이해 및 [사용자 지정.](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis)</span><span class="sxs-lookup"><span data-stu-id="13e0d-237">Activate directory synchronization as described in [Azure AD Connect sync: Understand and customize synchronization](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).</span></span>

2. <span data-ttu-id="13e0d-238">Azure AD Connect의 선행 구성에 설명된 바와 같이 AAD Connect를 실행하도록 On-premises 컴퓨터를 설치 [및 구성합니다.](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites)</span><span class="sxs-lookup"><span data-stu-id="13e0d-238">Install and configure an on-premises computer to run AAD Connect as described in [Prerequisites for Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites).</span></span>

3. <span data-ttu-id="13e0d-239">[Azure AD Connect에 사용할 설치 유형을 선택합니다.](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation)</span><span class="sxs-lookup"><span data-stu-id="13e0d-239">[Select which installation type to use for Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation):</span></span>

   - [<span data-ttu-id="13e0d-240">Express</span><span class="sxs-lookup"><span data-stu-id="13e0d-240">Express</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)

   - [<span data-ttu-id="13e0d-241">사용자 지정</span><span class="sxs-lookup"><span data-stu-id="13e0d-241">Custom</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-custom)

   - [<span data-ttu-id="13e0d-242">통과 인증</span><span class="sxs-lookup"><span data-stu-id="13e0d-242">Pass-through authentication</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-quick-start)

> [!IMPORTANT]
> <span data-ttu-id="13e0d-p121">Azure Active Directory 동기화 도구 구성 마법사를 완료하면 Active Directory 포리스트에 **MSOL_AD_SYNC** 계정이 만들어집니다. 이 계정을 사용하여 온-프레미스 Active Directory 정보를 읽고 동기화합니다. 디렉터리 동기화가 정상적으로 작동하도록 하려면 로컬 디렉터리 동기화 서버의 TCP 443이 열려 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="13e0d-p121">When you finish the Azure Active Directory Sync Tool Configuration Wizard, the **MSOL_AD_SYNC** account is created in your Active Directory forest. This account is used to read and synchronize your on-premises Active Directory information. In order for directory synchronization to work correctly, make sure that TCP 443 on your local directory synchronization server is open.</span></span>

<span data-ttu-id="13e0d-246">동기화를 구성한 후 AAD Connect가 올바르게 동기화하고 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="13e0d-246">After configuring your sync, be sure to verify that AAD Connect is synchronizing correctly.</span></span> <span data-ttu-id="13e0d-247">이렇게 하려면 EAC에서 **받는 사람** \> **연락처** 로 이동한 다음 온-프레미스 환경에서 사용자 목록이 올바르게 동기화되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="13e0d-247">In the EAC, go to **Recipients** \> **Contacts** and view that the list of users was correctly synchronized from your on-premises environment.</span></span>
