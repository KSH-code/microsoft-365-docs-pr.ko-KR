---
title: 미성년자 및 스토어에서 추가 기능 다운로드
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
description: 미성년자 개인 데이터를 규제하는 GDPR(일반 데이터 보호 규정) 규정에 대해 자세히 알아보고
ms.openlocfilehash: a738e22a0ac0b995c8e44fcf4cc5a2eb47375be5
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/29/2020
ms.locfileid: "47306554"
---
# <a name="minors-and-acquiring-add-ins-from-the-store"></a><span data-ttu-id="c5270-103">미성년자 및 스토어에서 추가 기능 다운로드</span><span class="sxs-lookup"><span data-stu-id="c5270-103">Minors and acquiring add-ins from the Store</span></span>

<span data-ttu-id="c5270-104">GDPR(일반 데이터 보호 규정)은 2018년 5월 25일 시행되는 유럽 연합 규정입니다.</span><span class="sxs-lookup"><span data-stu-id="c5270-104">The General Data Protection Regulation (GDPR) is a European Union regulation that becomes effective May 25, 2018.</span></span> <span data-ttu-id="c5270-105">사용자에게 데이터에 대한 권한 및 보호 권한을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c5270-105">It gives users rights to and protection of their data.</span></span> <span data-ttu-id="c5270-106">GDPR의 측면 중 하나는 미성년자가 부모 또는 보호자가 승인하지 않은 당사자에게 개인 데이터를 전송할 수 없다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="c5270-106">One of the aspects of the GDPR is that minors cannot have their personal data sent to parties that their parent or guardian hasn't approved.</span></span> <span data-ttu-id="c5270-107">부로 정의된 특정 연령은 개인이 있는 지역에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5270-107">The specific age defined as a minor depends on the region where the individual is located.</span></span>
  
<span data-ttu-id="c5270-108">부모 동의에 대한 법률 규정이 있는 지역은 미국, 대한민국, 영국 및 유럽 연합입니다.</span><span class="sxs-lookup"><span data-stu-id="c5270-108">Regions that have statutory regulations about parental consent include the United States, South Korea, the United Kingdom, and the European Union.</span></span> <span data-ttu-id="c5270-109">이러한 지역의 경우 미성년자는(Azure Active Directory를 통해) 스토어에서 새 Office 추가 기능을 다운로드하고 이전에 취득한 추가 기능을 실행하지 못하게 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5270-109">For those regions, a minor will be blocked (via Azure Active Directory) from getting any new Office add-ins from the Store and running add-ins that were previously acquired.</span></span> <span data-ttu-id="c5270-110">법률 규정이 없는 국가의 경우 다운로드 제한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c5270-110">For countries without statutory regulations, there will be no download restrictions.</span></span>
  
<span data-ttu-id="c5270-111">사용자는 Azure Active Directory에 지정된 데이터에 따라 부 사용자로 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5270-111">A user is determined to be a minor based on data specified in Azure Active Directory.</span></span> <span data-ttu-id="c5270-112">조직 관리자는 법적 연령 그룹 및 해당 사용자의 부모 동의를 선언해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5270-112">The organization admin is responsible for declaring the legal age group and the parental consent for that user.</span></span>
  
<span data-ttu-id="c5270-113">부모/보호자가 특정 추가 기능을 사용하는 미성년자에 동의하는 경우 조직 관리자는 중앙 집중식 배포를 사용하여 동의한 모든 미성년자에 해당 추가 기능을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5270-113">If the parent/guardian consents to a minor using a specific add-In, then the organization admin can use centralized deployment to deploy that add-In to all minors who have consent.</span></span>
  
<span data-ttu-id="c5270-114">미성년자에 대한 GDPR을 준수하려면 다음 Office 빌드 중 하나를 학교/조직에 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5270-114">To be GDPR compliant for minors you need to ensure that one of following builds of Office is deployed in your school/organization.</span></span>
 
 <span data-ttu-id="c5270-115">**Word, Excel, PowerPoint 및 Project의 경우:**</span><span class="sxs-lookup"><span data-stu-id="c5270-115">**For Word, Excel, PowerPoint, and Project**:</span></span> 

|<span data-ttu-id="c5270-116">**플랫폼**</span><span class="sxs-lookup"><span data-stu-id="c5270-116">**Platform**</span></span> <br/> |<span data-ttu-id="c5270-117">**빌드 번호**</span><span class="sxs-lookup"><span data-stu-id="c5270-117">**Build number**</span></span> <br/> |
|:-----|:-----|
|<span data-ttu-id="c5270-118">엔터프라이즈용 Microsoft 365 앱(현재 채널)</span><span class="sxs-lookup"><span data-stu-id="c5270-118">Microsoft 365 Apps for enterprise (Current Channel)</span></span>  <br/> |<span data-ttu-id="c5270-119">9001.2138</span><span class="sxs-lookup"><span data-stu-id="c5270-119">9001.2138</span></span>   <br/> |
|<span data-ttu-id="c5270-120">엔터프라이즈용 Microsoft 365 앱(반기 엔터프라이즈 채널)</span><span class="sxs-lookup"><span data-stu-id="c5270-120">Microsoft 365 Apps for enterprise (Semi-Annual Enterprise Channel)</span></span>  <br/> |<span data-ttu-id="c5270-121">8431.2159</span><span class="sxs-lookup"><span data-stu-id="c5270-121">8431.2159</span></span>  <br/> |
|<span data-ttu-id="c5270-122">Windows용 Office 2016</span><span class="sxs-lookup"><span data-stu-id="c5270-122">Office 2016 for Windows</span></span>  <br/> |<span data-ttu-id="c5270-123">16.0.4672.1000</span><span class="sxs-lookup"><span data-stu-id="c5270-123">16.0.4672.1000</span></span>  <br/> |
|<span data-ttu-id="c5270-124">Windows용 Office 2013</span><span class="sxs-lookup"><span data-stu-id="c5270-124">Office 2013 for Windows</span></span>  <br/> |<span data-ttu-id="c5270-125">15.0.5023.1000</span><span class="sxs-lookup"><span data-stu-id="c5270-125">15.0.5023.1000</span></span>  <br/> |
|<span data-ttu-id="c5270-126">Office 2016 for Mac</span><span class="sxs-lookup"><span data-stu-id="c5270-126">Office 2016 for Mac</span></span>  <br/> |<span data-ttu-id="c5270-127">16.11.18020200</span><span class="sxs-lookup"><span data-stu-id="c5270-127">16.11.18020200</span></span>  <br/> |
|<span data-ttu-id="c5270-128">웹용 Office</span><span class="sxs-lookup"><span data-stu-id="c5270-128">Office for the web</span></span>  <br/> |<span data-ttu-id="c5270-129">해당 없음</span><span class="sxs-lookup"><span data-stu-id="c5270-129">N/A</span></span>  <br/> |
   
 <span data-ttu-id="c5270-130">**Outlook의 경우:**</span><span class="sxs-lookup"><span data-stu-id="c5270-130">**For Outlook**:</span></span> 
  
|<span data-ttu-id="c5270-131">**플랫폼**</span><span class="sxs-lookup"><span data-stu-id="c5270-131">**Platform**</span></span> <br/> |<span data-ttu-id="c5270-132">**빌드 번호**</span><span class="sxs-lookup"><span data-stu-id="c5270-132">**Build number**</span></span> <br/> |
|:-----|:-----|
|<span data-ttu-id="c5270-133">Windows용 Outlook 2016(MSI)</span><span class="sxs-lookup"><span data-stu-id="c5270-133">Outlook 2016 for Windows (MSI)</span></span>  <br/> |<span data-ttu-id="c5270-134">TBD 빌드 안</span><span class="sxs-lookup"><span data-stu-id="c5270-134">Build No TBD</span></span>  <br/> |
|<span data-ttu-id="c5270-135">Windows용 Outlook 2016(C2R)</span><span class="sxs-lookup"><span data-stu-id="c5270-135">Outlook 2016 for Windows (C2R)</span></span>  <br/> |<span data-ttu-id="c5270-136">16.0.9323.1000</span><span class="sxs-lookup"><span data-stu-id="c5270-136">16.0.9323.1000</span></span>  <br/> |
|<span data-ttu-id="c5270-137">Office 2016 for Mac</span><span class="sxs-lookup"><span data-stu-id="c5270-137">Office 2016 for Mac</span></span>  <br/> |<span data-ttu-id="c5270-138">16.0.9318.1000</span><span class="sxs-lookup"><span data-stu-id="c5270-138">16.0.9318.1000</span></span>  <br/> |
|<span data-ttu-id="c5270-139">iOS용 Outlook 모바일</span><span class="sxs-lookup"><span data-stu-id="c5270-139">Outlook mobile for iOS</span></span>  <br/> |<span data-ttu-id="c5270-140">2.75.0</span><span class="sxs-lookup"><span data-stu-id="c5270-140">2.75.0</span></span>  <br/> |
|<span data-ttu-id="c5270-141">Android용 Outlook 모바일</span><span class="sxs-lookup"><span data-stu-id="c5270-141">Outlook mobile for Android</span></span>  <br/> |<span data-ttu-id="c5270-142">2.2.145</span><span class="sxs-lookup"><span data-stu-id="c5270-142">2.2.145</span></span>  <br/> |
|<span data-ttu-id="c5270-143">outlook.com</span><span class="sxs-lookup"><span data-stu-id="c5270-143">Outlook.com</span></span>  <br/> |<span data-ttu-id="c5270-144">해당 없음</span><span class="sxs-lookup"><span data-stu-id="c5270-144">N/A</span></span>  <br/> |

 <span data-ttu-id="c5270-145">**Office 2013 요구 사항**</span><span class="sxs-lookup"><span data-stu-id="c5270-145">**Office 2013 requirements**</span></span>
  
<span data-ttu-id="c5270-146">Windows용 Word, Excel 및 PowerPoint 2013에서는 ADAL(Active Directory 인증 라이브러리)이 활성화되어 있는 경우 동일한 부 버전 검사를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="c5270-146">Word, Excel, and PowerPoint 2013 for Windows will support the same minors checks if Active Directory Authentication Library (ADAL) is enabled.</span></span> <span data-ttu-id="c5270-147">다음에 설명된 규정 준수에 대한 두 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5270-147">There are two options for compliance, as explained next.</span></span>
  
- <span data-ttu-id="c5270-148">**ADAL을 사용하도록 설정.**</span><span class="sxs-lookup"><span data-stu-id="c5270-148">**Enable ADAL**.</span></span> <span data-ttu-id="c5270-149">이 문서에서는 Office 2013용 ADAL을 사용하도록 설정하는 방법: Office 클라이언트에서 Microsoft 365 최신 인증 [사용에 대해 설명합니다.](https://docs.microsoft.com/microsoft-365/enterprise/modern-auth-for-office-2013-and-2016)</span><span class="sxs-lookup"><span data-stu-id="c5270-149">This article explains how to enable ADAL for Office 2013: [Using Microsoft 365 modern authentication with Office clients](https://docs.microsoft.com/microsoft-365/enterprise/modern-auth-for-office-2013-and-2016).</span></span><br/><span data-ttu-id="c5270-150">Windows 장치에서 [Office 2013에](../security-and-compliance/enable-modern-authentication.md)대한 최신 인증 사용에 설명된 따라 ADAL을 사용하도록 레지스트리 키를 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5270-150">You also need to set the registry keys to enable ADAL as explained in [Enable Modern Authentication for Office 2013 on Windows devices](../security-and-compliance/enable-modern-authentication.md).</span></span><br/><span data-ttu-id="c5270-151">또한 Office 2013에 대한 다음 4월 업데이트를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5270-151">Additionally, you need to install the following April updates for Office 2013:</span></span>
    
  - [<span data-ttu-id="c5270-152">Office 2013의 보안 업데이트에 대한 설명: 2018년 4월 10일</span><span class="sxs-lookup"><span data-stu-id="c5270-152">Description of the security update for Office 2013: April 10, 2018</span></span>](https://support.microsoft.com/help/4018330/description-of-the-security-update-for-office-2013-april-10-2018)
    
  - [<span data-ttu-id="c5270-153">2018년 4월 3일, Office 2013에 대한 업데이트(KB4018333)</span><span class="sxs-lookup"><span data-stu-id="c5270-153">April 3, 2018, update for Office 2013 (KB4018333)</span></span>](https://support.microsoft.com/help/4018333/april-3-2018-update-for-office-2013-kb4018333)
    
- <span data-ttu-id="c5270-154">**ADAL을 사용하도록 설정하지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="c5270-154">**Don't enable ADAL**.</span></span> <span data-ttu-id="c5270-155">Office 2013에서 ADAL을 사용하도록 설정할 수 없는 경우 그룹 정책을 사용하여 Office 클라이언트에 대한 스토어를 해제하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c5270-155">If you're unable to enable ADAL in Office 2013, then our recommendation is to use Group Policy to turn off the Store for the Office clients.</span></span> <span data-ttu-id="c5270-156">Office 설정용 앱을 끄는 방법에 대한 정보는 여기에 [있습니다.](https://technet.microsoft.com/library/cc178992.aspx)</span><span class="sxs-lookup"><span data-stu-id="c5270-156">Information on how to turn off the app for Office settings is located [here](https://technet.microsoft.com/library/cc178992.aspx).</span></span>

## <a name="related-articles"></a><span data-ttu-id="c5270-157">관련 문서</span><span class="sxs-lookup"><span data-stu-id="c5270-157">Related articles</span></span>

[<span data-ttu-id="c5270-158">관리 센터에서 추가 기능 배포</span><span class="sxs-lookup"><span data-stu-id="c5270-158">Deploy add-ins in the admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)

[<span data-ttu-id="c5270-159">관리 센터에서 추가 기능 관리</span><span class="sxs-lookup"><span data-stu-id="c5270-159">Manage add-ins in the admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center)
    
