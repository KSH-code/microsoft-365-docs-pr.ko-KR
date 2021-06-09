---
title: " Microsoft 365로 디렉터리 동기화 준비"
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365p_AddUsersWithDirSync
- O365M_AddUsersWithDirSync
- O365E_HRCSetupAADConnectAboutLM617031
- O365E_AddUsersWithDirSync
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOP150
- MOE150
- MBS150
ms.assetid: 01920974-9e6f-4331-a370-13aea4e82b3e
description: 디렉터리 동기화를 사용하여 사용자를 프로비전할 수 있도록 준비하는 Microsoft 365 이 방법을 사용하는 경우의 장기적인 이점에 대해 설명
ms.openlocfilehash: 7f701bf0a8b165323f7fd61b50b41fb5e18268a6
ms.sourcegitcommit: 5a1cb7d95070eef47d401a4693cc137a90550a5e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52259562"
---
# <a name="prepare-for-directory-synchronization-to-microsoft-365"></a><span data-ttu-id="ed850-103"> Microsoft 365로 디렉터리 동기화 준비</span><span class="sxs-lookup"><span data-stu-id="ed850-103">Prepare for directory synchronization to Microsoft 365</span></span>

<span data-ttu-id="ed850-104">*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="ed850-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="ed850-105">하이브리드 ID 및 디렉터리 동기화의 이점은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ed850-105">The benefits to hybrid identity and directory synchronization your organization include:</span></span>

- <span data-ttu-id="ed850-106">조직의 관리 프로그램 줄이기</span><span class="sxs-lookup"><span data-stu-id="ed850-106">Reducing the administrative programs in your organization</span></span>
- <span data-ttu-id="ed850-107">선택적으로 Single Sign-On 시나리오 사용</span><span class="sxs-lookup"><span data-stu-id="ed850-107">Optionally enabling single sign-on scenario</span></span>
- <span data-ttu-id="ed850-108">2013에서 계정 변경 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ed850-108">Automating account changes in Microsoft 365</span></span>

<span data-ttu-id="ed850-109">디렉터리 동기화 사용의 이점에 대한 자세한 내용은 에 대한 하이브리드 [ID(Azure AD)Azure Active Directory](/azure/active-directory/hybrid/whatis-hybrid-identity) 및 하이브리드 [ID를 Microsoft 365.](plan-for-directory-synchronization.md)</span><span class="sxs-lookup"><span data-stu-id="ed850-109">For more information about the advantages of using directory synchronization, see [hybrid identity with Azure Active Directory (Azure AD)](/azure/active-directory/hybrid/whatis-hybrid-identity) and [hybrid identity for Microsoft 365](plan-for-directory-synchronization.md).</span></span>

<span data-ttu-id="ed850-110">그러나 디렉터리 동기화를 수행하려면 AD DS(Active Directory 도메인 서비스)가 최소 오류와 함께 Microsoft 365 구독의 Azure AD 테넌트와 동기화되도록 계획하고 준비해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed850-110">However, directory synchronization requires planning and preparation to ensure that your Active Directory Domain Services (AD DS) synchronizes to the Azure AD tenant of your Microsoft 365 subscription with a minimum of errors.</span></span>

<span data-ttu-id="ed850-111">최상의 결과를 얻기 위해 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="ed850-111">Follow these steps in order for the best results.</span></span>

## <a name="1-directory-cleanup-tasks"></a><span data-ttu-id="ed850-112">1. 디렉터리 정리 작업</span><span class="sxs-lookup"><span data-stu-id="ed850-112">1. Directory cleanup tasks</span></span>

<span data-ttu-id="ed850-113">AD DS를 Azure AD 테넌트와 동기화하기 전에 AD DS를 정리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed850-113">Before you synchronize your AD DS to your Azure AD tenant, you need to clean up your AD DS.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ed850-114">동기화하기 전에 AD DS 정리를 수행하지 않는 경우 배포 프로세스에 상당한 부정적인 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed850-114">If you don't perform AD DS cleanup before you synchronize, it can lead to a significant negative impact on the deployment process.</span></span> <span data-ttu-id="ed850-115">디렉터리 동기화 주기를 거치고 오류를 식별하고 다시 동기화하는 데 며칠 또는 몇 주가 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed850-115">It might take days, or even weeks, to go through the cycle of directory synchronization, identifying errors, and re-synchronization.</span></span>

<span data-ttu-id="ed850-116">AD DS에서 Microsoft 365 할당할 각 사용자 계정에 대해 다음 정리 작업을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="ed850-116">In your AD DS, complete the following clean-up tasks for each user account that will be assigned a Microsoft 365 license:</span></span>

1. <span data-ttu-id="ed850-117">**proxyAddresses** 특성에서 유효하고 고유한 전자 메일 주소를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed850-117">Ensure a valid and unique email address in the **proxyAddresses** attribute.</span></span>

2. <span data-ttu-id="ed850-118">**proxyAddresses 특성에서 중복된 값을 제거합니다.**</span><span class="sxs-lookup"><span data-stu-id="ed850-118">Remove any duplicate values in the **proxyAddresses** attribute.</span></span>

3. <span data-ttu-id="ed850-119">가능한 경우 사용자 개체의 **userPrincipalName** 특성에 대한 유효하고 고유한 값을 **보장합니다.**</span><span class="sxs-lookup"><span data-stu-id="ed850-119">If possible, ensure a valid and unique value for the **userPrincipalName** attribute in the user's **user** object.</span></span> <span data-ttu-id="ed850-120">최상의 동기화 환경을 위해 AD DS UPN이 Azure AD UPN과 일치하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed850-120">For the best synchronization experience, ensure that the AD DS UPN matches the Azure AD UPN.</span></span> <span data-ttu-id="ed850-121">사용자에게 **userPrincipalName** 특성 값이 없는 경우 사용자 개체에는 **sAMAccountName** 특성에 대한 유효하고 고유한 값이 포함되어야 합니다. </span><span class="sxs-lookup"><span data-stu-id="ed850-121">If a user does not have a value for the **userPrincipalName** attribute, then the **user** object must contain a valid and unique value for the **sAMAccountName** attribute.</span></span> <span data-ttu-id="ed850-122">**userPrincipalName** 특성에서 중복된 값을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="ed850-122">Remove any duplicate values in the **userPrincipalName** attribute.</span></span>

4. <span data-ttu-id="ed850-123">GAL(전체 주소 목록)을 최적으로 사용하려면 AD DS 사용자 계정의 다음 특성에 있는 정보가 올바른지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ed850-123">For optimal use of the global address list (GAL), ensure the information in the following attributes of the AD DS user account is correct:</span></span>

   - <span data-ttu-id="ed850-124">givenName</span><span class="sxs-lookup"><span data-stu-id="ed850-124">givenName</span></span>
   - <span data-ttu-id="ed850-125">surname</span><span class="sxs-lookup"><span data-stu-id="ed850-125">surname</span></span>
   - <span data-ttu-id="ed850-126">displayName</span><span class="sxs-lookup"><span data-stu-id="ed850-126">displayName</span></span>
   - <span data-ttu-id="ed850-127">직함</span><span class="sxs-lookup"><span data-stu-id="ed850-127">Job Title</span></span>
   - <span data-ttu-id="ed850-128">부서</span><span class="sxs-lookup"><span data-stu-id="ed850-128">Department</span></span>
   - <span data-ttu-id="ed850-129">사무실</span><span class="sxs-lookup"><span data-stu-id="ed850-129">Office</span></span>
   - <span data-ttu-id="ed850-130">사무실 전화</span><span class="sxs-lookup"><span data-stu-id="ed850-130">Office Phone</span></span>
   - <span data-ttu-id="ed850-131">휴대폰 번호</span><span class="sxs-lookup"><span data-stu-id="ed850-131">Mobile Phone</span></span>
   - <span data-ttu-id="ed850-132">팩스 번호</span><span class="sxs-lookup"><span data-stu-id="ed850-132">Fax Number</span></span>
   - <span data-ttu-id="ed850-133">주소</span><span class="sxs-lookup"><span data-stu-id="ed850-133">Street Address</span></span>
   - <span data-ttu-id="ed850-134">구/군/시</span><span class="sxs-lookup"><span data-stu-id="ed850-134">City</span></span>
   - <span data-ttu-id="ed850-135">시/도</span><span class="sxs-lookup"><span data-stu-id="ed850-135">State or Province</span></span>
   - <span data-ttu-id="ed850-136">우편 번호</span><span class="sxs-lookup"><span data-stu-id="ed850-136">Zip or Postal Code</span></span>
   - <span data-ttu-id="ed850-137">국가</span><span class="sxs-lookup"><span data-stu-id="ed850-137">Country or Region</span></span>

## <a name="2-directory-object-and-attribute-preparation"></a><span data-ttu-id="ed850-138">2. 디렉터리 개체 및 특성 준비</span><span class="sxs-lookup"><span data-stu-id="ed850-138">2. Directory object and attribute preparation</span></span>

<span data-ttu-id="ed850-139">AD DS와 MICROSOFT 365 성공적으로 디렉터리를 동기화하려면 AD DS 특성이 제대로 준비되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed850-139">Successful directory synchronization between your AD DS and Microsoft 365 requires that your AD DS attributes are properly prepared.</span></span> <span data-ttu-id="ed850-140">예를 들어 특정 문자가 특정 환경과 동기화된 특정 특성에서 Microsoft 365 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed850-140">For example, you need to ensure that specific characters aren't used in certain attributes that are synchronized with the Microsoft 365 environment.</span></span> <span data-ttu-id="ed850-141">예기치 않은 문자로 인해 디렉터리 동기화가 실패하지는 않지만 경고가 반환될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed850-141">Unexpected characters do not cause directory synchronization to fail but might return a warning.</span></span> <span data-ttu-id="ed850-142">잘못된 문자로 인해 디렉터리 동기화가 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="ed850-142">Invalid characters will cause directory synchronization to fail.</span></span>

<span data-ttu-id="ed850-143">AD DS 사용자 중 일부에 중복 특성이 하나 이상 있는 경우 디렉터리 동기화가 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="ed850-143">Directory synchronization will also fail if some of your AD DS users have one or more duplicate attributes.</span></span> <span data-ttu-id="ed850-144">각 사용자는 고유한 특성을 가지고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed850-144">Each user must have unique attributes.</span></span>

<span data-ttu-id="ed850-145">준비해야 하는 특성은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ed850-145">The attributes that you need to prepare are listed here:</span></span>

- <span data-ttu-id="ed850-146">**displayName**</span><span class="sxs-lookup"><span data-stu-id="ed850-146">**displayName**</span></span>

  - <span data-ttu-id="ed850-147">사용자 개체에 특성이 있는 경우 이 특성은 사용자 개체와 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ed850-147">If the attribute exists in the user object, it will be synchronized with Microsoft 365.</span></span>
  - <span data-ttu-id="ed850-148">사용자 개체에 이 특성이 있는 경우 해당 특성에 대한 값이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed850-148">If this attribute exists in the user object, there must be a value for it.</span></span> <span data-ttu-id="ed850-149">즉, 특성을 비워 두면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed850-149">That is, the attribute must not be blank.</span></span>
  - <span data-ttu-id="ed850-150">최대 문자 수: 256</span><span class="sxs-lookup"><span data-stu-id="ed850-150">Maximum number of characters: 256</span></span>

- <span data-ttu-id="ed850-151">**givenName**</span><span class="sxs-lookup"><span data-stu-id="ed850-151">**givenName**</span></span>

  - <span data-ttu-id="ed850-152">사용자 개체에 특성이 있는 경우 이 특성은 Microsoft 365 동기화되지만 Microsoft 365 필요하거나 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ed850-152">If the attribute exists in the user object, it will be synchronized with Microsoft 365, but Microsoft 365 does not require or use it.</span></span>
  - <span data-ttu-id="ed850-153">최대 문자 수: 64</span><span class="sxs-lookup"><span data-stu-id="ed850-153">Maximum number of characters: 64</span></span>

- <span data-ttu-id="ed850-154">**메일**</span><span class="sxs-lookup"><span data-stu-id="ed850-154">**mail**</span></span>

  - <span data-ttu-id="ed850-155">특성 값은 디렉터리 내에서 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed850-155">The attribute value must be unique within the directory.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ed850-156">중복된 값이 있는 경우 값이 있는 첫 번째 사용자가 동기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed850-156">If there are duplicate values, the first user with the value is synchronized.</span></span> <span data-ttu-id="ed850-157">이후 사용자는 해당 사용자에게 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ed850-157">Subsequent users will not appear in Microsoft 365.</span></span> <span data-ttu-id="ed850-158">AD DS에서 두 사용자가 모두 표시될 수 있도록 Microsoft 365 값을 수정하거나 AD DS의 값을 모두 수정해야 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ed850-158">You must modify either the value in Microsoft 365 or modify both of the values in AD DS in order for both users to appear in Microsoft 365.</span></span>

- <span data-ttu-id="ed850-159">**mailNickname(Exchange** 별칭)</span><span class="sxs-lookup"><span data-stu-id="ed850-159">**mailNickname** (Exchange alias)</span></span>

  - <span data-ttu-id="ed850-160">특성 값은 기간(.)으로 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ed850-160">The attribute value cannot begin with a period (.).</span></span>
  - <span data-ttu-id="ed850-161">특성 값은 디렉터리 내에서 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed850-161">The attribute value must be unique within the directory.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ed850-162">동기화된 이름의 밑어("_")는 이 특성의 원래 값에 잘못된 문자가 포함되어 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ed850-162">Underscores ("_") in the synchronized name indicates that the original value of this attribute contains invalid characters.</span></span> <span data-ttu-id="ed850-163">이 특성에 대한 자세한 내용은 별칭 [Exchange 참조하세요.](/powershell/module/exchange/set-mailbox)</span><span class="sxs-lookup"><span data-stu-id="ed850-163">For more information on this attribute, see [Exchange alias attribute](/powershell/module/exchange/set-mailbox).</span></span>
    >

- <span data-ttu-id="ed850-164">**proxyAddresses**</span><span class="sxs-lookup"><span data-stu-id="ed850-164">**proxyAddresses**</span></span>

  - <span data-ttu-id="ed850-165">다중 값 특성</span><span class="sxs-lookup"><span data-stu-id="ed850-165">Multiple-value attribute</span></span>
  - <span data-ttu-id="ed850-166">값당 최대 문자 수: 256</span><span class="sxs-lookup"><span data-stu-id="ed850-166">Maximum number of characters per value: 256</span></span>
  - <span data-ttu-id="ed850-167">특성 값에 공백이 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed850-167">The attribute value must not contain a space.</span></span>
  - <span data-ttu-id="ed850-168">특성 값은 디렉터리 내에서 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed850-168">The attribute value must be unique within the directory.</span></span>
  - <span data-ttu-id="ed850-169">잘못된 문자: \< \> ( ) ; , [ ] "</span><span class="sxs-lookup"><span data-stu-id="ed850-169">Invalid characters: \< \> ( ) ; , [ ] "</span></span>

    <span data-ttu-id="ed850-170">유효하지 않은 문자는 형식이 ":"인 문자에 적용되어 SMTP:User@contso.com 허용되지만 SMTP:user:M@contoso.com 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ed850-170">Note that the invalid characters apply to the characters following the type delimiter and ":", such that SMTP:User@contso.com is allowed, but SMTP:user:M@contoso.com is not.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="ed850-171">모든 SMTP(Simple Mail Transport Protocol) 주소는 전자 메일 메시징 표준을 준수해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed850-171">All Simple Mail Transport Protocol (SMTP) addresses should comply with email messaging standards.</span></span> <span data-ttu-id="ed850-172">중복되거나 원치 않는 주소(있는 경우)를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="ed850-172">Remove duplicate or unwanted addresses if they exist.</span></span>

- <span data-ttu-id="ed850-173">**sAMAccountName**</span><span class="sxs-lookup"><span data-stu-id="ed850-173">**sAMAccountName**</span></span>

  - <span data-ttu-id="ed850-174">최대 문자 수: 20</span><span class="sxs-lookup"><span data-stu-id="ed850-174">Maximum number of characters: 20</span></span>
  - <span data-ttu-id="ed850-175">특성 값은 디렉터리 내에서 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed850-175">The attribute value must be unique within the directory.</span></span>
  - <span data-ttu-id="ed850-176">잘못된 문자: [ \ " | , / : \< \> + = ; ?</span><span class="sxs-lookup"><span data-stu-id="ed850-176">Invalid characters: [ \ " | , / : \< \> + = ; ?</span></span> <span data-ttu-id="ed850-177">\* ']</span><span class="sxs-lookup"><span data-stu-id="ed850-177">\* ']</span></span>
  - <span data-ttu-id="ed850-178">사용자에게 잘못된 **sAMAccountName** 특성이 있지만 **userPrincipalName** 특성이 유효한 경우 사용자 계정이 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ed850-178">If a user has an invalid **sAMAccountName** attribute but has a valid **userPrincipalName** attribute, the user account is created in Microsoft 365.</span></span>
  - <span data-ttu-id="ed850-179">**sAMAccountName과** **userPrincipalName이** 모두 유효하지 않은 경우 AD DS **userPrincipalName** 특성을 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed850-179">If both **sAMAccountName** and **userPrincipalName** are invalid, the AD DS **userPrincipalName** attribute must be updated.</span></span>

- <span data-ttu-id="ed850-180">**sn(성)**</span><span class="sxs-lookup"><span data-stu-id="ed850-180">**sn** (surname)</span></span>

  - <span data-ttu-id="ed850-181">사용자 개체에 특성이 있는 경우 이 특성은 Microsoft 365 동기화되지만 Microsoft 365 필요하거나 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ed850-181">If the attribute exists in the user object, it will be synchronized with Microsoft 365, but Microsoft 365 does not require or use it.</span></span>

- <span data-ttu-id="ed850-182">**targetAddress**</span><span class="sxs-lookup"><span data-stu-id="ed850-182">**targetAddress**</span></span>

    <span data-ttu-id="ed850-183">사용자에 대해 채워진 **targetAddress** 특성(예: SMTP:tom@contoso.com)이 GAL에 Microsoft 365 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ed850-183">It's required that the **targetAddress** attribute (for example, SMTP:tom@contoso.com) that's populated for the user must appear in the Microsoft 365 GAL.</span></span> <span data-ttu-id="ed850-184">타사 메시징 마이그레이션 시나리오에서는 AD DS에 대한 Microsoft 365 확장이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ed850-184">In third-party messaging migration scenarios, this would require the Microsoft 365 schema extension for the AD DS.</span></span> <span data-ttu-id="ed850-185">또한 Microsoft 365 확장은 AD DS의 디렉터리 동기화 도구를 사용하여 채워지는 Microsoft 365 개체를 관리하는 다른 유용한 특성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ed850-185">The Microsoft 365 schema extension would also add other useful attributes to manage Microsoft 365 objects that are populated by using a directory synchronization tool from AD DS.</span></span> <span data-ttu-id="ed850-186">예를 들어 숨겨진 사서함 또는 메일 그룹을 관리하는 **msExchHideFromAddressLists** 특성이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed850-186">For example, the **msExchHideFromAddressLists** attribute to manage hidden mailboxes or distribution groups would be added.</span></span>

  - <span data-ttu-id="ed850-187">최대 문자 수: 256</span><span class="sxs-lookup"><span data-stu-id="ed850-187">Maximum number of characters: 256</span></span>
  - <span data-ttu-id="ed850-188">특성 값에 공백이 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed850-188">The attribute value must not contain a space.</span></span>
  - <span data-ttu-id="ed850-189">특성 값은 디렉터리 내에서 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed850-189">The attribute value must be unique within the directory.</span></span>
  - <span data-ttu-id="ed850-190">잘못된 문자: \ \< \> ( ) ; , [ ] "</span><span class="sxs-lookup"><span data-stu-id="ed850-190">Invalid characters: \ \< \> ( ) ; , [ ] "</span></span>
  - <span data-ttu-id="ed850-191">모든 SMTP(Simple Mail Transport Protocol) 주소는 전자 메일 메시징 표준을 준수해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed850-191">All Simple Mail Transport Protocol (SMTP) addresses should comply with email messaging standards.</span></span>

- <span data-ttu-id="ed850-192">**userPrincipalName**</span><span class="sxs-lookup"><span data-stu-id="ed850-192">**userPrincipalName**</span></span>

  - <span data-ttu-id="ed850-193">**userPrincipalName** 특성은 사용자 이름이 다음에 기호(@) 및 도메인 이름과 같은 인터넷 스타일 로그인 형식(예: user@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="ed850-193">The **userPrincipalName** attribute must be in the Internet-style sign-in format where the user name is followed by the at sign (@) and a domain name: for example, user@contoso.com.</span></span> <span data-ttu-id="ed850-194">모든 SMTP(Simple Mail Transport Protocol) 주소는 전자 메일 메시징 표준을 준수해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed850-194">All Simple Mail Transport Protocol (SMTP) addresses should comply with email messaging standards.</span></span>
  - <span data-ttu-id="ed850-195">**userPrincipalName** 특성의 최대 문자 수는 113개입니다.</span><span class="sxs-lookup"><span data-stu-id="ed850-195">The maximum number of characters for the **userPrincipalName** attribute is 113.</span></span> <span data-ttu-id="ed850-196">다음과 같이 기호(@)의 앞과 뒤에서 특정 문자 수가 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed850-196">A specific number of characters are permitted before and after the at sign (@), as follows:</span></span>
  - <span data-ttu-id="ed850-197">기호(@) 앞에 있는 사용자 이름의 최대 문자 수: 64</span><span class="sxs-lookup"><span data-stu-id="ed850-197">Maximum number of characters for the username that is in front of the at sign (@): 64</span></span>
  - <span data-ttu-id="ed850-198">@ 기호 다음의 도메인 이름에 대한 최대 문자 수: 48</span><span class="sxs-lookup"><span data-stu-id="ed850-198">Maximum number of characters for the domain name following the at sign (@): 48</span></span>
  - <span data-ttu-id="ed850-199">잘못된 문자: \ % &amp; \* + / = ?</span><span class="sxs-lookup"><span data-stu-id="ed850-199">Invalid characters: \ % &amp; \* + / = ?</span></span> <span data-ttu-id="ed850-200">{ } | \< \> ( ) ; : , [ ] "</span><span class="sxs-lookup"><span data-stu-id="ed850-200">{ } | \< \> ( ) ; : , [ ] "</span></span>
  - <span data-ttu-id="ed850-201">문자 허용: A – Z, a - z, 0 - 9, ' .</span><span class="sxs-lookup"><span data-stu-id="ed850-201">Characters allowed: A – Z, a - z, 0 – 9, ' .</span></span> <span data-ttu-id="ed850-202">- _ !</span><span class="sxs-lookup"><span data-stu-id="ed850-202">- _ !</span></span> <span data-ttu-id="ed850-203"># ^ ~</span><span class="sxs-lookup"><span data-stu-id="ed850-203"># ^ ~</span></span>
  - <span data-ttu-id="ed850-204">umlauts, accents, tildes와 같은 악센트 부호가 있는 문자는 유효하지 않은 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="ed850-204">Letters with diacritical marks, such as umlauts, accents, and tildes, are invalid characters.</span></span>
  - <span data-ttu-id="ed850-205">@ 문자는 각 **userPrincipalName 값에** 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ed850-205">The @ character is required in each **userPrincipalName** value.</span></span>
  - <span data-ttu-id="ed850-206">@ 문자는 각 **userPrincipalName** 값의 첫 번째 문자일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ed850-206">The @ character cannot be the first character in each **userPrincipalName** value.</span></span>
  - <span data-ttu-id="ed850-207">사용자 이름은 마침침(.), 앰퍼and( ), 공백 또는 기호(@)로 끝날 &amp; 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ed850-207">The username cannot end with a period (.), an ampersand (&amp;), a space, or an at sign (@).</span></span>
  - <span data-ttu-id="ed850-208">사용자 이름에는 공백을 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ed850-208">The username cannot contain any spaces.</span></span>
  - <span data-ttu-id="ed850-209">라우팅 가능한 도메인을 사용해야 합니다. 예를 들어 로컬 또는 내부 도메인은 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ed850-209">Routable domains must be used; for example, local or internal domains cannot be used.</span></span>
  - <span data-ttu-id="ed850-210">유니코드는 밑줄 문자로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed850-210">Unicode is converted to underscore characters.</span></span>
  - <span data-ttu-id="ed850-211">**userPrincipalName은** 디렉터리에 중복된 값을 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ed850-211">**userPrincipalName** cannot contain any duplicate values in the directory.</span></span>

## <a name="3-prepare-the-userprincipalname-attribute"></a><span data-ttu-id="ed850-212">3. userPrincipalName 특성 준비</span><span class="sxs-lookup"><span data-stu-id="ed850-212">3. Prepare the userPrincipalName attribute</span></span>

<span data-ttu-id="ed850-213">Active Directory는 조직의 최종 사용자가 **sAMAccountName** 또는 **userPrincipalName** 을 사용하여 디렉터리에 로그인할 수 있도록 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ed850-213">Active Directory is designed to allow the end users in your organization to sign in to your directory by using either **sAMAccountName** or **userPrincipalName**.</span></span> <span data-ttu-id="ed850-214">마찬가지로 최종 사용자는 자신의 직장 또는 학교 계정의 UPN(Microsoft 365 이름)을 사용하여 로그인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed850-214">Similarly, end users can sign in to Microsoft 365 by using the user principal name (UPN) of their work or school account.</span></span> <span data-ttu-id="ed850-215">디렉터리 동기화는 AD DS에 Azure Active Directory UPN을 사용하여 새 사용자를 만들하려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="ed850-215">Directory synchronization attempts to create new users in Azure Active Directory by using the same UPN that's in your AD DS.</span></span> <span data-ttu-id="ed850-216">UPN의 형식은 전자 메일 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="ed850-216">The UPN is formatted like an email address.</span></span>

<span data-ttu-id="ed850-217">이 Microsoft 365 UPN은 전자 메일 주소를 생성하는 데 사용되는 기본 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="ed850-217">In Microsoft 365, the UPN is the default attribute that's used to generate the email address.</span></span> <span data-ttu-id="ed850-218">ad DS 및 Azure AD에서 **userPrincipalName** 및 **proxyAddresses의** 기본 전자 메일 주소를 서로 다른 값으로 설정하기가 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="ed850-218">It's easy to get **userPrincipalName** (in AD DS and in Azure AD) and the primary email address in **proxyAddresses** set to different values.</span></span> <span data-ttu-id="ed850-219">값을 서로 다른 값으로 설정하면 관리자와 최종 사용자에게 혼동을 주게 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed850-219">When they are set to different values, there can be confusion for administrators and end users.</span></span>

<span data-ttu-id="ed850-220">혼동을 줄이기 위해 이러한 특성을 맞추는 것이 가장 좋은 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ed850-220">It's best to align these attributes to reduce confusion.</span></span> <span data-ttu-id="ed850-221">AD FS(Active Directory Federation Services) 2.0을 사용한 Single Sign-On의 요구 사항을 충족하려면 Azure Active Directory 및 AD DS의 UPNS가 일치하는지와 유효한 도메인 네임스페이스를 사용하는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed850-221">To meet the requirements of single sign-on with Active Directory Federation Services (AD FS) 2.0, you need to ensure that the UPNs in Azure Active Directory and your AD DS match and are using a valid domain namespace.</span></span>

## <a name="4-add-an-alternative-upn-suffix-to-ad-ds"></a><span data-ttu-id="ed850-222">4. AD DS에 대체 UPN 접미사 추가</span><span class="sxs-lookup"><span data-stu-id="ed850-222">4. Add an alternative UPN suffix to AD DS</span></span>

<span data-ttu-id="ed850-223">사용자의 회사 자격 증명을 사용자 회사 자격 증명과 연결하기 위해 대체 UPN 접미어를 Microsoft 365 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed850-223">You may need to add an alternative UPN suffix to associate the user's corporate credentials with the Microsoft 365 environment.</span></span> <span data-ttu-id="ed850-224">UPN 접미사는 UPN에서 @ 문자 오른쪽에 있는 부분입니다.</span><span class="sxs-lookup"><span data-stu-id="ed850-224">A UPN suffix is the part of a UPN to the right of the @ character.</span></span> <span data-ttu-id="ed850-225">Single Sign-On에 사용되는 UPN에는 문자, 숫자, 마침표, 대시 및 밑줄을 포함할 수 있으며 다른 유형의 문자는 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ed850-225">UPNs that are used for single sign-on can contain letters, numbers, periods, dashes, and underscores, but no other types of characters.</span></span>

<span data-ttu-id="ed850-226">Active Directory에 대체 UPN 접미사 추가 방법에 대한 자세한 내용은 디렉터리 동기화 [준비를 참조하세요.]( https://go.microsoft.com/fwlink/p/?LinkId=525430)</span><span class="sxs-lookup"><span data-stu-id="ed850-226">For more information on how to add an alternative UPN suffix to Active Directory, see [Prepare for directory synchronization]( https://go.microsoft.com/fwlink/p/?LinkId=525430).</span></span>

## <a name="5-match-the-ad-ds-upn-with-the-microsoft-365-upn"></a><span data-ttu-id="ed850-227">5. AD DS UPN과 UPN Microsoft 365 일치</span><span class="sxs-lookup"><span data-stu-id="ed850-227">5. Match the AD DS UPN with the Microsoft 365 UPN</span></span>

<span data-ttu-id="ed850-228">디렉터리 동기화를 이미 설정한 경우 해당 디렉터리에 대한 Microsoft 365 AD DS에 정의된 사용자의 AD DS UPN과 일치하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed850-228">If you've already set up directory synchronization, the user's UPN for Microsoft 365 may not match the user's AD DS UPN that's defined in your AD DS.</span></span> <span data-ttu-id="ed850-229">도메인이 확인되기 전에 사용자에게 라이선스가 할당된 경우 이와 같은 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed850-229">This can occur when a user was assigned a license before the domain was verified.</span></span> <span data-ttu-id="ed850-230">이 문제를 해결하려면 [PowerShell을 사용하여 중복된 UPN을](https://go.microsoft.com/fwlink/p/?LinkId=396730) 수정하여 사용자의 UPN을 업데이트하여 Microsoft 365 UPN이 회사 사용자 이름 및 도메인과 일치하는지 확인</span><span class="sxs-lookup"><span data-stu-id="ed850-230">To fix this, use [PowerShell to fix duplicate UPN](https://go.microsoft.com/fwlink/p/?LinkId=396730) to update the user's UPN to ensure that the Microsoft 365 UPN matches the corporate user name and domain.</span></span> <span data-ttu-id="ed850-231">AD DS에서 UPN을 업데이트하고 AZURE ACTIVE DIRECTORY ID와 동기화하려면 AD DS를 변경하기 전에 Microsoft 365 라이선스를 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed850-231">If you are updating the UPN in the AD DS and would like it to synchronize with the Azure Active Directory identity, you need to remove the user's license in Microsoft 365 prior to making the changes in AD DS.</span></span>

<span data-ttu-id="ed850-232">디렉터리 동기화를 위해 라우팅할 수 없는 도메인(예: [.local 도메인)을 준비하는 방법도 참조합니다.](prepare-a-non-routable-domain-for-directory-synchronization.md)</span><span class="sxs-lookup"><span data-stu-id="ed850-232">Also see [How to prepare a non-routable domain (such as .local domain) for directory synchronization](prepare-a-non-routable-domain-for-directory-synchronization.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="ed850-233">다음 단계</span><span class="sxs-lookup"><span data-stu-id="ed850-233">Next steps</span></span>

<span data-ttu-id="ed850-234">위의 1~5단계를 완료한 경우 디렉터리 동기화 설정 [을 참조하세요.](set-up-directory-synchronization.md)</span><span class="sxs-lookup"><span data-stu-id="ed850-234">If you have done steps 1 through 5 above, see [Set up directory synchronization](set-up-directory-synchronization.md).</span></span>
