---
title: Microsoft Managed Desktop 기술
description: 이 항목에서는 Microsoft Managed Desktop에 사용 되는 기술과 앱을 소개 합니다.
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: beab5df5b978cc3e2fd6dd345609a22209501298
ms.sourcegitcommit: 237589a0c8a24510e5c8f3b8b4747d944ad0afbf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/20/2019
ms.locfileid: "37113721"
---
# <a name="microsoft-managed-desktop-technologies"></a><span data-ttu-id="659c3-104">Microsoft Managed Desktop 기술</span><span class="sxs-lookup"><span data-stu-id="659c3-104">Microsoft Managed Desktop technologies</span></span>

<span data-ttu-id="659c3-105">이 항목에서는 Microsoft Managed Desktop에 사용 되는 기술과 앱을 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="659c3-105">This topic lists the technologies and apps used in Microsoft Managed Desktop.</span></span>

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

<span data-ttu-id="659c3-106">Microsoft 365 Enterprise 라이선스는 모든 Microsoft 관리 되는 데스크톱 사용자에 게 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="659c3-106">Microsoft 365 Enterprise licensing is required for all Microsoft Managed Desktop users.</span></span> <span data-ttu-id="659c3-107">서비스에 대 한 라이선스 요구 사항에 대 한 자세한 내용은 [Microsoft Managed Desktop의 필수 구성 요소](../get-ready/prerequisites.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="659c3-107">For more information on licensing requirements for the service, see [Prerequisites for Microsoft Managed Desktop](../get-ready/prerequisites.md).</span></span>

<span data-ttu-id="659c3-108">이 항목에서는 필요한 엔터프라이즈 라이선스에 포함 된 구성 요소에 대해 설명 하 고, 서비스가 Microsoft Managed Desktop 장치에서 각 구성 요소를 사용 하는 방법에 대 한 설명을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="659c3-108">This topic summarizes the components included in the required Enterprise licenses, with a description of how the service uses each component with Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="659c3-109">각 영역에 대 한 특정 역할과 책임은 Microsoft Managed Desktop 설명서 전반에 자세히 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="659c3-109">Specific roles and responsibilities for each area are detailed throughout Microsoft Managed Desktop documentation.</span></span> 

## <a name="office-365-e3-or-e5"></a><span data-ttu-id="659c3-110">Office 365 E3 또는 E5</span><span class="sxs-lookup"><span data-stu-id="659c3-110">Office 365 E3 or E5</span></span>
 |
 --- | ---
<span data-ttu-id="659c3-111">Office 365 ProPlus (64 비트)</span><span class="sxs-lookup"><span data-stu-id="659c3-111">Office 365 ProPlus (64-bit)</span></span> | <span data-ttu-id="659c3-112">이러한 Office 응용 프로그램은 Word, Excel, PowerPoint, Outlook, Publisher, Access, 비즈니스용 Skype, OneNote와 함께 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="659c3-112">These Office applications will be shipped with the device: Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for Business, OneNote.</span></span><br><br><span data-ttu-id="659c3-113">64 비트 정식 버전의 Microsoft Project 및 Microsoft Visio는 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="659c3-113">The 64-bit full versions of Microsoft Project and Microsoft Visio are not included.</span></span> <span data-ttu-id="659c3-114">그러나 이러한 응용 프로그램의 설치가 Office 365 ProPlus 설치에 따라 달라 지기 때문에 Microsoft Managed Desktop은 기본 Microsoft Intune 배포 및 보안 그룹을 만들어 이러한 응용 프로그램을 사용이 허가 된 것으로 배포 하는 데 사용할 수 있습니다. 최종 사용자</span><span class="sxs-lookup"><span data-stu-id="659c3-114">However, since the installation of these applications depends on the Office 365 ProPlus installation, Microsoft Managed Desktop has created default Microsoft Intune deployments and security groups that you can then use to deploy these applications to licensed end users.</span></span> <span data-ttu-id="659c3-115">자세한 내용은 microsoft [Managed 데스크톱 장치에서 Microsoft Project 또는 Microsoft Visio 설치](../get-started/project-visio.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="659c3-115">For more information, see [Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices](../get-started/project-visio.md).</span></span>
<span data-ttu-id="659c3-116">비즈니스용 OneDrive</span><span class="sxs-lookup"><span data-stu-id="659c3-116">OneDrive for Business</span></span> |<span data-ttu-id="659c3-117">Azure Active Directory Single Sign-on은 최종 사용자가 비즈니스용 OneDrive에 처음 로그인 할 때 사용 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="659c3-117">Azure Active Directory Single Sign On is enabled for end users upon first sign in to OneDrive for Business.</span></span><br><br><span data-ttu-id="659c3-118">"Desktop", "Document" 및 "Pictures" 폴더에 대해 알려진 폴더 리디렉션이 포함 됩니다. Microsoft Managed Desktop에서 사용 하도록 설정 하 고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="659c3-118">Known Folder Redirection for "Desktop", "Document", and "Pictures" folders is included; enabled and configured by Microsoft Managed Desktop.</span></span> 
<span data-ttu-id="659c3-119">스토어 앱</span><span class="sxs-lookup"><span data-stu-id="659c3-119">Store Apps</span></span> |    <span data-ttu-id="659c3-120">Microsoft Sway 및 Power BI는 장치와 함께 제공 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="659c3-120">Microsoft Sway and Power BI are not shipped with the device.</span></span> <span data-ttu-id="659c3-121">이러한 앱은 Microsoft Store에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="659c3-121">These apps are available for download from Microsoft Store.</span></span>
<span data-ttu-id="659c3-122">Win32 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="659c3-122">Win32 Applications</span></span> |    <span data-ttu-id="659c3-123">팀은 장치와 함께 제공 되지 않지만 microsoft에서 관리 되는 데스크톱 장치용으로 패키지화 되 고 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="659c3-123">Teams is not shipped with the device, but is packaged and provided by Microsoft for Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="659c3-124">Azure Information Protection 클라이언트는 장치와 함께 제공 되지 않지만이 패키지를 배포용으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="659c3-124">Azure Information Protection Client is not shipped with the device, but you can have this packaged for deployment.</span></span> 
<span data-ttu-id="659c3-125">웹 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="659c3-125">Web Applications</span></span> |  <span data-ttu-id="659c3-126">Yammer, Office for browser, Delve, 흐름, StaffHub, PowerApps 및 Planner가 장치와 함께 제공 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="659c3-126">Yammer, Office in a browser, Delve, Flow, StaffHub, PowerApps, and Planner are not shipped with the device.</span></span> <span data-ttu-id="659c3-127">사용자는 브라우저를 사용 하 여 이러한 응용 프로그램의 웹 버전에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="659c3-127">Users can access the web version of these applications with a browser.</span></span>


## <a name="windows-10-enterprise-e3-or-e5"></a><span data-ttu-id="659c3-128">Windows 10 Enterprise E3 또는 E5</span><span class="sxs-lookup"><span data-stu-id="659c3-128">Windows 10 Enterprise E3 or E5</span></span>

 |
 --- | ---
<span data-ttu-id="659c3-129">Application Virtualization (App-v)</span><span class="sxs-lookup"><span data-stu-id="659c3-129">Application Virtualization (App-V)</span></span> |    <span data-ttu-id="659c3-130">고객은 Intune Win32 앱 관리 클라이언트를 사용 하 여 App-v 패키지를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="659c3-130">Customers can deploy App-V packages using the Intune Win32 app management client.</span></span>
<span data-ttu-id="659c3-131">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="659c3-131">Microsoft Defender Advanced Threat Protection</span></span> |  <span data-ttu-id="659c3-132">Microsoft Managed Desktop은이를 사용 하 여 장치 보안을 모니터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="659c3-132">Microsoft Managed Desktop uses this to monitor device security.</span></span> 

## <a name="enterprise-mobility--security-e5"></a><span data-ttu-id="659c3-133">Enterprise Mobility + Security E5</span><span class="sxs-lookup"><span data-stu-id="659c3-133">Enterprise Mobility + Security E5</span></span>

 |
 --- | ---
<span data-ttu-id="659c3-134">Enterprise Mobility + Security E3</span><span class="sxs-lookup"><span data-stu-id="659c3-134">Enterprise Mobility + Security E3</span></span><br><span data-ttu-id="659c3-135">Azure Active Directory Premium P2</span><span class="sxs-lookup"><span data-stu-id="659c3-135">Azure Active Directory Premium P2</span></span> |    <span data-ttu-id="659c3-136">Enterprise Mobility + Security E3 및 Azure Active Directory Premium P2의 모든 기능을 사용 하 여 MDM 장치를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="659c3-136">You can use all features of Enterprise Mobility + Security E3 and Azure Active Directory Premium P2 to manage MDM devices.</span></span>
<span data-ttu-id="659c3-137">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="659c3-137">Microsoft Cloud App Security</span></span> |  <span data-ttu-id="659c3-138">이 선택적 기능은 Microsoft Managed Desktop에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="659c3-138">You can use this optional feature with Microsoft Managed Desktop.</span></span>
<span data-ttu-id="659c3-139">Azure Information Protection P2</span><span class="sxs-lookup"><span data-stu-id="659c3-139">Azure Information Protection P2</span></span>  | <span data-ttu-id="659c3-140">이 선택적 기능은 Microsoft Managed Desktop에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="659c3-140">You can use this optional feature with Microsoft Managed Desktop.</span></span>
