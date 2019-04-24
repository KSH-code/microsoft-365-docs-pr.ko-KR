---
title: Microsoft Managed Desktop 용 앱 준비
description: ''
keywords: microsoft Managed Desktop, microsoft 365, 서비스, 설명서
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.collection: M365-modern-desktop
ms.openlocfilehash: be28760fc3facdb21643943ace11deda378d437c
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32289071"
---
# <a name="preparing-apps-for-microsoft-managed-desktop"></a><span data-ttu-id="5c21d-103">Microsoft Managed Desktop 용 앱 준비</span><span class="sxs-lookup"><span data-stu-id="5c21d-103">Preparing apps for Microsoft Managed Desktop</span></span>

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
<span data-ttu-id="5c21d-104">microsoft 및 microsoft managed desktop 고객은 동일 하 게 중요 하지만 microsoft managed desktop에서 사용 되는 응용 프로그램에 대 한 책임은 서로 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="5c21d-104">Microsoft and Microsoft Managed Desktop customers have equally critical, yet different responsibilities around applications used with Microsoft Managed Desktop.</span></span>

## <a name="microsoft-responsibilities"></a><span data-ttu-id="5c21d-105">Microsoft의 책임</span><span class="sxs-lookup"><span data-stu-id="5c21d-105">Microsoft responsibilities</span></span>
<span data-ttu-id="5c21d-106">**Office 365 앱** Microsoft는 특정 Office 365 앱의 배포, 업데이트 및 지원에 대 한 전체 서비스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c21d-106">**Office 365 apps** Microsoft will provide full service for the deployment, update, and support of specific Office 365 apps.</span></span> <span data-ttu-id="5c21d-107">모든 사용자는 사용자가 빠르게 생산성을 높일 수 있도록 장치 이미지에 포함 된 응용 프로그램의 기본 집합 (64 비트 버전)을 수신 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c21d-107">All users will receive the base set of Office 365 click to run, 64 bit version of applications included in the device’s image so that a user can quickly become productive.</span></span> <span data-ttu-id="5c21d-108">Office 365 제품군의 프로젝트 및 Visio 응용 프로그램은 별도로 사용이 허가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c21d-108">The Project and Visio applications in of the Office 365 suite are licensed separately.</span></span>  <span data-ttu-id="5c21d-109">Microsoft Managed Desktop은 IT 관리자가 라이선스를 관리 하 고 이러한 응용 프로그램을 조직에 적절 하 게 배포할 수 있도록 하는 배포 그룹을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c21d-109">Microsoft Managed Desktop will provide deployment groups allowing the IT Administrator to manage licenses and deploy these applications appropriately for their organization.</span></span> <span data-ttu-id="5c21d-110">microsoft는 microsoft 관리 데스크톱 지원 채널을 통해 이러한 응용 프로그램의 최종 사용자를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c21d-110">Microsoft will support end users of these applications through the Microsoft Managed Desktop Support channels.</span></span>

<span data-ttu-id="5c21d-111">**기간 업무** (lob) 앱 Microsoft는 IT 관리자에 게 Intune 제품의 일부로 최종 사용자에 게 LOB (기간 업무) 응용 프로그램을 관리 하 고 배포할 수 있는 도구를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c21d-111">**Line-of-business apps** Microsoft provides tooling for IT Administrators to manage and deploy their line-of-business (LOB) applications to end users as a part of the Intune product.</span></span> <span data-ttu-id="5c21d-112">Microsoft는 기간 업무 (lob) [응용 프로그램](#line-of-business-applications) 에 설명 된 것 처럼 응용 프로그램 배포 문제를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c21d-112">Microsoft will support application deployment issues as detailed in [Line-of-business applications](#line-of-business-applications)</span></span> 

<span data-ttu-id="5c21d-113">**Intune을 사용 하 여 배포** intune은 microsoft Managed Desktop 온 보 딩 중 **비즈니스용 microsoft 스토어** 에 연결 되며,이를 통해 확보 된 앱을 Intune을 통해 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c21d-113">**Deploy with Intune** Intune will be linked to the **Microsoft Store for Business** during Microsoft Managed Desktop onboarding allowing procured apps to be deployed through Intune.</span></span> <span data-ttu-id="5c21d-114">microsoft는 IT 관리자가 최종 사용자에 게 셀프 서비스 환경을 제공할 수 있도록 microsoft Store의 회사 포털 응용 프로그램도 최종 사용자에 게 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c21d-114">Microsoft will also deploy the Company Portal application from the Microsoft Store to end users so that IT Administrators can provide a self-service experience for their end users.</span></span>

<span data-ttu-id="5c21d-115">**앱 관리** Microsoft는 시스템에 영향을 주므로 최신 직장에 적합 하지 않은 제한 된 응용 프로그램을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c21d-115">**App management** Microsoft may identify restricted applications which are not suitable for the modern workplace because of their system impact.</span></span> <span data-ttu-id="5c21d-116">이러한 응용 프로그램이 식별 되 면 Microsoft에서 고객에 게 알리고 해당 응용 프로그램을 테 넌 트에서 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c21d-116">When such an application is identified Microsoft will notify the customer and that application will need to be removed from the tenant.</span></span> 

<span data-ttu-id="5c21d-117">제한 된 앱 동작 및 앱 요구 사항에 대 한 자세한 내용은 [Microsoft Managed Desktop app 요구 사항](../service-description/mmd-app-requirements.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5c21d-117">For more information on restricted app behaviors and app requirements, see [Microsoft Managed Desktop app requirements](../service-description/mmd-app-requirements.md)</span></span>

## <a name="customer-responsibilities"></a><span data-ttu-id="5c21d-118">고객 책임</span><span class="sxs-lookup"><span data-stu-id="5c21d-118">Customer responsibilities</span></span>
<span data-ttu-id="5c21d-119">Office 365 제품군은 microsoft의 생산성 제공에 핵심 이며, 모든 microsoft 관리 데스크톱 사용자의 microsoft 365 라이선스에 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c21d-119">The Office 365 Suite is core to Microsoft’s productivity offerings and is included in the Microsoft 365 License for all Microsoft Managed Desktop users.</span></span> <span data-ttu-id="5c21d-120">microsoft에서 관리 하는 데스크톱 장치에 대 한 Office 응용 프로그램을 배포, 업데이트 및 지 원하는 반면, 고객은 여전히 일부 영역을 담당 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c21d-120">While Microsoft deploys, updates, and supports Office Applications to Microsoft Managed Desktop Devices there are still some areas for which the customer is responsible.</span></span>
- <span data-ttu-id="5c21d-121">**라이선스 할당** -고객은 최종 사용자에 게 Office 365에 대 한 적절 한 라이선스를 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c21d-121">**Assign licenses** - Customers are responsible for assigning the appropriate licenses to end users for Office 365.</span></span> 
- <span data-ttu-id="5c21d-122">**보안 그룹에 사용자 추가** -프로젝트나 Visio가 필요한 사용자를 위해 IT 관리자는 해당 사용자를 적절 한 배포 그룹에 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c21d-122">**Add users to security groups** - For customers with users who need Project or Visio, the IT administrator must add those users to the appropriate deployment groups.</span></span> <span data-ttu-id="5c21d-123">IT 관리자는 해당 사용자의 최종 기간을 관리 하는 역할도 담당 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c21d-123">IT administrators are also responsible for managing end of life for those users.</span></span> 
- <span data-ttu-id="5c21d-124">**Deploy office 365 Add 애드온** -고객이 필요한 것으로 간주 되는 office 365 제품군에 플러그 인을 배포 하는 일을 담당 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c21d-124">**Deploy Office 365 Add Ons** - Customers are responsible for deploying any plugins to the Office 365 suite which are deemed necessary.</span></span> 

<span data-ttu-id="5c21d-125">기간 업무 (lob) 앱은 각 고객에 대해 고유 하므로 고객은 Microsoft에서 배포 하지 않은 조직 내의 모든 응용 프로그램을 관리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c21d-125">Since line-of-business (LOB) apps are unique for each customer, customers are responsible for managing all applications within their organization not deployed by Microsoft.</span></span> <span data-ttu-id="5c21d-126">성능 저하를 줄여주는 방법에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c21d-126">This includes:</span></span>
- <span data-ttu-id="5c21d-127">필요한 앱 및 요구 사항 결정</span><span class="sxs-lookup"><span data-stu-id="5c21d-127">Deciding which apps are needed and who needs them</span></span>
- <span data-ttu-id="5c21d-128">해당 사용자에 게 앱 할당</span><span class="sxs-lookup"><span data-stu-id="5c21d-128">Assigning apps to those users</span></span>
- <span data-ttu-id="5c21d-129">앱 할당 관리를 위한 Azure Active Directory (AD) 그룹 만들기 및 유지 관리</span><span class="sxs-lookup"><span data-stu-id="5c21d-129">Create and maintain Azure Active Directory (AD) groups for managing app assignments</span></span> 

<span data-ttu-id="5c21d-130">고객은 LOB 앱을 Intune에 업로드 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c21d-130">The customer must upload LOB apps to Intune.</span></span> <span data-ttu-id="5c21d-131">그런 다음 각 수명 주기 동안 이러한 응용 프로그램을 배포, 업데이트 및 제거 하 고 사용자를 위해 이러한 앱에 대 한 지원을 관리 하는 일을 담당 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c21d-131">They are then responsible for deploying, updating, and decommissioning those applications over their respective lifecycles, as well as managing support for these apps for their users.</span></span>

## <a name="office-applications"></a><span data-ttu-id="5c21d-132">Office 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="5c21d-132">Office applications</span></span>
<span data-ttu-id="5c21d-133">microsoft 365 E5 라이선스의 일부로, microsoft가 Office 365 Standard Suite (64 비트)를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c21d-133">As part of the Microsoft 365 E5 license, Office 365 Standard Suite (64 Bit) is deployed by Microsoft.</span></span> 

<span data-ttu-id="5c21d-134">자세한 내용은 [Microsoft Managed Desktop 기술](../intro/technologies.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5c21d-134">For details, see [Microsoft Managed Desktop technologies](../intro/technologies.md)</span></span> <!--- and the other applications licensed under Office 365 E5 may be deployed by the customer using Intune’s deployment tools.-->

## <a name="line-of-business-applications"></a><span data-ttu-id="5c21d-135">기간 업무 (lob) 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="5c21d-135">Line-of-business applications</span></span>
<span data-ttu-id="5c21d-136">이 표에는 기간 업무 (lob) 응용 프로그램의 각 단계에 대 한 책임이 요약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c21d-136">This table summarizes responsibilities across the different phases for line-of-business (LOB) applications.</span></span> 

<span data-ttu-id="5c21d-137">응용 프로그램 작업 항목</span><span class="sxs-lookup"><span data-stu-id="5c21d-137">Application work items</span></span> |    <span data-ttu-id="5c21d-138">고객</span><span class="sxs-lookup"><span data-stu-id="5c21d-138">Customer</span></span>    | <span data-ttu-id="5c21d-139">Microsoft</span><span class="sxs-lookup"><span data-stu-id="5c21d-139">Microsoft</span></span>
--- | --- | ---
<span data-ttu-id="5c21d-140">**온 보 딩 앱**</span><span class="sxs-lookup"><span data-stu-id="5c21d-140">**Onboarding apps**</span></span> |  |
<span data-ttu-id="5c21d-141">대상 사용자 그룹에 필요한 응용 프로그램 확인</span><span class="sxs-lookup"><span data-stu-id="5c21d-141">Identify applications needed for targeted user groups</span></span>   | ![예](images/checkmark.png)  |
<span data-ttu-id="5c21d-143">앱 배포를 위한 Azure AD 그룹 만들기 및 관리</span><span class="sxs-lookup"><span data-stu-id="5c21d-143">Create and manage Azure AD groups for app deployment</span></span> | ![예](images/checkmark.png) |   
<span data-ttu-id="5c21d-145">**앱 패키징**</span><span class="sxs-lookup"><span data-stu-id="5c21d-145">**App Packaging**</span></span> |  |
<span data-ttu-id="5c21d-146">Intune 배포 표준에 맞게 앱 패키지</span><span class="sxs-lookup"><span data-stu-id="5c21d-146">Package apps to meet Intune deployment standards</span></span> |  ![예](images/checkmark.png) |  
<span data-ttu-id="5c21d-148">Intune에 앱 업로드</span><span class="sxs-lookup"><span data-stu-id="5c21d-148">Upload apps to Intune</span></span> | ![예](images/checkmark.png)     |
<span data-ttu-id="5c21d-150">Microsoft Managed Desktop 환경의 앱 테스트</span><span class="sxs-lookup"><span data-stu-id="5c21d-150">Test apps in Microsoft Managed Desktop environment</span></span> |    ![예](images/checkmark.png) |  
<span data-ttu-id="5c21d-152">최종 사용자가 포함 된 앱 테스트</span><span class="sxs-lookup"><span data-stu-id="5c21d-152">Test apps with end users</span></span>    | ![예](images/checkmark.png) |    
<span data-ttu-id="5c21d-154">**배포**</span><span class="sxs-lookup"><span data-stu-id="5c21d-154">**Deployment**</span></span> | |
<span data-ttu-id="5c21d-155">사용자 관리 및 응용 프로그램에 할당</span><span class="sxs-lookup"><span data-stu-id="5c21d-155">Manage and assign users to applications</span></span>  | ![예](images/checkmark.png)  |
<span data-ttu-id="5c21d-157">Intune 배포 도구를 통해 원격 클라이언트에 응용 프로그램 제공</span><span class="sxs-lookup"><span data-stu-id="5c21d-157">Intune deployment tools delivers application to remote clients</span></span>| |   ![예](images/checkmark.png)
<span data-ttu-id="5c21d-159">Intune을 통해 응용 프로그램 업데이트 식별 및 배포</span><span class="sxs-lookup"><span data-stu-id="5c21d-159">Identify and deploy application updates through Intune</span></span> | ![예](images/checkmark.png)    |
<span data-ttu-id="5c21d-161">중지 된 응용 프로그램을 Unistall 및 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c21d-161">Unistall and remove applications when they have been retired</span></span>    | ![예](images/checkmark.png) |    
<span data-ttu-id="5c21d-163">**관리**</span><span class="sxs-lookup"><span data-stu-id="5c21d-163">**Management**</span></span> | |
<span data-ttu-id="5c21d-164">라이선스 조달 및 할당</span><span class="sxs-lookup"><span data-stu-id="5c21d-164">Procure and assign licenses</span></span> |   ![예](images/checkmark.png)     |
<span data-ttu-id="5c21d-166">기간 업무 (lob) 앱에 대 한 최종 사용자 지원 제공</span><span class="sxs-lookup"><span data-stu-id="5c21d-166">Provide end-user support for line-of-business apps</span></span>  | ![예](images/checkmark.png) |
<span data-ttu-id="5c21d-168">원격으로 앱 설정 관리</span><span class="sxs-lookup"><span data-stu-id="5c21d-168">Manage app settings remotely</span></span>    | ![예](images/checkmark.png) |

<span data-ttu-id="5c21d-170">LOB 응용 프로그램 요구 사항에 대 한 자세한 내용은 [Microsoft Managed Desktop application 요구 사항](../service-description/mmd-app-requirements.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5c21d-170">For information on LOB application requirements, see [Microsoft Managed Desktop application requirements](../service-description/mmd-app-requirements.md)</span></span>


## <a name="intune-application-deployment"></a><span data-ttu-id="5c21d-171">Intune 응용 프로그램 배포</span><span class="sxs-lookup"><span data-stu-id="5c21d-171">Intune application deployment</span></span>
<span data-ttu-id="5c21d-172">응용 프로그램 관리는 Microsoft Managed Desktop Admin 포털을 통해 또는 Intune 포털을 통해 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c21d-172">Application management can be handled through the Microsoft Managed Desktop Admin portal, or through the Intune portal.</span></span> <span data-ttu-id="5c21d-173">Intune의 앱 관리 포털에는 Windows, Android 및 iOS 용으로 배포 된 응용 프로그램이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c21d-173">Intune’s app management portal shows applications deployed for Windows, Android, and iOS.</span></span> <span data-ttu-id="5c21d-174">Microsoft Managed Desktop administration portal은 보기를 Windows 10 응용 프로그램으로 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c21d-174">Microsoft Managed Desktop Admin portal limits the view to Windows 10 applications.</span></span> <span data-ttu-id="5c21d-175">둘 다 Azure Portal을 통해 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c21d-175">Both are available through the Azure Portal.</span></span> 
* [<span data-ttu-id="5c21d-176">Intune 앱 관리 기본 사항</span><span class="sxs-lookup"><span data-stu-id="5c21d-176">Intune app management basics</span></span>](https://docs.microsoft.com/intune/app-management)
* [<span data-ttu-id="5c21d-177">Intune에 앱 추가</span><span class="sxs-lookup"><span data-stu-id="5c21d-177">Add apps to Intune</span></span>](https://docs.microsoft.com/intune/app-management)
   * [<span data-ttu-id="5c21d-178">기간 업무 (lob) 앱 추가</span><span class="sxs-lookup"><span data-stu-id="5c21d-178">Add a line-of-business App</span></span>](https://docs.microsoft.com/intune/lob-apps-windows)
   * [<span data-ttu-id="5c21d-179">Intune에 Win32 앱 추가</span><span class="sxs-lookup"><span data-stu-id="5c21d-179">Add Win32 apps to Intune</span></span>](https://docs.microsoft.com/intune/apps-win32-app-management)
   * [<span data-ttu-id="5c21d-180">웹 응용 프로그램 추가</span><span class="sxs-lookup"><span data-stu-id="5c21d-180">Add web applications</span></span>](https://docs.microsoft.com/intune/web-app)
* [<span data-ttu-id="5c21d-181">앱 배포</span><span class="sxs-lookup"><span data-stu-id="5c21d-181">Deploy apps</span></span>](https://docs.microsoft.com/intune/apps-deploy)
   * [<span data-ttu-id="5c21d-182">Windows 10에 앱 배포</span><span class="sxs-lookup"><span data-stu-id="5c21d-182">Deploy apps to Windows 10</span></span>](https://docs.microsoft.com/intune/apps-windows-10-app-deploy)
* <span data-ttu-id="5c21d-183">회사 포털</span><span class="sxs-lookup"><span data-stu-id="5c21d-183">Company Portal</span></span>
   * [<span data-ttu-id="5c21d-184">회사 포털 배포</span><span class="sxs-lookup"><span data-stu-id="5c21d-184">Deploy the Company Portal</span></span>](https://docs.microsoft.com/intune/store-apps-company-portal-app)
   * [<span data-ttu-id="5c21d-185">회사 포털 앱 구성</span><span class="sxs-lookup"><span data-stu-id="5c21d-185">Configure the Company Portal app</span></span>](https://docs.microsoft.com/intune/company-portal-app)
