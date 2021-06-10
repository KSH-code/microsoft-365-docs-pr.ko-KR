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
audience: Admin
ms.openlocfilehash: 571acc9c240fc0243998050ac3013258a2f85a3e
ms.sourcegitcommit: e02cf5702af178ddd2968877a808874ecb49ed2c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2021
ms.locfileid: "52028947"
---
# <a name="apps-in-microsoft-managed-desktop"></a><span data-ttu-id="6ceb5-104">Microsoft Managed Desktop의 앱</span><span class="sxs-lookup"><span data-stu-id="6ceb5-104">Apps in Microsoft Managed Desktop</span></span>

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
## <a name="apps-generally"></a><span data-ttu-id="6ceb5-105">일반적으로 앱</span><span class="sxs-lookup"><span data-stu-id="6ceb5-105">Apps generally</span></span>

<span data-ttu-id="6ceb5-106">Microsoft에는 앱에 참여하는 데 필요한 Microsoft 365 E3 또는 E5 라이선스와 함께 특정 주요 앱이 Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="6ceb5-106">Microsoft includes certain key apps along with the Microsoft 365 E3 or E5 license needed to participate in Microsoft Managed Desktop.</span></span> <span data-ttu-id="6ceb5-107">그러나 이러한 앱을 제공하겠지만 여전히 완료할 특정 책임과 작업이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ceb5-107">However, even though we provide these apps, you still have certain responsibilities and actions to complete.</span></span>

<span data-ttu-id="6ceb5-108">또한 앱 배포 파이프라인을 사용하여 회사 포털 필요한 백그라운드 설치를 통해 셀프 서비스를 위해 Microsoft가 아닌 다른 앱을 Microsoft Intune 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ceb5-108">You can also deploy additional non-Microsoft apps to your users for self-service through the Company Portal or a required background installation, all using Microsoft Intune’s deployment pipeline.</span></span> 

## <a name="apps-provided-by-microsoft"></a><span data-ttu-id="6ceb5-109">Microsoft에서 제공하는 앱</span><span class="sxs-lookup"><span data-stu-id="6ceb5-109">Apps provided by Microsoft</span></span>

<span data-ttu-id="6ceb5-110">Microsoft Managed Desktop 라이선스에 포함된 앱의 64비트 버전은 엔터프라이즈용 Microsoft 365 앱 Standard Suite(Word, Excel, PowerPoint, Outlook, Publisher, Access, 비즈니스용 Skype 및 OneNote)입니다. Click-to-Run 버전의 Microsoft Project Visio 기본적으로 포함되지 않지만  추가를 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ceb5-110">Included with your Microsoft Managed Desktop license are 64-bit versions of the apps in the Microsoft 365 Apps for enterprise Standard Suite (Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for Business, and OneNote.) Click-to-Run versions of Microsoft Project and Visio are *not* included by default, but you can request them to be added.</span></span> <span data-ttu-id="6ceb5-111">이러한 앱에 대한 자세한 내용은 디바이스에 Microsoft Project 또는 Microsoft Visio [설치를 Microsoft Managed Desktop 참조하세요.](../get-started/project-visio.md)</span><span class="sxs-lookup"><span data-stu-id="6ceb5-111">For more information about these apps, see [Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices](../get-started/project-visio.md).</span></span>

### <a name="what-microsoft-does-to-support-the-apps-we-provide"></a><span data-ttu-id="6ceb5-112">Microsoft에서 제공하는 앱을 지원하기 위해 Microsoft가 하는 일</span><span class="sxs-lookup"><span data-stu-id="6ceb5-112">What Microsoft does to support the apps we provide</span></span>

<span data-ttu-id="6ceb5-113">Microsoft는 포함된 앱의 배포, 업데이트 및 지원을 위한 전체 엔터프라이즈용 Microsoft 365 앱 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6ceb5-113">Microsoft will provide full service for the deployment, update, and support for the included Microsoft 365 Apps for enterprise apps.</span></span> <span data-ttu-id="6ceb5-114">Microsoft Project 및 Visio 클릭하여 실행 버전은 기본적으로 포함되지  않지만 Microsoft Managed Desktop 배포 그룹을 제공하므로 IT 관리자가 라이선스를 관리하고 조직에 적합한 응용 프로그램을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ceb5-114">Click-to-Run versions of Microsoft Project and Visio are *not* included by default, but Microsoft Managed Desktop will provide deployment groups allowing your IT administrator to manage licenses and deploy these applications appropriately for your organization.</span></span> <span data-ttu-id="6ceb5-115">Microsoft는 지원 채널을 통해 이러한 응용 Microsoft Managed Desktop 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="6ceb5-115">Microsoft will support users of these applications through the Microsoft Managed Desktop support channels.</span></span>

### <a name="what-you-need-to-do-to-support-the-apps-we-provide"></a><span data-ttu-id="6ceb5-116">제공한 앱을 지원하기 위해 필요한 일</span><span class="sxs-lookup"><span data-stu-id="6ceb5-116">What you need to do to support the apps we provide</span></span>

<span data-ttu-id="6ceb5-117">이러한 앱에서는 여전히 몇 가지 작업을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ceb5-117">There are still certain things you need to do with these apps:</span></span>

- <span data-ttu-id="6ceb5-118">**라이선스 할당** - 사용자에게 적절한 라이선스를 획득하고 할당해야 엔터프라이즈용 Microsoft 365 앱.</span><span class="sxs-lookup"><span data-stu-id="6ceb5-118">**Assign licenses** - You are responsible for obtaining and assigning the appropriate licenses to users for Microsoft 365 Apps for enterprise.</span></span>
- <span data-ttu-id="6ceb5-119">**보안 그룹에** 사용자 추가 - Microsoft Project 또는 Visio 사용하는 경우 IT 관리자가 해당 사용자를 적절한 배포 그룹에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ceb5-119">**Add users to security groups** - If you're using Microsoft Project or Visio, your IT administrator must add those users to the appropriate deployment groups.</span></span> <span data-ttu-id="6ceb5-120">또한 IT 관리자는 퇴사하는 경우 해당 사용자로부터 라이선스를 취득할 책임이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ceb5-120">IT administrators are also responsible for reclaiming licenses from those users if they leave the company.</span></span>
- <span data-ttu-id="6ceb5-121">**추가 Microsoft 365** 배포 - 모든 엔터프라이즈용 Microsoft 365 앱 앱에 대한 추가 기능을 필요로 하는 경우 다른 Windows 32 앱처럼 중앙에서 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="6ceb5-121">**Deploy Microsoft 365 Add-ons** - If you need any Add-ons for any of the Microsoft 365 Apps for enterprise apps, deploy them centrally like any other Windows 32 app.</span></span> 

## <a name="apps-you-provide"></a><span data-ttu-id="6ceb5-122">제공하는 앱</span><span class="sxs-lookup"><span data-stu-id="6ceb5-122">Apps you provide</span></span>

<span data-ttu-id="6ceb5-123">비즈니스 작업에 필요한 다른 앱이 있는 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ceb5-123">You probably have other apps you need for your business operations.</span></span> <span data-ttu-id="6ceb5-124">이러한 앱은 Microsoft Managed Desktop 파이프라인을 사용하여 Microsoft Intune 장치로만 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ceb5-124">These apps can only be deployed to Microsoft Managed Desktop devices by using Microsoft Intune’s deployment pipeline.</span></span> <span data-ttu-id="6ceb5-125">응용 프로그램 배포에 대한 자세한 내용은 [Deploy apps to Microsoft Managed Desktop 참조하십시오.](../get-started/deploy-apps.md)</span><span class="sxs-lookup"><span data-stu-id="6ceb5-125">For more information about application deployment follow the steps in [Deploy apps to Microsoft Managed Desktop devices](../get-started/deploy-apps.md).</span></span>

### <a name="preparing-your-own-apps-for-inclusion-in-microsoft-managed-desktop"></a><span data-ttu-id="6ceb5-126">앱에 포함하기 위해 자체 앱 Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="6ceb5-126">Preparing your own apps for inclusion in Microsoft Managed Desktop</span></span>
<span data-ttu-id="6ceb5-127">앱을 검토하여 다음을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="6ceb5-127">Review your apps, checking:</span></span>

- <span data-ttu-id="6ceb5-128">앱 요구 사항에 설명된 바와 같이 어떤 앱도 금지되거나 제한된 Microsoft Managed Desktop [없습니다.](../service-description/mmd-app-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="6ceb5-128">None of the apps are prohibited or have restricted behavior, as described in [Microsoft Managed Desktop app requirements](../service-description/mmd-app-requirements.md).</span></span>
- <span data-ttu-id="6ceb5-129">앱을 관리하기 위한 준비가 완료되어야 Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="6ceb5-129">Apps must be ready for management by Microsoft Intune.</span></span> <span data-ttu-id="6ceb5-130">이 항목에 대한 자세한 [내용은](/intune/apps-windows-10-app-deploy) Windows 10 앱 배포 및 Microsoft Intune 앱 추가를 [Microsoft Intune.](/intune/apps-add)</span><span class="sxs-lookup"><span data-stu-id="6ceb5-130">For more about this topic, see [Windows 10 app deployment using Microsoft Intune](/intune/apps-windows-10-app-deploy) and [Add apps to Microsoft Intune](/intune/apps-add).</span></span>
- <span data-ttu-id="6ceb5-131">라이선스 키 제공, 사용 조건 계약 및 서버 연결 사전 설정과 같은 기타 패키징 전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="6ceb5-131">Other pre-packaging requirements such as providing license keys, agreement with license terms, and pre-setting server connections.</span></span>

## <a name="steps-to-get-ready"></a><span data-ttu-id="6ceb5-132">준비 단계</span><span class="sxs-lookup"><span data-stu-id="6ceb5-132">Steps to get ready</span></span>

1. <span data-ttu-id="6ceb5-133">에 대한 [선행 Microsoft Managed Desktop.](prerequisites.md)</span><span class="sxs-lookup"><span data-stu-id="6ceb5-133">Review [Prerequisites for Microsoft Managed Desktop](prerequisites.md).</span></span>
2. <span data-ttu-id="6ceb5-134">준비 [평가 도구를 사용합니다.](readiness-assessment-tool.md)</span><span class="sxs-lookup"><span data-stu-id="6ceb5-134">Use [Readiness assessment tools](readiness-assessment-tool.md).</span></span>
3. [<span data-ttu-id="6ceb5-135">게스트 계정에 대한 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="6ceb5-135">Prerequisites for guest accounts</span></span>](guest-accounts.md)
4. [<span data-ttu-id="6ceb5-136">Microsoft Managed Desktop의 네트워크 구성</span><span class="sxs-lookup"><span data-stu-id="6ceb5-136">Network configuration for Microsoft Managed Desktop</span></span>](network.md)
5. [<span data-ttu-id="6ceb5-137">Microsoft Managed Desktop 인증서 및 네트워크 프로필 준비</span><span class="sxs-lookup"><span data-stu-id="6ceb5-137">Prepare certificates and network profiles for Microsoft Managed Desktop</span></span>](certs-wifi-lan.md)
6. [<span data-ttu-id="6ceb5-138">Microsoft Managed Desktop의 온-프레미스 리소스 액세스 준비</span><span class="sxs-lookup"><span data-stu-id="6ceb5-138">Prepare on-premises resources access for Microsoft Managed Desktop</span></span>](authentication.md)
7. <span data-ttu-id="6ceb5-139">[앱의 Microsoft Managed Desktop(이](apps.md) 문서)</span><span class="sxs-lookup"><span data-stu-id="6ceb5-139">[Apps in Microsoft Managed Desktop](apps.md) (This article)</span></span>
8. [<span data-ttu-id="6ceb5-140">Microsoft Managed Desktop의 매핑된 드라이브 준비</span><span class="sxs-lookup"><span data-stu-id="6ceb5-140">Prepare mapped drives for Microsoft Managed Desktop</span></span>](mapped-drives.md)
9. [<span data-ttu-id="6ceb5-141">Microsoft Managed Desktop의 인쇄 리소스 준비</span><span class="sxs-lookup"><span data-stu-id="6ceb5-141">Prepare printing resources for Microsoft Managed Desktop</span></span>](printing.md)
