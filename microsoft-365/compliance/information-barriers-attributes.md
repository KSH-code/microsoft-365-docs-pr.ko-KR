---
title: 정보 장벽 정책의 속성
description: 이 문서는 정보 장벽 세그먼트를 정의하는 데 사용할 수 있는 Azure Active Directory 사용자 계정 특성에 대한 참조입니다.
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5e7815dbcfc6129685322a250351276476f8a9e3
ms.sourcegitcommit: c10eb675da725830e9776d2a0566ba3622eb361c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/26/2021
ms.locfileid: "49980052"
---
# <a name="attributes-for-information-barrier-policies"></a><span data-ttu-id="099a2-103">정보 장벽 정책의 속성</span><span class="sxs-lookup"><span data-stu-id="099a2-103">Attributes for information barrier policies</span></span>

<span data-ttu-id="099a2-104">Azure Active Directory의 특정 특성을 사용하여 사용자를 분할할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="099a2-104">Certain attributes in Azure Active Directory can be used to segment users.</span></span> <span data-ttu-id="099a2-105">세그먼트가 정의되고 나면 이러한 세그먼트를 정보 장벽 정책에 대한 필터로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="099a2-105">Once segments are defined, those segments can be used as filters for information barrier policies.</span></span> <span data-ttu-id="099a2-106">예를 들어 **Department를** 사용하여 조직 내의 부서별로 사용자 세그먼트를 정의할 수 있습니다(동시에 두 부서에 대해 한 직원이 일하지 않을 경우).</span><span class="sxs-lookup"><span data-stu-id="099a2-106">For example, you might use **Department** to define segments of users by department within your organization (assuming no single employee works for two departments at the same time).</span></span>

<span data-ttu-id="099a2-107">이 문서에서는 정보 장벽이 있는 특성을 사용하는 방법을 설명하고 사용할 수 있는 특성 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="099a2-107">This article describes how to use attributes with information barriers, and it provides a list of attributes that can be used.</span></span> <span data-ttu-id="099a2-108">정보 장벽에 대한 자세한 내용은 다음 리소스를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="099a2-108">To learn more about information barriers, see the following resources:</span></span>

- [<span data-ttu-id="099a2-109">정보 장벽</span><span class="sxs-lookup"><span data-stu-id="099a2-109">Information barriers</span></span>](information-barriers.md)
- [<span data-ttu-id="099a2-110">Microsoft Teams의 정보 장벽에 대한 정책 정의</span><span class="sxs-lookup"><span data-stu-id="099a2-110">Define policies for information barriers in Microsoft Teams</span></span>](information-barriers-policies.md)
- [<span data-ttu-id="099a2-111">정보 장벽 정책 편집(또는 제거)</span><span class="sxs-lookup"><span data-stu-id="099a2-111">Edit (or remove) information barrier policies</span></span>](information-barriers-edit-segments-policies.md)

## <a name="how-to-use-attributes-in-information-barrier-policies"></a><span data-ttu-id="099a2-112">정보 장벽 정책에서 특성을 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="099a2-112">How to use attributes in information barrier policies</span></span>

<span data-ttu-id="099a2-113">이 문서에 나열된 특성을 사용하여 사용자 세그먼트를 정의하거나 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="099a2-113">The attributes listed in this article can be used to define or edit segments of users.</span></span> <span data-ttu-id="099a2-114">정의된 세그먼트는 정보 장벽 정책에서 매개 *변수(UserGroupFilter* [값)로 작용합니다.](information-barriers-policies.md)</span><span class="sxs-lookup"><span data-stu-id="099a2-114">Your defined segments serve as parameters (called *UserGroupFilter* values) in [information barrier policies](information-barriers-policies.md).</span></span>

1. <span data-ttu-id="099a2-115">세그먼트를 정의하는 데 사용할 특성을 결정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="099a2-115">Determine which attribute you want to use to define segments.</span></span> <span data-ttu-id="099a2-116">(이 [문서의 참조](#reference) 섹션을 참조하세요.)</span><span class="sxs-lookup"><span data-stu-id="099a2-116">(See the [Reference](#reference) section in this article.)</span></span>

2. <span data-ttu-id="099a2-117">1단계에서 선택한 특성에 대해 사용자 계정에 값이 채워진지 확인</span><span class="sxs-lookup"><span data-stu-id="099a2-117">Make sure the user accounts have values filled in for the attribute(s) you selected in Step 1.</span></span> <span data-ttu-id="099a2-118">사용자 계정 세부 정보를 보고 필요한 경우 특성 값을 포함하도록 사용자 계정을 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="099a2-118">View user account details, and if necessary, edit user accounts to include attribute values.</span></span> 

    - <span data-ttu-id="099a2-119">여러 계정을 편집하거나 PowerShell을 사용하여 단일 계정을 편집하려면 [Office 365 PowerShell을](https://docs.microsoft.com/microsoft-365/enterprise/configure-user-account-properties-with-microsoft-365-powershell)사용하여 사용자 계정 속성 구성을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="099a2-119">To edit multiple accounts (or use PowerShell to edit a single account), see [Configure user account properties with Office 365 PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/configure-user-account-properties-with-microsoft-365-powershell).</span></span>

    - <span data-ttu-id="099a2-120">단일 계정을 편집하려면 Azure Active Directory를 사용하여 사용자의 프로필 정보 추가 또는 [업데이트를 참조하세요.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)</span><span class="sxs-lookup"><span data-stu-id="099a2-120">To edit a single account, see [Add or update a user's profile information using Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span></span>

3. <span data-ttu-id="099a2-121">[다음 예와 유사하게 PowerShell을](information-barriers-policies.md#define-segments-using-powershell)사용하여 세그먼트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="099a2-121">[Define segments using PowerShell](information-barriers-policies.md#define-segments-using-powershell), similar to the following examples:</span></span>

    |<span data-ttu-id="099a2-122">**예**</span><span class="sxs-lookup"><span data-stu-id="099a2-122">**Example**</span></span>|<span data-ttu-id="099a2-123">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="099a2-123">**Cmdlet**</span></span>|
    |:----------|:---------|
    | <span data-ttu-id="099a2-124">Department 특성을 사용하여 Segment1이라는 세그먼트 정의</span><span class="sxs-lookup"><span data-stu-id="099a2-124">Define a segment called Segment1 using the Department attribute</span></span> | `New-OrganizationSegment -Name "Segment1" -UserGroupFilter "Department -eq 'Department1'"` |
    | <span data-ttu-id="099a2-125">MemberOf 특성을 사용하여 SegmentA라는 세그먼트를 정의합니다(이 특성에 "BlueGroup"과 같은 그룹 이름이 포함되어 있는 경우)</span><span class="sxs-lookup"><span data-stu-id="099a2-125">Define a segment called SegmentA using the MemberOf attribute (suppose this attribute contains group names, such as "BlueGroup")</span></span> | `New-OrganizationSegment -Name "SegmentA" -UserGroupFilter "MemberOf -eq 'BlueGroup'"` |
    | <span data-ttu-id="099a2-126">ExtensionAttribute1을 사용하여 DayTraders라는 세그먼트를 정의합니다(이 특성에 "DayTrader"와 같은 직위가 포함되어 있는 경우)</span><span class="sxs-lookup"><span data-stu-id="099a2-126">Define a segment called DayTraders using ExtensionAttribute1 (suppose this attribute contains job titles, such as "DayTrader")</span></span> | `New-OrganizationSegment -Name "DayTraders" -UserGroupFilter "ExtensionAttribute1 -eq 'DayTrader'"` |

    > [!TIP]
    > <span data-ttu-id="099a2-127">세그먼트를 정의할 때 모든 세그먼트에 대해 동일한 특성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="099a2-127">When you define segments, use the same attribute for all your segments.</span></span> <span data-ttu-id="099a2-128">예를 들어 Department를 사용하여 일부 세그먼트를 정의하는 *경우 Department를* 사용하여 모든 세그먼트를 *정의합니다.*</span><span class="sxs-lookup"><span data-stu-id="099a2-128">For example, if you define some segments using *Department*, define all of the segments using *Department*.</span></span> <span data-ttu-id="099a2-129">Department를 사용하여 일부 세그먼트를 정의하고 MemberOf를 사용하는 세그먼트는 *정의하지 않습니다.* </span><span class="sxs-lookup"><span data-stu-id="099a2-129">Don't define some segments using *Department* and others using *MemberOf*.</span></span> <span data-ttu-id="099a2-130">세그먼트가 겹치지 않는지 확인 각 사용자를 정확히 하나의 세그먼트에 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="099a2-130">Make sure your segments do not overlap; each user should be assigned to exactly one segment.</span></span>

## <a name="reference"></a><span data-ttu-id="099a2-131">참조</span><span class="sxs-lookup"><span data-stu-id="099a2-131">Reference</span></span>

<span data-ttu-id="099a2-132">다음 표에는 정보 장벽에 사용할 수 있는 특성이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="099a2-132">The following table lists the attributes that you can use with information barriers.</span></span>

|<span data-ttu-id="099a2-133">**Azure Active Directory 속성 <br/> 이름(LDAP 표시 이름)**</span><span class="sxs-lookup"><span data-stu-id="099a2-133">**Azure Active Directory property name<br/>(LDAP display name)**</span></span>|<span data-ttu-id="099a2-134">**Exchange 속성 이름**</span><span class="sxs-lookup"><span data-stu-id="099a2-134">**Exchange property name**</span></span>|
|:---------------------------------------------------------------|:-------------------------|
| <span data-ttu-id="099a2-135">Co</span><span class="sxs-lookup"><span data-stu-id="099a2-135">Co</span></span> | <span data-ttu-id="099a2-136">Co</span><span class="sxs-lookup"><span data-stu-id="099a2-136">Co</span></span> |
| <span data-ttu-id="099a2-137">Company</span><span class="sxs-lookup"><span data-stu-id="099a2-137">Company</span></span> | <span data-ttu-id="099a2-138">Company</span><span class="sxs-lookup"><span data-stu-id="099a2-138">Company</span></span> |
| <span data-ttu-id="099a2-139">부서</span><span class="sxs-lookup"><span data-stu-id="099a2-139">Department</span></span> | <span data-ttu-id="099a2-140">부서</span><span class="sxs-lookup"><span data-stu-id="099a2-140">Department</span></span> |
| <span data-ttu-id="099a2-141">ExtensionAttribute1</span><span class="sxs-lookup"><span data-stu-id="099a2-141">ExtensionAttribute1</span></span> | <span data-ttu-id="099a2-142">CustomAttribute1</span><span class="sxs-lookup"><span data-stu-id="099a2-142">CustomAttribute1</span></span> |
| <span data-ttu-id="099a2-143">ExtensionAttribute2</span><span class="sxs-lookup"><span data-stu-id="099a2-143">ExtensionAttribute2</span></span> | <span data-ttu-id="099a2-144">CustomAttribute2</span><span class="sxs-lookup"><span data-stu-id="099a2-144">CustomAttribute2</span></span> |
| <span data-ttu-id="099a2-145">ExtensionAttribute3</span><span class="sxs-lookup"><span data-stu-id="099a2-145">ExtensionAttribute3</span></span> | <span data-ttu-id="099a2-146">CustomAttribute3</span><span class="sxs-lookup"><span data-stu-id="099a2-146">CustomAttribute3</span></span> |
| <span data-ttu-id="099a2-147">ExtensionAttribute4</span><span class="sxs-lookup"><span data-stu-id="099a2-147">ExtensionAttribute4</span></span> | <span data-ttu-id="099a2-148">CustomAttribute4</span><span class="sxs-lookup"><span data-stu-id="099a2-148">CustomAttribute4</span></span> |
| <span data-ttu-id="099a2-149">ExtensionAttribute5</span><span class="sxs-lookup"><span data-stu-id="099a2-149">ExtensionAttribute5</span></span> | <span data-ttu-id="099a2-150">CustomAttribute5</span><span class="sxs-lookup"><span data-stu-id="099a2-150">CustomAttribute5</span></span> |
| <span data-ttu-id="099a2-151">ExtensionAttribute6</span><span class="sxs-lookup"><span data-stu-id="099a2-151">ExtensionAttribute6</span></span> | <span data-ttu-id="099a2-152">CustomAttribute6</span><span class="sxs-lookup"><span data-stu-id="099a2-152">CustomAttribute6</span></span> |
| <span data-ttu-id="099a2-153">ExtensionAttribute7</span><span class="sxs-lookup"><span data-stu-id="099a2-153">ExtensionAttribute7</span></span> | <span data-ttu-id="099a2-154">CustomAttribute7</span><span class="sxs-lookup"><span data-stu-id="099a2-154">CustomAttribute7</span></span> |
| <span data-ttu-id="099a2-155">ExtensionAttribute8</span><span class="sxs-lookup"><span data-stu-id="099a2-155">ExtensionAttribute8</span></span> | <span data-ttu-id="099a2-156">CustomAttribute8</span><span class="sxs-lookup"><span data-stu-id="099a2-156">CustomAttribute8</span></span> |
| <span data-ttu-id="099a2-157">ExtensionAttribute9</span><span class="sxs-lookup"><span data-stu-id="099a2-157">ExtensionAttribute9</span></span> | <span data-ttu-id="099a2-158">CustomAttribute9</span><span class="sxs-lookup"><span data-stu-id="099a2-158">CustomAttribute9</span></span> |
| <span data-ttu-id="099a2-159">ExtensionAttribute10</span><span class="sxs-lookup"><span data-stu-id="099a2-159">ExtensionAttribute10</span></span> | <span data-ttu-id="099a2-160">CustomAttribute10</span><span class="sxs-lookup"><span data-stu-id="099a2-160">CustomAttribute10</span></span> |
| <span data-ttu-id="099a2-161">ExtensionAttribute11</span><span class="sxs-lookup"><span data-stu-id="099a2-161">ExtensionAttribute11</span></span> | <span data-ttu-id="099a2-162">CustomAttribute11</span><span class="sxs-lookup"><span data-stu-id="099a2-162">CustomAttribute11</span></span> |
| <span data-ttu-id="099a2-163">ExtensionAttribute12</span><span class="sxs-lookup"><span data-stu-id="099a2-163">ExtensionAttribute12</span></span> | <span data-ttu-id="099a2-164">CustomAttribute12</span><span class="sxs-lookup"><span data-stu-id="099a2-164">CustomAttribute12</span></span> |
| <span data-ttu-id="099a2-165">ExtensionAttribute13</span><span class="sxs-lookup"><span data-stu-id="099a2-165">ExtensionAttribute13</span></span> | <span data-ttu-id="099a2-166">CustomAttribute13</span><span class="sxs-lookup"><span data-stu-id="099a2-166">CustomAttribute13</span></span> |
| <span data-ttu-id="099a2-167">ExtensionAttribute14</span><span class="sxs-lookup"><span data-stu-id="099a2-167">ExtensionAttribute14</span></span> | <span data-ttu-id="099a2-168">CustomAttribute14</span><span class="sxs-lookup"><span data-stu-id="099a2-168">CustomAttribute14</span></span> |
| <span data-ttu-id="099a2-169">ExtensionAttribute15</span><span class="sxs-lookup"><span data-stu-id="099a2-169">ExtensionAttribute15</span></span> | <span data-ttu-id="099a2-170">CustomAttribute15</span><span class="sxs-lookup"><span data-stu-id="099a2-170">CustomAttribute15</span></span> |
| <span data-ttu-id="099a2-171">MSExchExtensionCustomAttribute1</span><span class="sxs-lookup"><span data-stu-id="099a2-171">MSExchExtensionCustomAttribute1</span></span> | <span data-ttu-id="099a2-172">ExtensionCustomAttribute1</span><span class="sxs-lookup"><span data-stu-id="099a2-172">ExtensionCustomAttribute1</span></span> |
| <span data-ttu-id="099a2-173">MSExchExtensionCustomAttribute2</span><span class="sxs-lookup"><span data-stu-id="099a2-173">MSExchExtensionCustomAttribute2</span></span> | <span data-ttu-id="099a2-174">ExtensionCustomAttribute2</span><span class="sxs-lookup"><span data-stu-id="099a2-174">ExtensionCustomAttribute2</span></span> |
| <span data-ttu-id="099a2-175">MSExchExtensionCustomAttribute3</span><span class="sxs-lookup"><span data-stu-id="099a2-175">MSExchExtensionCustomAttribute3</span></span> | <span data-ttu-id="099a2-176">ExtensionCustomAttribute3</span><span class="sxs-lookup"><span data-stu-id="099a2-176">ExtensionCustomAttribute3</span></span> |
| <span data-ttu-id="099a2-177">MSExchExtensionCustomAttribute4</span><span class="sxs-lookup"><span data-stu-id="099a2-177">MSExchExtensionCustomAttribute4</span></span> | <span data-ttu-id="099a2-178">ExtensionCustomAttribute4</span><span class="sxs-lookup"><span data-stu-id="099a2-178">ExtensionCustomAttribute4</span></span> |
| <span data-ttu-id="099a2-179">MSExchExtensionCustomAttribute5</span><span class="sxs-lookup"><span data-stu-id="099a2-179">MSExchExtensionCustomAttribute5</span></span> | <span data-ttu-id="099a2-180">ExtensionCustomAttribute5</span><span class="sxs-lookup"><span data-stu-id="099a2-180">ExtensionCustomAttribute5</span></span> |
| <span data-ttu-id="099a2-181">MailNickname</span><span class="sxs-lookup"><span data-stu-id="099a2-181">MailNickname</span></span> | <span data-ttu-id="099a2-182">별칭</span><span class="sxs-lookup"><span data-stu-id="099a2-182">Alias</span></span> |
| <span data-ttu-id="099a2-183">PhysicalDeliveryOfficeName</span><span class="sxs-lookup"><span data-stu-id="099a2-183">PhysicalDeliveryOfficeName</span></span> | <span data-ttu-id="099a2-184">사무실</span><span class="sxs-lookup"><span data-stu-id="099a2-184">Office</span></span> |
| <span data-ttu-id="099a2-185">PostalCode</span><span class="sxs-lookup"><span data-stu-id="099a2-185">PostalCode</span></span> | <span data-ttu-id="099a2-186">PostalCode</span><span class="sxs-lookup"><span data-stu-id="099a2-186">PostalCode</span></span> |
| <span data-ttu-id="099a2-187">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="099a2-187">ProxyAddresses</span></span> | <span data-ttu-id="099a2-188">EmailAddresses</span><span class="sxs-lookup"><span data-stu-id="099a2-188">EmailAddresses</span></span> |
| <span data-ttu-id="099a2-189">StreetAddress</span><span class="sxs-lookup"><span data-stu-id="099a2-189">StreetAddress</span></span> | <span data-ttu-id="099a2-190">StreetAddress</span><span class="sxs-lookup"><span data-stu-id="099a2-190">StreetAddress</span></span> |
| <span data-ttu-id="099a2-191">TargetAddress</span><span class="sxs-lookup"><span data-stu-id="099a2-191">TargetAddress</span></span> | <span data-ttu-id="099a2-192">ExternalEmailAddress</span><span class="sxs-lookup"><span data-stu-id="099a2-192">ExternalEmailAddress</span></span> |
| <span data-ttu-id="099a2-193">UsageLocation</span><span class="sxs-lookup"><span data-stu-id="099a2-193">UsageLocation</span></span> | <span data-ttu-id="099a2-194">UsageLocation</span><span class="sxs-lookup"><span data-stu-id="099a2-194">UsageLocation</span></span> |
| <span data-ttu-id="099a2-195">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="099a2-195">UserPrincipalName</span></span> | <span data-ttu-id="099a2-196">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="099a2-196">UserPrincipalName</span></span> |
| <span data-ttu-id="099a2-197">메일</span><span class="sxs-lookup"><span data-stu-id="099a2-197">Mail</span></span> | <span data-ttu-id="099a2-198">WindowsEmailAddress</span><span class="sxs-lookup"><span data-stu-id="099a2-198">WindowsEmailAddress</span></span> |
| <span data-ttu-id="099a2-199">설명</span><span class="sxs-lookup"><span data-stu-id="099a2-199">Description</span></span> | <span data-ttu-id="099a2-200">설명</span><span class="sxs-lookup"><span data-stu-id="099a2-200">Description</span></span> |
| <span data-ttu-id="099a2-201">MemberOf</span><span class="sxs-lookup"><span data-stu-id="099a2-201">MemberOf</span></span> | <span data-ttu-id="099a2-202">MemberOfGroup</span><span class="sxs-lookup"><span data-stu-id="099a2-202">MemberOfGroup</span></span> |

## <a name="resources"></a><span data-ttu-id="099a2-203">리소스</span><span class="sxs-lookup"><span data-stu-id="099a2-203">Resources</span></span>

- [<span data-ttu-id="099a2-204">Microsoft Teams의 정보 장벽에 대한 정책 정의</span><span class="sxs-lookup"><span data-stu-id="099a2-204">Define policies for information barriers in Microsoft Teams</span></span>](information-barriers-policies.md)
- [<span data-ttu-id="099a2-205">정보 장벽 문제 해결</span><span class="sxs-lookup"><span data-stu-id="099a2-205">Troubleshooting information barriers</span></span>](information-barriers-troubleshooting.md)
- [<span data-ttu-id="099a2-206">정보 장벽</span><span class="sxs-lookup"><span data-stu-id="099a2-206">Information barriers</span></span>](information-barriers.md)
