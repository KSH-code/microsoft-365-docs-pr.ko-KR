---
title: 관리 되는 데스크톱 앱을 준비 하 고 Microsoft에 대 한
description: ''
keywords: Microsoft 관리 되는 데스크톱, Microsoft 365 서비스, 설명서
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: b46e3de4a4cfe2140574ab9fc589e3a738bd2e17
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26869922"
---
# <a name="preparing-apps-for-microsoft-managed-desktop"></a><span data-ttu-id="6e4ac-103">관리 되는 데스크톱 앱을 준비 하 고 Microsoft에 대 한</span><span class="sxs-lookup"><span data-stu-id="6e4ac-103">Preparing apps for Microsoft Managed Desktop</span></span>

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
<span data-ttu-id="6e4ac-104">Microsoft 및 데스크톱을 관리 하는 Microsoft 고객 중심으로 데스크톱을 관리 하는 Microsoft와 함께 사용 하는 응용 프로그램의 중요 한, 아직 다른 책임은 동일 하 게 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6e4ac-104">Microsoft and Microsoft Managed Desktop customers have equally critical, yet different responsibilities around applications used with Microsoft Managed Desktop.</span></span>

## <a name="microsoft-responsibilities"></a><span data-ttu-id="6e4ac-105">Microsoft의 업무</span><span class="sxs-lookup"><span data-stu-id="6e4ac-105">Microsoft responsibilities</span></span>
<span data-ttu-id="6e4ac-p101">**Office 365 앱** Microsoft는 배포, 업데이트 및 특정 Office 365 앱의 지원에 대 한 전체 서비스를 제공 합니다. 모든 사용자에 게 사용자 생산성을 신속 하 게 될 수 있도록 장치의 이미지에 포함 된 응용 프로그램의 64 비트 버전을 실행 하려면 Office 365의 기본 집합을 받게 됩니다. 프로젝트 및 Visio 응용 프로그램에서 Office 365 제품군의는 별도로 사용이 허가 됩니다.  Microsoft 관리 되는 데스크톱은 IT 관리자에 게 라이선스를 관리 하 고 이러한 응용 프로그램을 조직에 적절 하 게 배포를 허용 하는 배포 그룹을 제공 합니다. Microsoft는 Microsoft 관리 되는 데스크톱 지원 채널을 통해 이러한 응용 프로그램의 최종 사용자를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e4ac-p101">**Office 365 apps** Microsoft will provide full service for the deployment, update, and support of specific Office 365 apps. All users will receive the base set of Office 365 click to run, 64 bit version of applications included in the device’s image so that a user can quickly become productive. The Project and Visio applications in of the Office 365 suite are licensed separately.  Microsoft Managed Desktop will provide deployment groups allowing the IT Administrator to manage licenses and deploy these applications appropriately for their organization. Microsoft will support end users of these applications through the Microsoft Managed Desktop Support channels.</span></span>

<span data-ttu-id="6e4ac-p102">**비즈니스 라인 앱** Microsoft IT 관리자가 Intune 제품의 일부로 최종 사용자에 게 자신의 기간 업무 (LOB) 응용 프로그램을 배포 및 관리 도구를 제공 합니다. Microsoft는 [비즈니스 라인 응용 프로그램](#line-of-business-applications) 에서 설명한 대로 배포 문제를 응용 프로그램을 지원</span><span class="sxs-lookup"><span data-stu-id="6e4ac-p102">**Line-of-business apps** Microsoft provides tooling for IT Administrators to manage and deploy their line-of-business (LOB) applications to end users as a part of the Intune product. Microsoft will support application deployment issues as detailed in [Line-of-business applications](#line-of-business-applications)</span></span> 

<span data-ttu-id="6e4ac-p103">**Intune를 사용 하 여 배포** Intune는 Microsoft 관리 되는 데스크톱 온 보 딩 확보 앱 Intune를 통해 배포할 수 있도록 허용 하는 동안 **비즈니스를 위한 Microsoft 저장소** 에 연결 됩니다. Microsoft IT 관리자가 최종 사용자에 대 한 셀프서비스 경험을 제공할 수 있도록 최종 사용자에 게 웹 기반 버전의 회사 포털 배포도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e4ac-p103">**Deploy with Intune** Intune will be linked to the **Microsoft Store for Business** during Microsoft Managed Desktop onboarding allowing procured apps to be deployed through Intune. Microsoft will also deploy the web-based version of the Company Portal to end users so that IT Administrators can provide a self-service experience for end users.</span></span>

<span data-ttu-id="6e4ac-p104">**응용 프로그램 관리** Microsoft는 자신의 시스템 영향으로 인해 현대 직장에 적합 하지 않은 제한 된 응용 프로그램을 식별할 수 있습니다. 이러한 응용 프로그램 식별 되는 Microsoft 고객 알림을 생성 하는 하 고 해당 응용 프로그램 테 넌 트에서 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e4ac-p104">**App management** Microsoft may identify restricted applications which are not suitable for the modern workplace because of their system impact. When such an application is identified Microsoft will notify the customer and that application will need to be removed from the tenant.</span></span> 

<span data-ttu-id="6e4ac-117">제한 된 응용 프로그램 동작 및 응용 프로그램 요구 사항에 대 한 자세한 내용은 [Microsoft 관리 되는 데스크톱 응용 프로그램 요구 사항](../service-description/mmd-app-requirements.md) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="6e4ac-117">For more information on restricted app behaviors and app requirements, see [Microsoft Managed Desktop app requirements](../service-description/mmd-app-requirements.md)</span></span>

## <a name="customer-responsibilities"></a><span data-ttu-id="6e4ac-118">고객 책임</span><span class="sxs-lookup"><span data-stu-id="6e4ac-118">Customer responsibilities</span></span>
<span data-ttu-id="6e4ac-p105">Office 365 제품군 Microsoft의 생산성 제품의 필수 요소 이며 모든 Microsoft 관리 되는 데스크톱 사용자에 대 한 Microsoft 365 라이선스에 포함 됩니다. Microsoft 배포, 업데이트 하 고 데스크톱 장치를 관리 하는 Microsoft Office 응용 프로그램을 지원 하는 동안 가지 여전히 일부 고객은 책임을 집니다.</span><span class="sxs-lookup"><span data-stu-id="6e4ac-p105">The Office 365 Suite is core to Microsoft’s productivity offerings and is included in the Microsoft 365 License for all Microsoft Managed Desktop users. While Microsoft deploys, updates, and supports Office Applications to Microsoft Managed Desktop Devices there are still some areas for which the customer is responsible.</span></span>
- <span data-ttu-id="6e4ac-121">**라이선스 할당** -고객에 게는 Office 365에 대 한 최종 사용자에 게 적절 한 라이선스를 할당 하는 일을 담당 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e4ac-121">**Assign licenses** - Customers are responsible for assigning the appropriate licenses to end users for Office 365.</span></span> 
- <span data-ttu-id="6e4ac-p106">**보안 그룹에 사용자 추가** -사용자와 프로젝트 또는 Visio, 고객에 대 한 IT 관리자가 해당 사용자를 추가 해야 적절 한 배포 그룹입니다. IT 관리자가 해당 사용자에 대 한 제공 종료를 관리 하기 위한도 책임이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e4ac-p106">**Add users to security groups** - For customers with users who need Project or Visio, the IT administrator must add those users to the appropriate deployment groups. IT administrators are also responsible for managing end of life for those users.</span></span> 
- <span data-ttu-id="6e4ac-124">**Office 365 추가 기능 배포** -고객에 게는 모든 플러그인 필요한 것으로 간주 되는 Office 365 제품군을 배포 하는 일을 담당 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e4ac-124">**Deploy Office 365 Add Ons** - Customers are responsible for deploying any plugins to the Office 365 suite which are deemed necessary.</span></span> 

<span data-ttu-id="6e4ac-p107">비즈니스 라인 (lob 기간 업무) 응용 프로그램은 각 고객에 대 한 고유, 고객은 Microsoft에 의해 배포 되지 않은 조직 내에서 모든 응용 프로그램 관리를 담당 합니다. 이는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e4ac-p107">Since line-of-business (LOB) apps are unique for each customer, customers are responsible for managing all applications within their organization not deployed by Microsoft. This includes:</span></span>
- <span data-ttu-id="6e4ac-127">앱 필요 하 고 필요한 사용자를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e4ac-127">Deciding which apps are needed and who needs them</span></span>
- <span data-ttu-id="6e4ac-128">앱 해당 사용자에 게 할당</span><span class="sxs-lookup"><span data-stu-id="6e4ac-128">Assigning apps to those users</span></span>
- <span data-ttu-id="6e4ac-129">작성 및 응용 프로그램 할당을 관리 하기 위한 Azure Active Directory (AD) 그룹을 유지 관리</span><span class="sxs-lookup"><span data-stu-id="6e4ac-129">Create and maintain Azure Active Directory (AD) groups for managing app assignments</span></span> 

<span data-ttu-id="6e4ac-p108">고객은 Intune를 LOB 응용 프로그램을 업로드 해야 합니다. 배포, 업데이트 하 고 자신의 개별 수명 주기를 통해 해당 응용 프로그램을 해제 뿐아니라 사용자에 게 이러한 앱에 대 한 지원을 관리 하는 일을 담당 하는 다음 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e4ac-p108">The customer must upload LOB apps to Intune. They are then responsible for deploying, updating, and decommissioning those applications over their respective lifecycles, as well as managing support for these apps for their users.</span></span>

## <a name="office-applications"></a><span data-ttu-id="6e4ac-132">Office 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="6e4ac-132">Office applications</span></span>
<span data-ttu-id="6e4ac-133">Microsoft 365 E5 라이선스의 일부로 Office 365 표준 도구 모음 (64 비트)는 Microsoft에서 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e4ac-133">As part of the Microsoft 365 E5 license, Office 365 Standard Suite (64 Bit) is deployed by Microsoft.</span></span> 

<span data-ttu-id="6e4ac-134">자세한 내용은 [Microsoft 관리 되는 데스크톱 기술](../intro/technologies.md) 참조<!--- and the other applications licensed under Office 365 E5 may be deployed by the customer using Intune’s deployment tools.--></span><span class="sxs-lookup"><span data-stu-id="6e4ac-134">For details, see [Microsoft Managed Desktop technologies](../intro/technologies.md) <!--- and the other applications licensed under Office 365 E5 may be deployed by the customer using Intune’s deployment tools.--></span></span>

## <a name="line-of-business-applications"></a><span data-ttu-id="6e4ac-135">비즈니스 라인 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="6e4ac-135">Line-of-business applications</span></span>
<span data-ttu-id="6e4ac-136">이 표에서 비즈니스 라인 (lob 기간 업무) 응용 프로그램에 대 한 서로 다른 단계에서 책임을 요약합니다.</span><span class="sxs-lookup"><span data-stu-id="6e4ac-136">This table summarizes responsibilities across the different phases for line-of-business (LOB) applications.</span></span> 

<span data-ttu-id="6e4ac-137">응용 프로그램 작업 항목</span><span class="sxs-lookup"><span data-stu-id="6e4ac-137">Application work items</span></span> |    <span data-ttu-id="6e4ac-138">고객</span><span class="sxs-lookup"><span data-stu-id="6e4ac-138">Customer</span></span>    | <span data-ttu-id="6e4ac-139">Microsoft</span><span class="sxs-lookup"><span data-stu-id="6e4ac-139">Microsoft</span></span>
--- | --- | ---
<span data-ttu-id="6e4ac-140">**온 보 딩 앱**</span><span class="sxs-lookup"><span data-stu-id="6e4ac-140">**Onboarding apps**</span></span> |  |
<span data-ttu-id="6e4ac-141">대상된 사용자 그룹에 필요한 응용 프로그램을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e4ac-141">Identify applications needed for targeted user groups</span></span>   | ![예](images/checkmark.png)  |
<span data-ttu-id="6e4ac-143">응용 프로그램 배포를 위한 Azure AD 그룹 만들기 및 관리</span><span class="sxs-lookup"><span data-stu-id="6e4ac-143">Create and manage Azure AD groups for app deployment</span></span> | ![예](images/checkmark.png) |   
<span data-ttu-id="6e4ac-145">**응용 프로그램 패키지**</span><span class="sxs-lookup"><span data-stu-id="6e4ac-145">**App Packaging**</span></span> |  |
<span data-ttu-id="6e4ac-146">Intune 배포 표준을 충족 하기 위해 패키지 앱</span><span class="sxs-lookup"><span data-stu-id="6e4ac-146">Package apps to meet Intune deployment standards</span></span> |  ![예](images/checkmark.png) |  
<span data-ttu-id="6e4ac-148">Intune에 앱을 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e4ac-148">Upload apps to Intune</span></span> | ![예](images/checkmark.png)     |
<span data-ttu-id="6e4ac-150">Microsoft 관리 되는 데스크톱 환경에서 앱을 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e4ac-150">Test apps in Microsoft Managed Desktop environment</span></span> |    ![예](images/checkmark.png) |  
<span data-ttu-id="6e4ac-152">최종 사용자와 함께 응용 프로그램 테스트</span><span class="sxs-lookup"><span data-stu-id="6e4ac-152">Test apps with end users</span></span>    | ![예](images/checkmark.png) |    
<span data-ttu-id="6e4ac-154">**배포**</span><span class="sxs-lookup"><span data-stu-id="6e4ac-154">**Deployment**</span></span> | |
<span data-ttu-id="6e4ac-155">관리 및 응용 프로그램에 사용자 할당</span><span class="sxs-lookup"><span data-stu-id="6e4ac-155">Manage and assign users to applications</span></span>  | ![예](images/checkmark.png)  |
<span data-ttu-id="6e4ac-157">원격 클라이언트에 응용 프로그램을 제공 하는 Intune 배포 도구</span><span class="sxs-lookup"><span data-stu-id="6e4ac-157">Intune deployment tools delivers application to remote clients</span></span>| |   ![예](images/checkmark.png)
<span data-ttu-id="6e4ac-159">식별 하 고 Intune 통해 응용 프로그램 업데이트 배포</span><span class="sxs-lookup"><span data-stu-id="6e4ac-159">Identify and deploy application updates through Intune</span></span> | ![예](images/checkmark.png)    |
<span data-ttu-id="6e4ac-161">사용 되지 않은 경우 설치 제거 하 고 제거 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="6e4ac-161">Unistall and remove applications when they have been retired</span></span>    | ![예](images/checkmark.png) |    
<span data-ttu-id="6e4ac-163">**관리**</span><span class="sxs-lookup"><span data-stu-id="6e4ac-163">**Management**</span></span> | |
<span data-ttu-id="6e4ac-164">조달 및 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="6e4ac-164">Procure and assign licenses</span></span> |   ![예](images/checkmark.png)     |
<span data-ttu-id="6e4ac-166">비즈니스 라인 앱에 대 한 최종 사용자 지원 제공</span><span class="sxs-lookup"><span data-stu-id="6e4ac-166">Provide end-user support for line-of-business apps</span></span>  | ![예](images/checkmark.png) |
<span data-ttu-id="6e4ac-168">응용 프로그램 설정 관리 원격으로</span><span class="sxs-lookup"><span data-stu-id="6e4ac-168">Manage app settings remotely</span></span>    | ![예](images/checkmark.png) |

<span data-ttu-id="6e4ac-170">LOB 응용 프로그램 요구 사항에 대 한 정보를 [Microsoft 관리 되는 데스크톱 응용 프로그램 요구 사항](../service-description/mmd-app-requirements.md) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="6e4ac-170">For information on LOB application requirements, see [Microsoft Managed Desktop application requirements](../service-description/mmd-app-requirements.md)</span></span>


## <a name="intune-application-deployment"></a><span data-ttu-id="6e4ac-171">Intune 응용 프로그램 배포</span><span class="sxs-lookup"><span data-stu-id="6e4ac-171">Intune application deployment</span></span>
<span data-ttu-id="6e4ac-p109">Microsoft 관리 되는 데스크톱 관리 포털을 통해 또는 Intune 포털을 통해 응용 프로그램 관리를 처리할 수 있습니다. Intune의 응용 프로그램 관리 포털, Android, 창과 iOS에 대 한 배포 하는 응용 프로그램을 보여줍니다. Microsoft 관리 되는 데스크톱 관리 포털 Windows 10 응용 프로그램에 대 한 보기를 제한합니다. 두 가지 Azure 포털을 통해 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e4ac-p109">Application management can be handled through the Microsoft Managed Desktop Admin portal, or through the Intune portal. Intune’s app management portal shows applications deployed for Windows, Android, and iOS. Microsoft Managed Desktop Admin portal limits the view to Windows 10 applications. Both are available through the Azure Portal.</span></span> 
* [<span data-ttu-id="6e4ac-176">Intune 응용 프로그램 관리 기본 사항</span><span class="sxs-lookup"><span data-stu-id="6e4ac-176">Intune app management basics</span></span>](https://docs.microsoft.com/intune/app-management)
* [<span data-ttu-id="6e4ac-177">Intune에 앱 추가</span><span class="sxs-lookup"><span data-stu-id="6e4ac-177">Add apps to Intune</span></span>](https://docs.microsoft.com/intune/app-management)
   * [<span data-ttu-id="6e4ac-178">비즈니스 라인 응용 프로그램을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e4ac-178">Add a line-of-business App</span></span>](https://docs.microsoft.com/intune/lob-apps-windows)
   * [<span data-ttu-id="6e4ac-179">Intune에 Win32 앱 추가</span><span class="sxs-lookup"><span data-stu-id="6e4ac-179">Add Win32 apps to Intune</span></span>](https://docs.microsoft.com/intune/apps-win32-app-management)
   * [<span data-ttu-id="6e4ac-180">웹 응용 프로그램 추가</span><span class="sxs-lookup"><span data-stu-id="6e4ac-180">Add web applications</span></span>](https://docs.microsoft.com/intune/web-app)
* [<span data-ttu-id="6e4ac-181">응용 프로그램 배포</span><span class="sxs-lookup"><span data-stu-id="6e4ac-181">Deploy apps</span></span>](https://docs.microsoft.com/intune/apps-deploy)
   * [<span data-ttu-id="6e4ac-182">Windows 10에 앱을 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e4ac-182">Deploy apps to Windows 10</span></span>](https://docs.microsoft.com/intune/apps-windows-10-app-deploy)
* <span data-ttu-id="6e4ac-183">회사 포털</span><span class="sxs-lookup"><span data-stu-id="6e4ac-183">Company Portal</span></span>
   * [<span data-ttu-id="6e4ac-184">회사 포털 배포</span><span class="sxs-lookup"><span data-stu-id="6e4ac-184">Deploy the Company Portal</span></span>](https://docs.microsoft.com/intune/store-apps-company-portal-app)
   * [<span data-ttu-id="6e4ac-185">회사 포털 응용 프로그램 구성</span><span class="sxs-lookup"><span data-stu-id="6e4ac-185">Configure the Company Portal app</span></span>](https://docs.microsoft.com/intune/company-portal-app)
