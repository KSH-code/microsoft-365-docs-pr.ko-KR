---
title: Microsoft Managed Desktop 기술
description: 이 문서에서는 Microsoft Managed Desktop에서 사용되는 기술 및 앱을 나열합니다.
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: cb368939e87ddbbfc8f5386c6fc5d6bff110a7ec
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840904"
---
# <a name="microsoft-managed-desktop-technologies"></a><span data-ttu-id="e1f6a-104">Microsoft Managed Desktop 기술</span><span class="sxs-lookup"><span data-stu-id="e1f6a-104">Microsoft Managed Desktop technologies</span></span>

<span data-ttu-id="e1f6a-105">이 문서에는 Microsoft Managed Desktop에서 사용되는 기술 및 앱이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1f6a-105">This article lists the technologies and apps used in Microsoft Managed Desktop.</span></span>

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

<span data-ttu-id="e1f6a-106">모든 Microsoft Managed Desktop 사용자에게는 Microsoft 365 Enterprise 라이선스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e1f6a-106">Microsoft 365 Enterprise licensing is required for all Microsoft Managed Desktop users.</span></span> <span data-ttu-id="e1f6a-107">서비스의 라이선스 요구 사항에 대한 자세한 내용은 [Microsoft Managed Desktop의 사전 요구 사항을 참조하세요.](../get-ready/prerequisites.md)</span><span class="sxs-lookup"><span data-stu-id="e1f6a-107">For more information on licensing requirements for the service, see [Prerequisites for Microsoft Managed Desktop](../get-ready/prerequisites.md).</span></span>

<span data-ttu-id="e1f6a-108">이 문서에서는 필수 Enterprise 라이선스에 포함된 구성 요소를 요약하고 서비스에서 Microsoft Managed Desktop 장치에서 각 구성 요소를 사용하는 방법에 대한 설명을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e1f6a-108">This article summarizes the components included in the required Enterprise licenses, with a description of how the service uses each component with Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="e1f6a-109">각 영역에 대한 특정 역할 및 책임은 Microsoft Managed Desktop 설명서에서 자세히 설명됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1f6a-109">Specific roles and responsibilities for each area are detailed throughout Microsoft Managed Desktop documentation.</span></span> 

## <a name="office-365-e3-or-e5"></a><span data-ttu-id="e1f6a-110">Office 365 E3 또는 E5</span><span class="sxs-lookup"><span data-stu-id="e1f6a-110">Office 365 E3 or E5</span></span>
 |
 --- | ---
<span data-ttu-id="e1f6a-111">엔터프라이즈용 Microsoft 365 앱(64비트)</span><span class="sxs-lookup"><span data-stu-id="e1f6a-111">Microsoft 365 Apps for enterprise (64-bit)</span></span> | <span data-ttu-id="e1f6a-112">이러한 Office 응용 프로그램은 Word, Excel, PowerPoint, Outlook, Publisher, Access, 비즈니스용 Skype, OneNote와 함께 발송됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1f6a-112">These Office applications will be shipped with the device: Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for Business, OneNote.</span></span><br><br><span data-ttu-id="e1f6a-113">64비트 정식 버전의 Microsoft Project 및 Microsoft Visio는 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e1f6a-113">The 64-bit full versions of Microsoft Project and Microsoft Visio aren't included.</span></span> <span data-ttu-id="e1f6a-114">그러나 이러한 응용 프로그램의 설치는 엔터프라이즈용 Microsoft 365 앱 설치에 따라 달라지기 때문에 Microsoft Managed Desktop은 기본 Microsoft Intune 배포 및 보안 그룹을 만들어 라이선스가 있는 사용자에게 이러한 응용 프로그램을 배포하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1f6a-114">However, since the installation of these applications depends on the Microsoft 365 Apps for enterprise installation, Microsoft Managed Desktop has created default Microsoft Intune deployments and security groups that you can then use to deploy these applications to licensed users.</span></span> <span data-ttu-id="e1f6a-115">자세한 내용은 Microsoft Managed Desktop 장치에 Microsoft Project 또는 [Microsoft Visio 설치를 참조하세요.](../get-started/project-visio.md)</span><span class="sxs-lookup"><span data-stu-id="e1f6a-115">For more information, see [Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices](../get-started/project-visio.md).</span></span>
<span data-ttu-id="e1f6a-116">OneDrive</span><span class="sxs-lookup"><span data-stu-id="e1f6a-116">OneDrive</span></span> |<span data-ttu-id="e1f6a-117">Azure Active Directory Single Sign-On은 사용자가 OneDrive에 처음 로그인할 때 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1f6a-117">Azure Active Directory Single Sign On is enabled for users when they first sign in to OneDrive.</span></span><br><br><span data-ttu-id="e1f6a-118">"데스크톱", "문서" 및 "그림" 폴더에 대한 알려진 폴더 리디렉션이 포함됩니다. Microsoft Managed Desktop에서 사용하도록 설정하고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="e1f6a-118">Known Folder Redirection for "Desktop", "Document", and "Pictures" folders is included; enabled and configured by Microsoft Managed Desktop.</span></span>
<span data-ttu-id="e1f6a-119">스토어 앱</span><span class="sxs-lookup"><span data-stu-id="e1f6a-119">Store Apps</span></span> |    <span data-ttu-id="e1f6a-120">Microsoft Sway 및 Power BI는 디바이스와 함께 배송되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e1f6a-120">Microsoft Sway and Power BI aren't shipped with the device.</span></span> <span data-ttu-id="e1f6a-121">이러한 앱은 Microsoft Store에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1f6a-121">These apps are available for download from Microsoft Store.</span></span>
<span data-ttu-id="e1f6a-122">Win32 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="e1f6a-122">Win32 Applications</span></span> |    <span data-ttu-id="e1f6a-123">Teams는 디바이스와 함께 제공되지 않지만 Microsoft에서 Microsoft Managed Desktop 장치용 패키지 및 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e1f6a-123">Teams isn't shipped with the device, but is packaged and provided by Microsoft for Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="e1f6a-124">Azure Information Protection Client는 디바이스와 함께 제공되지 않지만 배포를 위해 패키지로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1f6a-124">Azure Information Protection Client isn't shipped with the device, but you can have it packaged for deployment.</span></span>
<span data-ttu-id="e1f6a-125">웹 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="e1f6a-125">Web Applications</span></span> |  <span data-ttu-id="e1f6a-126">Yammer, 브라우저의 Office, Delve, Flow, StaffHub, PowerApps 및 Planner는 디바이스와 함께 배송되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e1f6a-126">Yammer, Office in a browser, Delve, Flow, StaffHub, PowerApps, and Planner aren't shipped with the device.</span></span> <span data-ttu-id="e1f6a-127">사용자는 브라우저를 사용하여 이러한 응용 프로그램의 웹 버전에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1f6a-127">Users can access the web version of these applications with a browser.</span></span>


## <a name="windows-10-enterprise-e5-or-e3-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="e1f6a-128">끝점용 Microsoft Defender가 있는 Windows 10 Enterprise E5 또는 E3</span><span class="sxs-lookup"><span data-stu-id="e1f6a-128">Windows 10 Enterprise E5 or E3 with Microsoft Defender for Endpoint</span></span>

 |
 --- | ---
<span data-ttu-id="e1f6a-129">App-V(Application Virtualization)</span><span class="sxs-lookup"><span data-stu-id="e1f6a-129">Application Virtualization (App-V)</span></span> |    <span data-ttu-id="e1f6a-130">고객은 Intune Win32 앱 관리 클라이언트를 사용하여 App-V 패키지를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1f6a-130">Customers can deploy App-V packages using the Intune Win32 app management client.</span></span>
<span data-ttu-id="e1f6a-131">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="e1f6a-131">Microsoft Defender for Endpoint</span></span> |    <span data-ttu-id="e1f6a-132">Microsoft Managed Desktop은 이 제품을 사용하여 장치 보안을 모니터링합니다.</span><span class="sxs-lookup"><span data-stu-id="e1f6a-132">Microsoft Managed Desktop uses this product to monitor device security.</span></span> 

## <a name="enterprise-mobility--security-e5"></a><span data-ttu-id="e1f6a-133">Enterprise Mobility + Security E5</span><span class="sxs-lookup"><span data-stu-id="e1f6a-133">Enterprise Mobility + Security E5</span></span>

 |
 --- | ---
<span data-ttu-id="e1f6a-134">Enterprise Mobility + Security E3</span><span class="sxs-lookup"><span data-stu-id="e1f6a-134">Enterprise Mobility + Security E3</span></span><br><span data-ttu-id="e1f6a-135">Azure Active Directory Premium P2</span><span class="sxs-lookup"><span data-stu-id="e1f6a-135">Azure Active Directory Premium P2</span></span> |    <span data-ttu-id="e1f6a-136">Enterprise Mobility + Security E3 및 Azure Active Directory Premium P2의 모든 기능을 사용하여 MDM 장치를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1f6a-136">You can use all features of Enterprise Mobility + Security E3 and Azure Active Directory Premium P2 to manage MDM devices.</span></span>
<span data-ttu-id="e1f6a-137">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="e1f6a-137">Microsoft Cloud App Security</span></span> |  <span data-ttu-id="e1f6a-138">Microsoft Managed Desktop에서 이 선택적 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1f6a-138">You can use this optional feature with Microsoft Managed Desktop.</span></span>
<span data-ttu-id="e1f6a-139">Azure Information Protection P2</span><span class="sxs-lookup"><span data-stu-id="e1f6a-139">Azure Information Protection P2</span></span>  | <span data-ttu-id="e1f6a-140">Microsoft Managed Desktop에서 이 선택적 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1f6a-140">You can use this optional feature with Microsoft Managed Desktop.</span></span>
