---
title: 권장 암호 정책
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- Adm_O365
- Adm_NonTOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9fa2539a-2211-41fd-85a0-bc37b9619ca4
description: 암호 공격으로부터 조직을 더 안전하게 보호하는 방법과 일반적인 암호를 금지하고 위험 기반 다단계 인증을 사용해야 하는 이유를 알아봅니다.
ms.openlocfilehash: 66a4048ac1add3a0d47f256dc29519a91ae6cb11
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926717"
---
# <a name="password-policy-recommendations"></a><span data-ttu-id="2043d-103">권장 암호 정책</span><span class="sxs-lookup"><span data-stu-id="2043d-103">Password policy recommendations</span></span>

<span data-ttu-id="2043d-104">조직의 관리자는 조직의 사용자에 대한 암호 정책을 설정할 책임이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2043d-104">As the admin of an organization, you're responsible for setting password policy for users in your organization.</span></span> <span data-ttu-id="2043d-105">암호 정책의 설정은 복잡하고 혼동될 수 있습니다. 이 문서에서는 조직을 암호 공격으로부터 더 안전하게 보호하기 위한 권장 사항을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2043d-105">Setting password policy can be complicated and confusing, and this article provides recommendations to make your organization more secure against password attacks.</span></span>
  
<span data-ttu-id="2043d-106">조직의 Microsoft 365 암호 만료 주기를 확인하려면 [Microsoft 365 암호 만료 정책 설정](../manage/set-password-expiration-policy.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2043d-106">To determine how often Microsoft 365 passwords expire in your organization, see [Set password expiration policy for Microsoft 365](../manage/set-password-expiration-policy.md).</span></span>

<span data-ttu-id="2043d-107">Microsoft 365 암호에 대한 자세한 내용은[관련 문서](#related-articles)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2043d-107">For more information about Microsoft 365 passwords, see these [related articles](#related-articles).</span></span>
  
## <a name="understanding-password-recommendations"></a><span data-ttu-id="2043d-108">암호 권장 사항 이해</span><span class="sxs-lookup"><span data-stu-id="2043d-108">Understanding password recommendations</span></span>

<span data-ttu-id="2043d-109">좋은 암호의 예는 몇 가지 광범위한 범주로 분류됩니다.</span><span class="sxs-lookup"><span data-stu-id="2043d-109">Good password practices fall into a few broad categories:</span></span>
  
- <span data-ttu-id="2043d-110">**일반적인 공격에 대한 저항** 사용자가 암호를 입력하는 위치(좋은 맬웨어 검색을 사용하는 알려지고 신뢰하는 장치, 유효성이 검사된 사이트) 및 선택할 암호(길이와 고유성)를 선택하는 것과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2043d-110">**Resisting common attacks** This involves the choice of where users enter passwords (known and trusted devices with good malware detection, validated sites), and the choice of what password to choose (length and uniqueness).</span></span>

- <span data-ttu-id="2043d-111">**성공한 해커 공격 포함** 성공적인 해커 공격 포함은 특정 서비스에 대한 노출을 제한하거나, 사용자의 암호가 도난 당한 경우 그 피해를 완전히 방지하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2043d-111">**Containing successful attacks** Containing successful hacker attacks is about limiting exposure to a specific service, or preventing that damage altogether, if a user's password gets stolen.</span></span> <span data-ttu-id="2043d-112">예를 들어, 소셜 네트워킹 자격 증명이 침해되어도 은행 계좌를 취약하게 만들지 않도록 하거나 보안이 취약한 계정에서 중요한 계정에 대한 재설정 링크를 수락하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2043d-112">For example, ensuring that a breach of your social networking credentials doesn't make your bank account vulnerable, or not letting a poorly guarded account accept reset links for an important account.</span></span>

- <span data-ttu-id="2043d-113">**인간 본성 이해** 많은 유효한 암호의 예가 자연스러운 인간 행동으로 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="2043d-113">**Understanding human nature** Many valid password practices fail in the face of natural human behaviors.</span></span> <span data-ttu-id="2043d-114">연구에 따르면 사용자에게 부과되는 거의 모든 규칙이 암호 품질을 약화시킬 수 있음을 보여주기 때문에 인간의 본성을 이해하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="2043d-114">Understanding human nature is critical because research shows that almost every rule you impose on your users will result in a weakening of password quality.</span></span> <span data-ttu-id="2043d-115">길이 요구 사항, 특수 문자 요구 사항, 암호 변경 요구 사항 모두 암호의 정규화하므로 공격자가 암호를 추측하거나 해독하기 쉽게 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2043d-115">Length requirements, special character requirements, and password change requirements all result in normalization of passwords, which makes it easier for attackers to guess or crack passwords.</span></span>

## <a name="password-guidelines-for-administrators"></a><span data-ttu-id="2043d-116">관리자를 위한 암호 관련 지침</span><span class="sxs-lookup"><span data-stu-id="2043d-116">Password guidelines for administrators</span></span>

<span data-ttu-id="2043d-117">더욱 안전한 암호 시스템의 기본 목적은 암호 다양성입니다.</span><span class="sxs-lookup"><span data-stu-id="2043d-117">The primary goal of a more secure password system is password diversity.</span></span> <span data-ttu-id="2043d-118">암호 정책에 다양하고 추측하기 어려운 비밀번호를 포함하고 싶을 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2043d-118">You want your password policy to contain lots of different and hard to guess passwords.</span></span> <span data-ttu-id="2043d-119">다음은 조직을 최대한 안전한 상태로 유지하기 위한 몇 가지 권장 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="2043d-119">Here are a few recommendations for keeping your organization as secure as possible.</span></span>
  
- <span data-ttu-id="2043d-120">최소 8자 이상 길이 요구 사항 유지(길다고 꼭 좋은 것은 아닙니다.)</span><span class="sxs-lookup"><span data-stu-id="2043d-120">Maintain an 8-character minimum length requirement (longer isn't necessarily better)</span></span>

- <span data-ttu-id="2043d-121">문자 구성 요구 사항은 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2043d-121">Don't require character composition requirements.</span></span> <span data-ttu-id="2043d-122">예: \*&amp;(^%$</span><span class="sxs-lookup"><span data-stu-id="2043d-122">For example, \*&amp;(^%$</span></span>

- <span data-ttu-id="2043d-123">사용자 계정의 주기적인 암호 재설정 필요 없음</span><span class="sxs-lookup"><span data-stu-id="2043d-123">Don't require mandatory periodic password resets for user accounts</span></span>

- <span data-ttu-id="2043d-124">가장 취약한 암호를 사용하지 않도록 일반적인 암호 금지</span><span class="sxs-lookup"><span data-stu-id="2043d-124">Ban common passwords, to keep the most vulnerable passwords out of your system</span></span>

- <span data-ttu-id="2043d-125">사용자에게 조직 암호를 회사 관련이 아닌 목적으로 재사용하지 않도록 교육합니다.</span><span class="sxs-lookup"><span data-stu-id="2043d-125">Educate your users to not re-use their organization passwords for non-work related purposes</span></span>

- <span data-ttu-id="2043d-126">[다단계 인증](../security-and-compliance/set-up-multi-factor-authentication.md) 등록 시행</span><span class="sxs-lookup"><span data-stu-id="2043d-126">Enforce registration for [multi-factor authentication](../security-and-compliance/set-up-multi-factor-authentication.md)</span></span>

- <span data-ttu-id="2043d-127">위험 기반 다단계 인증 챌린지 사용</span><span class="sxs-lookup"><span data-stu-id="2043d-127">Enable risk-based multi-factor authentication challenges</span></span>

### <a name="password-guidance-for-your-users"></a><span data-ttu-id="2043d-128">사용자를 위한 암호 지침</span><span class="sxs-lookup"><span data-stu-id="2043d-128">Password guidance for your users</span></span>

<span data-ttu-id="2043d-129">조직의 사용자를 위한 몇 가지 암호 지침입니다.</span><span class="sxs-lookup"><span data-stu-id="2043d-129">Here's some password guidance for users in your organization.</span></span> <span data-ttu-id="2043d-130">사용자가 이러한 권장 사항을 알고 있어야 하며 조직 수준에서 권장 암호 정책을 시행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2043d-130">Make sure to let your users know about these recommendations and enforce the recommended password policies at the organizational level.</span></span>
  
- <span data-ttu-id="2043d-131">다른 웹 사이트에서 사용하는 것과 같거나 비슷한 암호를 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="2043d-131">Don't use a password that is the same or similar to one you use on any other websites</span></span>

- <span data-ttu-id="2043d-132">예를 들어 **password** 같은 한 단어나 **Iloveyou** 와 같은 일반적으로 사용되는 문구를 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="2043d-132">Don't use a single word, for example, **password**, or a commonly-used phrase like **Iloveyou**</span></span>

- <span data-ttu-id="2043d-133">친구나 가족의 이름과 생일, 좋아하는 밴드, 사용하기 좋아하는 문구와 같이 자신에 대해 많이 아는 사람들도 암호를 추측하기 어렵게 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2043d-133">Make passwords hard to guess, even by those who know a lot about you, such as the names and birthdays of your friends and family, your favorite bands, and phrases you like to use</span></span>

## <a name="some-common-approaches-and-their-negative-impacts"></a><span data-ttu-id="2043d-134">몇 가지 일반적인 접근 방법과 부정적인 영향</span><span class="sxs-lookup"><span data-stu-id="2043d-134">Some common approaches and their negative impacts</span></span>

<span data-ttu-id="2043d-135">다음은 가장 자주 사용하는 암호 관리 사례이지만 연구는 이 예의 부정적인 영향에 대해 경고합니다.</span><span class="sxs-lookup"><span data-stu-id="2043d-135">These are some of the most commonly used password management practices, but research warns us about the negative impacts of them.</span></span>
  
### <a name="password-expiration-requirements-for-users"></a><span data-ttu-id="2043d-136">사용자의 암호 만료 요구 사항</span><span class="sxs-lookup"><span data-stu-id="2043d-136">Password expiration requirements for users</span></span>

<span data-ttu-id="2043d-137">암호 만료 요구 사항은 사용자가 서로 밀접하게 관련이 있는 순차적인 단어 및 숫자로 구성된 예측 가능한 암호를 선택하도록 하기 때문에 득보다 해를 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2043d-137">Password expiration requirements do more harm than good, because these requirements make users select predictable passwords, composed of sequential words and numbers which are closely related to each other.</span></span> <span data-ttu-id="2043d-138">이 경우 이전 암호를 기준으로 다음 암호를 예측할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2043d-138">In these cases, the next password can be predicted based on the previous password.</span></span> <span data-ttu-id="2043d-139">사이버 범죄자는 자격 증명이 손상되는 즉시 거의 항상 자격 증명을 사용하므로 암호 만료 요구 사항에는 방지 이점이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2043d-139">Password expiration requirements offer no containment benefits because cyber criminals almost always use credentials as soon as they compromise them.</span></span> <span data-ttu-id="2043d-140">자세한 내용은 [강제 비밀번호 변경을 다시 생각할 시간](https://go.microsoft.com/fwlink/p/?linkid=861018)을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="2043d-140">Check out [Time to rethink mandatory password changes](https://go.microsoft.com/fwlink/p/?linkid=861018) for more info.</span></span>
  
### <a name="requiring-long-passwords"></a><span data-ttu-id="2043d-141">긴 암호 요구</span><span class="sxs-lookup"><span data-stu-id="2043d-141">Requiring long passwords</span></span>

<span data-ttu-id="2043d-142">암호 길이 요구 사항(10자 이상)에는 예측 가능하고 바람직하지 않은 사용자 동작이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2043d-142">Password length requirements (greater than about 10 characters) can result in user behavior that is predictable and undesirable.</span></span> <span data-ttu-id="2043d-143">예를 들어, 16자 암호를 입력해야 하는 사용자가 문자 길이 요구 사항을 충족하지만 추측하기 어렵지 않은 **fourfourfourfour** 또는 **passwordpassword** 와 같은 반복되는 패턴을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2043d-143">For example, users who are required to have a 16-character password may choose repeating patterns like **fourfourfourfour** or **passwordpassword** that meet the character length requirement but aren't hard to guess.</span></span> <span data-ttu-id="2043d-144">또한 길이 요구 사항으로 사용자는 암호를 적어 두거나 재사용하거나 문서에 암호화되지 않은 상태로 저장하는 등의 안전하지 않은 방법을 채택할 확률이 높아집니다.</span><span class="sxs-lookup"><span data-stu-id="2043d-144">Additionally, length requirements increase the chances that users will adopt other insecure practices, such as writing their passwords down, re-using them, or storing them unencrypted in their documents.</span></span> <span data-ttu-id="2043d-145">사용자가 고유한 암호를 생각하도록 유도하려면 최소 8자 길이의 적정 요구 사항을 유지하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2043d-145">To encourage users to think about a unique password, we recommend keeping a reasonable 8-character minimum length requirement.</span></span>
  
### <a name="requiring-the-use-of-multiple-character-sets"></a><span data-ttu-id="2043d-146">여러 문자 집합을 사용해야 하는 경우</span><span class="sxs-lookup"><span data-stu-id="2043d-146">Requiring the use of multiple character sets</span></span>

<span data-ttu-id="2043d-147">암호 복잡성 요구 사항은 주요 공간을 줄이고 사용자가 득보다 해가 될 수 있는 예측 가능한 방식으로 행동하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2043d-147">Password complexity requirements reduce key space and cause users to act in predictable ways, doing more harm than good.</span></span> <span data-ttu-id="2043d-148">대부분의 시스템에서는 암호 복잡성 요구 사항을 어느 정도 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="2043d-148">Most systems enforce some level of password complexity requirements.</span></span> <span data-ttu-id="2043d-149">예를 들어, 암호에 다음 세 가지 범주의 문자가 모두 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2043d-149">For example, passwords need characters from all three of the following categories:</span></span>
  
- <span data-ttu-id="2043d-150">대문자</span><span class="sxs-lookup"><span data-stu-id="2043d-150">uppercase characters</span></span>

- <span data-ttu-id="2043d-151">소문자</span><span class="sxs-lookup"><span data-stu-id="2043d-151">lowercase characters</span></span>

- <span data-ttu-id="2043d-152">영숫자가 아닌 문자</span><span class="sxs-lookup"><span data-stu-id="2043d-152">non-alphanumeric characters</span></span>

<span data-ttu-id="2043d-153">대부분의 사용자는 첫 번째 위치에는 대문자, 마지막에는 기호, 마지막에서 두 번째 위치에는 숫자를 사용하는 등의 유사한 패턴을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2043d-153">Most people use similar patterns, for example, a capital letter in the first position, a symbol in the last, and a number in the last 2.</span></span> <span data-ttu-id="2043d-154">사이버 범죄자는 이 사실을 알고 있으므로 "s"에 대한 "$", "a"에 대한 "@", "l"에 대한 "1"과 같은 가장 일반적인 대체를 사용하여 사전 공격을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2043d-154">Cyber criminals know this, so they run their dictionary attacks using the most common substitutions, "$" for "s", "@" for "a," "1" for "l".</span></span> <span data-ttu-id="2043d-155">사용자가 대/소문자, 숫자, 특수 문자를 원하는 대로 조합하여 선택하도록 하면 부정적인 영항을 끼칩니다.</span><span class="sxs-lookup"><span data-stu-id="2043d-155">Forcing your users to choose a combination of upper, lower, digits, special characters has a negative effect.</span></span> <span data-ttu-id="2043d-156">일부 복잡한 요구 사항은 사용자가 안전하고 기억하기 쉬운 암호를 사용하지 못하게 하고 덜 안전하고 덜 기억하기 쉬운 암호를 제공하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2043d-156">Some complexity requirements even prevent users from using secure and memorable passwords, and force them into coming up with less secure and less memorable passwords.</span></span>
  
## <a name="successful-patterns"></a><span data-ttu-id="2043d-157">성공한 패턴</span><span class="sxs-lookup"><span data-stu-id="2043d-157">Successful Patterns</span></span>

<span data-ttu-id="2043d-158">이와 대조적으로, 다음은 암호 다양성을 위해 권장되는 몇 가지 권장 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="2043d-158">In contrast, here are some recommendations in encouraging password diversity.</span></span>
  
### <a name="ban-common-passwords"></a><span data-ttu-id="2043d-159">일반적인 암호 금지</span><span class="sxs-lookup"><span data-stu-id="2043d-159">Ban common passwords</span></span>

<span data-ttu-id="2043d-160">암호를 만들 때 사용자에게 제공해야 하는 가장 중요한 암호 요구 사항은 조직의 무작위 암호 공격에 대한 취약성을 줄이기 위해 일반적인 암호 사용을 금지하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2043d-160">The most important password requirement you should put on your users when creating passwords is to ban the use of common passwords to reduce your organization's susceptibility to brute force password attacks.</span></span> <span data-ttu-id="2043d-161">일반적인 사용자 암호에는 **abcdefg**, **password**, **monkey** 가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2043d-161">Common user passwords include, **abcdefg**, **password**, **monkey**.</span></span>
  
### <a name="educate-users-to-not-re-use-organization-passwords-anywhere-else"></a><span data-ttu-id="2043d-162">다른 곳에서 조직 암호를 다시 사용하지 않도록 사용자를 교육합니다.</span><span class="sxs-lookup"><span data-stu-id="2043d-162">Educate users to not re-use organization passwords anywhere else</span></span>

<span data-ttu-id="2043d-163">조직의 사용자에게 전달한 가장 중요한 메시지 중 하나는 조직 암호를 다른 위치에서 다시 사용하지 않는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2043d-163">One of the most important messages to get across to users in your organization is to not re-use their organization password anywhere else.</span></span> <span data-ttu-id="2043d-164">외부 웹 사이트에서 조직 암호를 사용하면 사이버 범죄자가 암호를 해킹할 가능성이 크게 높아집니다.</span><span class="sxs-lookup"><span data-stu-id="2043d-164">The use of organization passwords in external websites greatly increases the likelihood that cyber criminals will compromise these passwords.</span></span>
  
### <a name="enforce-multi-factor-authentication-registration"></a><span data-ttu-id="2043d-165">다단계 인증 등록 시행</span><span class="sxs-lookup"><span data-stu-id="2043d-165">Enforce Multi-Factor Authentication registration</span></span>

<span data-ttu-id="2043d-166">사용자가 대체 전자 메일 주소, 전화 번호 또는 푸시 알림에 등록된 장치 등의 연락처 및 보안 정보를 업데이트하여 보안 문제에 대응하고 보안 이벤트 알림을 받을 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2043d-166">Make sure your users update contact and security information, like an alternate email address, phone number, or a device registered for push notifications, so they can respond to security challenges and be notified of security events.</span></span> <span data-ttu-id="2043d-167">업데이트된 연락처 및 보안 정보는 사용자가 암호를 잊어버린 경우 또는 다른 사용자가 자신의 계정을 사용하려고 시도하는 경우 신원을 확인하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2043d-167">Updated contact and security information helps users verify their identity if they ever forget their password, or if someone else tries to take over their account.</span></span> <span data-ttu-id="2043d-168">로그인 시도나 암호 변경 같은 보안 이벤트의 경우에도 대역 외 알림 채널을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2043d-168">It also provides an out of band notification channel in the case of security events such as login attempts or changed passwords.</span></span> 
  
<span data-ttu-id="2043d-169">자세한 내용은 [다단계 인증을 설정](../security-and-compliance/set-up-multi-factor-authentication.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2043d-169">To learn more, see [Set up multi-factor authentication](../security-and-compliance/set-up-multi-factor-authentication.md).</span></span>
  
### <a name="enable-risk-based-multi-factor-authentication"></a><span data-ttu-id="2043d-170">위험 기반 다단계 인증 사용</span><span class="sxs-lookup"><span data-stu-id="2043d-170">Enable risk-based multi-factor authentication</span></span>

<span data-ttu-id="2043d-171">위험 기반 다단계 인증을 사용하면 시스템에서 의심스러운 작업이 감지되면 사용자가 합법적 계정 소유자인지 확인하도록 요구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2043d-171">Risk-based multi-factor authentication ensures that when our system detects suspicious activity, it can challenge the user to ensure that they are the legitimate account owner.</span></span> 
  
## <a name="want-to-know-more-recommended-reading"></a><span data-ttu-id="2043d-172">추가 정보</span><span class="sxs-lookup"><span data-stu-id="2043d-172">Want to know more?</span></span> <span data-ttu-id="2043d-173">추천 읽기</span><span class="sxs-lookup"><span data-stu-id="2043d-173">Recommended reading</span></span>

- [<span data-ttu-id="2043d-174">강력한 웹 암호는 어떤 작업을 수행하나요?</span><span class="sxs-lookup"><span data-stu-id="2043d-174">Do Strong Web Passwords Accomplish Anything?</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861008)

- [<span data-ttu-id="2043d-175">암호 포트폴리오 및 Finite-Effort 사용자</span><span class="sxs-lookup"><span data-stu-id="2043d-175">Password Portfolios and the Finite-Effort User</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861014)

- [<span data-ttu-id="2043d-176">사용자의 마음을 읽어 취약한 암호 방지</span><span class="sxs-lookup"><span data-stu-id="2043d-176">Preventing Weak Passwords by Reading Users' Minds</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861015)

- [<span data-ttu-id="2043d-177">보안 암호 선택</span><span class="sxs-lookup"><span data-stu-id="2043d-177">Choosing Secure Passwords</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861016)

- [<span data-ttu-id="2043d-178">필수 암호 변경 내용을 다시 생각하는 시간</span><span class="sxs-lookup"><span data-stu-id="2043d-178">Time to rethink mandatory password changes</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861018)

- [<span data-ttu-id="2043d-179">2015년 최악의 비밀번호</span><span class="sxs-lookup"><span data-stu-id="2043d-179">Worst Passwords of 2015</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861020)

## <a name="related-articles"></a><span data-ttu-id="2043d-180">관련 문서</span><span class="sxs-lookup"><span data-stu-id="2043d-180">Related articles</span></span>

[<span data-ttu-id="2043d-181">암호 초기화</span><span class="sxs-lookup"><span data-stu-id="2043d-181">Reset passwords</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/reset-passwords)

[<span data-ttu-id="2043d-182">개별 사용자 암호가 만료되지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="2043d-182">Set an individual user's password to never expire</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/set-password-to-never-expire)

[<span data-ttu-id="2043d-183">사용자가 암호를 직접 재설정할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="2043d-183">Let users reset their own passwords</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/let-users-reset-passwords)

[<span data-ttu-id="2043d-184">사용자 암호 다시 보내기 - 관리자 도움말</span><span class="sxs-lookup"><span data-stu-id="2043d-184">Resend a user's password - Admin Help</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/resend-user-password)
