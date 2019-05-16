---
title: Microsoft Managed Desktop에 대 한 매핑된 드라이브 준비
description: 확인 해야 하는 중요 한 단계
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 설명서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: b3fc4a4ed82c01188f348d2e494a0dbf7effc77a
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "34079275"
---
#  <a name="prepare-mapped-drives-for-microsoft-managed-desktop"></a><span data-ttu-id="dbb33-104">Microsoft Managed Desktop에 대 한 매핑된 드라이브 준비</span><span class="sxs-lookup"><span data-stu-id="dbb33-104">Prepare mapped drives for Microsoft Managed Desktop</span></span>

<span data-ttu-id="dbb33-105">대부분의 엔터프라이즈 환경에서는 사용자 또는 팀이 파일을 공유 및 저장 하거나 온-프레미스 응용 프로그램을 사용할 수 있도록 매핑된 드라이브에 대 한 레거시 요구 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbb33-105">Many enterprise environments have legacy requirements for mapped drives to allow their users or teams to share and store files, or for on-premises applications.</span></span> <span data-ttu-id="dbb33-106">Microsoft 관리 데스크톱에서는 매핑된 드라이브를 사용 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="dbb33-106">Microsoft does not recommend the use of mapped drives with the Microsoft Managed Desktop.</span></span> <span data-ttu-id="dbb33-107">대신 다음과 같이 yor 파일 액세스 솔루션을 modernize 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="dbb33-107">Instead, we recommend that you modernize yor file access solutions as follows:</span></span>
  
- <span data-ttu-id="dbb33-108">개별 사용자가 사용 하는 매핑된 드라이브를 비즈니스용 OneDrive로 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="dbb33-108">Migrate mapped drives used by individual users to OneDrive for Business.</span></span> 
- <span data-ttu-id="dbb33-109">팀에서 SharePoint Online으로 파일을 공유 하는 데 사용 하는 매핑된 드라이브를 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="dbb33-109">Migrate mapped drives used by teams to share files to SharePoint Online.</span></span> 
- <span data-ttu-id="dbb33-110">온-프레미스 파일 공유를 사용 하는 모든 응용 프로그램을 Modernize 하거나 대체 하 여 해당 요구 사항을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbb33-110">Modernize or replace any applications that use on-premises file shares to remove that requirement.</span></span>
  
<span data-ttu-id="dbb33-111">현대화 이러한 서비스를 사용 하면 최상의 최종 사용자 환경을 Microsoft Managed Desktop과 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbb33-111">Modernizing these services will allow the best end-user experience with Microsoft Managed Desktop.</span></span> <span data-ttu-id="dbb33-112">Microsoft FastTrack 서비스는 Microsoft 클라우드 서비스를 사용 하 여 환경 현대화를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbb33-112">Microsoft FastTrack Services can assist you in modernizing your environment by using Microsoft Cloud Services.</span></span> <span data-ttu-id="dbb33-113">[적합 한 서비스 및 계획](https://docs.microsoft.com/fasttrack/m365-eligible-services-and-plans) 에서 fasttrack 서비스를 사용할 수 있는지 여부를 확인 한 다음 Microsoft Managed Desktop을 준비 하기 위해 직접 연락 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbb33-113">You can check whether you're eligible for FastTrack services at [Eligible Services and Plans](https://docs.microsoft.com/fasttrack/m365-eligible-services-and-plans) and then contact them directly to prepare for Microsoft Managed Desktop.</span></span> <span data-ttu-id="dbb33-114">FastTrack 비즈니스용 OneDrive 또는 SharePoint Online 마이그레이션에 대 한 배경 정보는 [데이터 마이그레이션을](https://docs.microsoft.com/fasttrack/o365-data-migration)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="dbb33-114">For background about FastTrack OneDrive for Business or SharePoint Online Migration, see [Data Migration](https://docs.microsoft.com/fasttrack/o365-data-migration).</span></span>

## <a name="mapped-drives-on-microsoft-managed-desktop"></a><span data-ttu-id="dbb33-115">Microsoft Managed Desktop의 매핑된 드라이브</span><span class="sxs-lookup"><span data-stu-id="dbb33-115">Mapped drives on Microsoft Managed Desktop</span></span>
 
<span data-ttu-id="dbb33-116">일부 사용 사례에서 매핑된 드라이브를 제거 하거나 바꿀 수 없는 경우 microsoft managed desktop portal에서 지원 요청을 제출 하 여 Microsoft Managed Desktop users에 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbb33-116">If you cannot remove or replace mapped drives for some use cases, you should submit a support request in the Microsoft Managed Desktop portal to have them deployed to Microsoft Managed Desktop users.</span></span>
    
<span data-ttu-id="dbb33-117">이러한 요청의 경우 지원 요청에 다음과 같은 세부 정보를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbb33-117">For such a request, you'll have to provide the following details in the support request:</span></span> 

- <span data-ttu-id="dbb33-118">Microsoft Managed Desktop 장치에 대해 매핑되어야 하는 파일 공유 위치의 모든 UNC 경로</span><span class="sxs-lookup"><span data-stu-id="dbb33-118">All UNC paths to file share locations that will need to be mapped for Microsoft Managed Desktop devices</span></span> 
- <span data-ttu-id="dbb33-119">이러한 파일 공유 위치에 액세스 해야 하는 사용자 그룹</span><span class="sxs-lookup"><span data-stu-id="dbb33-119">User groups that require access to these file share locations</span></span> 
- <span data-ttu-id="dbb33-120">할당 해야 하는 특정 드라이브 문자 (필요한 경우)</span><span class="sxs-lookup"><span data-stu-id="dbb33-120">Any specific drive letter that needs to be assigned (if necessary)</span></span>

<span data-ttu-id="dbb33-121">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="dbb33-121">For example:</span></span>

| <span data-ttu-id="dbb33-122">드라이브 문자</span><span class="sxs-lookup"><span data-stu-id="dbb33-122">Drive letter</span></span> | <span data-ttu-id="dbb33-123">UNC 경로</span><span class="sxs-lookup"><span data-stu-id="dbb33-123">UNC path</span></span> | <span data-ttu-id="dbb33-124">사용자 그룹</span><span class="sxs-lookup"><span data-stu-id="dbb33-124">User group</span></span> |
|--------------|----------|------------|
| <span data-ttu-id="dbb33-125">좌표</span><span class="sxs-lookup"><span data-stu-id="dbb33-125">X:</span></span>  | <span data-ttu-id="dbb33-126">\\\server\share\Marketing</span><span class="sxs-lookup"><span data-stu-id="dbb33-126">\\\server\share\Marketing</span></span> | <span data-ttu-id="dbb33-127">ContosoMarketing</span><span class="sxs-lookup"><span data-stu-id="dbb33-127">ContosoMarketing</span></span> |

<span data-ttu-id="dbb33-128">사용자와 그룹이 파일 공유 위치에 액세스 하기 위한 적절 한 권한을 보유 하 고 온-프레미스 파일 서비스에 액세스할 수 있도록 유지 하는 것은 전적으로 책임입니다.</span><span class="sxs-lookup"><span data-stu-id="dbb33-128">It's entirely your responsibility to ensure that users and groups have and maintain the right permissions to access file share locations and that the on-premises file services remain accessible.</span></span> <span data-ttu-id="dbb33-129">또한 가능한 한 빨리 이러한 파일 공유에 대 한 요구 사항을 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbb33-129">Also, you should remove your requirements for such file shares as soon as possible.</span></span>

### <a name="to-have-mapped-drives-deployed-in-microsoft-managed-desktop"></a><span data-ttu-id="dbb33-130">매핑된 드라이브를 Microsoft Managed Desktop에 배포 하려면</span><span class="sxs-lookup"><span data-stu-id="dbb33-130">To have mapped drives deployed in Microsoft Managed Desktop</span></span>
 
<span data-ttu-id="dbb33-131">매핑된 드라이브를 회피 하 고 서비스 요청을 제출 하기 전에 요구 사항을 신중히 검토 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbb33-131">Make sure that mapped drives cannot be avoided and you have carefully reviewed the requirements before submitting any service request.</span></span> <span data-ttu-id="dbb33-132">그런 후 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbb33-132">Then follow these steps:</span></span>

1. <span data-ttu-id="dbb33-133">[Microsoft Managed Desktop 포털로](https://aka.ms/mmdportal)이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbb33-133">Navigate to the [Microsoft Managed Desktop portal](https://aka.ms/mmdportal).</span></span>  
2. <span data-ttu-id="dbb33-134">**지원 _GT_ 지원 요청** 섹션을 통해 "매핑된 드라이브 배포" 라는 지원 요청을 제출 하 고 필요한 파일 공유 세부 정보를 모두 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbb33-134">Submit a support request titled “Mapped drives deployment” through the **Support > Support requests** section and provide all the required file share details.</span></span>  
3. <span data-ttu-id="dbb33-135">Microsoft Managed Desktop 작업은 요청이 완료 되 면 지원 요청 업데이트를 사용 하 여 권고를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbb33-135">Microsoft Managed Desktop Operations will advise, by using support request updates, when the request has been completed.</span></span> <span data-ttu-id="dbb33-136">이 구성은 처음에 테스트 배포 그룹의 장치에만 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbb33-136">Initially this configuration will only be deployed to devices in the Test deployment group.</span></span>  
4. <span data-ttu-id="dbb33-137">Microsoft Managed Desktop Operations team을 통해 배포 되는 구성이 예상 대로 작동 하는지 여부를 테스트 하 고 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbb33-137">You must test and confirm whether the configuration deployed by the Microsoft Managed Desktop Operations team works as you expect.</span></span> <span data-ttu-id="dbb33-138">테스트를 완료 한 후 지원 요청을 사용 하 여 Microsoft Managed Desktop 작업을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbb33-138">Use the support request to update Microsoft Managed Desktop Operations once you've completed your testing.</span></span>  
5. <span data-ttu-id="dbb33-139">그러면 Microsoft Managed Desktop Operations 팀이 구성을 다른 배포 그룹에 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbb33-139">Microsoft Managed Desktop Operations team will then deploy the configuration to the other deployment groups.</span></span> 