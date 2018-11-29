---
title: 데스크톱을 관리 하는 Microsoft 기술
description: 이 항목의 기술와 Microsoft 관리 되는 데스크톱에 사용 되는 응용 프로그램을 나열 합니다.
keywords: Microsoft 관리 되는 데스크톱, Microsoft 365 서비스, 설명서
ms.service: m365-md
author: jdeckerms
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: da0268c6b0eddbd44cf62de2a95b963a443c3278
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869924"
---
# <a name="microsoft-managed-desktop-technologies"></a><span data-ttu-id="71f80-104">데스크톱을 관리 하는 Microsoft 기술</span><span class="sxs-lookup"><span data-stu-id="71f80-104">Microsoft Managed Desktop technologies</span></span>

<span data-ttu-id="71f80-105">이 항목의 기술와 Microsoft 관리 되는 데스크톱에 사용 되는 응용 프로그램을 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="71f80-105">This topic lists the technologies and apps used in Microsoft Managed Desktop.</span></span>

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

<span data-ttu-id="71f80-p101">Microsoft 365 e 5 라이선스 (또는에 상응)은 데스크톱을 관리 하는 Microsoft 서비스에 필요 합니다. 이 라이선스 및 데스크톱을 관리 하는 Microsoft 데스크톱을 관리 하는 Microsoft 장치와 각 구성 요소를 사용 하는 방법에 포함 된 모든 구성 요소는 다음과 같습니다.  특정 역할 및 책임 각 영역에 대 한 전체 데스크톱을 관리 하는 Microsoft 항목에서 자세히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="71f80-p101">Microsoft 365 E5 License (or equivalent) is required for Microsoft Managed Desktop service. The following are all components that are included in this license and how Microsoft Managed Desktop uses each component with Microsoft Managed Desktop devices.  Specific roles and responsibilities for each area are detailed throughout Microsoft Managed Desktop topics.</span></span> 

<span data-ttu-id="71f80-109">Microsoft 365 e 5는 3 구성 요소로 이루어져: Office 365 e 5 "," Windows 10 Enterprise "및" e 5 "," Enterprise 이동성 "+" 보안 e 5입니다.</span><span class="sxs-lookup"><span data-stu-id="71f80-109">Microsoft 365 E5 is comprised of 3 components: Office 365 E5, Windows 10 Enterprise and E5, Enterprise Mobility + Security E5.</span></span>  

## <a name="office-365-e5"></a><span data-ttu-id="71f80-110">Office 365 e 5</span><span class="sxs-lookup"><span data-stu-id="71f80-110">Office 365 E5</span></span>
 |
 --- | ---
<span data-ttu-id="71f80-111">Office 365 표준 제품군 (64 비트) \*</span><span class="sxs-lookup"><span data-stu-id="71f80-111">Office 365 Standard Suite (64bit)\*</span></span> | <span data-ttu-id="71f80-112">응용 프로그램의 표준 Office 제품군 장치 함께 제공 됩니다: Word, Excel, PowerPoint, Outlook, Publisher, Access, 비즈니스, OneNote에 대 한 Skype 합니다.</span><span class="sxs-lookup"><span data-stu-id="71f80-112">The standard Office Suite of applications will be shipped with the device: Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for Business, OneNote.</span></span><br><br><span data-ttu-id="71f80-p102">64 비트 하 고 실행을 클릭 (C2R) 전체 버전의 Microsoft Project 및 Microsoft Visio는 Office 365 표준 제품군에 포함 되지 않습니다.  그러나 이러한 응용 프로그램의 설치 되는 표준 Office 제품군 설치에 따라 다릅니다, 이후 데스크톱을 관리 하는 Microsoft가 만든 기본 Intune 배포 하 고 이러한 응용 프로그램을 배포 하는 고객에서 사용할 보안 그룹 최종 사용자에 게 사용이 허가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="71f80-p102">The 64bit Click to Run (C2R) full versions of Microsoft Project and Microsoft Visio are not included in the Office 365 Standard Suite.  However, since the installation of these applications are dependent on the standard Office Suite installation, Microsoft Managed Desktop has created default Intune deployments and Security groups that the customer will use to deploy these applications to licensed end users.</span></span>  
<span data-ttu-id="71f80-115">앱을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="71f80-115">Store Apps</span></span> |    <span data-ttu-id="71f80-p103">Microsoft 영향, Microsoft 팀의, Power BI 데스크톱 (하지 Pro)에 포함 되지 않은 장치입니다. 이러한 응용 프로그램은 Microsoft 저장소에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71f80-p103">Microsoft Sway, Microsoft Teams, Power BI Desktop (not Pro) are not shipped with device. These apps are available for download from Microsoft Store.</span></span>
<span data-ttu-id="71f80-118">Win32 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="71f80-118">Win32 Applications</span></span> |    <span data-ttu-id="71f80-119">Power BI Pro, Azure 정보를 보호 하는 클라이언트 및 Microsoft 플래너 장치와 함께 제공 하지 않는 및 고객에 의해 배포에 대 한 패키지화 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71f80-119">Power BI Pro, Azure Information Protection Client, and Microsoft Planner are not shipped with device and can be packaged for deployment by the customer.</span></span> 
<span data-ttu-id="71f80-120">웹 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="71f80-120">Web Applications</span></span> |  <span data-ttu-id="71f80-p104">Yammer, Delve, Office Online, 흐름, StaffHub, PowerApps 장치와 함께 제공 되지 않습니다. 사용자가 브라우저를 통해 이러한 응용 프로그램의 웹 버전에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71f80-p104">Yammer, Office Online, Delve, Flow, StaffHub, PowerApps are not shipped with the device. Users can access the web version of these applications with a browser.</span></span>
<span data-ttu-id="71f80-123">비즈니스 온라인 클라우드 PBX에 대 한 Skype</span><span class="sxs-lookup"><span data-stu-id="71f80-123">Skype for Business Online Cloud PBX</span></span> | <span data-ttu-id="71f80-p105">이 기능은 Office 365 e 5를 통해 사용할 수 있습니다. 데스크톱을 관리 하는 Microsoft에서이 서비스의 모든 측면을 구성 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="71f80-p105">This feature is available via Office 365 E5. Microsoft Managed Desktop will not configure any aspect of this service</span></span>

## <a name="windows-10-enterprise-e5"></a><span data-ttu-id="71f80-126">Windows 10 Enterprise e 5</span><span class="sxs-lookup"><span data-stu-id="71f80-126">Windows 10 Enterprise E5</span></span>

 |
 --- | ---
<span data-ttu-id="71f80-127">자격 증명 Guard</span><span class="sxs-lookup"><span data-stu-id="71f80-127">Credential Guard</span></span> |  <span data-ttu-id="71f80-128">데스크톱을 관리 하는 Microsoft가 지침을 제공 하 고이 기능의 클라우드 측면을 관리</span><span class="sxs-lookup"><span data-stu-id="71f80-128">Microsoft Managed Desktop will provide guidance and manage cloud aspects of this feature</span></span>
<span data-ttu-id="71f80-129">장치 Guard (Windows Defender 응용 프로그램 제어)</span><span class="sxs-lookup"><span data-stu-id="71f80-129">Device Guard ( Windows Defender Application Control )</span></span>   | <span data-ttu-id="71f80-p106">Microsoft 관리 되는 데스크톱 정책이 만들어집니다. 고객 서명 관리</span><span class="sxs-lookup"><span data-stu-id="71f80-p106">Microsoft Managed Desktop will create the policy. Customer will manage signatures</span></span>
<span data-ttu-id="71f80-132">AppLocker 관리</span><span class="sxs-lookup"><span data-stu-id="71f80-132">AppLocker management</span></span> |  <span data-ttu-id="71f80-p107">Microsoft 관리 되는 데스크톱 정책이 만들어집니다. 고객 서명 관리</span><span class="sxs-lookup"><span data-stu-id="71f80-p107">Microsoft Managed Desktop will create the policy. Customer will manage signatures</span></span>
<span data-ttu-id="71f80-135">응용 프로그램 가상화 (App-v)</span><span class="sxs-lookup"><span data-stu-id="71f80-135">Application Virtualization (App-V)</span></span> |    <span data-ttu-id="71f80-136">Microsoft 관리 되는 데스크톱 Intune에서 지원 되지 않습니다으로이 유형의 배포를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="71f80-136">Microsoft Managed Desktop does not support this type of deployment as it is not supported on Intune.</span></span>
<span data-ttu-id="71f80-137">사용자 환경 가상화 (사용자 교육-V)</span><span class="sxs-lookup"><span data-stu-id="71f80-137">User Experience Virtualization (UE-V)</span></span> | <span data-ttu-id="71f80-138">이 Microsoft에 관리 하는 바탕 화면을 관리 하는 장치는 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="71f80-138">This is not used with Microsoft Managed Desktop managed devices</span></span>
<span data-ttu-id="71f80-139">관리 되는 사용자 환경</span><span class="sxs-lookup"><span data-stu-id="71f80-139">Managed User Experience</span></span>  | <span data-ttu-id="71f80-p108">이 값은 Microsoft에 관리 하는 바탕 화면을 관리 하는 장치는 사용 되지 않습니다. MDM 장치 관리에 대 한 솔루션으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="71f80-p108">This is not used with Microsoft Managed Desktop managed devices. MDM is used as a solution for device management</span></span>
<span data-ttu-id="71f80-142">Windows Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="71f80-142">Windows Defender Advanced Threat Protection</span></span> |   <span data-ttu-id="71f80-143">이 장치 보안 정책을 관리 하려면 Microsoft 관리 되는 데스크톱에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="71f80-143">This is used by Microsoft Managed Desktop to manage device security policies.</span></span> 

## <a name="enterprise-mobility--security"></a><span data-ttu-id="71f80-144">Enterprise Mobility + Security</span><span class="sxs-lookup"><span data-stu-id="71f80-144">Enterprise Mobility + Security</span></span> 

 |
 --- | ---
<span data-ttu-id="71f80-145">엔터프라이즈 이동성 + 보안 E3</span><span class="sxs-lookup"><span data-stu-id="71f80-145">Enterprise Mobility + Security E3</span></span><br><span data-ttu-id="71f80-146">Azure Active Directory 프리미엄 P2</span><span class="sxs-lookup"><span data-stu-id="71f80-146">Azure Active Directory Premium P2</span></span> |    <span data-ttu-id="71f80-147">MDM 장치를 관리 하는 엔터프라이즈 이동성 + 보안 E3 및 AADP의 모든 측면을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71f80-147">All aspects of the Enterprise Mobility + Security E3 and AADP may be used to manage MDM devices</span></span>
<span data-ttu-id="71f80-148">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="71f80-148">Microsoft Cloud App Security</span></span> |  <span data-ttu-id="71f80-149">이것은 고객이 Microsoft 관리 되는 데스크톱 서비스와 함께 사용할 수 있는 선택적 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="71f80-149">This is an optional feature that customers can use with the Microsoft Managed Desktop service.</span></span>
<span data-ttu-id="71f80-150">Azure 정보 보호 P2</span><span class="sxs-lookup"><span data-stu-id="71f80-150">Azure Information Protection P2</span></span>  |<span data-ttu-id="71f80-151">이것은 고객이 Microsoft 관리 되는 데스크톱 서비스와 함께 사용할 수 있는 선택적 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="71f80-151">This is an optional feature that customers can use with the Microsoft Managed Desktop service.</span></span>