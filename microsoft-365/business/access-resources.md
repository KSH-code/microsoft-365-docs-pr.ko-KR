---
title: Microsoft 365 비즈니스의 Azure AD 조인 장치에서 온-프레미스 리소스에 액세스
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.collection: M365-subscription-management
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: Azure Active Directory에 연결된 Windows 10 장치의 LOB(기간 업무) 앱, 파일 공유 및 프린터와 같은 온-프레미스 리소스에 액세스하는 방법을 알아봅니다.
ms.openlocfilehash: b78509d72cbd9b3c121039c4965625bf5c21c7e0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913525"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business-premium"></a><span data-ttu-id="ae7c6-103">Microsoft 365 Business Premium의 Azure AD 가입 장치에서의 사내 리소스 액세스</span><span class="sxs-lookup"><span data-stu-id="ae7c6-103">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business Premium</span></span>

<span data-ttu-id="ae7c6-104">이 문서는 Microsoft 365 Business Premium에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae7c6-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="ae7c6-105">Azure Active Directory에 가입된 모든 Windows 10 디바이스는 Microsoft 365 앱과 같은 모든 클라우드 기반 리소스에 액세스할 수 있으며 Microsoft 365 Business Premium으로 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae7c6-105">Any Windows 10 device that is Azure Active Directory joined has access to all cloud-based resources, such as your Microsoft 365 apps, and can be protected by Microsoft 365 Business Premium.</span></span> <span data-ttu-id="ae7c6-106">LOB(기간 업무) 앱, 파일 공유 및 프린터와 같은 온-프레미스 리소스에 대한 액세스를 허용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae7c6-106">You can also allow access to on-premises resources like line of business (LOB) apps, file shares, and printers.</span></span> <span data-ttu-id="ae7c6-107">액세스를 허용하려면 [Azure AD Connect](/azure/active-directory/connect/active-directory-aadconnect)를 사용하여 온-프레미스 Active Directory를 Azure Active Directory와 동기화합니다.</span><span class="sxs-lookup"><span data-stu-id="ae7c6-107">To allow access, use [Azure AD Connect](/azure/active-directory/connect/active-directory-aadconnect) to synchronize your on-premises Active Directory with Azure Active Directory.</span></span> 

<span data-ttu-id="ae7c6-108">자세한 내용은 [Azure Active Directory에서 장치 관리 소개](/azure/active-directory/device-management-introduction)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ae7c6-108">To learn more, see [Introduction to device management in Azure Active Directory](/azure/active-directory/device-management-introduction).</span></span>
<span data-ttu-id="ae7c6-109">다음 섹션에서도 단계는 요약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae7c6-109">The steps are also summarized in the following sections.</span></span>
 
## <a name="run-azure-ad-connect"></a><span data-ttu-id="ae7c6-110">Azure AD Connect를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ae7c6-110">Run Azure AD Connect</span></span>

<span data-ttu-id="ae7c6-111">조직의 Azure AD 조인 장치에서 온-프레미스 리소스에 액세스하도록 설정하려면 다음 단계를 완료하세요.</span><span class="sxs-lookup"><span data-stu-id="ae7c6-111">Complete the following steps to enable your organization's Azure AD joined devices to access on-premises resources.</span></span>
  
1. <span data-ttu-id="ae7c6-112">로컬 Active Directory의 사용자, 그룹 및 연락처를 Azure Active Directory와 동기화하려면 [Office 365에 대한 디렉터리 동기화 설정](../enterprise/set-up-directory-synchronization.md)에서 설명한 대로 디렉터리 동기화 마법사 및 Azure AD Connect를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ae7c6-112">To synchronize your users, groups, and contacts from local Active Directory into Azure Active Directory, run the Directory synchronization wizard and Azure AD Connect as described in [Set up directory synchronization for Office 365](../enterprise/set-up-directory-synchronization.md).</span></span>
    
2. <span data-ttu-id="ae7c6-113">디렉터리 동기화가 완료되면 조직의 Windows 10 장치가 Azure AD에 연결되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ae7c6-113">After the directory synchronization is complete, make sure your organization's Windows 10 devices are Azure AD joined.</span></span> <span data-ttu-id="ae7c6-114">이 단계는 각각의 Windows 10 장치에서 개별적으로 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae7c6-114">This step is done individually on each Windows 10 device.</span></span> <span data-ttu-id="ae7c6-115">자세한 [내용은 Microsoft 365 Business Premium](set-up-windows-devices.md) 사용자를 위한 Windows 장치 설치를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="ae7c6-115">See [Set up Windows devices for Microsoft 365 Business Premium users](set-up-windows-devices.md) for details.</span></span> 
    
3. <span data-ttu-id="ae7c6-116">Windows 10 장치가 Azure AD에 가입된 후 각 사용자는 장치를 다시 시작하고 Microsoft 365 Business Premium 자격 증명으로 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae7c6-116">Once the Windows 10 devices are Azure AD joined, each user must reboot their devices and sign in with their Microsoft 365 Business Premium credentials.</span></span> <span data-ttu-id="ae7c6-117">이제 모든 장치에서 온-프레미스 리소스에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae7c6-117">All devices now have access to on-premises resources as well.</span></span>
    
<span data-ttu-id="ae7c6-118">Azure AD 조인 장치에 대한 온-프레미스 리소스에 액세스하는 데 필요한 추가 단계는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ae7c6-118">No additional steps are required to get access to on-premises resources for Azure AD joined devices.</span></span> <span data-ttu-id="ae7c6-119">이 기능은 Windows 10에서 기본 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae7c6-119">This functionality is built into Windows 10.</span></span> 

<span data-ttu-id="ae7c6-120">WHFB 자격 증명 로그인을 통해 PIN/Bio-metric과 같은 암호 방식 이외에 AADJ 장치에 로그인한 다음 온-프레미스 리소스(공유, 프린터 등)에 액세스하려는 경우 https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="ae7c6-120">If you have plans to login to the AADJ device other than password method Like PIN/Bio-metric via WHFB credential login and then access on-premise resources (shares,printers..etc), please follow https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base</span></span>
  
<span data-ttu-id="ae7c6-121">조직에서 앞서 설명한 Azure AD 조인 장치 구성에 배포할 준비가 되지 않은 경우 [하이브리드 Azure AD 조인 장치 구성](manage-windows-devices.md)을 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ae7c6-121">If your organization isn't ready to deploy in the Azure AD joined device configuration described above, consider setting up [Hybrid Azure AD Joined device configuration](manage-windows-devices.md).</span></span>
  
### <a name="considerations-when-you-join-windows-devices-to-azure-ad"></a><span data-ttu-id="ae7c6-122">Azure AD에 Windows 장치를 연결할 때의 고려 사항</span><span class="sxs-lookup"><span data-stu-id="ae7c6-122">Considerations when you join Windows devices to Azure AD</span></span>

<span data-ttu-id="ae7c6-123">Azure AD에 연결된 Windows 장치가 이전에 도메인에 가입된 경우 또는 작업 그룹에 있는 경우 다음 제한 사항을 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="ae7c6-123">If the Windows device that you Azure-AD joined was previously domain-joined or in a workgroup, consider the following limitations:</span></span>
  
- <span data-ttu-id="ae7c6-124">장치에 Azure AD가 연결되면 기존 프로필을 참조하지 않고 새 사용자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ae7c6-124">When a device Azure AD joins, it creates a new user without referencing an existing profile.</span></span> <span data-ttu-id="ae7c6-125">프로필은 수동으로 마이그레이션해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae7c6-125">Profiles must be manually migrated.</span></span> <span data-ttu-id="ae7c6-126">사용자 프로필에는 즐겨찾기, 로컬 파일, 브라우저 설정 및 시작 메뉴 설정과 같은 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae7c6-126">A user profile contains information like favorites, local files, browser settings, and Start menu settings.</span></span> <span data-ttu-id="ae7c6-127">가장 좋은 방법은 기존 파일 및 설정을 새 프로필로 매핑하는 타사 도구를 찾는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ae7c6-127">A best approach is to find a third-party tool to map existing files and settings to the new profile.</span></span>

- <span data-ttu-id="ae7c6-128">장치가 GPO(그룹 정책 개체)를 사용하는 경우 일부 GPO는 Intune에서 유사한 [Configuration Service Provider](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers)(CSP)를 갖지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae7c6-128">If the device is using Group Policy Objects (GPO), some GPOs may not have a comparable [Configuration Service Provider](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) in Intune.</span></span> <span data-ttu-id="ae7c6-129">[MMAT 도구](https://www.microsoft.com/download/details.aspx?id=45520)를 실행하여 기존 GPO와 유사한 CSP를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="ae7c6-129">Run the [MMAT tool](https://www.microsoft.com/download/details.aspx?id=45520) to find comparable CSPs for existing GPOs.</span></span>

- <span data-ttu-id="ae7c6-130">사용자가 Active Directory 인증을 사용하는 응용 프로그램에 인증하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae7c6-130">Users might not be able to authenticate to applications that depend on Active Directory authentication.</span></span> <span data-ttu-id="ae7c6-131">레거시 앱을 평가하고 가능한 경우 최신 인증을 사용하는 앱으로 업데이트하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ae7c6-131">Evaluate the legacy app and consider updating to an app that uses modern Auth, if possible.</span></span>

- <span data-ttu-id="ae7c6-132">Active Directory 프린터 검색이 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ae7c6-132">Active Directory printer discovery won't work.</span></span> <span data-ttu-id="ae7c6-133">모든 사용자에게 직접 프린터 경로를 제공하거나 유니버설 [인쇄를 사용할 수 있습니다.](/universal-print/)</span><span class="sxs-lookup"><span data-stu-id="ae7c6-133">You can provide direct printer paths for all users or use [Universal Print](/universal-print/).</span></span>