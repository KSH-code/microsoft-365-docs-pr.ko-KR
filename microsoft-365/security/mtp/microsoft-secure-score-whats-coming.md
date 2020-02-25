---
title: Microsoft 보안 점수가 어떻게 제공 됩니까?
description: Microsoft 365 보안 센터의 Microsoft 보안 점수, 세부 정보를 계산 하는 방법 및 보안 관리자가 예상할 수 있는 사항에 대해 설명 합니다.
keywords: 보안, 맬웨어, Microsoft 365, M365, 보안 점수, 보안 센터, 개선 작업
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 55c7cb34c5484eaf8f6693be0ce439e33a82550f
ms.sourcegitcommit: 59b006f8e82d1772cae2029f278a59ae8a106736
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/25/2020
ms.locfileid: "42266976"
---
# <a name="whats-coming-in-microsoft-secure-score"></a><span data-ttu-id="8b81b-104">Microsoft 보안 점수가 어떻게 제공 됩니까?</span><span class="sxs-lookup"><span data-stu-id="8b81b-104">What's coming in Microsoft Secure Score?</span></span>

<span data-ttu-id="8b81b-105">Microsoft의 보안 점수를 보안 환경을 보다 효율적으로 대표 하 고 유용성을 향상 시키기 위해 곧 몇 가지 사항을 변경 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b81b-105">To make Microsoft Secure Score a better representative of your security posture and improve usability, we are making some changes in the near future.</span></span> <span data-ttu-id="8b81b-106">점수와 가능한 최대 점수가 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b81b-106">Your score and the maximum possible score will change.</span></span> <span data-ttu-id="8b81b-107">그러나 보안 환경을 변경 하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="8b81b-107">However, this does not imply a change in your security posture.</span></span>

<span data-ttu-id="8b81b-108">최근 변경 내용에 대 한 자세한 내용은 [Microsoft 보안 점수의 새로운 기능](microsoft-secure-score.md#whats-new) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8b81b-108">To learn about recent changes, see [What's new in Microsoft Secure Score?](microsoft-secure-score.md#whats-new)</span></span>

## <a name="march-2nd-2020"></a><span data-ttu-id="8b81b-109">3 월 2 일 2020</span><span class="sxs-lookup"><span data-stu-id="8b81b-109">March 2nd 2020</span></span>

### <a name="removing-improvement-actions-from-intune"></a><span data-ttu-id="8b81b-110">Intune에서 개선 작업 제거</span><span class="sxs-lookup"><span data-stu-id="8b81b-110">Removing improvement actions from Intune</span></span>

<span data-ttu-id="8b81b-111">Intune에서 제공 하는 Microsoft 보안 점수 향상 작업을 평가한 후에는 조직에서 장치의 보안 상태를 효과적으로 표현 하지 않기로 결정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8b81b-111">After an evaluation of the Microsoft Secure Score improvement actions supplied from Intune, it was decided that they do not provide a useful representation of the security posture of devices in organizations.</span></span> <span data-ttu-id="8b81b-112">정책을 중점적으로 설명 하는 대신, 장치의 구성 상태를 직접 평가 하는 보안 컨트롤을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8b81b-112">Instead of focusing on policies, we are working to bring in security controls that directly assess the configuration state of the devices.</span></span>

<span data-ttu-id="8b81b-113">다음 Intune 개선 작업이 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b81b-113">The following Intune improvement actions will be removed:</span></span>

- <span data-ttu-id="8b81b-114">Microsoft Intune 모바일 장치 관리 사용</span><span class="sxs-lookup"><span data-stu-id="8b81b-114">Enable Microsoft Intune Mobile Device Management</span></span>
- <span data-ttu-id="8b81b-115">Android 용 Microsoft Intune 준수 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="8b81b-115">Create a Microsoft Intune Compliance Policy for Android</span></span>
- <span data-ttu-id="8b81b-116">비즈니스용 Android 용 Microsoft Intune 준수 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="8b81b-116">Create a Microsoft Intune Compliance Policy for Android for Work</span></span>
- <span data-ttu-id="8b81b-117">Android 용 Microsoft Intune 앱 보호 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="8b81b-117">Create a Microsoft Intune App Protection Policy for Android</span></span>
- <span data-ttu-id="8b81b-118">IOS 용 Microsoft Intune 앱 보호 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="8b81b-118">Create a Microsoft Intune App Protection Policy for iOS</span></span>
- <span data-ttu-id="8b81b-119">Microsoft Intune 준수 정책이 비규격으로 지정 된 장치 표시</span><span class="sxs-lookup"><span data-stu-id="8b81b-119">Mark devices with no Microsoft Intune Compliance Policy assigned as not compliant</span></span>
- <span data-ttu-id="8b81b-120">IOS 용 Microsoft Intune 준수 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="8b81b-120">Create a Microsoft Intune Compliance Policy for iOS</span></span>
- <span data-ttu-id="8b81b-121">MacOS에 대 한 Microsoft Intune 준수 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="8b81b-121">Create a Microsoft Intune Compliance Policy for macOS</span></span>
- <span data-ttu-id="8b81b-122">Windows 용 Microsoft Intune 준수 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="8b81b-122">Create a Microsoft Intune Compliance Policy for Windows</span></span>
- <span data-ttu-id="8b81b-123">Android 용 Microsoft Intune 구성 프로필 만들기</span><span class="sxs-lookup"><span data-stu-id="8b81b-123">Create a Microsoft Intune Configuration Profile for Android</span></span>
- <span data-ttu-id="8b81b-124">비즈니스용 Android 용 Microsoft Intune 구성 프로필 만들기</span><span class="sxs-lookup"><span data-stu-id="8b81b-124">Create a Microsoft Intune Configuration Profile for Android for Work</span></span>
- <span data-ttu-id="8b81b-125">MacOS 용 Microsoft Intune 구성 프로필 만들기</span><span class="sxs-lookup"><span data-stu-id="8b81b-125">Create a Microsoft Intune Configuration Profile for macOS</span></span>
- <span data-ttu-id="8b81b-126">IOS 용 Microsoft Intune 구성 프로필 만들기</span><span class="sxs-lookup"><span data-stu-id="8b81b-126">Create a Microsoft Intune Configuration Profile for iOS</span></span>
- <span data-ttu-id="8b81b-127">Windows 용 Microsoft Intune 구성 프로필 만들기</span><span class="sxs-lookup"><span data-stu-id="8b81b-127">Create a Microsoft Intune Configuration Profile for Windows</span></span>
- <span data-ttu-id="8b81b-128">Microsoft Intune에서 향상 된 jailbreak 검색 사용</span><span class="sxs-lookup"><span data-stu-id="8b81b-128">Enable enhanced jailbreak detection in Microsoft Intune</span></span>
- <span data-ttu-id="8b81b-129">모든 장치에 패치를 적용 하 고 바이러스 백신 및 방화벽을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b81b-129">Require all devices to be patched, have anti-virus, and firewalls enabled</span></span>
- <span data-ttu-id="8b81b-130">Microsoft Intune에 Windows Defender ATP 통합 사용</span><span class="sxs-lookup"><span data-stu-id="8b81b-130">Enable Windows Defender ATP integration into Microsoft Intune</span></span>
- <span data-ttu-id="8b81b-131">Microsoft Intune Windows Information Protection 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="8b81b-131">Create a Microsoft Intune Windows Information Protection Policy</span></span>
- <span data-ttu-id="8b81b-132">모든 장치에 고급 보안 구성 필요</span><span class="sxs-lookup"><span data-stu-id="8b81b-132">Require all devices to have advanced security configurations</span></span>
- <span data-ttu-id="8b81b-133">매주 차단 된 장치 보고서 검토</span><span class="sxs-lookup"><span data-stu-id="8b81b-133">Review blocked devices report weekly</span></span>

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement"></a><span data-ttu-id="8b81b-134">신뢰할 수 있는 측정에 대 한 기대치를 충족 하지 않는 개선 작업 제거</span><span class="sxs-lookup"><span data-stu-id="8b81b-134">Removing improvement actions that don't meet expectations for reliable measurement</span></span>

<span data-ttu-id="8b81b-135">Microsoft 보안 점수가 의미 있고 모든 개선 조치를 측정할 수 있으며 안정성을 유지 하려면 다음과 같은 개선 작업을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b81b-135">To ensure that the Microsoft Secure Score is meaningful and that every improvement action is measurable and reliable, we are removing the following improvement actions.</span></span>

- <span data-ttu-id="8b81b-136">감사 데이터 기록 켜기</span><span class="sxs-lookup"><span data-stu-id="8b81b-136">Turn on audit data recording</span></span>
- <span data-ttu-id="8b81b-137">위험한 및 비호환 섀도 IT 응용 프로그램 검색</span><span class="sxs-lookup"><span data-stu-id="8b81b-137">Discover risky and non-compliant shadow IT applications</span></span>
- <span data-ttu-id="8b81b-138">사용 권한 검토 & 환경에 연결 된 위험한 OAuth 응용 프로그램 차단</span><span class="sxs-lookup"><span data-stu-id="8b81b-138">Review permissions & block risky OAuth applications connected to your environment</span></span>
- <span data-ttu-id="8b81b-139">SharePoint online 문서 라이브러리에 대 한 버전 관리 설정</span><span class="sxs-lookup"><span data-stu-id="8b81b-139">Set up versioning on SharePoint online document libraries</span></span>

### <a name="mfa-improvement-action-updates"></a><span data-ttu-id="8b81b-140">MFA 개선 작업 업데이트</span><span class="sxs-lookup"><span data-stu-id="8b81b-140">MFA improvement action updates</span></span>

<span data-ttu-id="8b81b-141">비즈니스의 보안을 강화 하기 위해 기업에서 요구 하는 사항을 반영 하기 위해 Microsoft 보안 점수는 다단계 인증을 중심으로 하는 세 가지 개선 작업을 제거 하 고 두 개를 추가 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8b81b-141">To reflect the need for businesses to ensure the upmost security while applying policies that work with their business, Microsoft Secure Score is removing three improvement actions centered around multi-factor authentication, and adding two.</span></span>

<span data-ttu-id="8b81b-142">제거 되는 3:</span><span class="sxs-lookup"><span data-stu-id="8b81b-142">The three that will be removed:</span></span>

- <span data-ttu-id="8b81b-143">Multi-factor authentication에 대 한 모든 사용자 등록</span><span class="sxs-lookup"><span data-stu-id="8b81b-143">Register all users for multi-factor authentication</span></span>
- <span data-ttu-id="8b81b-144">모든 사용자에 대해 MFA 요구</span><span class="sxs-lookup"><span data-stu-id="8b81b-144">Require MFA for all users</span></span>
- <span data-ttu-id="8b81b-145">Azure AD 권한 있는 역할에 대해 MFA 필요</span><span class="sxs-lookup"><span data-stu-id="8b81b-145">Require MFA for Azure AD privileged roles</span></span>

<span data-ttu-id="8b81b-146">새로 추가 된 개선 작업:</span><span class="sxs-lookup"><span data-stu-id="8b81b-146">New improvement actions added:</span></span>

- <span data-ttu-id="8b81b-147">모든 사용자가 보안 액세스를 위해 multi-factor authentication을 완료할 수 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="8b81b-147">Ensure all users can complete multi-factor authentication for secure access</span></span>
- <span data-ttu-id="8b81b-148">관리 역할에 대 한 MFA 필요</span><span class="sxs-lookup"><span data-stu-id="8b81b-148">Require MFA for administrative roles</span></span>

 <span data-ttu-id="8b81b-149">이러한 새로운 향상 작업을 수행 하려면 디렉터리 전체에서 MFA (multi-factor authentication)에 대 한 사용자 또는 관리자를 등록 하 고 조직의 요구 사항에 맞는 적절 한 정책 집합을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b81b-149">These new improvement actions will require registering your users or admins for multi-factor authentication (MFA) across your directory and establishing the right set of policies that fit your organizational needs.</span></span> <span data-ttu-id="8b81b-150">기본 목표는 모든 사용자와 관리자가 여러 요소 또는 위험 기반 id 확인 메시지를 사용 하 여 인증할 수 있도록 하는 데 유연성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b81b-150">The main goal is have flexibility while ensuring all your users and admins can authenticate with multiple factors or risk-based identity verification prompts.</span></span> <span data-ttu-id="8b81b-151">이는 범위 결정을 적용 하는 정책이 여러 개 있거나 Microsoft가 MFA를 위해 사용자를 challenge 해야 하는 경우를 결정할 수 있도록 보안 기본값 (16 월 여섯째 부분)을 설정 하는 형태입니다.</span><span class="sxs-lookup"><span data-stu-id="8b81b-151">That can take the form of having multiple policies that apply scoped decisions, or setting security defaults (coming March 16th) that let Microsoft decide when to challenge users for MFA.</span></span>

### <a name="removing-review-improvement-actions"></a><span data-ttu-id="8b81b-152">"검토" 개선 작업 제거</span><span class="sxs-lookup"><span data-stu-id="8b81b-152">Removing “review” improvement actions</span></span>

<span data-ttu-id="8b81b-153">보안 점수 원칙 중 하나는 점수가 표준화 되 고 간편 하 게 관련 되어야 한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8b81b-153">One of the principles of Secure Score is that the score should be standardized and easy to relate to.</span></span> <span data-ttu-id="8b81b-154">기능을 사용할 수 없거나 작업을 수행 하는 향상 된 기능으로 인해 혼동이 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8b81b-154">Having improvement actions that are not measurable or actionable has been causing confusion.</span></span> <span data-ttu-id="8b81b-155">한 Microsoft 보안 점수는 모든 권장 사항이 점수에 분명 하 게 영향을 미칠 수 있는 경우에만 의미가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b81b-155">One Microsoft Secure Score only makes sense when every recommendation can have a clear effect on the score.</span></span> <span data-ttu-id="8b81b-156">검토 개선 작업은 다른 개선 작업과 같은 표준으로 측정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8b81b-156">Review improvement actions are not measured to the same standard as other improvement actions.</span></span>  

<span data-ttu-id="8b81b-157">이러한 이유로 검토 흐름을 필요로 하는 모든 개선 작업이 일시적으로 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b81b-157">For these reasons, all improvement actions that required a review cadence will be temporarily removed.</span></span> <span data-ttu-id="8b81b-158">해당 부분에 대 한 작업이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8b81b-158">No action is needed on your part.</span></span>

## <a name="march-16th-2020"></a><span data-ttu-id="8b81b-159">16 월 여섯째 2020</span><span class="sxs-lookup"><span data-stu-id="8b81b-159">March 16th 2020</span></span>

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement"></a><span data-ttu-id="8b81b-160">신뢰할 수 있는 측정에 대 한 기대치를 충족 하지 않는 개선 작업 제거</span><span class="sxs-lookup"><span data-stu-id="8b81b-160">Removing improvement actions that don't meet expectations for reliable measurement</span></span>

<span data-ttu-id="8b81b-161">Microsoft 보안 점수가 의미 있고 모든 개선 조치를 측정할 수 있으며 안정성을 유지 하려면 다음과 같은 개선 작업을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b81b-161">To ensure that the Microsoft Secure Score is meaningful and that every improvement action is measurable and reliable, we are removing the following improvement actions.</span></span>

- <span data-ttu-id="8b81b-162">비즈니스용 OneDrive에 사용자 문서 저장</span><span class="sxs-lookup"><span data-stu-id="8b81b-162">Store user documents in OneDrive for Business</span></span>
- <span data-ttu-id="8b81b-163">Office 365 ATP 안전한 첨부 파일 정책 설정</span><span class="sxs-lookup"><span data-stu-id="8b81b-163">Set up Office 365 ATP Safe Attachment policies</span></span>
- <span data-ttu-id="8b81b-164">Url을 확인 하기 위한 Office 365 안전한 링크 설정</span><span class="sxs-lookup"><span data-stu-id="8b81b-164">Set up Office 365 Safe Links to verify URLs</span></span>
- <span data-ttu-id="8b81b-165">사서함 위임 허용 안 함</span><span class="sxs-lookup"><span data-stu-id="8b81b-165">Do not allow mailbox delegation</span></span>
- <span data-ttu-id="8b81b-166">사이트 및 문서에 대 한 익명 게스트 공유 링크 허용</span><span class="sxs-lookup"><span data-stu-id="8b81b-166">Allow anonymous guest sharing links for sites and docs</span></span>

### <a name="supporting-security-defaults-for-azure-ad-improvement-actions"></a><span data-ttu-id="8b81b-167">Azure AD 개선 작업에 대 한 보안 기본값 지원</span><span class="sxs-lookup"><span data-stu-id="8b81b-167">Supporting security defaults for Azure AD improvement actions</span></span>

<span data-ttu-id="8b81b-168">Microsoft 보안 점수는 [AZURE AD에서 보안 기본값](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)을 지원 하기 위해 개선 작업을 업데이트 하 여 일반적인 공격에 대 한 미리 구성 된 보안 설정으로 조직을 보호 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b81b-168">Microsoft Secure Score will be updating improvement actions to support [security defaults in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), which make it easier to help protect your organization with pre-configured security settings for common attacks.</span></span>

<span data-ttu-id="8b81b-169">이는 다음과 같은 개선 작업에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8b81b-169">It will affect the following improvement actions:</span></span>

- <span data-ttu-id="8b81b-170">모든 사용자가 보안 액세스를 위해 multi-factor authentication을 완료할 수 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="8b81b-170">Ensure all users can complete multi-factor authentication for secure access</span></span>
- <span data-ttu-id="8b81b-171">관리 역할에 대 한 MFA 필요</span><span class="sxs-lookup"><span data-stu-id="8b81b-171">Require MFA for administrative roles</span></span>
- <span data-ttu-id="8b81b-172">정책을 사용 하 여 레거시 인증 차단</span><span class="sxs-lookup"><span data-stu-id="8b81b-172">Enable policy to block legacy authentication</span></span>
