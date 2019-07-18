---
title: Microsoft Managed Desktop 기술
description: 이 항목에서는 Microsoft Managed Desktop에 사용 되는 기술과 앱을 소개 합니다.
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 설명서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.collection: M365-modern-desktop
ms.openlocfilehash: 914a90b4267132c9cb942740ceb974b084bcdf82
ms.sourcegitcommit: 2f4a61f02ea90102ded8e5d71c9b78a1f7f6b789
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/18/2019
ms.locfileid: "35778093"
---
# <a name="microsoft-managed-desktop-technologies"></a><span data-ttu-id="87e64-104">Microsoft Managed Desktop 기술</span><span class="sxs-lookup"><span data-stu-id="87e64-104">Microsoft Managed Desktop technologies</span></span>

<span data-ttu-id="87e64-105">이 항목에서는 Microsoft Managed Desktop에 사용 되는 기술과 앱을 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="87e64-105">This topic lists the technologies and apps used in Microsoft Managed Desktop.</span></span>

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

<span data-ttu-id="87e64-106">Microsoft 365 Enterprise 라이선스는 모든 Microsoft 관리 되는 데스크톱 사용자에 게 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="87e64-106">Microsoft 365 Enterprise licensing is required for all Microsoft Managed Desktop users.</span></span> <span data-ttu-id="87e64-107">서비스에 대 한 라이선스 요구 사항에 대 한 자세한 내용은 [Microsoft Managed Desktop의 필수 구성 요소](../get-ready/prerequisites.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="87e64-107">For more information on licensing requirements for the service, see [Prerequisites for Microsoft Managed Desktop](../get-ready/prerequisites.md).</span></span>

<span data-ttu-id="87e64-108">다음은 필요한 엔터프라이즈 라이선스에 포함 된 모든 구성 요소와 서비스가 Microsoft Managed Desktop 장치에서 각 구성 요소를 사용 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="87e64-108">The following are all components that are included in the required Enterprise licenses and how the service uses each component with Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="87e64-109">각 영역에 대 한 특정 역할과 책임은 Microsoft Managed Desktop 항목 전체에 자세히 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87e64-109">Specific roles and responsibilities for each area are detailed throughout the Microsoft Managed Desktop topic.</span></span> 

## <a name="office-365-e3"></a><span data-ttu-id="87e64-110">Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="87e64-110">Office 365 E3</span></span>
 |
 --- | ---
<span data-ttu-id="87e64-111">Office 365 Standard Suite (64 비트) \*</span><span class="sxs-lookup"><span data-stu-id="87e64-111">Office 365 Standard Suite (64bit)\*</span></span> | <span data-ttu-id="87e64-112">표준 Office 응용 프로그램 제품군은 Word, Excel, PowerPoint, Outlook, Publisher, Access, 비즈니스용 Skype, OneNote와 함께 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87e64-112">The standard Office Suite of applications will be shipped with the device: Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for Business, OneNote.</span></span><br><br><span data-ttu-id="87e64-113">C2R (64 비트)를 클릭 하 여 실행 (전체 버전의 Microsoft Project) 및 Microsoft Visio는 Office 365 Standard Suite에 포함 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="87e64-113">The 64bit Click to Run (C2R) full versions of Microsoft Project and Microsoft Visio are not included in the Office 365 Standard Suite.</span></span>  <span data-ttu-id="87e64-114">그러나 이러한 응용 프로그램의 설치가 표준 Office 제품군 설치에 종속 되기 때문에 Microsoft Managed Desktop은 고객이 이러한 응용 프로그램을 배포 하는 데 사용할 기본 Intune 배포 및 보안 그룹을 만들었습니다. 최종 사용자 사용권</span><span class="sxs-lookup"><span data-stu-id="87e64-114">However, since the installation of these applications are dependent on the standard Office Suite installation, Microsoft Managed Desktop has created default Intune deployments and Security groups that the customer will use to deploy these applications to licensed end users.</span></span>  
<span data-ttu-id="87e64-115">스토어 앱</span><span class="sxs-lookup"><span data-stu-id="87e64-115">Store Apps</span></span> |    <span data-ttu-id="87e64-116">Microsoft Sway, Power BI Desktop은 디바이스와 함께 제공 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="87e64-116">Microsoft Sway, Power BI Desktop are not shipped with device.</span></span> <span data-ttu-id="87e64-117">이러한 앱은 Microsoft Store에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87e64-117">These apps are available for download from Microsoft Store.</span></span>
<span data-ttu-id="87e64-118">Win32 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="87e64-118">Win32 Applications</span></span> |    <span data-ttu-id="87e64-119">Power BI Pro, Azure Information Protection 클라이언트 및 Microsoft Planner는 장치와 함께 제공 되지 않으며, 고객의 배포용으로 패키지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87e64-119">Power BI Pro, Azure Information Protection Client, and Microsoft Planner are not shipped with device and can be packaged for deployment by the customer.</span></span> 
<span data-ttu-id="87e64-120">웹 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="87e64-120">Web Applications</span></span> |  <span data-ttu-id="87e64-121">Yammer, Office for browser, Delve, Flow, StaffHub, PowerApps는 장치와 함께 제공 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="87e64-121">Yammer, Office in a browser, Delve, Flow, StaffHub, PowerApps are not shipped with the device.</span></span> <span data-ttu-id="87e64-122">사용자는 브라우저를 사용 하 여 이러한 응용 프로그램의 웹 버전에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87e64-122">Users can access the web version of these applications with a browser.</span></span>
<span data-ttu-id="87e64-123">비즈니스용 Skype Online 클라우드 PBX</span><span class="sxs-lookup"><span data-stu-id="87e64-123">Skype for Business Online Cloud PBX</span></span> | <span data-ttu-id="87e64-124">이 기능은 Office 365을 통해 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87e64-124">This feature is available via Office 365.</span></span> <span data-ttu-id="87e64-125">Microsoft Managed Desktop은이 서비스의 모든 측면을 구성 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="87e64-125">Microsoft Managed Desktop will not configure any aspect of this service</span></span>

## <a name="windows-10-enterprise-e5"></a><span data-ttu-id="87e64-126">Windows 10 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="87e64-126">Windows 10 Enterprise E5</span></span>

 |
 --- | ---
<span data-ttu-id="87e64-127">Credential Guard</span><span class="sxs-lookup"><span data-stu-id="87e64-127">Credential Guard</span></span> |  <span data-ttu-id="87e64-128">Microsoft는이 기능에 대 한 지침을 제공 하 고 클라우드를 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="87e64-128">Microsoft will provide guidance and manage cloud aspects of this feature.</span></span>
<span data-ttu-id="87e64-129">Application Virtualization (App-v)</span><span class="sxs-lookup"><span data-stu-id="87e64-129">Application Virtualization (App-V)</span></span> |    <span data-ttu-id="87e64-130">Microsoft Managed Desktop은 Intune에서 지원 되지 않으므로이 유형의 배포를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="87e64-130">Microsoft Managed Desktop does not support this type of deployment as it is not supported on Intune.</span></span>
<span data-ttu-id="87e64-131">UE-V (User Experience Virtualization)</span><span class="sxs-lookup"><span data-stu-id="87e64-131">User Experience Virtualization (UE-V)</span></span> | <span data-ttu-id="87e64-132">이 기능은 Microsoft Managed Desktop managed 장치에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="87e64-132">This is not used with Microsoft Managed Desktop managed devices.</span></span>
<span data-ttu-id="87e64-133">관리 되는 사용자 환경</span><span class="sxs-lookup"><span data-stu-id="87e64-133">Managed User Experience</span></span>  | <span data-ttu-id="87e64-134">이 기능은 Microsoft Managed Desktop managed 장치에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="87e64-134">This is not used with Microsoft Managed Desktop managed devices.</span></span> <span data-ttu-id="87e64-135">MDM은 장치 관리를 위한 솔루션으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87e64-135">MDM is used as a solution for device management.</span></span>
<span data-ttu-id="87e64-136">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="87e64-136">Microsoft Defender Advanced Threat Protection</span></span> | <span data-ttu-id="87e64-137">이는 Microsoft Managed Desktop에서 장치 보안 정책을 관리 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87e64-137">This is used by Microsoft Managed Desktop to manage device security policies.</span></span> 

## <a name="enterprise-mobility--security-e5"></a><span data-ttu-id="87e64-138">Enterprise Mobility + Security E5</span><span class="sxs-lookup"><span data-stu-id="87e64-138">Enterprise Mobility + Security E5</span></span>

 |
 --- | ---
<span data-ttu-id="87e64-139">Enterprise Mobility + Security E3</span><span class="sxs-lookup"><span data-stu-id="87e64-139">Enterprise Mobility + Security E3</span></span><br><span data-ttu-id="87e64-140">Azure Active Directory Premium P2</span><span class="sxs-lookup"><span data-stu-id="87e64-140">Azure Active Directory Premium P2</span></span> |    <span data-ttu-id="87e64-141">엔터프라이즈 이동성 + Security E3 및 AADP의 모든 측면은 MDM 장치를 관리 하는 데 사용 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87e64-141">All aspects of the Enterprise Mobility + Security E3 and AADP may be used to manage MDM devices.</span></span>
<span data-ttu-id="87e64-142">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="87e64-142">Microsoft Cloud App Security</span></span> |  <span data-ttu-id="87e64-143">이 기능은 고객이 Microsoft Managed Desktop service에 사용할 수 있는 선택적 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="87e64-143">This is an optional feature that customers can use with the Microsoft Managed Desktop service.</span></span>
<span data-ttu-id="87e64-144">Azure Information Protection P2</span><span class="sxs-lookup"><span data-stu-id="87e64-144">Azure Information Protection P2</span></span>  |<span data-ttu-id="87e64-145">이 기능은 고객이 Microsoft Managed Desktop service에 사용할 수 있는 선택적 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="87e64-145">This is an optional feature that customers can use with the Microsoft Managed Desktop service.</span></span>
