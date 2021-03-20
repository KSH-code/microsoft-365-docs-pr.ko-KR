---
title: Microsoft 365 클라이언트 및 서비스 앱 지원
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
search.appverid:
- MET150
f1.keywords:
- NOCSH
description: 이 문서에서는 Microsoft 365 클라이언트 및 서비스 앱 지원에 대한 세부 정보를 찾아야 합니다.
ms.openlocfilehash: e380efffc1bf29cbd4d3a77d32e4d1f8b2994da3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905011"
---
# <a name="microsoft-365-client-and-services-app-support"></a><span data-ttu-id="1d71d-103">Microsoft 365 클라이언트 및 서비스 앱 지원</span><span class="sxs-lookup"><span data-stu-id="1d71d-103">Microsoft 365 client and services app support</span></span>

<span data-ttu-id="1d71d-104">Microsoft는 고객 데이터를 안전하게 유지할 수 있도록 광범위한 보안, 인증 및 규정 준수 기능을 지원하며 IT 관리자가 사용자를 위해 Microsoft 365 관리 센터 내에서 정책을 사용자 지정할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d71d-104">Microsoft supports a wide range of security, authentication, and compliance features to keep customer data safe and allows IT administrators to customize policies within the Microsoft 365 admin center for their users.</span></span> <span data-ttu-id="1d71d-105">다음 기능은 Microsoft 365 구독에 따라 구성할 수 있는 많은 엔터프라이즈 기능의 일부일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d71d-105">The following features are just a subset of the many enterprise features that you can configure depending on your Microsoft 365 subscription.</span></span>

## <a name="client-and-service-support"></a><span data-ttu-id="1d71d-106">클라이언트 및 서비스 지원</span><span class="sxs-lookup"><span data-stu-id="1d71d-106">Client and service support</span></span>

### <a name="continuous-access-evaluation-preview"></a><span data-ttu-id="1d71d-107">연속 액세스 평가(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="1d71d-107">Continuous access evaluation (preview)</span></span>

<span data-ttu-id="1d71d-108">지속적인 액세스 평가는 Exchange Online, SharePoint Online 및 Teams와 같은 서비스가 Azure Active Directory의 중요한 이벤트를 구독할 수 있도록 하여 이러한 이벤트를 거의 실시간으로 평가하고 적용할 수 있도록 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d71d-108">Continuous access evaluation is implemented by enabling services, like Exchange Online, SharePoint Online, and Teams, to subscribe to critical events in Azure Active Directory so that those events can be evaluated and enforced near real time.</span></span> <span data-ttu-id="1d71d-109">중요한 이벤트 평가는 조건부 액세스 정책을 사용하지 않습니다. 따라서 모든 테넌트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d71d-109">Critical event evaluation does not rely on Conditional Access policies so is available in any tenant.</span></span>

<span data-ttu-id="1d71d-110">현재 다음 이벤트가 평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d71d-110">The following events are currently evaluated:</span></span>

- <span data-ttu-id="1d71d-111">사용자 계정이 삭제되거나 사용되지 않도록 설정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1d71d-111">A user account is deleted or disabled</span></span>
- <span data-ttu-id="1d71d-112">사용자의 암호가 변경되거나 다시 설정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1d71d-112">The password for a user is changed or reset</span></span>
- <span data-ttu-id="1d71d-113">사용자에 대해 다단계 인증 사용</span><span class="sxs-lookup"><span data-stu-id="1d71d-113">Multi-factor authentication is enabled for the user</span></span>
- <span data-ttu-id="1d71d-114">관리자가 사용자에 대한 모든 새로 고침 토큰을 명시적으로 해지</span><span class="sxs-lookup"><span data-stu-id="1d71d-114">Administrator explicitly revokes all refresh tokens for a user</span></span>
- <span data-ttu-id="1d71d-115">Azure AD ID 보호에서 감지된 높은 사용자 위험</span><span class="sxs-lookup"><span data-stu-id="1d71d-115">Elevated user risk detected by Azure AD Identity Protection</span></span>

<span data-ttu-id="1d71d-116">클라이언트 및 서비스 앱 지원에 대한 지속적인 액세스 평가에 대한 자세한 내용은 연속 액세스 평가(미리 [보기)를 참조하세요.](/azure/active-directory/conditional-access/concept-continuous-access-evaluation)</span><span class="sxs-lookup"><span data-stu-id="1d71d-116">For more information about continuous access evaluation for client and services app support, see [Continuous access evaluation (preview)](/azure/active-directory/conditional-access/concept-continuous-access-evaluation).</span></span>

## <a name="client-support"></a><span data-ttu-id="1d71d-117">클라이언트 지원</span><span class="sxs-lookup"><span data-stu-id="1d71d-117">Client support</span></span>

### <a name="certificate-based-authentication"></a><span data-ttu-id="1d71d-118">인증서 기반 인증</span><span class="sxs-lookup"><span data-stu-id="1d71d-118">Certificate-based authentication</span></span>

<span data-ttu-id="1d71d-119">CBA(인증서 기반 인증)는 리소스, 네트워크, 응용 프로그램 또는 서비스에 대한 액세스 권한을 부여하기 전에 디지털 인증서를 사용하여 사용자, 컴퓨터 또는 장치를 식별하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1d71d-119">Certificate-based authentication (CBA) is the use of a digital certificate to identify a user, machine, or device before granting access to a resource, network, application, or service.</span></span> <span data-ttu-id="1d71d-120">사용자 인증에서는 사용자 이름 및 암호와 같은 기존 방법과 함께 배포되는 경우가 종종 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d71d-120">In user authentication, it is often deployed in coordination with traditional methods such as usernames and passwords.</span></span>

<span data-ttu-id="1d71d-121">일부 기존 솔루션은 생체 인식 및 OTP(일회용 암호)과 같은 사용자만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d71d-121">Some traditional solutions only work for users, such as biometrics and one-time passwords (OTP).</span></span> <span data-ttu-id="1d71d-122">인증서 기반 인증을 사용하는 경우 모든 끝점에 동일한 솔루션을 사용할 수 있습니다. 사용자, 장치 및 점점 증가하는 IoT(사물 인터넷)</span><span class="sxs-lookup"><span data-stu-id="1d71d-122">With certificate-based authentication, the same solution can be used for all endpoints; users, devices, and the growing Internet of Things (IoT).</span></span>

<span data-ttu-id="1d71d-123">클라이언트 및 서비스 앱 지원에 대한 인증서 기반 인증에 대한 자세한 내용은 [Microsoft 365 클라이언트](microsoft-365-client-support-certificate-based-authentication.md)앱 지원: 인증서 기반 인증을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d71d-123">For more information about certificate-based authentication for client and services app support, see [Microsoft 365 Client App Support: Certificate-based Authentication](microsoft-365-client-support-certificate-based-authentication.md).</span></span>

### <a name="conditional-access"></a><span data-ttu-id="1d71d-124">조건부 액세스</span><span class="sxs-lookup"><span data-stu-id="1d71d-124">Conditional Access</span></span>

<span data-ttu-id="1d71d-125">조건부 액세스는 Azure Active Directory에서 신호를 함께 가져오고, 결정을 내리고, 조직 액세스 정책을 적용하는 데 사용하는 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="1d71d-125">Conditional Access is the tool used by Azure Active Directory to bring signals together, to make decisions, and enforce organizational access policies.</span></span> <span data-ttu-id="1d71d-126">조건부 액세스는 새로운 ID 기반 컨트롤 모델의 핵심입니다.</span><span class="sxs-lookup"><span data-stu-id="1d71d-126">Conditional Access is at the heart of the new identity-driven control model.</span></span>

<span data-ttu-id="1d71d-127">조건부 액세스 정책은 리소스에 대한 액세스 권한을 부여하기 위한 if-then 문입니다.</span><span class="sxs-lookup"><span data-stu-id="1d71d-127">Conditional Access policies are if-then statements for granting access to resources.</span></span> <span data-ttu-id="1d71d-128">사용자가 리소스에 액세스하려는 경우 사용자가 작업을 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d71d-128">If a user wants to access a resource, then the user must complete an action.</span></span> <span data-ttu-id="1d71d-129">정책 액세스 결정을 내릴 때 조건부 액세스에서 사용할 수 있는 일반적인 신호는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1d71d-129">Common signals that Conditional Access can use when making a policy access decision include:</span></span>

- <span data-ttu-id="1d71d-130">사용자 또는 그룹 구성원</span><span class="sxs-lookup"><span data-stu-id="1d71d-130">User or group membership</span></span>
- <span data-ttu-id="1d71d-131">IP 위치 정보</span><span class="sxs-lookup"><span data-stu-id="1d71d-131">IP location information</span></span>
- <span data-ttu-id="1d71d-132">장치 정보</span><span class="sxs-lookup"><span data-stu-id="1d71d-132">Device information</span></span>
- <span data-ttu-id="1d71d-133">응용 프로그램 정보</span><span class="sxs-lookup"><span data-stu-id="1d71d-133">Application information</span></span>
- <span data-ttu-id="1d71d-134">실시간 및 계산된 위험 감지</span><span class="sxs-lookup"><span data-stu-id="1d71d-134">Real-time and calculated risk detection</span></span>
- <span data-ttu-id="1d71d-135">Microsoft Cloud App Security (MCAS)</span><span class="sxs-lookup"><span data-stu-id="1d71d-135">Microsoft Cloud App Security (MCAS)</span></span>

<span data-ttu-id="1d71d-136">이러한 액세스 결정을 내릴 때 정책은 다른 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d71d-136">When making these access decisions, the policies can take different actions:</span></span>

- <span data-ttu-id="1d71d-137">이 정책은 액세스를 차단할 수 있습니다. 이 구성은 가장 제한적인 작업으로, 사용자가 리소스에 액세스하지 못하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d71d-137">The policy can block access: This configuration is the most restrictive action and prevents the user from accessing the resource.</span></span>
- <span data-ttu-id="1d71d-138">이 정책은 액세스 권한을 부여할 수 있습니다. 이 구성은 덜 제한적인 결정으로, 다음 옵션 중 하나 이상이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d71d-138">The policy can grant access: This configuration is a less restrictive decision and may still require one or more of the following options:</span></span>

    - <span data-ttu-id="1d71d-139">다단계 인증</span><span class="sxs-lookup"><span data-stu-id="1d71d-139">Multi-factor authentication</span></span>
    - <span data-ttu-id="1d71d-140">규격으로 표시될 장치</span><span class="sxs-lookup"><span data-stu-id="1d71d-140">The device to be marked as compliant</span></span>
    - <span data-ttu-id="1d71d-141">장치가 하이브리드 Azure AD에 가입된 경우</span><span class="sxs-lookup"><span data-stu-id="1d71d-141">The device is hybrid Azure AD joined</span></span>
    - <span data-ttu-id="1d71d-142">승인된 클라이언트 앱</span><span class="sxs-lookup"><span data-stu-id="1d71d-142">An approved client app</span></span>
    - <span data-ttu-id="1d71d-143">구성된 앱 보호 정책(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="1d71d-143">App protection policy configured (preview)</span></span>

<span data-ttu-id="1d71d-144">클라이언트 및 서비스 앱 지원에 대한 조건부 액세스에 대한 자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d71d-144">For more information about Conditional Access for client and services app support, see:</span></span>

- [<span data-ttu-id="1d71d-145">Microsoft 365 클라이언트 앱 지원: 장치 기반 조건부 액세스</span><span class="sxs-lookup"><span data-stu-id="1d71d-145">Microsoft 365 Client App Support: Device-based Conditional Access</span></span>](microsoft-365-client-support-conditional-access.md)

### <a name="mobile-application-management"></a><span data-ttu-id="1d71d-146">모바일 응용 프로그램 관리</span><span class="sxs-lookup"><span data-stu-id="1d71d-146">Mobile application management</span></span>

<span data-ttu-id="1d71d-147">사용자는 종종 동일한 모바일 장치에서 조직 및 개인 문서, 전자 메일 및 데이터에 모두 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="1d71d-147">Users often access both organization and personal documents, email, and data from the same mobile device.</span></span> <span data-ttu-id="1d71d-148">이러한 장치는 종종 개인적으로 소유하며 조직 데이터와 사용자의 개인 정보를 모두 보호하도록 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d71d-148">Those devices are often personally owned and should be configured to protect both organization data and the user's personal privacy.</span></span>

<span data-ttu-id="1d71d-149">사용자가 조직 데이터에 액세스할 때 조직은 구성 정책 및 보호 정책과 같은 조직 정책이 장치의 조직 데이터를 보호하는 데 도움이 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d71d-149">When a user accesses organization data, the organization must be confident that organization policies, such as configuration policies and protection policies, are applied to help protect organization data on the device.</span></span> <span data-ttu-id="1d71d-150">또한 장치의 사용자 개인 콘텐츠는 조직의 제어 외부에 유지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d71d-150">Additionally, the user's personal content on the device should remain outside of the organization's control.</span></span>

<span data-ttu-id="1d71d-151">조직 관리 콘텐츠의 경우 응용 프로그램 관리 정책을 적용하여 Microsoft Intune을 사용하여 데이터가 액세스, 공유 및 사용되는 방법을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d71d-151">For organization-managed content, you can apply application management policies to control how data is accessed, shared, and used by using Microsoft Intune.</span></span> <span data-ttu-id="1d71d-152">예를 들어 다음 작업이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d71d-152">For example, the following actions are supported:</span></span>

- <span data-ttu-id="1d71d-153">관리되는 조직 콘텐츠(조직 데이터라고도 하는 원격 지우기)</span><span class="sxs-lookup"><span data-stu-id="1d71d-153">Remote wipe the managed organization content (also referred to org data)</span></span>
- <span data-ttu-id="1d71d-154">조직 콘텐츠를 비조직 위치에 붙여넣지 못하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d71d-154">Prevent pasting organization content into non-organization locations</span></span>
- <span data-ttu-id="1d71d-155">조직 콘텐츠에 액세스하려면 PIN 필요</span><span class="sxs-lookup"><span data-stu-id="1d71d-155">Require a PIN to access organization content</span></span>
- <span data-ttu-id="1d71d-156">무단 또는 루팅된 장치에서 관리되는 앱이 실행되지 않도록 방지</span><span class="sxs-lookup"><span data-stu-id="1d71d-156">Prevent managed apps from running on jailbroken or rooted devices</span></span>
- <span data-ttu-id="1d71d-157">조직 콘텐츠가 승인되지 않은 클라우드 저장소 공급자에 저장되지 않도록 방지</span><span class="sxs-lookup"><span data-stu-id="1d71d-157">Prevent organization content from being saved to unapproved cloud storage providers</span></span>
- <span data-ttu-id="1d71d-158">승인되지 않은 콘텐츠가 관리되는 응용 프로그램으로 전송되지 않도록 방지</span><span class="sxs-lookup"><span data-stu-id="1d71d-158">Prevent unapproved content from being transferred into managed applications</span></span>
- <span data-ttu-id="1d71d-159">정책이 적용된 후에만 조직 콘텐츠에 대한 액세스 허용</span><span class="sxs-lookup"><span data-stu-id="1d71d-159">Allow access to organization content only after policies have been applied</span></span>
- <span data-ttu-id="1d71d-160">응용 프로그램 구성을 전달하여 응용 프로그램의 동작 및 설정 관리</span><span class="sxs-lookup"><span data-stu-id="1d71d-160">Deliver application configuration to manage the application's behavior and settings</span></span>
- <span data-ttu-id="1d71d-161">다중 ID 기능 또는 개인 사용을 사용 안 하도록 설정하여 관리되는 응용 프로그램을 정의된 ID로 제한</span><span class="sxs-lookup"><span data-stu-id="1d71d-161">Restrict the managed application to a defined identity by disabling multi-identity capabilities or personal usage</span></span>

<span data-ttu-id="1d71d-162">Microsoft Intune을 통해 모바일 응용 프로그램 관리에 대한 자세한 내용은 [Microsoft Intune 앱 관리란?을 참조하세요.](/mem/intune/apps/app-management)</span><span class="sxs-lookup"><span data-stu-id="1d71d-162">For more information about mobile application management with Microsoft Intune, see [What is Microsoft Intune app management?](/mem/intune/apps/app-management)</span></span>

### <a name="multi-factor-authentication"></a><span data-ttu-id="1d71d-163">다단계 인증</span><span class="sxs-lookup"><span data-stu-id="1d71d-163">Multi-factor authentication</span></span>

<span data-ttu-id="1d71d-164">[MFA(다단계 인증)는 인증 메커니즘에 여러 가지 별도의 증거 조각을 성공적으로 제공한 후에만 사용자에게 액세스 권한을 부여하는 컴퓨터 액세스 제어 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="1d71d-164">[Multi-factor authentication (MFA) is a method of computer access control in which a user is granted access only after successfully presenting several separate pieces of evidence to an authentication mechanism.</span></span> <span data-ttu-id="1d71d-165">이 메서드는 일반적으로 다음 범주 중 두 개 이상을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1d71d-165">This method typically uses at least two of the following categories:</span></span>

- <span data-ttu-id="1d71d-166">지식(알고 있는 정보)</span><span class="sxs-lookup"><span data-stu-id="1d71d-166">Knowledge (something they know)</span></span>
- <span data-ttu-id="1d71d-167">소유(보유한 것)</span><span class="sxs-lookup"><span data-stu-id="1d71d-167">Possession (something they have)</span></span>
- <span data-ttu-id="1d71d-168">본질(있는 것)</span><span class="sxs-lookup"><span data-stu-id="1d71d-168">Inherence (something they are)</span></span>

<span data-ttu-id="1d71d-169">클라이언트 및 서비스 앱 지원에 대한 다단계 인증에 대한 자세한 내용은 [Microsoft 365 클라이언트](microsoft-365-client-support-multi-factor-authentication.md)앱 지원: 다단계 인증을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d71d-169">For more information about multi-factor authentication for client and services app support, see [Microsoft 365 Client App Support: Multi-factor authentication](microsoft-365-client-support-multi-factor-authentication.md).</span></span>

### <a name="single-sign-on"></a><span data-ttu-id="1d71d-170">Single Sign-On</span><span class="sxs-lookup"><span data-stu-id="1d71d-170">Single sign-on</span></span>

<span data-ttu-id="1d71d-171">SSO(Single Sign-On)는 사용자가 Azure Active Directory의 응용 프로그램에 로그인할 때 보안과 편의성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1d71d-171">Single sign-on (SSO) adds security and convenience when your users sign-on to applications in Azure Active Directory.</span></span> <span data-ttu-id="1d71d-172">Single Sign-On을 사용하면 사용자는 한 계정으로 한 번 로그인하여 조직의 사내 AD DS(Active Directory 도메인 서비스) 도메인 가입 장치, SaaS(Software as a Service) 응용 프로그램 및 웹 응용 프로그램에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="1d71d-172">With single sign-on, users sign in once with one account to access on-premises Active Directory Domain Services (AD DS) domain-joined devices, software as a service (SaaS) applications, and web applications in your organization.</span></span>

<span data-ttu-id="1d71d-173">클라이언트 및 서비스 앱 지원을 위한 Single Sign-On에 대한 자세한 내용은 [Microsoft 365 클라이언트 앱 지원: Single Sign-On을 참조하세요.](microsoft-365-client-support-single-sign-on.md)</span><span class="sxs-lookup"><span data-stu-id="1d71d-173">For more information about single sign-on for client and services app support, see [Microsoft 365 Client App Support: Single sign-on](microsoft-365-client-support-single-sign-on.md).</span></span>

## <a name="services-support"></a><span data-ttu-id="1d71d-174">서비스 지원</span><span class="sxs-lookup"><span data-stu-id="1d71d-174">Services support</span></span>

### <a name="modern-authentication"></a><span data-ttu-id="1d71d-175">최신 인증</span><span class="sxs-lookup"><span data-stu-id="1d71d-175">Modern authentication</span></span>

<span data-ttu-id="1d71d-176">최신 인증을 사용하면 고객이 Office 365에 대해 인증하고 테넌트 관리자가 Office 365 테넌트에 대해 다음과 같은 특정 인증 요구 사항을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d71d-176">Modern authentication enables new scenarios for customers to authenticate against Office 365 and for tenant admins to enforce specific authentication requirements across the Office 365 tenancy, such as:</span></span>

- <span data-ttu-id="1d71d-177">테넌트 및 서비스와의 관리 상호 작용, 응용 프로그램 및 해당 데이터와의 최종 사용자 상호 작용에 대한 다단계 인증 지원</span><span class="sxs-lookup"><span data-stu-id="1d71d-177">Multi-factor authentication support for administrative interaction with the tenancy and services, and end-user interaction with applications and their data</span></span>
- <span data-ttu-id="1d71d-178">조건부 액세스</span><span class="sxs-lookup"><span data-stu-id="1d71d-178">Conditional access</span></span>
- <span data-ttu-id="1d71d-179">SAML 기반 타사 ID 공급자 로그인</span><span class="sxs-lookup"><span data-stu-id="1d71d-179">SAML-based third-party identity provider sign-in</span></span>
- <span data-ttu-id="1d71d-180">개인 컴퓨터의 스마트 카드 로그</span><span class="sxs-lookup"><span data-stu-id="1d71d-180">Smartcard log on personal computers</span></span>
- <span data-ttu-id="1d71d-181">모바일 장치에서 인증서 기반 인증</span><span class="sxs-lookup"><span data-stu-id="1d71d-181">Certificate-based authentication on mobile devices</span></span>
- <span data-ttu-id="1d71d-182">더 이상 기본 인증을 통해 자격 증명을 전송할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1d71d-182">No longer require the transmission of credentials over basic authentication.</span></span>

<span data-ttu-id="1d71d-183">최신 인증 서비스 지원에 대한 자세한 내용은 인증 및 [권한 부여를 참조하세요.](/azure/active-directory/develop/authentication-vs-authorization)</span><span class="sxs-lookup"><span data-stu-id="1d71d-183">For more information about modern authentication services support, see [Authentication vs. authorization](/azure/active-directory/develop/authentication-vs-authorization).</span></span>

### <a name="azure-active-directory-conditional-access"></a><span data-ttu-id="1d71d-184">Azure Active Directory 조건부 액세스</span><span class="sxs-lookup"><span data-stu-id="1d71d-184">Azure Active Directory Conditional Access</span></span>

<span data-ttu-id="1d71d-185">Azure AD(Azure Active Directory) 조건부 액세스 규칙을 통해 고객은 장치 준수 또는 네트워크 위치와 같은 특성에 따라 온라인 서비스에 대한 액세스를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d71d-185">Azure Active Directory (Azure AD) Conditional Access rules allow customers to control access to online services, based on attributes such as device compliance or network location.</span></span> <span data-ttu-id="1d71d-186">다음 솔루션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d71d-186">The following solutions may be used:</span></span>

- <span data-ttu-id="1d71d-187">Azure AD 다단계 인증 기반 조건부 액세스</span><span class="sxs-lookup"><span data-stu-id="1d71d-187">Azure AD multi-factor authentication-based Conditional Access</span></span>
- <span data-ttu-id="1d71d-188">Azure AD 위치 기반 조건부 액세스</span><span class="sxs-lookup"><span data-stu-id="1d71d-188">Azure AD location-based Conditional Access</span></span>
- <span data-ttu-id="1d71d-189">Azure AD 장치 기반 조건부 액세스</span><span class="sxs-lookup"><span data-stu-id="1d71d-189">Azure AD device-based Conditional Access</span></span>

<span data-ttu-id="1d71d-190">Azure AD 조건부 액세스 규칙은 응용 프로그램마다 적용되고 고객이 다양한 조건에 따라 액세스를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d71d-190">Azure AD Conditional access rules are applied per-application and are available for customers to control access based on different conditions.</span></span> <span data-ttu-id="1d71d-191">MDM(모바일 장치 관리) 또는 [Intune을](/mem/intune/fundamentals/what-is-device-management)사용하여 고객은 조직 장치를 사용 중이거나 관리를 위해 개인 장치를 등록한 사용자만 Microsoft 365에 대한 액세스를 제한할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d71d-191">Using [Mobile Device Management (MDM) or Intune](/mem/intune/fundamentals/what-is-device-management), customers must be able to restrict access to Microsoft 365 to only those users who are using an organization device or who have enrolled their personal device for management.</span></span> <span data-ttu-id="1d71d-192">예를 들어 고객은 다음과 같은 컨트롤을 적용하도록 조건부 액세스 규칙을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d71d-192">For example, customers may configure Conditional Access rules to enforce controls such as:</span></span>

- <span data-ttu-id="1d71d-193">도메인에 가입되거나 도메인을 준수하는 장치에서만 액세스 허용</span><span class="sxs-lookup"><span data-stu-id="1d71d-193">Only allow access from devices that are domain joined or domain compliant</span></span>
- <span data-ttu-id="1d71d-194">Exchange Online 서비스에 대한 모든 액세스에 대해 다단계 인증 적용</span><span class="sxs-lookup"><span data-stu-id="1d71d-194">Enforce multi-factor authentication for all access to Exchange Online services</span></span>

<span data-ttu-id="1d71d-195">Azure Active Directory 조건부 액세스에 대한 자세한 내용은 [조건부 액세스란?을 참조하세요.](/azure/active-directory/conditional-access/overview)</span><span class="sxs-lookup"><span data-stu-id="1d71d-195">For more information about Azure Active Directory Conditional Access, see [What is Conditional Access?](/azure/active-directory/conditional-access/overview)</span></span>

### <a name="tls-12-support"></a><span data-ttu-id="1d71d-196">TLS 1.2 지원</span><span class="sxs-lookup"><span data-stu-id="1d71d-196">TLS 1.2 support</span></span>

<span data-ttu-id="1d71d-197">고객에게 동급 최고의 암호화를 제공하기 위해 Microsoft는 Office 365 및 Office 365 GCC에서 TLS(전송 계층 보안) 버전 1.0 및 1.1에 대한 지원을 중단할 계획입니다.</span><span class="sxs-lookup"><span data-stu-id="1d71d-197">To provide the best-in-class encryption to our customers, Microsoft plans to discontinue support for Transport Layer Security (TLS) versions 1.0 and 1.1 in Office 365 and Office 365 GCC.</span></span>

<span data-ttu-id="1d71d-198">데이터 보안이 중요하다는 점을 이해하고 있으며 TLS 서비스 사용에 영향을 줄 수 있는 변경 사항에 대해 투명성을 유지할 것을 약속드립니다.</span><span class="sxs-lookup"><span data-stu-id="1d71d-198">We understand that the security of your data is important, and we're committed to transparency about changes that may affect your use of the TLS service.</span></span> <span data-ttu-id="1d71d-199">모든 클라이언트-서버 및 브라우저-서버 조합은 TLS 1.2(이상 버전)를 사용하여 Office 365 서비스에 대한 연결을 유지하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1d71d-199">We recommend that all client-server and browser-server combinations use TLS 1.2 (or a later version) to maintain connection to Office 365 services.</span></span> <span data-ttu-id="1d71d-200">특정 클라이언트-서버 및 브라우저-서버 조합을 업데이트해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d71d-200">You might have to update certain client-server and browser-server combinations.</span></span>

<span data-ttu-id="1d71d-201">TLS 1.2 지원 및 서비스 지원에 대한 자세한 내용은 [Office 365 및 Office 365 GCC에서 TLS 1.2 준비를 참조하세요.](../compliance/prepare-tls-1.2-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="1d71d-201">For more information about TLS 1.2 support and services support, see [Preparing for TLS 1.2 in Office 365 and Office 365 GCC](../compliance/prepare-tls-1.2-in-office-365.md).</span></span>