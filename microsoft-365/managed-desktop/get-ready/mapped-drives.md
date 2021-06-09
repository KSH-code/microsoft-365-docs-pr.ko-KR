---
title: Microsoft Managed Desktop의 매핑된 드라이브 준비
description: 사용자가 매핑된 드라이브의 데이터에 액세스할 수 있도록 하는 중요한 단계
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: f770f5083fe9193660b03e7971b09a127f2dae16
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574562"
---
#  <a name="prepare-mapped-drives-for-microsoft-managed-desktop"></a><span data-ttu-id="2c168-104">Microsoft Managed Desktop의 매핑된 드라이브 준비</span><span class="sxs-lookup"><span data-stu-id="2c168-104">Prepare mapped drives for Microsoft Managed Desktop</span></span>

<span data-ttu-id="2c168-105">대부분의 엔터프라이즈 환경에는 매핑된 드라이브에 대한 레거시 요구 사항이 있습니다. 이러한 요구 사항은 사용자 또는 팀이 파일을 공유하고 저장할 수 있도록 허용하거나, 또는 사내 응용 프로그램용입니다.</span><span class="sxs-lookup"><span data-stu-id="2c168-105">Many enterprise environments have legacy requirements for mapped drives to allow their users or teams to share and store files, or for on-premises applications.</span></span> <span data-ttu-id="2c168-106">Microsoft는 매핑된 드라이브와 함께 매핑된 드라이브를 사용하지 Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="2c168-106">Microsoft does not recommend the use of mapped drives with the Microsoft Managed Desktop.</span></span> <span data-ttu-id="2c168-107">대신 다음과 같이 파일 액세스 솔루션을 최신화하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2c168-107">Instead, we recommend that you modernize your file access solutions as follows:</span></span>
  
- <span data-ttu-id="2c168-108">개별 사용자가 사용하는 매핑된 드라이브를 마이그레이션하여 비즈니스용 OneDrive.</span><span class="sxs-lookup"><span data-stu-id="2c168-108">Migrate mapped drives used by individual users to OneDrive for Business.</span></span> 
- <span data-ttu-id="2c168-109">팀에서 파일을 공유하는 데 사용하는 매핑된 드라이브를 온라인 SharePoint 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="2c168-109">Migrate mapped drives used by teams to share files to SharePoint Online.</span></span> 
- <span data-ttu-id="2c168-110">해당 요구 사항을 제거하기 위해 사내 파일 공유를 사용하는 응용 프로그램을 최신화하거나 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="2c168-110">Modernize or replace any applications that use on-premises file shares to remove that requirement.</span></span>
  
<span data-ttu-id="2c168-111">이러한 서비스를 현대화하면 사용자 환경을 가장 잘 사용할 수 Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="2c168-111">Modernizing these services will allow the best user experience with Microsoft Managed Desktop.</span></span> <span data-ttu-id="2c168-112">Microsoft FastTrack 서비스는 Microsoft 클라우드 서비스를 사용하여 환경을 현대화하는 데 도움을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2c168-112">Microsoft FastTrack Services can assist you in modernizing your environment by using Microsoft Cloud Services.</span></span> <span data-ttu-id="2c168-113">적합한 서비스 및 계획에서 FastTrack 서비스를 [](/fasttrack/m365-eligible-services-and-plans) 사용할 자격이 있는지 확인한 다음 직접 연락하여 서비스 준비를 Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="2c168-113">You can check whether you're eligible for FastTrack services at [Eligible Services and Plans](/fasttrack/m365-eligible-services-and-plans) and then contact them directly to prepare for Microsoft Managed Desktop.</span></span> <span data-ttu-id="2c168-114">FastTrack 비즈니스용 OneDrive 또는 SharePoint 마이그레이션에 대한 배경 내용은 [데이터 마이그레이션을 참조하세요.](/fasttrack/o365-data-migration)</span><span class="sxs-lookup"><span data-stu-id="2c168-114">For background about FastTrack OneDrive for Business or SharePoint Online Migration, see [Data Migration](/fasttrack/o365-data-migration).</span></span>

## <a name="mapped-drives-on-microsoft-managed-desktop"></a><span data-ttu-id="2c168-115">드라이브의 매핑된 Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="2c168-115">Mapped drives on Microsoft Managed Desktop</span></span>
 
<span data-ttu-id="2c168-116">일부 사용 사례에 대해 매핑된 드라이브를 제거하거나 교체할 수 없는 경우 Microsoft Managed Desktop 관리 포털에서 지원 요청을 제출하여 Microsoft Managed Desktop 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c168-116">If you cannot remove or replace mapped drives for some use cases, you should submit a support request in the Microsoft Managed Desktop admin portal to have them deployed to Microsoft Managed Desktop users.</span></span>
    
<span data-ttu-id="2c168-117">이러한 요청의 경우 지원 요청에 다음 세부 정보를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c168-117">For such a request, you'll have to provide the following details in the support request:</span></span> 

- <span data-ttu-id="2c168-118">Microsoft Managed Desktop 위해 매핑해야 하는 파일 공유 위치에 대한 모든 UNC 경로</span><span class="sxs-lookup"><span data-stu-id="2c168-118">All UNC paths to file share locations that will need to be mapped for Microsoft Managed Desktop devices</span></span> 
- <span data-ttu-id="2c168-119">이러한 파일 공유 위치에 액세스해야 하는 사용자 그룹</span><span class="sxs-lookup"><span data-stu-id="2c168-119">User groups that require access to these file share locations</span></span> 
- <span data-ttu-id="2c168-120">할당해야 하는 특정 드라이브 문자(필요한 경우)</span><span class="sxs-lookup"><span data-stu-id="2c168-120">Any specific drive letter that needs to be assigned (if necessary)</span></span>

<span data-ttu-id="2c168-121">예:</span><span class="sxs-lookup"><span data-stu-id="2c168-121">For example:</span></span>

| <span data-ttu-id="2c168-122">드라이브 문자</span><span class="sxs-lookup"><span data-stu-id="2c168-122">Drive letter</span></span> | <span data-ttu-id="2c168-123">UNC 경로</span><span class="sxs-lookup"><span data-stu-id="2c168-123">UNC path</span></span> | <span data-ttu-id="2c168-124">사용자 그룹</span><span class="sxs-lookup"><span data-stu-id="2c168-124">User group</span></span> |
|--------------|----------|------------|
| <span data-ttu-id="2c168-125">X:</span><span class="sxs-lookup"><span data-stu-id="2c168-125">X:</span></span>  | <span data-ttu-id="2c168-126">\\\server\share\Marketing</span><span class="sxs-lookup"><span data-stu-id="2c168-126">\\\server\share\Marketing</span></span> | <span data-ttu-id="2c168-127">ContosoMarketing</span><span class="sxs-lookup"><span data-stu-id="2c168-127">ContosoMarketing</span></span> |

<span data-ttu-id="2c168-128">사용자 및 그룹이 파일 공유 위치에 액세스하기 위한 올바른 권한을 가지고 유지 관리하고, 액세스 가능한 상태로 유지 관리하고, 사내 파일 서비스에 계속 액세스할 수 있도록 하는 것은 전적으로 사용자의 책임입니다.</span><span class="sxs-lookup"><span data-stu-id="2c168-128">It's entirely your responsibility to ensure that users and groups have and maintain the right permissions to access file share locations and that the on-premises file services remain accessible.</span></span> <span data-ttu-id="2c168-129">또한 이러한 파일 공유에 대한 요구 사항을 최대한 빨리 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c168-129">Also, you should remove your requirements for such file shares as soon as possible.</span></span>

### <a name="to-have-mapped-drives-deployed-in-microsoft-managed-desktop"></a><span data-ttu-id="2c168-130">매핑된 드라이브를 배포할 수 Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="2c168-130">To have mapped drives deployed in Microsoft Managed Desktop</span></span>
 
<span data-ttu-id="2c168-131">매핑된 드라이브를 피할 수 없는지와 서비스 요청을 제출하기 전에 요구 사항을 신중하게 검토해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c168-131">Make sure that mapped drives cannot be avoided and you have carefully reviewed the requirements before submitting any service request.</span></span> <span data-ttu-id="2c168-132">그런 다음 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="2c168-132">Then follow these steps:</span></span>

1. <span data-ttu-id="2c168-133">서비스 [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) "문제 해결 + 지원"을 선택한 다음 Microsoft Managed Desktop 섹션에서 "서비스 요청"을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="2c168-133">Navigate to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and select "Troubleshooting + support" then look for "Service requests" under the Microsoft Managed Desktop section.</span></span>  
2. <span data-ttu-id="2c168-134">"매핑된 드라이브 배포"라는 지원 요청을 제출하고 필요한 모든 파일 공유 세부 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2c168-134">Submit a support request titled “Mapped drives deployment” and provide all the required file share details.</span></span>  
3. <span data-ttu-id="2c168-135">Microsoft Managed Desktop IT 운영은 요청이 완료되면 지원 요청 업데이트를 사용하여 이를 권고합니다.</span><span class="sxs-lookup"><span data-stu-id="2c168-135">Microsoft Managed Desktop IT Operations will advise, by using support request updates, when the request has been completed.</span></span> <span data-ttu-id="2c168-136">처음에 이 구성은 테스트 배포 그룹의 장치에만 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c168-136">Initially this configuration will only be deployed to devices in the Test deployment group.</span></span>  
4. <span data-ttu-id="2c168-137">IT 작업에서 배포한 구성이 예상한 Microsoft Managed Desktop 테스트하고 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c168-137">You must test and confirm whether the configuration deployed by the Microsoft Managed Desktop IT Operations works as you expect.</span></span> <span data-ttu-id="2c168-138">테스트를 완료한 후 동일한 지원 요청의 세부 정보에서 Microsoft Managed Desktop IT 작업에게 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c168-138">Reply using the Discussion tab in the details of the same support request to notify Microsoft Managed Desktop IT Operations once you've completed your testing.</span></span>  
5. <span data-ttu-id="2c168-139">Microsoft Managed Desktop IT 운영 팀은 구성을 다른 배포 그룹에 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="2c168-139">Microsoft Managed Desktop IT Operations team will then deploy the configuration to the other deployment groups.</span></span> 

## <a name="steps-to-get-ready"></a><span data-ttu-id="2c168-140">준비 단계</span><span class="sxs-lookup"><span data-stu-id="2c168-140">Steps to get ready</span></span>

1. <span data-ttu-id="2c168-141">에 대한 [선행 Microsoft Managed Desktop.](prerequisites.md)</span><span class="sxs-lookup"><span data-stu-id="2c168-141">Review [Prerequisites for Microsoft Managed Desktop](prerequisites.md).</span></span>
2. <span data-ttu-id="2c168-142">[준비 평가 도구를 사용합니다.](readiness-assessment-tool.md)</span><span class="sxs-lookup"><span data-stu-id="2c168-142">[Use Readiness assessment tools](readiness-assessment-tool.md).</span></span>
3. [<span data-ttu-id="2c168-143">게스트 계정에 대한 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="2c168-143">Prerequisites for guest accounts</span></span>](guest-accounts.md)
4. [<span data-ttu-id="2c168-144">Microsoft Managed Desktop의 네트워크 구성</span><span class="sxs-lookup"><span data-stu-id="2c168-144">Network configuration for Microsoft Managed Desktop</span></span>](network.md)
5. [<span data-ttu-id="2c168-145">Microsoft Managed Desktop 인증서 및 네트워크 프로필 준비</span><span class="sxs-lookup"><span data-stu-id="2c168-145">Prepare certificates and network profiles for Microsoft Managed Desktop</span></span>](certs-wifi-lan.md)
6. [<span data-ttu-id="2c168-146">Microsoft Managed Desktop의 온-프레미스 리소스 액세스 준비</span><span class="sxs-lookup"><span data-stu-id="2c168-146">Prepare on-premises resources access for Microsoft Managed Desktop</span></span>](authentication.md)
7. [<span data-ttu-id="2c168-147">Microsoft Managed Desktop의 앱</span><span class="sxs-lookup"><span data-stu-id="2c168-147">Apps in Microsoft Managed Desktop</span></span>](apps.md)
8. <span data-ttu-id="2c168-148">[매핑된 드라이브에서 Microsoft Managed Desktop](mapped-drives.md) 준비(이 문서)</span><span class="sxs-lookup"><span data-stu-id="2c168-148">[Prepare mapped drives for Microsoft Managed Desktop](mapped-drives.md) (This article)</span></span>
9. [<span data-ttu-id="2c168-149">Microsoft Managed Desktop의 인쇄 리소스 준비</span><span class="sxs-lookup"><span data-stu-id="2c168-149">Prepare printing resources for Microsoft Managed Desktop</span></span>](printing.md)
