---
title: 사용자 Microsoft 365 암호 관리
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: 사용자 계정 암호를 관리하는 Microsoft 365 대해 자세히 알아보아야 합니다.
ms.openlocfilehash: 2062da49310121ec18f7ce21f523531f10d6df9b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905095"
---
# <a name="manage-microsoft-365-user-account-passwords"></a><span data-ttu-id="8e843-103">사용자 Microsoft 365 암호 관리</span><span class="sxs-lookup"><span data-stu-id="8e843-103">Manage Microsoft 365 user account passwords</span></span>

<span data-ttu-id="8e843-104">*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="8e843-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="8e843-105">ID 구성에 Microsoft 365 여러 가지 방법으로 사용자 계정 암호를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e843-105">You can manage Microsoft 365 user account passwords in several different ways, depending on your identity configuration.</span></span> <span data-ttu-id="8e843-106">ad DS(Active Directory [도메인 서비스)](../admin/add-users/index.yml)Microsoft 365 또는 Azure AD(Active Directory 도메인 서비스) 관리 센터에서 사용자 계정을 Azure Active Directory 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e843-106">You can manage user accounts in the [Microsoft 365 admin center](../admin/add-users/index.yml), in Active Directory Domain Services (AD DS), or in the Azure Active Directory (Azure AD) admin center.</span></span>

## <a name="plan-for-where-and-how-you-will-manage-your-user-account-passwords"></a><span data-ttu-id="8e843-107">사용자 계정 암호를 관리하는 위치 및 방법 계획</span><span class="sxs-lookup"><span data-stu-id="8e843-107">Plan for where and how you will manage your user account passwords</span></span>

<span data-ttu-id="8e843-108">사용자 계정을 관리하는 위치 및 방법은 사용자 계정의 ID 모델에 따라 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8e843-108">Where and how you can manage your user accounts depends on the identity model you want to use for your Microsoft 365.</span></span> <span data-ttu-id="8e843-109">두 모델은 클라우드 전용 및 하이브리드입니다.</span><span class="sxs-lookup"><span data-stu-id="8e843-109">The two models are cloud-only and hybrid.</span></span>
  
### <a name="cloud-only"></a><span data-ttu-id="8e843-110">클라우드 전용</span><span class="sxs-lookup"><span data-stu-id="8e843-110">Cloud-only</span></span>

<span data-ttu-id="8e843-111">다음에서 사용자 계정 암호를 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="8e843-111">You manage user account passwords in:</span></span>

- [<span data-ttu-id="8e843-112">Microsoft 365 관리 센터</span><span class="sxs-lookup"><span data-stu-id="8e843-112">The Microsoft 365 admin center</span></span>](../admin/add-users/index.yml)
- <span data-ttu-id="8e843-113">Azure AD 관리 센터</span><span class="sxs-lookup"><span data-stu-id="8e843-113">The Azure AD admin center</span></span>
    
### <a name="hybrid"></a><span data-ttu-id="8e843-114">하이브리드</span><span class="sxs-lookup"><span data-stu-id="8e843-114">Hybrid</span></span>

<span data-ttu-id="8e843-115">하이브리드 ID를 사용하면 암호가 AD DS에 저장됩니다. 따라서 사용자 계정 암호를 관리하려면 사내 AD DS 도구를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e843-115">With hybrid identity, passwords are stored in AD DS so you must use on-premises AD DS tools to manage user account passwords.</span></span> <span data-ttu-id="8e843-116">Azure AD가 이미 해시된 버전의 해시된 버전을 AD DS에 저장하는 PHS(암호 해시 동기화)를 사용하는 경우에도 사용자와 사용자는 AD DS에서 암호를 관리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e843-116">Even when using Password Hash Synchronization (PHS), in which Azure AD stores a hashed version of the already hashed version in AD DS, you and users must manage their passwords in AD DS.</span></span>

<span data-ttu-id="8e843-117">암호 [쓰기 저장을](#pw_writeback)사용하여 사용자는 Azure AD를 통해 AD DS 암호를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e843-117">With [password writeback](#pw_writeback), your users can change their AD DS passwords through Azure AD.</span></span>

## <a name="prevent-bad-passwords"></a><span data-ttu-id="8e843-118">잘못된 암호 방지</span><span class="sxs-lookup"><span data-stu-id="8e843-118">Prevent bad passwords</span></span>

<span data-ttu-id="8e843-119">모든 사용자가 [Microsoft의 암호 지침](https://www.microsoft.com/research/publication/password-guidance) 을 사용하여 사용자 계정 암호를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e843-119">All your users should be using [Microsoft's password guidance](https://www.microsoft.com/research/publication/password-guidance) to create their user account passwords.</span></span>

<span data-ttu-id="8e843-120">사용자가 쉽게 확인할 수 있는 암호를 만들지 못하도록 하려면 전역 금지 암호 목록과 사용자가 지정한 선택적 사용자 지정 금지 암호 목록을 사용하는 Azure AD 암호 보호를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e843-120">To prevent users from creating an easily-determined password, use Azure AD password protection, which uses both a global banned password list and an optional custom banned password list that you specify.</span></span> <span data-ttu-id="8e843-121">예를 들어, 다음과 같이 조직에 맞는 조건을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e843-121">For example, you can specify terms that are specific to your organization, such as:</span></span>

- <span data-ttu-id="8e843-122">브랜드 이름</span><span class="sxs-lookup"><span data-stu-id="8e843-122">Brand names</span></span>
- <span data-ttu-id="8e843-123">제품 이름</span><span class="sxs-lookup"><span data-stu-id="8e843-123">Product names</span></span>
- <span data-ttu-id="8e843-124">위치(예: 본사)</span><span class="sxs-lookup"><span data-stu-id="8e843-124">Locations (for example, such as company headquarters)</span></span>
- <span data-ttu-id="8e843-125">회사 관련 내부 조건</span><span class="sxs-lookup"><span data-stu-id="8e843-125">Company-specific internal terms</span></span>
- <span data-ttu-id="8e843-126">특정 회사 의미를 갖는 약어</span><span class="sxs-lookup"><span data-stu-id="8e843-126">Abbreviations that have specific company meaning</span></span>

<span data-ttu-id="8e843-127">클라우드 및 사내 [](/azure/active-directory/authentication/concept-password-ban-bad) [AD DS의](/azure/active-directory/authentication/concept-password-ban-bad-on-premises)잘못된 암호를 금지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e843-127">You can ban bad passwords [in the cloud](/azure/active-directory/authentication/concept-password-ban-bad) and for your [on-premises AD DS](/azure/active-directory/authentication/concept-password-ban-bad-on-premises).</span></span>

## <a name="simplify-user-sign-in"></a><span data-ttu-id="8e843-128">사용자 로그인 간소화</span><span class="sxs-lookup"><span data-stu-id="8e843-128">Simplify user sign-in</span></span>

<span data-ttu-id="8e843-129">Azure AD Seamless Single Sign-On(Azure AD Seamless SSO)는 PHS 및 PTA(Pass-Through Authentication)와 함께 작동하여 사용자가 암호 및 대부분의 경우 사용자 이름을 입력하지 않고도 Azure AD 사용자 계정을 사용하는 서비스에 로그인할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e843-129">Azure AD Seamless Single Sign-On (Azure AD Seamless SSO) works with PHS and Pass-Through Authentication (PTA), to allow your users to sign in to services that use Azure AD user accounts without having to type in their passwords, and in many cases, their usernames.</span></span> <span data-ttu-id="8e843-130">이는 사용자의 계정이 Office 365와 같은 클라우드 기반 응용 프로그램에 identity 페더레이션 서버와 같은 추가적인 온 프레미스 구성 요소 필요없이 더 쉽게 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e843-130">This gives your users easier access to cloud-based applications, such as Office 365, without needing any additional on-premises components such as identity federation servers.</span></span>

<span data-ttu-id="8e843-131">Azure AD Connect 도구를 사용하여 Azure AD Seamless SSO를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="8e843-131">You configure Azure AD Seamless SSO with the Azure AD Connect tool.</span></span> <span data-ttu-id="8e843-132">[Azure AD Seamless SSO 구성 지침](/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8e843-132">See the [instructions to configure Azure AD Seamless SSO](/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span></span>

<a name="pw_writeback"></a>
## <a name="simplify-password-updates-to-ad-ds"></a><span data-ttu-id="8e843-133">AD DS에 대한 암호 업데이트 간소화</span><span class="sxs-lookup"><span data-stu-id="8e843-133">Simplify password updates to AD DS</span></span>

<span data-ttu-id="8e843-134">암호 쓰기 저장을 사용하면 사용자가 Azure AD를 통해 암호를 다시 설정하도록 허용하고 AD DS로 복제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e843-134">With password writeback, you can allow users to reset their passwords through Azure AD, which is then replicated to AD DS.</span></span> <span data-ttu-id="8e843-135">사용자는 암호를 업데이트하기 위해 자신의 사내 AD DS에 액세스할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8e843-135">Users don’t need to access their on-premises AD DS to update their passwords.</span></span> <span data-ttu-id="8e843-136">온-프레미스 네트워크에 대한 원격 액세스 연결이 없는 로밍 또는 원격 사용자에게 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e843-136">This is valuable to roaming or remote users who do not have a remote access connection to the on-premises network.</span></span>

<span data-ttu-id="8e843-137">암호 쓰기 저장은 계정 손상의 높은 위험이 감지된 경우 사용자에게 온-프레미스 암호를 변경하도록 요구하는 등 Azure AD ID 보호 기능을 최대한 활용하기 위해 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8e843-137">Password writeback is required to fully utilize Azure AD Identity Protection capabilities, such as requiring users to change their on-premises passwords when there has been a high risk of account compromise detected.</span></span>

<span data-ttu-id="8e843-138">추가 정보 및 구성 지침은 [암호 쓰기 저장을 지원하는 Azure AD SSPR](/azure/active-directory/active-directory-passwords-writeback)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8e843-138">For additional information and configuration instructions, see [Azure AD SSPR with password writeback](/azure/active-directory/active-directory-passwords-writeback).</span></span>

>[!Note]
><span data-ttu-id="8e843-p108">가능한 최상의 환경 및 새로운 기능(릴리스될 때)을 유지하도록 최신 버전의 Azure AD Connect로 업그레이드하세요. 자세한 내용은 [Azure AD Connect의 사용자 지정 설치](/azure/active-directory/connect/active-directory-aadconnect-get-started-custom)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8e843-p108">Upgrade to the latest version of Azure AD Connect to ensure the best possible experience and new features as they are released. For more information, see [Custom installation of Azure AD Connect](/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).</span></span>
>

## <a name="simplify-password-resets"></a><span data-ttu-id="8e843-141">암호 재설정 간소화</span><span class="sxs-lookup"><span data-stu-id="8e843-141">Simplify password resets</span></span>

<span data-ttu-id="8e843-142">SSPR(셀프 서비스 암호 재설정)을 사용하면 사용자가 암호 또는 계정을 다시 설정하거나 잠금을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e843-142">Self-service password reset (SSPR) allows users to reset or unlock their passwords or accounts.</span></span> <span data-ttu-id="8e843-143">오용 또는 남용에 대한 경고로 사용자가 시스템에 언제 액세스하는지 추적하는 상세한 보고서와 알림을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e843-143">To alert you to misuse or abuse, you can use the detailed reporting that tracks when users access the system, along with notifications.</span></span> <span data-ttu-id="8e843-144">암호 [재설정을 배포하려면](#pw_writeback) 먼저 암호 쓰기 저장을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e843-144">You must enable [password writeback](#pw_writeback) before you can deploy password resets.</span></span>

<span data-ttu-id="8e843-145">[암호 재설정을 시작하기 위한 지침](/azure/active-directory/authentication/howto-sspr-deployment)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8e843-145">See the [instructions to roll out password reset](/azure/active-directory/authentication/howto-sspr-deployment).</span></span>