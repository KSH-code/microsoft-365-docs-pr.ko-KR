---
title: 미성년자가을 사용 하 여 스토어에서 추가 기능 가져오기
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: 미성년자가의 개인 데이터를 제어 하는 GDPR (일반 데이터 보호 규정) 규정에 대해 알아봅니다.
ms.openlocfilehash: a738e22a0ac0b995c8e44fcf4cc5a2eb47375be5
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/29/2020
ms.locfileid: "47306554"
---
# <a name="minors-and-acquiring-add-ins-from-the-store"></a><span data-ttu-id="1afdb-103">미성년자가을 사용 하 여 스토어에서 추가 기능 가져오기</span><span class="sxs-lookup"><span data-stu-id="1afdb-103">Minors and acquiring add-ins from the Store</span></span>

<span data-ttu-id="1afdb-104">GDPR (일반 데이터 보호 규정)은 실제 5 월 25 일 2018이 되는 유럽 연합 규정입니다.</span><span class="sxs-lookup"><span data-stu-id="1afdb-104">The General Data Protection Regulation (GDPR) is a European Union regulation that becomes effective May 25, 2018.</span></span> <span data-ttu-id="1afdb-105">사용자에 게 해당 데이터에 대 한 권한을 부여 하 고 보호 합니다.</span><span class="sxs-lookup"><span data-stu-id="1afdb-105">It gives users rights to and protection of their data.</span></span> <span data-ttu-id="1afdb-106">GDPR의 특징 중 하나는 미성년자가가 자신의 부모 또는 보호를 승인 하지 않은 파티에 개인 데이터를 보낼 수 없다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1afdb-106">One of the aspects of the GDPR is that minors cannot have their personal data sent to parties that their parent or guardian hasn't approved.</span></span> <span data-ttu-id="1afdb-107">약간만 정의 되는 특정 기간은 개인이 있는 지역에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="1afdb-107">The specific age defined as a minor depends on the region where the individual is located.</span></span>
  
<span data-ttu-id="1afdb-108">자녀 보호에 대 한 법적 규정이 있는 지역에는 미국, 대한민국, 영국 및 유럽 연합 등이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1afdb-108">Regions that have statutory regulations about parental consent include the United States, South Korea, the United Kingdom, and the European Union.</span></span> <span data-ttu-id="1afdb-109">이러한 지역의 경우 저장소에서 새 Office 추가 기능을 가져오는 작업과 이전에 획득 한 추가 기능을 실행 하는 것을 Azure Active Directory를 통해 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="1afdb-109">For those regions, a minor will be blocked (via Azure Active Directory) from getting any new Office add-ins from the Store and running add-ins that were previously acquired.</span></span> <span data-ttu-id="1afdb-110">법적 규정이 없는 국가의 경우에는 다운로드 제한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1afdb-110">For countries without statutory regulations, there will be no download restrictions.</span></span>
  
<span data-ttu-id="1afdb-111">사용자는 Azure Active Directory에 지정 된 데이터를 기반으로 하는 부 버전으로 확인 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1afdb-111">A user is determined to be a minor based on data specified in Azure Active Directory.</span></span> <span data-ttu-id="1afdb-112">조직 관리자는 해당 사용자의 법적 연령 그룹 및 보호자 보호를 선언 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1afdb-112">The organization admin is responsible for declaring the legal age group and the parental consent for that user.</span></span>
  
<span data-ttu-id="1afdb-113">특정 추가 기능을 사용 하 여 상위/보호자를 consents 하는 경우 조직 관리자는 중앙 집중식 배포를 사용 하 여 사용자가 동의 하는 모든 미성년자가에 해당 추가 기능을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1afdb-113">If the parent/guardian consents to a minor using a specific add-In, then the organization admin can use centralized deployment to deploy that add-In to all minors who have consent.</span></span>
  
<span data-ttu-id="1afdb-114">미성년자가에 대 한 GDPR을 준수 하려면 학교/조직에 Office의 다음 빌드 중 하나가 배포 되었는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1afdb-114">To be GDPR compliant for minors you need to ensure that one of following builds of Office is deployed in your school/organization.</span></span>
 
 <span data-ttu-id="1afdb-115">**Word, Excel, PowerPoint 및 Project에 대해**다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1afdb-115">**For Word, Excel, PowerPoint, and Project**:</span></span> 

|<span data-ttu-id="1afdb-116">**플랫폼**</span><span class="sxs-lookup"><span data-stu-id="1afdb-116">**Platform**</span></span> <br/> |<span data-ttu-id="1afdb-117">**빌드 번호**</span><span class="sxs-lookup"><span data-stu-id="1afdb-117">**Build number**</span></span> <br/> |
|:-----|:-----|
|<span data-ttu-id="1afdb-118">Microsoft 365 Apps for enterprise (현재 채널)</span><span class="sxs-lookup"><span data-stu-id="1afdb-118">Microsoft 365 Apps for enterprise (Current Channel)</span></span>  <br/> |<span data-ttu-id="1afdb-119">9001.2138</span><span class="sxs-lookup"><span data-stu-id="1afdb-119">9001.2138</span></span>   <br/> |
|<span data-ttu-id="1afdb-120">Microsoft 365 Apps for enterprise (반기 엔터프라이즈 채널)</span><span class="sxs-lookup"><span data-stu-id="1afdb-120">Microsoft 365 Apps for enterprise (Semi-Annual Enterprise Channel)</span></span>  <br/> |<span data-ttu-id="1afdb-121">8431.2159</span><span class="sxs-lookup"><span data-stu-id="1afdb-121">8431.2159</span></span>  <br/> |
|<span data-ttu-id="1afdb-122">Windows 용 Office 2016</span><span class="sxs-lookup"><span data-stu-id="1afdb-122">Office 2016 for Windows</span></span>  <br/> |<span data-ttu-id="1afdb-123">16.0.4672.1000</span><span class="sxs-lookup"><span data-stu-id="1afdb-123">16.0.4672.1000</span></span>  <br/> |
|<span data-ttu-id="1afdb-124">Windows 용 Office 2013</span><span class="sxs-lookup"><span data-stu-id="1afdb-124">Office 2013 for Windows</span></span>  <br/> |<span data-ttu-id="1afdb-125">15.0.5023.1000</span><span class="sxs-lookup"><span data-stu-id="1afdb-125">15.0.5023.1000</span></span>  <br/> |
|<span data-ttu-id="1afdb-126">Office 2016 for Mac</span><span class="sxs-lookup"><span data-stu-id="1afdb-126">Office 2016 for Mac</span></span>  <br/> |<span data-ttu-id="1afdb-127">16.11.18020200</span><span class="sxs-lookup"><span data-stu-id="1afdb-127">16.11.18020200</span></span>  <br/> |
|<span data-ttu-id="1afdb-128">웹에 대 한 Office</span><span class="sxs-lookup"><span data-stu-id="1afdb-128">Office for the web</span></span>  <br/> |<span data-ttu-id="1afdb-129">해당 없음</span><span class="sxs-lookup"><span data-stu-id="1afdb-129">N/A</span></span>  <br/> |
   
 <span data-ttu-id="1afdb-130">**Outlook의 경우**:</span><span class="sxs-lookup"><span data-stu-id="1afdb-130">**For Outlook**:</span></span> 
  
|<span data-ttu-id="1afdb-131">**플랫폼**</span><span class="sxs-lookup"><span data-stu-id="1afdb-131">**Platform**</span></span> <br/> |<span data-ttu-id="1afdb-132">**빌드 번호**</span><span class="sxs-lookup"><span data-stu-id="1afdb-132">**Build number**</span></span> <br/> |
|:-----|:-----|
|<span data-ttu-id="1afdb-133">Windows 용 Outlook 2016 (MSI)</span><span class="sxs-lookup"><span data-stu-id="1afdb-133">Outlook 2016 for Windows (MSI)</span></span>  <br/> |<span data-ttu-id="1afdb-134">TBD 만들기</span><span class="sxs-lookup"><span data-stu-id="1afdb-134">Build No TBD</span></span>  <br/> |
|<span data-ttu-id="1afdb-135">C2R (Windows 용 Outlook 2016)</span><span class="sxs-lookup"><span data-stu-id="1afdb-135">Outlook 2016 for Windows (C2R)</span></span>  <br/> |<span data-ttu-id="1afdb-136">16.0.9323.1000</span><span class="sxs-lookup"><span data-stu-id="1afdb-136">16.0.9323.1000</span></span>  <br/> |
|<span data-ttu-id="1afdb-137">Office 2016 for Mac</span><span class="sxs-lookup"><span data-stu-id="1afdb-137">Office 2016 for Mac</span></span>  <br/> |<span data-ttu-id="1afdb-138">16.0.9318.1000</span><span class="sxs-lookup"><span data-stu-id="1afdb-138">16.0.9318.1000</span></span>  <br/> |
|<span data-ttu-id="1afdb-139">IOS 용 Outlook 모바일</span><span class="sxs-lookup"><span data-stu-id="1afdb-139">Outlook mobile for iOS</span></span>  <br/> |<span data-ttu-id="1afdb-140">2.75.0</span><span class="sxs-lookup"><span data-stu-id="1afdb-140">2.75.0</span></span>  <br/> |
|<span data-ttu-id="1afdb-141">Android 용 Outlook 모바일</span><span class="sxs-lookup"><span data-stu-id="1afdb-141">Outlook mobile for Android</span></span>  <br/> |<span data-ttu-id="1afdb-142">2.2.145</span><span class="sxs-lookup"><span data-stu-id="1afdb-142">2.2.145</span></span>  <br/> |
|<span data-ttu-id="1afdb-143">Outlook.com</span><span class="sxs-lookup"><span data-stu-id="1afdb-143">Outlook.com</span></span>  <br/> |<span data-ttu-id="1afdb-144">해당 없음</span><span class="sxs-lookup"><span data-stu-id="1afdb-144">N/A</span></span>  <br/> |

 <span data-ttu-id="1afdb-145">**Office 2013 요구 사항**</span><span class="sxs-lookup"><span data-stu-id="1afdb-145">**Office 2013 requirements**</span></span>
  
<span data-ttu-id="1afdb-146">Windows 용 Word, Excel 및 PowerPoint 2013은 ADAL (Active Directory 인증 라이브러리)을 사용 하는 경우 동일한 미성년자가 검사를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="1afdb-146">Word, Excel, and PowerPoint 2013 for Windows will support the same minors checks if Active Directory Authentication Library (ADAL) is enabled.</span></span> <span data-ttu-id="1afdb-147">다음에 설명 된 대로 준수에 대 한 두 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1afdb-147">There are two options for compliance, as explained next.</span></span>
  
- <span data-ttu-id="1afdb-148">**ADAL을 사용 하도록 설정**합니다.</span><span class="sxs-lookup"><span data-stu-id="1afdb-148">**Enable ADAL**.</span></span> <span data-ttu-id="1afdb-149">이 문서에서는 Office [365](https://docs.microsoft.com/microsoft-365/enterprise/modern-auth-for-office-2013-and-2016)2013에 대해 ADAL을 사용 하도록 설정 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="1afdb-149">This article explains how to enable ADAL for Office 2013: [Using Microsoft 365 modern authentication with Office clients](https://docs.microsoft.com/microsoft-365/enterprise/modern-auth-for-office-2013-and-2016).</span></span><br/><span data-ttu-id="1afdb-150">또한 [Windows 장치에서 Office 2013에 대 한 최신 인증 사용](../security-and-compliance/enable-modern-authentication.md)에 설명 된 대로 ADAL을 사용 하도록 레지스트리 키를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1afdb-150">You also need to set the registry keys to enable ADAL as explained in [Enable Modern Authentication for Office 2013 on Windows devices](../security-and-compliance/enable-modern-authentication.md).</span></span><br/><span data-ttu-id="1afdb-151">또한 Office 2013에 대 한 다음 4 월 업데이트를 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1afdb-151">Additionally, you need to install the following April updates for Office 2013:</span></span>
    
  - [<span data-ttu-id="1afdb-152">Office 2013의 보안 업데이트에 대 한 설명: 2018 년 4 월 10 일</span><span class="sxs-lookup"><span data-stu-id="1afdb-152">Description of the security update for Office 2013: April 10, 2018</span></span>](https://support.microsoft.com/help/4018330/description-of-the-security-update-for-office-2013-april-10-2018)
    
  - [<span data-ttu-id="1afdb-153">4 월 3 일, 2018, Office 2013 업데이트 (KB4018333)</span><span class="sxs-lookup"><span data-stu-id="1afdb-153">April 3, 2018, update for Office 2013 (KB4018333)</span></span>](https://support.microsoft.com/help/4018333/april-3-2018-update-for-office-2013-kb4018333)
    
- <span data-ttu-id="1afdb-154">**ADAL을 사용 하지 않도록 설정**합니다.</span><span class="sxs-lookup"><span data-stu-id="1afdb-154">**Don't enable ADAL**.</span></span> <span data-ttu-id="1afdb-155">Office 2013에서 ADAL을 사용 하도록 설정할 수 없는 경우 그룹 정책을 사용 하 여 Office 클라이언트에 대 한 저장소를 해제 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1afdb-155">If you're unable to enable ADAL in Office 2013, then our recommendation is to use Group Policy to turn off the Store for the Office clients.</span></span> <span data-ttu-id="1afdb-156">Office 용 앱 설정을 해제 하는 방법에 대 한 정보는 [여기](https://technet.microsoft.com/library/cc178992.aspx)에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1afdb-156">Information on how to turn off the app for Office settings is located [here](https://technet.microsoft.com/library/cc178992.aspx).</span></span>

## <a name="related-articles"></a><span data-ttu-id="1afdb-157">관련 문서</span><span class="sxs-lookup"><span data-stu-id="1afdb-157">Related articles</span></span>

[<span data-ttu-id="1afdb-158">관리 센터에서 추가 기능 배포</span><span class="sxs-lookup"><span data-stu-id="1afdb-158">Deploy add-ins in the admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)

[<span data-ttu-id="1afdb-159">관리 센터에서 추가 기능 관리</span><span class="sxs-lookup"><span data-stu-id="1afdb-159">Manage add-ins in the admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center)
    
