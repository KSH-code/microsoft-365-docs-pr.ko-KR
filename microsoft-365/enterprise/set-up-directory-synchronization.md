---
title: 사용자에 대한 디렉터리 동기화 Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED15
- MBS150
- BCS160
ms.assetid: 1b3b5318-6977-42ed-b5c7-96fa74b08846
description: Microsoft 365 Active Directory 간에 디렉터리 동기화를 설정하는 방법을 알아보십시오.
ms.openlocfilehash: 51cf52bd81004157606c884fd4f0b5d3604b877a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924907"
---
# <a name="set-up-directory-synchronization-for-microsoft-365"></a><span data-ttu-id="ef1f7-103">사용자에 대한 디렉터리 동기화 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ef1f7-103">Set up directory synchronization for Microsoft 365</span></span>

<span data-ttu-id="ef1f7-104">*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="ef1f7-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="ef1f7-105">Microsoft 365 Azure AD(Azure Active Directory) 테넌트에서 클라우드 기반 리소스에 액세스하기 위한 인증 및 사용 권한에 대한 ID를 저장하고 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="ef1f7-105">Microsoft 365 uses an Azure Active Directory (Azure AD) tenant to store and manage identities for authentication and permissions to access cloud-based resources.</span></span> 

<span data-ttu-id="ef1f7-106">AD DS(Active Directory 도메인 서비스) 도메인 또는 포리스트가 있는 경우 AD DS 사용자 계정, 그룹 및 연락처를 Microsoft 365 Azure AD 테넌트와 동기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef1f7-106">If you have an on-premises Active Directory Domain Services (AD DS) domain or forest, you can synchronize your AD DS user accounts, groups, and contacts with the Azure AD tenant of your Microsoft 365 subscription.</span></span> <span data-ttu-id="ef1f7-107">이 ID는 하이브리드 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ef1f7-107">This is hybrid identity for Microsoft 365.</span></span> <span data-ttu-id="ef1f7-108">구성 요소는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ef1f7-108">Here are its components.</span></span>

![사용자에 대한 디렉터리 동기화 구성 Microsoft 365](../media/about-microsoft-365-identity/hybrid-identity.png)

<span data-ttu-id="ef1f7-110">Azure AD 커넥트 실행되어 AD DS를 Azure AD 테넌트와 동기화합니다.</span><span class="sxs-lookup"><span data-stu-id="ef1f7-110">Azure AD Connect runs on an on-premises server and synchronizes your AD DS with the Azure AD tenant.</span></span> <span data-ttu-id="ef1f7-111">디렉터리 동기화와 함께 다음 인증 옵션을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef1f7-111">Along with directory synchronization, you can also specify these authentication options:</span></span>

- <span data-ttu-id="ef1f7-112">PHS(암호 해시 동기화)</span><span class="sxs-lookup"><span data-stu-id="ef1f7-112">Password hash synchronization (PHS)</span></span>

  <span data-ttu-id="ef1f7-113">Azure AD는 인증 자체를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="ef1f7-113">Azure AD performs the authentication itself.</span></span>

- <span data-ttu-id="ef1f7-114">통과 인증(PTA)</span><span class="sxs-lookup"><span data-stu-id="ef1f7-114">Pass-through authentication (PTA)</span></span>

  <span data-ttu-id="ef1f7-115">Azure AD에는 AD DS가 인증을 수행하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef1f7-115">Azure AD has AD DS perform the authentication.</span></span>

- <span data-ttu-id="ef1f7-116">페더레이션 인증</span><span class="sxs-lookup"><span data-stu-id="ef1f7-116">Federated authentication</span></span>

  <span data-ttu-id="ef1f7-117">Azure AD는 인증을 요청하는 클라이언트 컴퓨터를 다른 ID 공급자에게 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="ef1f7-117">Azure AD refers the client computer requesting authentication to another identity provider.</span></span>

<span data-ttu-id="ef1f7-118">자세한 [내용은 하이브리드 ID를](plan-for-directory-synchronization.md) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ef1f7-118">See [Hybrid identities](plan-for-directory-synchronization.md) for more information.</span></span>
  
## <a name="1-review-prerequisites-for-azure-ad-connect"></a><span data-ttu-id="ef1f7-119">1. Azure AD 2013의 선행 커넥트</span><span class="sxs-lookup"><span data-stu-id="ef1f7-119">1. Review prerequisites for Azure AD Connect</span></span>

<span data-ttu-id="ef1f7-120">Azure AD 구독을 무료로 받을 수 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ef1f7-120">You get a free Azure AD subscription with your Microsoft 365 subscription.</span></span> <span data-ttu-id="ef1f7-121">디렉터리 동기화를 설정하면 Azure AD 커넥트 서버 중 하나에 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef1f7-121">When you set up directory synchronization, you will install Azure AD Connect on one of your on-premises servers.</span></span>
  
<span data-ttu-id="ef1f7-122">이 Microsoft 365 다음을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef1f7-122">For Microsoft 365 you'll need to:</span></span>
  
- <span data-ttu-id="ef1f7-123">사내 도메인을 검증합니다.</span><span class="sxs-lookup"><span data-stu-id="ef1f7-123">Verify your on-premises domain.</span></span> <span data-ttu-id="ef1f7-124">Azure AD 커넥트 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="ef1f7-124">The Azure AD Connect wizard guides you through this.</span></span>
- <span data-ttu-id="ef1f7-125">테넌트 및 AD DS의 관리자 계정의 Microsoft 365 이름과 암호를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="ef1f7-125">Obtain the user names and passwords for the admin accounts of your Microsoft 365 tenant and AD DS.</span></span>

<span data-ttu-id="ef1f7-126">Azure AD 2016을 설치하는 커넥트 서버의 경우 다음이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ef1f7-126">For your on-premises server on which you install Azure AD Connect, you'll need:</span></span>
  
|<span data-ttu-id="ef1f7-127">**서버 OS**</span><span class="sxs-lookup"><span data-stu-id="ef1f7-127">**Server OS**</span></span>|<span data-ttu-id="ef1f7-128">**기타 소프트웨어**</span><span class="sxs-lookup"><span data-stu-id="ef1f7-128">**Other software**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ef1f7-129">Windows Server 2012 R2 이상</span><span class="sxs-lookup"><span data-stu-id="ef1f7-129">Windows Server 2012 R2 and later</span></span> | <span data-ttu-id="ef1f7-130">- PowerShell은 기본적으로 설치되어 있습니다. 필요한 작업은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ef1f7-130">- PowerShell is installed by default, no action is required.</span></span>  <br> <span data-ttu-id="ef1f7-131">- Net 4.5.1 이상 릴리스는 업데이트 업데이트를 통해 Windows 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef1f7-131">- Net 4.5.1 and later releases are offered through Windows Update.</span></span> <span data-ttu-id="ef1f7-132">제어판에서 Windows 최신 업데이트를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef1f7-132">Make sure you have installed the latest updates to Windows Server in the Control Panel.</span></span> |
|<span data-ttu-id="ef1f7-133">Windows Server 2008 R2 서비스 팩 1(SP1) 또는 Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="ef1f7-133">Windows Server 2008 R2 with Service Pack 1 (SP1)\*\* or Windows Server 2012</span></span> | <span data-ttu-id="ef1f7-134">- 최신 버전의 PowerShell은 4.0 Windows Management Framework 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef1f7-134">- The latest version of PowerShell is available in Windows Management Framework 4.0.</span></span> <span data-ttu-id="ef1f7-135">Microsoft 다운로드 [센터에서 검색합니다.](https://go.microsoft.com/fwlink/p/?LinkId=717996)</span><span class="sxs-lookup"><span data-stu-id="ef1f7-135">Search for it on [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996).</span></span>  <br> <span data-ttu-id="ef1f7-136">- .Net 4.5.1 이상 릴리스는 [Microsoft 다운로드 센터에서 사용할 수 있습니다.](https://go.microsoft.com/fwlink/p/?LinkId=717996)</span><span class="sxs-lookup"><span data-stu-id="ef1f7-136">- .Net 4.5.1 and later releases are available on [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996).</span></span> |
|<span data-ttu-id="ef1f7-137">Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="ef1f7-137">Windows Server 2008</span></span> | <span data-ttu-id="ef1f7-138">- 지원되는 최신 버전의 PowerShell은 Microsoft Windows Management Framework 3.0에서 사용할 [수 있습니다.](https://go.microsoft.com/fwlink/p/?LinkId=717996)</span><span class="sxs-lookup"><span data-stu-id="ef1f7-138">- The latest supported version of PowerShell is available in Windows Management Framework 3.0, available on [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996).</span></span>  <br> <span data-ttu-id="ef1f7-139">- .Net 4.5.1 이상 릴리스는 [Microsoft 다운로드 센터에서 사용할 수 있습니다.](https://go.microsoft.com/fwlink/p/?LinkId=717996)</span><span class="sxs-lookup"><span data-stu-id="ef1f7-139">- .Net 4.5.1 and later releases are available on [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996).</span></span> |

<span data-ttu-id="ef1f7-140">Azure AD Azure Active Directory 커넥트 하드웨어, [소프트웨어,](/azure/active-directory/hybrid/how-to-connect-install-prerequisites) 계정 및 사용 권한 요구 사항, SSL 인증서 요구 사항 및 개체 제한에 대한 자세한 내용은 커넥트.</span><span class="sxs-lookup"><span data-stu-id="ef1f7-140">See [Prerequisites for Azure Active Directory Connect](/azure/active-directory/hybrid/how-to-connect-install-prerequisites) for the details of hardware, software, account and permissions requirements, SSL certificate requirements, and object limits for Azure AD Connect.</span></span>
  
<span data-ttu-id="ef1f7-141">또한 Azure AD 커넥트 릴리스 기록을 검토하여 각 [릴리스에](/azure/active-directory/hybrid/reference-connect-version-history) 포함 및 고정된 버전을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef1f7-141">You can also review the Azure AD Connect [version release history](/azure/active-directory/hybrid/reference-connect-version-history) to see what is included and fixed in each release.</span></span>

## <a name="2-install-azure-ad-connect-and-configure-directory-synchronization"></a><span data-ttu-id="ef1f7-142">2. Azure AD 커넥트 설치 및 디렉터리 동기화 구성</span><span class="sxs-lookup"><span data-stu-id="ef1f7-142">2. Install Azure AD Connect and configure directory synchronization</span></span>

<span data-ttu-id="ef1f7-143">시작하기 전에 다음이 있는지 확인한 후 다음을 선택해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef1f7-143">Before you begin, make sure you have:</span></span>

- <span data-ttu-id="ef1f7-144">전역 관리자의 사용자 Microsoft 365 암호</span><span class="sxs-lookup"><span data-stu-id="ef1f7-144">The user name and password of a Microsoft 365 global admin</span></span>
- <span data-ttu-id="ef1f7-145">AD DS 도메인 관리자의 사용자 이름 및 암호</span><span class="sxs-lookup"><span data-stu-id="ef1f7-145">The user name and password of an AD DS domain administrator</span></span>
- <span data-ttu-id="ef1f7-146">어떤 인증 방법(PHS, PTA, 페더래드)</span><span class="sxs-lookup"><span data-stu-id="ef1f7-146">Which authentication method (PHS, PTA, federated)</span></span>
- <span data-ttu-id="ef1f7-147">[Azure AD Seamless SSO(Single Sign-On)를](/azure/active-directory/hybrid/how-to-connect-sso) 사용할지 여부</span><span class="sxs-lookup"><span data-stu-id="ef1f7-147">Whether you want to use [Azure AD Seamless Single Sign-on (SSO)](/azure/active-directory/hybrid/how-to-connect-sso)</span></span>

<span data-ttu-id="ef1f7-148">다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="ef1f7-148">Follow these steps:</span></span>

1. <span data-ttu-id="ef1f7-149">Microsoft 365 [센터에 로그인하고](https://admin.microsoft.com) 왼쪽 탐색에서 https://admin.microsoft.com) **사용자** \> **활성** 사용자를 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="ef1f7-149">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) (https://admin.microsoft.com) and choose **Users** \> **Active Users** on the left navigation.</span></span>
2. <span data-ttu-id="ef1f7-150">활성 **사용자 페이지에서** 더 **(세** 점) 디렉터리 동기화 \> **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ef1f7-150">On the **Active users** page, choose **More** (three dots) \> **Directory synchronization**.</span></span>
  
3. <span data-ttu-id="ef1f7-151">Azure Active Directory **준비** 페이지에서 다운로드 센터로 이동을 선택하여 **Azure AD** 커넥트 도구 링크를 시작하세요.</span><span class="sxs-lookup"><span data-stu-id="ef1f7-151">On the **Azure Active Directory preparation** page, select the **Go to the Download center to get the Azure AD Connect tool** link to get started.</span></span> 
4. <span data-ttu-id="ef1f7-152">Azure AD 커넥트 Azure AD 커넥트 [설치 로드맵의 단계를 따릅니다.](/azure/active-directory/hybrid/how-to-connect-install-roadmap)</span><span class="sxs-lookup"><span data-stu-id="ef1f7-152">Follow the steps in [Azure AD Connect and Azure AD Connect Health installation roadmap](/azure/active-directory/hybrid/how-to-connect-install-roadmap).</span></span>

## <a name="3-finish-setting-up-domains"></a><span data-ttu-id="ef1f7-153">3. 도메인 설정 완료</span><span class="sxs-lookup"><span data-stu-id="ef1f7-153">3. Finish setting up domains</span></span>

<span data-ttu-id="ef1f7-154">DNS 레코드를 관리할 때 도메인에 Microsoft 365 [DNS](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) 레코드 만들기의 단계에 따라 도메인 설정을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="ef1f7-154">Follow the steps in [Create DNS records for Microsoft 365 when you manage your DNS records](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) to finish setting up your domains.</span></span>

## <a name="next-step"></a><span data-ttu-id="ef1f7-155">다음 단계</span><span class="sxs-lookup"><span data-stu-id="ef1f7-155">Next step</span></span>

[<span data-ttu-id="ef1f7-156">사용자 계정에 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="ef1f7-156">Assign licenses to user accounts</span></span>](assign-licenses-to-user-accounts.md)