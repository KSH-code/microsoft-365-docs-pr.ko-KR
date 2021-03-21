---
title: Microsoft Managed Desktop의 앱
description: 앱을 패키지화, 배포 및 지원하는 방법을 포함하여 앱 처리 방법에 대해 설명
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: ea0990e5f30aa45ec48bb2e6a7c957c187c74ebb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922947"
---
# <a name="apps-in-microsoft-managed-desktop"></a><span data-ttu-id="0639b-104">Microsoft Managed Desktop의 앱</span><span class="sxs-lookup"><span data-stu-id="0639b-104">Apps in Microsoft Managed Desktop</span></span>

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
## <a name="apps-generally"></a><span data-ttu-id="0639b-105">일반적으로 앱</span><span class="sxs-lookup"><span data-stu-id="0639b-105">Apps generally</span></span>

<span data-ttu-id="0639b-106">Microsoft에는 Microsoft Managed Desktop에 참여하는 데 필요한 Microsoft 365 E3 또는 E5 라이선스와 함께 특정 주요 앱이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0639b-106">Microsoft includes certain key apps along with the Microsoft 365 E3 or E5 license needed to participate in Microsoft Managed Desktop.</span></span> <span data-ttu-id="0639b-107">그러나 이러한 앱을 제공하겠지만 여전히 완료할 특정 책임과 작업이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0639b-107">However, even though we provide these apps, you still have certain responsibilities and actions to complete.</span></span>

<span data-ttu-id="0639b-108">또한 Microsoft Intune의 배포 파이프라인을 사용하여 회사 포털 또는 필수 백그라운드 설치를 통해 셀프 서비스를 위해 Microsoft가 아닌 다른 앱을 사용자에게 배포할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0639b-108">You can also deploy additional non-Microsoft apps to your users for self-service through the Company Portal or a required background installation, all using Microsoft Intune’s deployment pipeline.</span></span> <span data-ttu-id="0639b-109">전문 지식이 있는 경우 필요한 앱을 마이그레이션할 수 있습니다. 또는 MCS(Microsoft Consulting Services) 또는 비 Microsoft 공급업체가 패키징 및 마이그레이션 프로젝트를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0639b-109">If you have the expertise, you can migrate those apps you need yourself; alternatively, Microsoft Consulting Services (MCS) or non-Microsoft vendors will be happy to help you with a packaging and migration project.</span></span> <span data-ttu-id="0639b-110">MCS 사용에 대한 자세한 내용은 Microsoft Consulting Services 작업을 [참조하세요.](apps-MCS.md)</span><span class="sxs-lookup"><span data-stu-id="0639b-110">For more information about working with MCS, see [Working with Microsoft Consulting Services](apps-MCS.md).</span></span>


## <a name="apps-provided-by-microsoft"></a><span data-ttu-id="0639b-111">Microsoft에서 제공하는 앱</span><span class="sxs-lookup"><span data-stu-id="0639b-111">Apps provided by Microsoft</span></span>

<span data-ttu-id="0639b-112">Microsoft Managed Desktop 라이선스에 포함된 앱의 64비트 버전은 엔터프라이즈용 Microsoft 365 앱 Standard Suite(Word, Excel, PowerPoint, Outlook, Publisher, Access, 비즈니스용 Skype 및 OneNote)입니다. Microsoft Project 및 Visio의 Click-to-Run 버전은 기본적으로 포함되지 않지만 추가를 요청할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="0639b-112">Included with your Microsoft Managed Desktop license are 64-bit versions of the apps in the Microsoft 365 Apps for enterprise Standard Suite (Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for Business, and OneNote.) Click-to-Run versions of Microsoft Project and Visio are *not* included by default, but you can request them to be added.</span></span> <span data-ttu-id="0639b-113">이러한 앱에 대한 자세한 내용은 Microsoft Managed Desktop 장치에 Microsoft Project 또는 [Microsoft Visio 설치를 참조하세요.](../get-started/project-visio.md)</span><span class="sxs-lookup"><span data-stu-id="0639b-113">For more information about these apps, see [Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices](../get-started/project-visio.md).</span></span>

### <a name="what-microsoft-does-to-support-the-apps-we-provide"></a><span data-ttu-id="0639b-114">Microsoft에서 제공하는 앱을 지원하기 위해 Microsoft가 하는 일</span><span class="sxs-lookup"><span data-stu-id="0639b-114">What Microsoft does to support the apps we provide</span></span>

<span data-ttu-id="0639b-115">Microsoft는 포함된 엔터프라이즈용 Microsoft 365 앱의 배포, 업데이트 및 지원을 위한 전체 서비스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0639b-115">Microsoft will provide full service for the deployment, update, and support for the included Microsoft 365 Apps for enterprise apps.</span></span> <span data-ttu-id="0639b-116">Microsoft Project 및 Visio의 Click-to-Run 버전은 기본적으로 포함되지 않지만 Microsoft Managed Desktop은 IT 관리자가 라이선스를 관리하고 조직에 적합한 응용 프로그램을 배포할 수 있도록 배포 그룹을 제공합니다. </span><span class="sxs-lookup"><span data-stu-id="0639b-116">Click-to-Run versions of Microsoft Project and Visio are *not* included by default, but Microsoft Managed Desktop will provide deployment groups allowing your IT administrator to manage licenses and deploy these applications appropriately for your organization.</span></span> <span data-ttu-id="0639b-117">Microsoft는 Microsoft Managed Desktop 지원 채널을 통해 이러한 응용 프로그램의 사용자를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="0639b-117">Microsoft will support users of these applications through the Microsoft Managed Desktop support channels.</span></span>

### <a name="what-you-need-to-do-to-support-the-apps-we-provide"></a><span data-ttu-id="0639b-118">제공한 앱을 지원하기 위해 필요한 일</span><span class="sxs-lookup"><span data-stu-id="0639b-118">What you need to do to support the apps we provide</span></span>

<span data-ttu-id="0639b-119">이러한 앱에서는 여전히 몇 가지 작업을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0639b-119">There are still certain things you need to do with these apps:</span></span>

- <span data-ttu-id="0639b-120">**라이선스 할당** - 엔터프라이즈용 Microsoft 365 앱의 사용자에게 적절한 라이선스를 획득하고 할당할 책임이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0639b-120">**Assign licenses** - You are responsible for obtaining and assigning the appropriate licenses to users for Microsoft 365 Apps for enterprise.</span></span>
- <span data-ttu-id="0639b-121">**보안 그룹에** 사용자 추가 - Microsoft Project 또는 Visio를 사용하는 경우 IT 관리자가 해당 사용자를 적절한 배포 그룹에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0639b-121">**Add users to security groups** - If you're using Microsoft Project or Visio, your IT administrator must add those users to the appropriate deployment groups.</span></span> <span data-ttu-id="0639b-122">또한 IT 관리자는 퇴사하는 경우 해당 사용자로부터 라이선스를 취득할 책임이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0639b-122">IT administrators are also responsible for reclaiming licenses from those users if they leave the company.</span></span>
- <span data-ttu-id="0639b-123">**Microsoft 365** 추가 기능 배포 - 엔터프라이즈용 Microsoft 365 앱에 대한 추가 기능을 필요로 하는 경우 다른 Windows 32 앱처럼 중앙에서 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="0639b-123">**Deploy Microsoft 365 Add-ons** - If you need any Add-ons for any of the Microsoft 365 Apps for enterprise apps, deploy them centrally like any other Windows 32 app.</span></span> 

## <a name="apps-you-provide"></a><span data-ttu-id="0639b-124">제공하는 앱</span><span class="sxs-lookup"><span data-stu-id="0639b-124">Apps you provide</span></span>

<span data-ttu-id="0639b-125">비즈니스 작업에 필요한 다른 앱이 있는 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0639b-125">You probably have other apps you need for your business operations.</span></span> <span data-ttu-id="0639b-126">이러한 앱은 Microsoft Intune의 배포 파이프라인을 사용하여 Microsoft Managed Desktop 장치에만 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0639b-126">These apps can only be deployed to Microsoft Managed Desktop devices by using Microsoft Intune’s deployment pipeline.</span></span> <span data-ttu-id="0639b-127">앱이 필요한 경우 공급업체(Microsoft가 아닌 공급업체 또는 MCS(Microsoft Consulting Services)일 수 있는)에서 패키지로 제공하거나, 필요한 경우 패키지로 직접 패키지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0639b-127">If the app needs it you can have them packaged by a vendor (which could be a non-Microsoft vendor or Microsoft Consulting Services (MCS)) or if you have the means, you can package them yourself.</span></span> <span data-ttu-id="0639b-128">그런 다음 이러한 패키지를 Microsoft Managed Desktop 포털에 추가하고 Azure Active Directory 그룹에 할당하여 배포를 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="0639b-128">You then add these packages to the Microsoft Managed Desktop portal and assign them to Azure Active Directory groups to trigger the deployment.</span></span> 

<span data-ttu-id="0639b-129">현재 Microsoft Endpoint Configuration Manager를 사용하여 앱을 배포하는 경우 Microsoft Managed Desktop은 앱을 평가하는 쿼리를 제공하고 Microsoft Intune으로 마이그레이션할 준비가 된 쿼리와 일부 조정이 필요할 수 있는 앱을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0639b-129">If you currently deploy your apps by using Microsoft Endpoint Configuration Manager, Microsoft Managed Desktop can provide you with a query to assess your apps and discover which ones are ready for to migrate to Microsoft Intune and which ones might require some adjustment.</span></span>


### <a name="preparing-your-own-apps-for-inclusion-in-microsoft-managed-desktop"></a><span data-ttu-id="0639b-130">Microsoft Managed Desktop에 포함하기 위해 자체 앱 준비</span><span class="sxs-lookup"><span data-stu-id="0639b-130">Preparing your own apps for inclusion in Microsoft Managed Desktop</span></span>
<span data-ttu-id="0639b-131">앱을 검토하여 다음을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="0639b-131">Review your apps, checking:</span></span>

- <span data-ttu-id="0639b-132">[Microsoft Managed Desktop](../service-description/mmd-app-requirements.md)앱 요구 사항에 설명된 바와 같이 금지되거나 제한된 동작이 없는 앱은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0639b-132">None of the apps are prohibited or have restricted behavior, as described in [Microsoft Managed Desktop app requirements](../service-description/mmd-app-requirements.md).</span></span>
- <span data-ttu-id="0639b-133">Microsoft Intune에서 앱을 관리하기 위해 준비해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0639b-133">Apps must be ready for management by Microsoft Intune.</span></span> <span data-ttu-id="0639b-134">이 항목에 대한 자세한 내용은 [Microsoft Intune을 사용하여 Windows 10](/intune/apps-windows-10-app-deploy) 앱 배포 및 Microsoft [Intune에 앱 추가를 참조하세요.](/intune/apps-add)</span><span class="sxs-lookup"><span data-stu-id="0639b-134">For more about this topic, see [Windows 10 app deployment using Microsoft Intune](/intune/apps-windows-10-app-deploy) and [Add apps to Microsoft Intune](/intune/apps-add).</span></span>
- <span data-ttu-id="0639b-135">라이선스 키 제공, 사용 조건 계약 및 서버 연결 사전 설정과 같은 기타 패키징 전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="0639b-135">Other pre-packaging requirements such as providing license keys, agreement with license terms, and pre-setting server connections.</span></span>

### <a name="decide-how-to-package-apps"></a><span data-ttu-id="0639b-136">앱을 패키지하는 방법 결정</span><span class="sxs-lookup"><span data-stu-id="0639b-136">Decide how to package apps</span></span>

<span data-ttu-id="0639b-137">일부 독립 소프트웨어 게시자는 앱을 중앙에서 배포하기 전에 패키지해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0639b-137">Some independent software publishers might require that your apps are packaged before they are centrally deployed.</span></span> <span data-ttu-id="0639b-138">"패키징"은 앱을 백그라운드에서 설치할 수 있도록 앱의 설치 관리자를 라이선스 키, 원격 서버 위치 또는 데스크톱 바로 가기와 같은 설정으로 구성하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0639b-138">“Packaging” means that the app’s installer is configured with settings like license keys, remote server locations, or desktop shortcuts so that the app can be installed in the background.</span></span>

<span data-ttu-id="0639b-139">앱을 패키지로 다운로드하는 세 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0639b-139">There are three options to get your apps packaged:</span></span> 


- <span data-ttu-id="0639b-140">직접 앱을 패키지로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0639b-140">You can package apps yourself</span></span>
- <span data-ttu-id="0639b-141">Microsoft가 아닌 공급업체와 함께 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0639b-141">You can work with a non-Microsoft vendor</span></span>
- <span data-ttu-id="0639b-142">MCS와 함께 앱을 패키지로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0639b-142">You can engage with MCS to package your apps.</span></span> <span data-ttu-id="0639b-143">Microsoft 계정 담당자와 함께 작업합니다.</span><span class="sxs-lookup"><span data-stu-id="0639b-143">Work with your Microsoft account representative.</span></span> <span data-ttu-id="0639b-144">자세한 내용은 Microsoft Consulting Services 작업을 [참조하세요.](apps-MCS.md)</span><span class="sxs-lookup"><span data-stu-id="0639b-144">For more information, see [Working with Microsoft Consulting Services](apps-MCS.md).</span></span>



## <a name="deploying-apps"></a><span data-ttu-id="0639b-145">앱 배포</span><span class="sxs-lookup"><span data-stu-id="0639b-145">Deploying apps</span></span>

<span data-ttu-id="0639b-146">앱을 패키지로 다운로드하는 데 사용하는 모든 방법을 완료하면 [Microsoft Managed Desktop](../get-started/deploy-apps.md)디바이스에 앱 배포의 단계를 따를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0639b-146">Whatever method you use to get apps packaged, once that is complete, you're ready to follow the steps in [Deploy apps to Microsoft Managed Desktop devices](../get-started/deploy-apps.md).</span></span>