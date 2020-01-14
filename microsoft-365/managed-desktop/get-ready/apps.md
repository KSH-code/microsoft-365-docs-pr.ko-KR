---
title: Microsoft Managed Desktop의 앱
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: ea6cc92fe84cc39502e3db97361ff9d294fdfca2
ms.sourcegitcommit: 39bd4be7e8846770f060b5dd7d895fc8040b18f5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/14/2020
ms.locfileid: "41112662"
---
# <a name="apps-in-microsoft-managed-desktop"></a><span data-ttu-id="09ad5-103">Microsoft Managed Desktop의 앱</span><span class="sxs-lookup"><span data-stu-id="09ad5-103">Apps in Microsoft Managed Desktop</span></span>

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
## <a name="apps-generally"></a><span data-ttu-id="09ad5-104">일반적으로 앱</span><span class="sxs-lookup"><span data-stu-id="09ad5-104">Apps generally</span></span>

<span data-ttu-id="09ad5-105">Microsoft에는 microsoft Managed Desktop에 참여 하는 데 필요한 Microsoft 365 E3 또는 E5 라이선스와 함께 특정 주요 앱이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09ad5-105">Microsoft includes certain key apps along with the Microsoft 365 E3 or E5 license needed to participate in Microsoft Managed Desktop.</span></span> <span data-ttu-id="09ad5-106">그러나 이러한 앱을 제공 하더라도 완료 해야 하는 몇 가지 책임과 작업이 계속 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09ad5-106">However, even though we provide these apps, you still have certain responsibilities and actions to complete.</span></span>

<span data-ttu-id="09ad5-107">또한 Microsoft Intune의 배포 파이프라인을 사용 하 여 회사 포털 또는 필요한 백그라운드 설치를 통해 셀프 서비스에 대 한 타사 앱을 추가 하 여 최종 사용자에 게 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09ad5-107">You can also deploy additional non-Microsoft apps to your end users for self-service through the Company Portal or a required background installation, all using Microsoft Intune’s deployment pipeline.</span></span> <span data-ttu-id="09ad5-108">전문 지식을 보유 한 사용자는 자신이 필요로 하는 앱을 마이그레이션할 수 있습니다. MCS (Microsoft 컨설팅 서비스) 또는 타사 공급 업체가 아니면 패키징 및 마이그레이션 프로젝트에 도움을 주는 데 도움이 될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="09ad5-108">If you have the expertise you can migrate those apps you need yourself; if not either Microsoft Consulting Services (MCS) or non-Microsoft vendors will be happy to help you with a packaging and migration project.</span></span> <span data-ttu-id="09ad5-109">MCS에서 작업 하는 방법에 대 한 자세한 내용은 [Microsoft 컨설팅 Services 사용](apps-MCS.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="09ad5-109">For more information about working with MCS, see [Working with Microsoft Consulting Services](apps-MCS.md).</span></span>


## <a name="apps-provided-by-microsoft"></a><span data-ttu-id="09ad5-110">Microsoft에서 제공 하는 앱</span><span class="sxs-lookup"><span data-stu-id="09ad5-110">Apps provided by Microsoft</span></span>

<span data-ttu-id="09ad5-111">Microsoft Managed Desktop license에는 Office 365 ProPlus Standard 제품군 (Word, Excel, PowerPoint, Outlook, Publisher, Access, 비즈니스용 Skype, OneNote)의 앱이 64 비트 버전으로 포함 되어 있습니다. 간편 실행 버전의 Microsoft Project 및 Visio는 기본적으로 포함 되어 *있지* 않지만 추가 하도록 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09ad5-111">Included with your Microsoft Managed Desktop license are 64-bit versions of the apps in the Office 365 ProPlus Standard Suite (Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for Business, and OneNote.) Click-to-Run versions of Microsoft Project and Visio are *not* included by default, but you can request them to be added.</span></span> <span data-ttu-id="09ad5-112">이러한 앱에 대 한 자세한 내용은 microsoft [Managed 데스크톱 장치에서 Microsoft Project 또는 Microsoft Visio 설치](../get-started/project-visio.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="09ad5-112">For more information about these apps, see [Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices](../get-started/project-visio.md).</span></span>

### <a name="what-microsoft-does-to-support-the-apps-we-provide"></a><span data-ttu-id="09ad5-113">제공 되는 앱을 지원 하기 위해 Microsoft에서 수행 하는 작업</span><span class="sxs-lookup"><span data-stu-id="09ad5-113">What Microsoft does to support the apps we provide</span></span>

<span data-ttu-id="09ad5-114">Microsoft는 포함 된 Office 365 ProPlus 앱에 대 한 배포, 업데이트 및 지원에 대 한 전체 서비스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="09ad5-114">Microsoft will provide full service for the deployment, update, and support for the included Office 365 ProPlus apps.</span></span> <span data-ttu-id="09ad5-115">간편 실행 버전의 Microsoft Project 및 Visio는 기본적으로 포함 되어 *있지* 않지만 Microsoft Managed Desktop은 배포 그룹을 제공 하므로 IT 관리자가 라이선스를 관리 하 고 이러한 응용 프로그램을 조직에 적절 하 게 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09ad5-115">Click-to-Run versions of Microsoft Project and Visio are *not* included by default, but Microsoft Managed Desktop will provide deployment groups allowing your IT administrator to manage licenses and deploy these applications appropriately for your organization.</span></span> <span data-ttu-id="09ad5-116">Microsoft는 Microsoft 관리 데스크톱 지원 채널을 통해 이러한 응용 프로그램의 최종 사용자를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="09ad5-116">Microsoft will support end users of these applications through the Microsoft Managed Desktop support channels.</span></span>

### <a name="what-you-need-to-do-to-support-the-apps-we-provide"></a><span data-ttu-id="09ad5-117">제공한 앱을 지원 하기 위해 수행 해야 하는 작업</span><span class="sxs-lookup"><span data-stu-id="09ad5-117">What you need to do to support the apps we provide</span></span>

<span data-ttu-id="09ad5-118">이러한 앱은 여전히 수행 해야 하는 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="09ad5-118">There are still certain things you need to do with these apps:</span></span>

- <span data-ttu-id="09ad5-119">**라이선스 할당** -최종 사용자에 게 Office 365 ProPlus에 대 한 적절 한 라이선스를 구하여 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09ad5-119">**Assign licenses** - You are responsible for obtaining and assigning the appropriate licenses to end users for Office 365 ProPlus.</span></span>
- <span data-ttu-id="09ad5-120">**보안 그룹에 사용자 추가** -Microsoft 프로젝트나 Visio를 사용 하는 경우 IT 관리자가 해당 사용자를 적절 한 배포 그룹에 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09ad5-120">**Add users to security groups** - If you're using Microsoft Project or Visio, your IT administrator must add those users to the appropriate deployment groups.</span></span> <span data-ttu-id="09ad5-121">또한 IT 관리자는 해당 사용자가 회사를 떠날 때 라이선스를 다시 확보 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09ad5-121">IT administrators are also responsible for reclaiming licenses from those users if they leave the company.</span></span>
- <span data-ttu-id="09ad5-122">Office **365 Addons 배포** -Office 365 ProPlus 앱에 대 한 Addons가 필요한 경우 다른 Windows 32 앱과 마찬가지로 중앙 집중식으로 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="09ad5-122">**Deploy Office 365 Addons** - If you need any Addons for any of the Office 365 ProPlus apps, deploy them centrally like any other Windows 32 app.</span></span> 

## <a name="apps-you-provide"></a><span data-ttu-id="09ad5-123">사용자가 제공한 앱</span><span class="sxs-lookup"><span data-stu-id="09ad5-123">Apps you provide</span></span>

<span data-ttu-id="09ad5-124">물론 비즈니스 작업에 필요한 다른 앱이 많이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09ad5-124">Of course, you probably have a number of other apps you need for your business operations.</span></span> <span data-ttu-id="09ad5-125">이러한 장치는 Microsoft Intune의 배포 파이프라인을 사용 하 여 Microsoft Managed Desktop devices에만 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09ad5-125">These can can only be deployed to Microsoft Managed Desktop devices by using Microsoft Intune’s deployment pipeline.</span></span> <span data-ttu-id="09ad5-126">앱이 필요한 경우 공급 업체에 의해 패키지 패키지로 제공 될 수 있습니다 (Microsoft 제품이 아닌 다른 공급 업체나 Microsoft 컨설팅 서비스 (MCS) 일 수 있음) 아니면이 방법을 사용 하는 경우 직접 패키지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09ad5-126">If the app needs it you can have them packaged by a vendor (which could be a non-Microsoft vendor or Microsoft Consulting Services (MCS)) or if you have the means, you can package them yourself.</span></span> <span data-ttu-id="09ad5-127">그런 다음 이러한 패키지를 Microsoft Managed Desktop portal에 추가 하 고이를 Azure Active Directory 그룹에 할당 하 여 배포를 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="09ad5-127">You then add these packages to the Microsoft Managed Desktop portal and assign them to Azure Active Directory groups to trigger the deployment.</span></span> 

<span data-ttu-id="09ad5-128">현재 Microsoft Endpoint Configuration Manager를 사용 하 여 앱을 배포 하는 경우 Microsoft Managed Desktop은 앱을 평가 하는 쿼리를 제공 하 고 Microsoft Intune으로 마이그레이션할 준비가 된 것과 몇 가지 문제가 발생할 수 있는 항목을 파악 하는 데 도움이 될 수 있습니다. 조절.</span><span class="sxs-lookup"><span data-stu-id="09ad5-128">If you currently deploy your apps by using Microsoft Endpoint Configuration Manager, Microsoft Managed Desktop can provide you with a query to assess your apps and discover which ones are ready for to migrate to Microsoft Intune and which ones might require some adjustment.</span></span>


### <a name="preparing-your-own-apps-for-inclusion-in-microsoft-managed-desktop"></a><span data-ttu-id="09ad5-129">Microsoft Managed Desktop에 포함할 앱 준비</span><span class="sxs-lookup"><span data-stu-id="09ad5-129">Preparing your own apps for inclusion in Microsoft Managed Desktop</span></span>
<span data-ttu-id="09ad5-130">앱을 검토 하 고 다음을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="09ad5-130">Review your apps, checking:</span></span>

- <span data-ttu-id="09ad5-131">[Microsoft Managed Desktop app 요구 사항](https://aka.ms/app-req)에 설명 된 대로 어떤 앱도 금지 되거나 제한 된 동작이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09ad5-131">None of the apps are prohibited or have restricted behavior, as described in [Microsoft Managed Desktop app requirements](https://aka.ms/app-req).</span></span>
- <span data-ttu-id="09ad5-132">앱은 Microsoft Intune을 통해 관리할 준비가 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09ad5-132">Apps must be ready for management by Microsoft Intune.</span></span> <span data-ttu-id="09ad5-133">이에 대 한 자세한 내용은 [Microsoft intune을 사용 하 여 Windows 10 앱 배포](https://docs.microsoft.com/intune/apps-windows-10-app-deploy) 및 [microsoft Intune에 앱 추가](https://docs.microsoft.com/intune/apps-add)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="09ad5-133">For more about this, see [Windows 10 app deployment using Microsoft Intune](https://docs.microsoft.com/intune/apps-windows-10-app-deploy) and [Add apps to Microsoft Intune](https://docs.microsoft.com/intune/apps-add).</span></span>
- <span data-ttu-id="09ad5-134">라이선스 키 제공, 사용권 조항에 대 한 계약, 사전 설정 서버 연결 등의 기타 사전 패키징 요구 사항</span><span class="sxs-lookup"><span data-stu-id="09ad5-134">Other pre-packaging requirements such as providing license keys, agreement with license terms, and pre-setting server connections.</span></span>

### <a name="decide-how-to-package-apps"></a><span data-ttu-id="09ad5-135">앱을 패키지 하는 방법을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="09ad5-135">Decide how to package apps</span></span>

<span data-ttu-id="09ad5-136">일부 독립 소프트웨어 공급 업체에서는 앱이 중앙에서 배포 되기 전에 패키지 되도록 해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09ad5-136">Some independent software vendors might require that your apps are packaged before they are centrally deployed.</span></span> <span data-ttu-id="09ad5-137">"패키징"은 앱의 설치 관리자가 앱을 백그라운드에서 설치할 수 있도록 라이선스 키, 원격 서버 위치 또는 바탕 화면 바로 가기와 같은 설정으로 구성 됨을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="09ad5-137">“Packaging” means that the app’s installer is configured with settings like license keys, remote server locations, or desktop shortcuts so that the app can be installed in the background.</span></span>

<span data-ttu-id="09ad5-138">앱을 패키지 하는 세 가지 옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="09ad5-138">There are three options to get your apps packaged:</span></span> 


- <span data-ttu-id="09ad5-139">앱을 직접 패키지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09ad5-139">You can package apps yourself</span></span>
- <span data-ttu-id="09ad5-140">Microsoft 제품이 아닌 다른 공급 업체와 함께 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09ad5-140">You can work with a non-Microsoft vendor</span></span>
- <span data-ttu-id="09ad5-141">MCS를 사용 하 여 앱을 패키지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09ad5-141">You can engage with MCS to package your apps.</span></span> <span data-ttu-id="09ad5-142">Microsoft 계정 담당자와 함께 작업 합니다.</span><span class="sxs-lookup"><span data-stu-id="09ad5-142">Work with your Microsoft account representative.</span></span> <span data-ttu-id="09ad5-143">자세한 내용은 [Microsoft 컨설팅 서비스 작업](apps-MCS.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="09ad5-143">For more details, see [Working with Microsoft Consulting Services](apps-MCS.md).</span></span>







## <a name="deploying-apps"></a><span data-ttu-id="09ad5-144">앱 배포</span><span class="sxs-lookup"><span data-stu-id="09ad5-144">Deploying apps</span></span>

<span data-ttu-id="09ad5-145">앱 패키지를 가져오는 데 사용 하는 방법에 관계 없이 완료 되 면 [Microsoft Managed 데스크톱 장치에 앱 배포](../get-started/deploy-apps.md)의 단계를 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09ad5-145">Whatever method you use to get apps packaged, once that is complete, you're ready to follow the steps in [Deploy apps to Microsoft Managed Desktop devices](../get-started/deploy-apps.md).</span></span>


