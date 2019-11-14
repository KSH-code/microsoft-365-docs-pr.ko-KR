---
title: Microsoft 365 Business의 Azure AD에 가입 된 장치에서 온-프레미스 리소스에 액세스
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
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: Azure Active Directory에 가입 된 Windows 10 장치에서 비즈니스 앱, 파일 공유 및 프린터와 같은 온-프레미스 리소스에 액세스 하는 방법을 알아봅니다.
ms.openlocfilehash: fdc1eca6913ba6af4f6b65691fdee2165e7c827e
ms.sourcegitcommit: 8193b7da5b1a415835d02ca96883c351df7326ed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/14/2019
ms.locfileid: "38323398"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business"></a><span data-ttu-id="b0719-103">Microsoft 365 Business의 Azure AD에 가입 된 장치에서 온-프레미스 리소스에 액세스</span><span class="sxs-lookup"><span data-stu-id="b0719-103">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business</span></span>

<span data-ttu-id="b0719-104">Azure Active Directory에 가입 된 모든 Windows 10 장치에는 Office 365 앱과 같은 모든 클라우드 기반 리소스에 대 한 액세스 권한이 있으며 Microsoft 365 Business를 통해 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0719-104">Any Windows 10 device that is Azure Active Directory joined has access to all cloud-based resources, such as your Office 365 apps, and can be protected by Microsoft 365 Business.</span></span> <span data-ttu-id="b0719-105">LOB (기간 업무) 앱, 파일 공유 및 프린터와 같은 온-프레미스 리소스에 대 한 액세스를 허용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0719-105">You can also allow access to on-premises resources like line of business (LOB) apps, file shares, and printers.</span></span> <span data-ttu-id="b0719-106">액세스를 허용 하려면 [AZURE AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) 를 사용 하 여 온-프레미스 Active Directory를 Azure Active directory와 동기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0719-106">To allow access, use [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) to synchronize your on-premises Active Directory with Azure Active Directory.</span></span> 

<span data-ttu-id="b0719-107">자세한 내용은 [Azure Active Directory의 장치 관리 소개](https://docs.microsoft.com/azure/active-directory/device-management-introduction)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b0719-107">To learn more, see [Introduction to device management in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/device-management-introduction).</span></span>
<span data-ttu-id="b0719-108">이 단계는 다음 섹션에도 요약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0719-108">The steps are also summarized in the following sections.</span></span>

## <a name="run-azure-ad-connect"></a><span data-ttu-id="b0719-109">Azure AD Connect 실행</span><span class="sxs-lookup"><span data-stu-id="b0719-109">Run Azure AD Connect</span></span>

<span data-ttu-id="b0719-110">조직의 Azure AD 조인 장치에서 온-프레미스 리소스에 액세스 하도록 설정 하려면 다음 단계를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0719-110">Complete the following steps to enable your organization's Azure AD joined devices to access on-premises resources.</span></span>
  
1. <span data-ttu-id="b0719-111">사용자, 그룹 및 연락처를 로컬 Active Directory에서 Azure Active Directory로 동기화 하려면 [Set up directory synchronization For Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846)에 설명 된 대로 디렉터리 동기화 마법사 및 Azure AD Connect를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0719-111">To synchronize your users, groups, and contacts from local Active Directory into Azure Active Directory, run the Directory synchronization wizard and Azure AD Connect as described in [Set up directory synchronization for Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).</span></span>
    
2. <span data-ttu-id="b0719-112">디렉터리 동기화가 완료 되 면 조직의 Windows 10 장치가 Azure AD에 가입 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0719-112">After the directory synchronization is complete, make sure your organization's Windows 10 devices are Azure AD joined.</span></span> <span data-ttu-id="b0719-113">이 단계는 각 Windows 10 장치에서 개별적으로 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0719-113">This step is done individually on each Windows 10 device.</span></span> <span data-ttu-id="b0719-114">자세한 내용은 [Microsoft 365 비즈니스 사용자를 위한 Windows 장치 설정을](set-up-windows-devices.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b0719-114">See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) for details.</span></span> 
    
3. <span data-ttu-id="b0719-115">Windows 10 장치가 Azure AD에 가입 되 면 각 사용자는 자신의 장치를 다시 부팅 하 고 Microsoft 365 Business 자격 증명으로 로그인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0719-115">Once the Windows 10 devices are Azure AD joined, each user must reboot their devices and sign in with their Microsoft 365 Business credentials.</span></span> <span data-ttu-id="b0719-116">이제 모든 장치에 온-프레미스 리소스에 대 한 액세스 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0719-116">All devices now have access to on-premises resources as well.</span></span>
    
<span data-ttu-id="b0719-117">Azure AD에 가입 된 장치에 대 한 온-프레미스 리소스에 액세스 하기 위해 추가 단계를 수행할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b0719-117">No additional steps are required to get access to on-premises resources for Azure AD joined devices.</span></span> <span data-ttu-id="b0719-118">이 기능은 Windows 10에서 기본 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0719-118">This functionality is built into Windows 10.</span></span> 
  
<span data-ttu-id="b0719-119">조직이 앞에서 설명한 Azure AD 조인한 장치 구성에 배포할 준비가 되지 않은 경우 [하이브리드 AZURE AD 조인한 장치 구성을](manage-windows-devices.md)설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b0719-119">If your organization isn't ready to deploy in the Azure AD joined device configuration described above, consider setting up [Hybrid Azure AD Joined device configuration](manage-windows-devices.md).</span></span>
  
### <a name="considerations-when-you-join-windows-devices-to-azure-ad"></a><span data-ttu-id="b0719-120">Azure AD에 Windows 장치를 연결할 때의 고려 사항</span><span class="sxs-lookup"><span data-stu-id="b0719-120">Considerations when you join Windows devices to Azure AD</span></span>

<span data-ttu-id="b0719-121">Azure AD에서 가입한 Windows 장치가 이전에 도메인에 가입 되어 있거나 작업 그룹에 있는 경우 다음 제한 사항을 고려 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b0719-121">If the Windows device that you Azure-AD joined was previously domain-joined or in a workgroup, consider the following limitations:</span></span>
  
- <span data-ttu-id="b0719-122">장치 Azure AD가 조인 되 면 기존 프로필을 참조 하지 않고 새 사용자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b0719-122">When a device Azure AD joins, it creates a new user without referencing an existing profile.</span></span> <span data-ttu-id="b0719-123">프로필을 수동으로 마이그레이션해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0719-123">Profiles must be manually migrated.</span></span> <span data-ttu-id="b0719-124">사용자 프로필에는 즐겨찾기, 로컬 파일, 브라우저 설정 및 시작 메뉴 설정과 같은 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0719-124">A user profile contains information like favorites, local files, browser settings, and Start menu settings.</span></span> <span data-ttu-id="b0719-125">기존 파일 및 설정을 새 프로필에 매핑하는 타사 도구를 찾는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b0719-125">A best approach is to find a third-party tool to map existing files and settings to the new profile.</span></span>

- <span data-ttu-id="b0719-126">장치에서 GPO (그룹 정책 개체)를 사용 하는 경우 일부 Gpo에는 Intune의 CSP ( [구성 서비스 공급자](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) )가 제공 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0719-126">If the device is using Group Policy Objects (GPO), some GPOs may not have a comparable [Configuration Service Provider](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) in Intune.</span></span> <span data-ttu-id="b0719-127">[Mmat 도구](https://www.microsoft.com/download/details.aspx?id=45520) 를 실행 하 여 기존 gpo에 대해 비교 가능한 csp를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b0719-127">Run the [MMAT tool](https://www.microsoft.com/download/details.aspx?id=45520) to find comparable CSPs for existing GPOs.</span></span>

- <span data-ttu-id="b0719-128">사용자는 Active Directory 인증을 통해 작동 하는 응용 프로그램을 인증할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b0719-128">Users won't be able to authenticate to applications that depend on Active Directory authentication.</span></span> <span data-ttu-id="b0719-129">레거시 앱을 평가 하 고 가능한 경우 최신 인증을 사용 하는 앱으로 업데이트 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b0719-129">Evaluate the legacy app and consider updating to an app that uses modern Auth, if possible.</span></span>

- <span data-ttu-id="b0719-130">Active Directory 프린터 검색이 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b0719-130">Active Directory printer discovery won't work.</span></span> <span data-ttu-id="b0719-131">모든 사용자에 대해 직접 프린터 경로를 제공 하거나 [하이브리드 클라우드 인쇄](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0719-131">You can provide direct printer paths for all users or use [Hybrid Cloud Print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).</span></span>
