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
description: 디렉터리 동기화 및이 방법을 사용할 경우의 장기적 이점을 사용 하 여 사용자를 Microsoft 365에 프로 비전 하도록 준비 하는 방법에 대해 설명 합니다.
ms.openlocfilehash: e49cc4472b47320650d8a0ca90395b69ae5b6df7
ms.sourcegitcommit: bdf65d48b20f0f428162c39ee997accfa84f4e5d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/20/2020
ms.locfileid: "49371627"
---
# <a name="prepare-for-directory-synchronization-to-microsoft-365"></a><span data-ttu-id="c71c2-103"> Microsoft 365로 디렉터리 동기화 준비</span><span class="sxs-lookup"><span data-stu-id="c71c2-103">Prepare for directory synchronization to Microsoft 365</span></span>

<span data-ttu-id="c71c2-104">*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="c71c2-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="c71c2-105">조직에 대 한 하이브리드 id 및 디렉터리 동기화의 이점은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-105">The benefits to hybrid identity and directory synchronization your organization include:</span></span>

- <span data-ttu-id="c71c2-106">조직의 관리 프로그램 감소</span><span class="sxs-lookup"><span data-stu-id="c71c2-106">Reducing the administrative programs in your organization</span></span>
- <span data-ttu-id="c71c2-107">선택적으로 single sign-on 시나리오를 사용 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="c71c2-107">Optionally enabling single sign-on scenario</span></span>
- <span data-ttu-id="c71c2-108">Microsoft 365에서 계정 변경 자동화</span><span class="sxs-lookup"><span data-stu-id="c71c2-108">Automating account changes in Microsoft 365</span></span>

<span data-ttu-id="c71c2-109">디렉터리 동기화를 사용할 때의 이점에 대 한 자세한 내용은 [하이브리드 identity With Azure Active directory (AZURE AD)](https://go.microsoft.com/fwlink/p/?LinkId=525398) 및 [Hybrid identity for Microsoft 365](plan-for-directory-synchronization.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c71c2-109">For more information about the advantages of using directory synchronization, see [hybrid identity with Azure Active Directory (Azure AD)](https://go.microsoft.com/fwlink/p/?LinkId=525398) and [hybrid identity for Microsoft 365](plan-for-directory-synchronization.md).</span></span>

<span data-ttu-id="c71c2-110">그러나 디렉터리를 동기화 하려면 계획 및 준비를 수행 해야 하므로 AD DS (Active Directory 도메인 서비스)가 Microsoft 365 구독의 Azure AD 테 넌 트와 동기화 하는 데 최소한의 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-110">However, directory synchronization requires planning and preparation to ensure that your Active Directory Domain Services (AD DS) synchronizes to the Azure AD tenant of your Microsoft 365 subscription with a minimum of errors.</span></span>

<span data-ttu-id="c71c2-111">최상의 결과를 위해 다음 단계를 순서 대로 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-111">Follow these steps in order for the best results.</span></span>

## <a name="1-directory-cleanup-tasks"></a><span data-ttu-id="c71c2-112">1. 디렉터리 정리 작업</span><span class="sxs-lookup"><span data-stu-id="c71c2-112">1. Directory cleanup tasks</span></span>

<span data-ttu-id="c71c2-113">Azure AD 테 넌 트에 AD DS를 동기화 하기 전에 AD DS를 정리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-113">Before you synchronize your AD DS to your Azure AD tenant, you need to clean up your AD DS.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c71c2-114">동기화 하기 전에 AD DS 정리를 수행 하지 않으면 배포 프로세스에 심각한 부정적인 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-114">If you don't perform AD DS cleanup before you synchronize, it can lead to a significant negative impact on the deployment process.</span></span> <span data-ttu-id="c71c2-115">디렉터리 동기화 주기, 오류 식별 및 다시 동기화를 진행 하는 데 며칠 또는 몇 주가 소요 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-115">It might take days, or even weeks, to go through the cycle of directory synchronization, identifying errors, and re-synchronization.</span></span>

<span data-ttu-id="c71c2-116">AD DS에서 Microsoft 365 라이선스가 할당 될 각 사용자 계정에 대해 다음과 같은 정리 작업을 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-116">In your AD DS, complete the following clean-up tasks for each user account that will be assigned a Microsoft 365 license:</span></span>

1. <span data-ttu-id="c71c2-117">**ProxyAddresses** 특성에 유효한 전자 메일 주소와 고유한 주소가 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-117">Ensure a valid and unique email address in the **proxyAddresses** attribute.</span></span>

2. <span data-ttu-id="c71c2-118">**ProxyAddresses** 특성에서 중복 된 값을 모두 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-118">Remove any duplicate values in the **proxyAddresses** attribute.</span></span>

3. <span data-ttu-id="c71c2-119">가능한 경우 사용자의 **user** 개체에 있는 **userPrincipalName** 특성에 대 한 유효한 값 및 고유함을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-119">If possible, ensure a valid and unique value for the **userPrincipalName** attribute in the user's **user** object.</span></span> <span data-ttu-id="c71c2-120">최상의 동기화 환경을 위해 AD DS UPN이 Azure AD UPN과 일치 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-120">For the best synchronization experience, ensure that the AD DS UPN matches the Azure AD UPN.</span></span> <span data-ttu-id="c71c2-121">사용자에 게 **userPrincipalName** 특성에 대 한 값이 없는 경우에는 **사용자** 개체에 **sAMAccountName** 특성에 대 한 유효한 값과 고유 정보가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-121">If a user does not have a value for the **userPrincipalName** attribute, then the **user** object must contain a valid and unique value for the **sAMAccountName** attribute.</span></span> <span data-ttu-id="c71c2-122">**UserPrincipalName** 특성에서 중복 된 값을 모두 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-122">Remove any duplicate values in the **userPrincipalName** attribute.</span></span>

4. <span data-ttu-id="c71c2-123">전체 주소 목록 (GAL)을 최적의 상태로 사용 하려면 AD DS 사용자 계정의 다음 특성에 있는 정보가 올바른지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-123">For optimal use of the global address list (GAL), ensure the information in the following attributes of the AD DS user account is correct:</span></span>

   - <span data-ttu-id="c71c2-124">givenName</span><span class="sxs-lookup"><span data-stu-id="c71c2-124">givenName</span></span>
   - <span data-ttu-id="c71c2-125">성</span><span class="sxs-lookup"><span data-stu-id="c71c2-125">surname</span></span>
   - <span data-ttu-id="c71c2-126">displayName</span><span class="sxs-lookup"><span data-stu-id="c71c2-126">displayName</span></span>
   - <span data-ttu-id="c71c2-127">직함</span><span class="sxs-lookup"><span data-stu-id="c71c2-127">Job Title</span></span>
   - <span data-ttu-id="c71c2-128">부서</span><span class="sxs-lookup"><span data-stu-id="c71c2-128">Department</span></span>
   - <span data-ttu-id="c71c2-129">사무실</span><span class="sxs-lookup"><span data-stu-id="c71c2-129">Office</span></span>
   - <span data-ttu-id="c71c2-130">사무실 전화</span><span class="sxs-lookup"><span data-stu-id="c71c2-130">Office Phone</span></span>
   - <span data-ttu-id="c71c2-131">휴대폰 번호</span><span class="sxs-lookup"><span data-stu-id="c71c2-131">Mobile Phone</span></span>
   - <span data-ttu-id="c71c2-132">팩스 번호</span><span class="sxs-lookup"><span data-stu-id="c71c2-132">Fax Number</span></span>
   - <span data-ttu-id="c71c2-133">주소</span><span class="sxs-lookup"><span data-stu-id="c71c2-133">Street Address</span></span>
   - <span data-ttu-id="c71c2-134">구/군/시</span><span class="sxs-lookup"><span data-stu-id="c71c2-134">City</span></span>
   - <span data-ttu-id="c71c2-135">시/도</span><span class="sxs-lookup"><span data-stu-id="c71c2-135">State or Province</span></span>
   - <span data-ttu-id="c71c2-136">우편 번호</span><span class="sxs-lookup"><span data-stu-id="c71c2-136">Zip or Postal Code</span></span>
   - <span data-ttu-id="c71c2-137">국가</span><span class="sxs-lookup"><span data-stu-id="c71c2-137">Country or Region</span></span>

## <a name="2-directory-object-and-attribute-preparation"></a><span data-ttu-id="c71c2-138">2. 디렉터리 개체 및 특성 준비</span><span class="sxs-lookup"><span data-stu-id="c71c2-138">2. Directory object and attribute preparation</span></span>

<span data-ttu-id="c71c2-139">AD DS와 Microsoft 365 간의 디렉터리 동기화가 정상적으로 수행 되려면 AD DS 특성이 적절 하 게 준비 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-139">Successful directory synchronization between your AD DS and Microsoft 365 requires that your AD DS attributes are properly prepared.</span></span> <span data-ttu-id="c71c2-140">예를 들어 Microsoft 365 환경과 동기화 되는 특정 특성에 특정 문자가 사용 되지 않는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-140">For example, you need to ensure that specific characters aren't used in certain attributes that are synchronized with the Microsoft 365 environment.</span></span> <span data-ttu-id="c71c2-141">예기치 않은 문자로 인해 디렉터리 동기화가 실패 하는 것은 아니지만 경고를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-141">Unexpected characters do not cause directory synchronization to fail but might return a warning.</span></span> <span data-ttu-id="c71c2-142">잘못 된 문자가 있으면 디렉터리 동기화가 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-142">Invalid characters will cause directory synchronization to fail.</span></span>

<span data-ttu-id="c71c2-143">AD DS 사용자 중 일부에 중복 된 특성이 하나 이상 있는 경우에도 디렉터리 동기화가 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-143">Directory synchronization will also fail if some of your AD DS users have one or more duplicate attributes.</span></span> <span data-ttu-id="c71c2-144">각 사용자에 게는 고유한 특성이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-144">Each user must have unique attributes.</span></span>

<span data-ttu-id="c71c2-145">준비 해야 하는 특성은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-145">The attributes that you need to prepare are listed here:</span></span>

- <span data-ttu-id="c71c2-146">**n**</span><span class="sxs-lookup"><span data-stu-id="c71c2-146">**displayName**</span></span>

  - <span data-ttu-id="c71c2-147">사용자 개체에 특성이 있으면 Microsoft 365와 동기화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-147">If the attribute exists in the user object, it will be synchronized with Microsoft 365.</span></span>
  - <span data-ttu-id="c71c2-148">이 특성이 사용자 개체에 있는 경우에는 해당 특성에 대 한 값이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-148">If this attribute exists in the user object, there must be a value for it.</span></span> <span data-ttu-id="c71c2-149">즉, 특성을 비워 두면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-149">That is, the attribute must not be blank.</span></span>
  - <span data-ttu-id="c71c2-150">최대 문자 수: 256</span><span class="sxs-lookup"><span data-stu-id="c71c2-150">Maximum number of characters: 256</span></span>

- <span data-ttu-id="c71c2-151">**givenName**</span><span class="sxs-lookup"><span data-stu-id="c71c2-151">**givenName**</span></span>

  - <span data-ttu-id="c71c2-152">특성이 사용자 개체에 있는 경우 Microsoft 365와 동기화 되지만 Microsoft 365에서는이를 필요로 하거나 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-152">If the attribute exists in the user object, it will be synchronized with Microsoft 365, but Microsoft 365 does not require or use it.</span></span>
  - <span data-ttu-id="c71c2-153">최대 문자 수: 64</span><span class="sxs-lookup"><span data-stu-id="c71c2-153">Maximum number of characters: 64</span></span>

- <span data-ttu-id="c71c2-154">**메일**</span><span class="sxs-lookup"><span data-stu-id="c71c2-154">**mail**</span></span>

  - <span data-ttu-id="c71c2-155">특성 값은 디렉터리 내에서 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-155">The attribute value must be unique within the directory.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c71c2-156">중복 된 값이 있는 경우 값이 있는 첫 번째 사용자가 동기화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-156">If there are duplicate values, the first user with the value is synchronized.</span></span> <span data-ttu-id="c71c2-157">이후 사용자는 Microsoft 365에 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-157">Subsequent users will not appear in Microsoft 365.</span></span> <span data-ttu-id="c71c2-158">두 사용자가 Microsoft 365에 나타나려면 Microsoft 365의 값을 수정 하거나 AD DS의 값을 모두 수정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-158">You must modify either the value in Microsoft 365 or modify both of the values in AD DS in order for both users to appear in Microsoft 365.</span></span>

- <span data-ttu-id="c71c2-159">**mailNickname** (Exchange 별칭)</span><span class="sxs-lookup"><span data-stu-id="c71c2-159">**mailNickname** (Exchange alias)</span></span>

  - <span data-ttu-id="c71c2-160">특성 값은 마침표 (.)로 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-160">The attribute value cannot begin with a period (.).</span></span>
  - <span data-ttu-id="c71c2-161">특성 값은 디렉터리 내에서 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-161">The attribute value must be unique within the directory.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c71c2-162">동기화 된 이름에서 밑줄 ("_")은이 특성의 원래 값에 잘못 된 문자가 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-162">Underscores ("_") in the synchronized name indicates that the original value of this attribute contains invalid characters.</span></span> <span data-ttu-id="c71c2-163">이 특성에 대 한 자세한 내용은 [Exchange alias 특성](https://docs.microsoft.com/powershell/module/exchange/set-mailbox)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c71c2-163">For more information on this attribute, see [Exchange alias attribute](https://docs.microsoft.com/powershell/module/exchange/set-mailbox).</span></span>
    >

- <span data-ttu-id="c71c2-164">**proxyAddresses**</span><span class="sxs-lookup"><span data-stu-id="c71c2-164">**proxyAddresses**</span></span>

  - <span data-ttu-id="c71c2-165">여러 값 특성</span><span class="sxs-lookup"><span data-stu-id="c71c2-165">Multiple-value attribute</span></span>
  - <span data-ttu-id="c71c2-166">값 당 최대 문자 수: 256</span><span class="sxs-lookup"><span data-stu-id="c71c2-166">Maximum number of characters per value: 256</span></span>
  - <span data-ttu-id="c71c2-167">특성 값에는 공백이 없어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-167">The attribute value must not contain a space.</span></span>
  - <span data-ttu-id="c71c2-168">특성 값은 디렉터리 내에서 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-168">The attribute value must be unique within the directory.</span></span>
  - <span data-ttu-id="c71c2-169">유효 하지 않은 문자: \< \> ();, [] "'</span><span class="sxs-lookup"><span data-stu-id="c71c2-169">Invalid characters: \< \> ( ) ; , [ ] " '</span></span>

    <span data-ttu-id="c71c2-170">잘못 된 문자는 형식 구분 기호 뒤에 있는 문자에 적용 되 고, SMTP:User@contso.com는 허용 되지만 SMTP:user:M@contoso.com는 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-170">Note that the invalid characters apply to the characters following the type delimiter and ":", such that SMTP:User@contso.com is allowed, but SMTP:user:M@contoso.com is not.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="c71c2-171">모든 SMTP (Simple Mail Transport Protocol) 주소는 전자 메일 메시징 표준을 준수 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-171">All Simple Mail Transport Protocol (SMTP) addresses should comply with email messaging standards.</span></span> <span data-ttu-id="c71c2-172">중복 또는 원하지 않는 주소 (있는 경우)를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-172">Remove duplicate or unwanted addresses if they exist.</span></span>

- <span data-ttu-id="c71c2-173">**sAMAccountName**</span><span class="sxs-lookup"><span data-stu-id="c71c2-173">**sAMAccountName**</span></span>

  - <span data-ttu-id="c71c2-174">최대 문자 수: 20</span><span class="sxs-lookup"><span data-stu-id="c71c2-174">Maximum number of characters: 20</span></span>
  - <span data-ttu-id="c71c2-175">특성 값은 디렉터리 내에서 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-175">The attribute value must be unique within the directory.</span></span>
  - <span data-ttu-id="c71c2-176">유효 하지 않은 문자: [\ "|,/: \< \> + =;?</span><span class="sxs-lookup"><span data-stu-id="c71c2-176">Invalid characters: [ \ " | , / : \< \> + = ; ?</span></span> <span data-ttu-id="c71c2-177">\* ']</span><span class="sxs-lookup"><span data-stu-id="c71c2-177">\* ']</span></span>
  - <span data-ttu-id="c71c2-178">사용자의 **sAMAccountName** 특성이 유효 하지 않지만 **userPrincipalName** 특성이 유효한 경우 사용자 계정이 Microsoft 365에서 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-178">If a user has an invalid **sAMAccountName** attribute but has a valid **userPrincipalName** attribute, the user account is created in Microsoft 365.</span></span>
  - <span data-ttu-id="c71c2-179">**SAMAccountName** 및 **userPrincipalName** 이 둘 다 유효 하지 않은 경우 AD DS **userPrincipalName** 특성을 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-179">If both **sAMAccountName** and **userPrincipalName** are invalid, the AD DS **userPrincipalName** attribute must be updated.</span></span>

- <span data-ttu-id="c71c2-180">**sn** (성)</span><span class="sxs-lookup"><span data-stu-id="c71c2-180">**sn** (surname)</span></span>

  - <span data-ttu-id="c71c2-181">특성이 사용자 개체에 있는 경우 Microsoft 365와 동기화 되지만 Microsoft 365에서는이를 필요로 하거나 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-181">If the attribute exists in the user object, it will be synchronized with Microsoft 365, but Microsoft 365 does not require or use it.</span></span>

- <span data-ttu-id="c71c2-182">**targetAddress**</span><span class="sxs-lookup"><span data-stu-id="c71c2-182">**targetAddress**</span></span>

    <span data-ttu-id="c71c2-183">사용자에 대해 채워지는 **targetAddress** 특성 (예: SMTP:tom@contoso.com)이 MICROSOFT 365 GAL에 나타나야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-183">It's required that the **targetAddress** attribute (for example, SMTP:tom@contoso.com) that's populated for the user must appear in the Microsoft 365 GAL.</span></span> <span data-ttu-id="c71c2-184">타사 메시징 마이그레이션 시나리오에서이를 위해서는 AD DS에 대 한 Microsoft 365 스키마 확장이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-184">In third-party messaging migration scenarios, this would require the Microsoft 365 schema extension for the AD DS.</span></span> <span data-ttu-id="c71c2-185">Microsoft 365 스키마 확장은 또한 AD DS에서 디렉터리 동기화 도구를 사용 하 여 채워지는 Microsoft 365 개체를 관리 하는 데 유용한 다른 특성도 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-185">The Microsoft 365 schema extension would also add other useful attributes to manage Microsoft 365 objects that are populated by using a directory synchronization tool from AD DS.</span></span> <span data-ttu-id="c71c2-186">예를 들어, 숨겨진 사서함 또는 메일 그룹을 관리 하기 위한 **msExchHideFromAddressLists** 특성이 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-186">For example, the **msExchHideFromAddressLists** attribute to manage hidden mailboxes or distribution groups would be added.</span></span>

  - <span data-ttu-id="c71c2-187">최대 문자 수: 256</span><span class="sxs-lookup"><span data-stu-id="c71c2-187">Maximum number of characters: 256</span></span>
  - <span data-ttu-id="c71c2-188">특성 값에는 공백이 없어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-188">The attribute value must not contain a space.</span></span>
  - <span data-ttu-id="c71c2-189">특성 값은 디렉터리 내에서 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-189">The attribute value must be unique within the directory.</span></span>
  - <span data-ttu-id="c71c2-190">유효 하지 않은 문자: \ \< \> ();, [] "</span><span class="sxs-lookup"><span data-stu-id="c71c2-190">Invalid characters: \ \< \> ( ) ; , [ ] "</span></span>
  - <span data-ttu-id="c71c2-191">모든 SMTP (Simple Mail Transport Protocol) 주소는 전자 메일 메시징 표준을 준수 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-191">All Simple Mail Transport Protocol (SMTP) addresses should comply with email messaging standards.</span></span>

- <span data-ttu-id="c71c2-192">**userPrincipalName**</span><span class="sxs-lookup"><span data-stu-id="c71c2-192">**userPrincipalName**</span></span>

  - <span data-ttu-id="c71c2-193">**UserPrincipalName** 특성은 사용자 이름 뒤에 @ 기호와 도메인 이름 (예: user@contoso.com)이 오는 인터넷 스타일 로그인 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-193">The **userPrincipalName** attribute must be in the Internet-style sign-in format where the user name is followed by the at sign (@) and a domain name: for example, user@contoso.com.</span></span> <span data-ttu-id="c71c2-194">모든 SMTP (Simple Mail Transport Protocol) 주소는 전자 메일 메시징 표준을 준수 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-194">All Simple Mail Transport Protocol (SMTP) addresses should comply with email messaging standards.</span></span>
  - <span data-ttu-id="c71c2-195">**UserPrincipalName** 특성의 최대 문자 수는 113입니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-195">The maximum number of characters for the **userPrincipalName** attribute is 113.</span></span> <span data-ttu-id="c71c2-196">다음과 같이 @ 기호 앞 이나 뒤에 특정 문자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-196">A specific number of characters are permitted before and after the at sign (@), as follows:</span></span>
  - <span data-ttu-id="c71c2-197">@ 기호 앞에 있는 사용자 이름의 최대 문자 수: 64</span><span class="sxs-lookup"><span data-stu-id="c71c2-197">Maximum number of characters for the username that is in front of the at sign (@): 64</span></span>
  - <span data-ttu-id="c71c2-198">@ 기호 뒤에 있는 도메인 이름의 최대 문자 수: 48</span><span class="sxs-lookup"><span data-stu-id="c71c2-198">Maximum number of characters for the domain name following the at sign (@): 48</span></span>
  - <span data-ttu-id="c71c2-199">유효 하지 않은 문자: \% &amp; \* +/=?</span><span class="sxs-lookup"><span data-stu-id="c71c2-199">Invalid characters: \ % &amp; \* + / = ?</span></span> <span data-ttu-id="c71c2-200">{ } | \< \> ( ) ; : , [ ] "</span><span class="sxs-lookup"><span data-stu-id="c71c2-200">{ } | \< \> ( ) ; : , [ ] "</span></span>
  - <span data-ttu-id="c71c2-201">허용 되는 문자: A – Z, a-z, 0 – 9, '</span><span class="sxs-lookup"><span data-stu-id="c71c2-201">Characters allowed: A – Z, a - z, 0 – 9, ' .</span></span> <span data-ttu-id="c71c2-202">- _ !</span><span class="sxs-lookup"><span data-stu-id="c71c2-202">- _ !</span></span> <span data-ttu-id="c71c2-203"># ^ ~</span><span class="sxs-lookup"><span data-stu-id="c71c2-203"># ^ ~</span></span>
  - <span data-ttu-id="c71c2-204">움라우트, 악센트 부호, 물결표 등의 분음 기호가 있는 문자는 사용할 수 없는 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-204">Letters with diacritical marks, such as umlauts, accents, and tildes, are invalid characters.</span></span>
  - <span data-ttu-id="c71c2-205">@ 문자는 각 **userPrincipalName** 값에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-205">The @ character is required in each **userPrincipalName** value.</span></span>
  - <span data-ttu-id="c71c2-206">@ 문자는 각 **userPrincipalName** 값의 첫 번째 문자일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-206">The @ character cannot be the first character in each **userPrincipalName** value.</span></span>
  - <span data-ttu-id="c71c2-207">사용자 이름은 마침표 (.), 앰퍼샌드 ( &amp; ), 공백 또는 @ 기호로 끝날 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-207">The username cannot end with a period (.), an ampersand (&amp;), a space, or an at sign (@).</span></span>
  - <span data-ttu-id="c71c2-208">사용자 이름에는 공백을 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-208">The username cannot contain any spaces.</span></span>
  - <span data-ttu-id="c71c2-209">라우팅 가능한 도메인을 사용 해야 합니다. 예를 들어 로컬 또는 내부 도메인은 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-209">Routable domains must be used; for example, local or internal domains cannot be used.</span></span>
  - <span data-ttu-id="c71c2-210">유니코드는 밑줄 문자로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-210">Unicode is converted to underscore characters.</span></span>
  - <span data-ttu-id="c71c2-211">**userPrincipalName** 는 디렉터리에 중복 된 값을 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-211">**userPrincipalName** cannot contain any duplicate values in the directory.</span></span>

## <a name="3-prepare-the-userprincipalname-attribute"></a><span data-ttu-id="c71c2-212">3. userPrincipalName 특성을 준비 합니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-212">3. Prepare the userPrincipalName attribute</span></span>

<span data-ttu-id="c71c2-213">Active Directory는 조직의 최종 사용자가 **sAMAccountName** 또는 **userPrincipalName** 를 사용 하 여 디렉터리에 로그인 할 수 있도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-213">Active Directory is designed to allow the end users in your organization to sign in to your directory by using either **sAMAccountName** or **userPrincipalName**.</span></span> <span data-ttu-id="c71c2-214">마찬가지로 최종 사용자는 회사 또는 학교 계정의 UPN (사용자 계정 이름)을 사용 하 여 Microsoft 365에 로그인 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-214">Similarly, end users can sign in to Microsoft 365 by using the user principal name (UPN) of their work or school account.</span></span> <span data-ttu-id="c71c2-215">디렉터리 동기화는 AD DS에 있는 것과 동일한 UPN을 사용 하 여 Azure Active Directory에 새 사용자를 만들려고 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-215">Directory synchronization attempts to create new users in Azure Active Directory by using the same UPN that's in your AD DS.</span></span> <span data-ttu-id="c71c2-216">UPN은 전자 메일 주소와 같은 형식으로 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-216">The UPN is formatted like an email address.</span></span>

<span data-ttu-id="c71c2-217">Microsoft 365에서 UPN은 전자 메일 주소를 생성 하는 데 사용 되는 기본 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-217">In Microsoft 365, the UPN is the default attribute that's used to generate the email address.</span></span> <span data-ttu-id="c71c2-218">**UserPrincipalName** (AD DS 및 Azure ad) 및 **proxyAddresses** 의 기본 전자 메일 주소를 다른 값으로 설정 하는 것이 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-218">It's easy to get **userPrincipalName** (in AD DS and in Azure AD) and the primary email address in **proxyAddresses** set to different values.</span></span> <span data-ttu-id="c71c2-219">서로 다른 값으로 설정 하면 관리자와 최종 사용자에 게 혼동이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-219">When they are set to different values, there can be confusion for administrators and end users.</span></span>

<span data-ttu-id="c71c2-220">혼동을 줄이려면 이러한 특성을 맞추는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-220">It's best to align these attributes to reduce confusion.</span></span> <span data-ttu-id="c71c2-221">AD FS (Active Directory Federation Services) 2.0에서 single sign-on 요구 사항을 충족 하려면 Azure Active Directory 및 AD DS의 Upn이 일치 하며 유효한 도메인 네임 스페이스를 사용 하 고 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-221">To meet the requirements of single sign-on with Active Directory Federation Services (AD FS) 2.0, you need to ensure that the UPNs in Azure Active Directory and your AD DS match and are using a valid domain namespace.</span></span>

## <a name="4-add-an-alternative-upn-suffix-to-ad-ds"></a><span data-ttu-id="c71c2-222">4. AD DS에 대체 UPN 접미사 추가</span><span class="sxs-lookup"><span data-stu-id="c71c2-222">4. Add an alternative UPN suffix to AD DS</span></span>

<span data-ttu-id="c71c2-223">사용자의 회사 자격 증명을 Microsoft 365 환경과 연결 하기 위해 대체 UPN 접미사를 추가 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-223">You may need to add an alternative UPN suffix to associate the user's corporate credentials with the Microsoft 365 environment.</span></span> <span data-ttu-id="c71c2-224">UPN 접미사는 UPN에서 @ 문자 오른쪽에 있는 부분입니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-224">A UPN suffix is the part of a UPN to the right of the @ character.</span></span> <span data-ttu-id="c71c2-225">Single Sign-On에 사용되는 UPN에는 문자, 숫자, 마침표, 대시 및 밑줄을 포함할 수 있으며 다른 유형의 문자는 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-225">UPNs that are used for single sign-on can contain letters, numbers, periods, dashes, and underscores, but no other types of characters.</span></span>

<span data-ttu-id="c71c2-226">Active Directory에 대체 UPN 접미사를 추가 하는 방법에 대 한 자세한 내용은 [디렉터리 동기화 준비]( https://go.microsoft.com/fwlink/p/?LinkId=525430)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c71c2-226">For more information on how to add an alternative UPN suffix to Active Directory, see [Prepare for directory synchronization]( https://go.microsoft.com/fwlink/p/?LinkId=525430).</span></span>

## <a name="5-match-the-ad-ds-upn-with-the-microsoft-365-upn"></a><span data-ttu-id="c71c2-227">5. AD DS UPN과 Microsoft 365 UPN을 일치 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-227">5. Match the AD DS UPN with the Microsoft 365 UPN</span></span>

<span data-ttu-id="c71c2-228">디렉터리 동기화를 이미 설정한 경우 사용자의 Microsoft 365 UPN이 AD DS에 정의 된 사용자의 AD DS UPN과 일치 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-228">If you've already set up directory synchronization, the user's UPN for Microsoft 365 may not match the user's AD DS UPN that's defined in your AD DS.</span></span> <span data-ttu-id="c71c2-229">도메인이 확인되기 전에 사용자에게 라이선스가 할당된 경우 이와 같은 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-229">This can occur when a user was assigned a license before the domain was verified.</span></span> <span data-ttu-id="c71c2-230">이 문제를 해결 하려면 [PowerShell을](https://go.microsoft.com/fwlink/p/?LinkId=396730) 사용 하 여 중복 UPN을 수정 하 여 MICROSOFT 365 upn이 회사 사용자 이름 및 도메인과 일치 하도록 사용자의 upn을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-230">To fix this, use [PowerShell to fix duplicate UPN](https://go.microsoft.com/fwlink/p/?LinkId=396730) to update the user's UPN to ensure that the Microsoft 365 UPN matches the corporate user name and domain.</span></span> <span data-ttu-id="c71c2-231">AD DS에서 UPN을 업데이트 하 고 Azure Active Directory id와 동기화 하 고 싶은 경우 AD DS에서 변경 작업을 수행 하기 전에 Microsoft 365에서 해당 사용자의 라이선스를 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c71c2-231">If you are updating the UPN in the AD DS and would like it to synchronize with the Azure Active Directory identity, you need to remove the user's license in Microsoft 365 prior to making the changes in AD DS.</span></span>

<span data-ttu-id="c71c2-232">또한 [디렉터리 동기화를 위해 라우팅할 수 없는 도메인 (예: 로컬 도메인)을 준비 하는 방법을](prepare-a-non-routable-domain-for-directory-synchronization.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c71c2-232">Also see [How to prepare a non-routable domain (such as .local domain) for directory synchronization](prepare-a-non-routable-domain-for-directory-synchronization.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="c71c2-233">다음 단계</span><span class="sxs-lookup"><span data-stu-id="c71c2-233">Next steps</span></span>

<span data-ttu-id="c71c2-234">위의 1 ~ 5 단계를 수행한 경우 [디렉터리 동기화 설정을](set-up-directory-synchronization.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c71c2-234">If you have done steps 1 through 5 above, see [Set up directory synchronization](set-up-directory-synchronization.md).</span></span>
