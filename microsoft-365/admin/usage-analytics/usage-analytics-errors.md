---
title: Microsoft 365 사용 현황 분석 문제 해결
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a73632a1-62c8-4a13-8115-913773b30f93
description: Microsoft 365 사용 현황 분석 템플릿 앱 관련 문제를 해결하는 방법을 알아보십시오.
ms.openlocfilehash: bc7f1f7188a209188f1a67a20bf79477c6e1d4a0
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580741"
---
# <a name="troubleshooting-microsoft-365-usage-analytics"></a><span data-ttu-id="7c1f5-103">Microsoft 365 사용 현황 분석 문제 해결</span><span class="sxs-lookup"><span data-stu-id="7c1f5-103">Troubleshooting Microsoft 365 usage analytics</span></span>

<span data-ttu-id="7c1f5-104">다음 오류 메시지 목록을 살펴보고 Microsoft 365 사용 현황 분석에서 가장 일반적인 문제에 대한 도움말을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f5-104">Explore the following list of error messages to get help with the most common issues with Microsoft 365 usage analytics.</span></span>
  
    
## <a name="we-are-unable-to-process-your-request-you-have-to-first-subscribe-to-this-data-from-the-microsoft-365-admin-center"></a><span data-ttu-id="7c1f5-105">요청을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f5-105">We are unable to process your request.</span></span> <span data-ttu-id="7c1f5-106">먼저 Microsoft 365 관리 센터에서 이 데이터를 구독해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f5-106">You have to first subscribe to this data from the Microsoft 365 admin center</span></span>

 <span data-ttu-id="7c1f5-107">**오류 코드:** 422</span><span class="sxs-lookup"><span data-stu-id="7c1f5-107">**Error Code:** 422</span></span> 
  
 <span data-ttu-id="7c1f5-108">**이 메시지가 표시될 위치:** Power BI에서 Microsoft 365 사용 현황 분석 템플릿 앱에 연결하거나 Microsoft 365 보고 API를 직접 호출할 때.</span><span class="sxs-lookup"><span data-stu-id="7c1f5-108">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="7c1f5-109">**원인:** 앱에 연결하려면 먼저 Microsoft 365 관리 센터에서 데이터를 구독해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f5-109">**Cause:** Before you can connect to the app, you have to subscribe to the data from the Microsoft 365 admin center.</span></span> <span data-ttu-id="7c1f5-110">이 단계를 먼저 수행하지 않은 경우 Microsoft 365 테넌트 ID를 제공한 경우에도 템플릿 앱에 연결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f5-110">If this step isn't done first, you won't be able to connect to the template app, even if you provide your Microsoft 365 tenant ID.</span></span> 
  
 <span data-ttu-id="7c1f5-111">**이 오류를 해결합니다.** 데이터를 구독하려면 관리 센터 보고서 사용 현황으로 이동하여 주 대시보드 페이지에서 \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a> Microsoft 365 사용 현황 분석 타일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f5-111">**To fix this error:** To subscribe to the data, go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="7c1f5-112">시작 **단추를** 선택한 다음 열  수 있는 보고서 창에서 Power BI에 대한 **Microsoft 365** 사용 현황 분석에 사용할 수 있도록 설정 및 저장 설정을 **으로 전환합니다.**</span><span class="sxs-lookup"><span data-stu-id="7c1f5-112">Select the **Get started** button and then in the **Reports** pane that opens, turn the **Make data available to Microsoft 365 usage analytics for Power BI** setting on and **Save**.</span></span>
  
## <a name="we-are-processing-your-data"></a><span data-ttu-id="7c1f5-113">데이터를 처리하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f5-113">We are processing your data</span></span>

 <span data-ttu-id="7c1f5-114">**이 메시지가 표시될 위치:** Microsoft **365** 관리 센터의  사용 현황 대시보드에 있는 Microsoft 365 사용 현황 분석 타일에서</span><span class="sxs-lookup"><span data-stu-id="7c1f5-114">**Where you will see this message:** In the **Microsoft 365 usage analytics** tile on the **Usage** dashboard in the Microsoft 365 admin center.</span></span> 
  
 <span data-ttu-id="7c1f5-115">**원인:** Microsoft [](enable-usage-analytics.md) 365 관리 센터에서 템플릿 앱에서 데이터를 보게 옵트인하면 Microsoft 365 시스템에서 조직의 이전 사용 현황 데이터를 생성하기 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f5-115">**Cause:** When you [opt in to seeing data in the template app](enable-usage-analytics.md) from the Microsoft 365 admin center, the Microsoft 365 system starts generating historical usage data for your organization.</span></span> <span data-ttu-id="7c1f5-116">테넌트의 크기에 따라 이 단계는 2시간에서 48시간까지 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f5-116">Depending on the size of your tenant, this step could take anywhere between 2 hours to 48 hours.</span></span> 
  
 <span data-ttu-id="7c1f5-117">**이 문제를 해결합니다.** 잠시 기다렸다가 메시지가 3일  후에 데이터로 변경되지 않는 경우 [비즈니스용 Microsoft 365 지원에 문의합니다.](../contact-support-for-business-products.md)</span><span class="sxs-lookup"><span data-stu-id="7c1f5-117">**To fix this:** Just be patient, but if the message does not change to **Your data is ready** after 3 days, [contact Microsoft 365 for business support](../contact-support-for-business-products.md).</span></span>
  
## <a name="we-are-unable-to-process-your-request-at-this-time-we-are-still-preparing-the-data-for-your-organization"></a><span data-ttu-id="7c1f5-118">현재 요청을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f5-118">We are unable to process your request at this time.</span></span> <span data-ttu-id="7c1f5-119">아직 조직의 데이터를 준비하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f5-119">We are still preparing the data for your organization</span></span>

 <span data-ttu-id="7c1f5-120">**오류 코드:** 423</span><span class="sxs-lookup"><span data-stu-id="7c1f5-120">**Error Code:** 423</span></span> 
  
 <span data-ttu-id="7c1f5-121">**이 메시지가 표시될 위치:** Power BI에서 Microsoft 365 사용 현황 분석 템플릿 앱에 연결하거나 Microsoft 365 보고 API를 직접 호출할 때.</span><span class="sxs-lookup"><span data-stu-id="7c1f5-121">**Where you will see this message:** In Power BI, when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="7c1f5-122">**원인:** 관리 [센터에서](enable-usage-analytics.md) 템플릿 앱에서 데이터를 보게 옵트인하면 Microsoft 365 시스템에서 조직의 이전 사용 현황 데이터를 생성하기 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f5-122">**Cause:** When you [opt in to seeing data in the template app](enable-usage-analytics.md) from the admin center, the Microsoft 365 system starts generating historical usage data for your organization.</span></span> <span data-ttu-id="7c1f5-123">테넌트의 크기에 따라 이 단계는 2시간에서 48시간까지 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f5-123">Depending on the size of your tenant, this step could take anywhere between two hours to 48 hours.</span></span> 
  
 <span data-ttu-id="7c1f5-124">**이 문제를 해결합니다.** 유의하시기 바랍니다. 그러나 메시지가 시작된 후 3일이라도 데이터가 준비된 것으로 변경되지 않는 경우 [비즈니스용 Microsoft 365 지원에 문의합니다.](../contact-support-for-business-products.md) </span><span class="sxs-lookup"><span data-stu-id="7c1f5-124">**To fix this:** Just be patient, but if the message does not change to **Your data is ready** even 3 days since initiation, [contact Microsoft 365 for business support](../contact-support-for-business-products.md).</span></span>
  
## <a name="the-tenant-id-you-provided-is-not-in-the-correct-format"></a><span data-ttu-id="7c1f5-125">입력하신 테넌트 ID의 형식이 올바르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f5-125">The tenant ID you provided is not in the correct format</span></span>

 <span data-ttu-id="7c1f5-126">**오류 코드:** 4:00</span><span class="sxs-lookup"><span data-stu-id="7c1f5-126">**Error Code:** 400</span></span> 
  
 <span data-ttu-id="7c1f5-127">**이 메시지가 표시될 위치:** Power BI에서 Microsoft 365 사용 현황 분석 템플릿 앱에 연결하거나 Microsoft 365 보고 API를 직접 호출할 때.</span><span class="sxs-lookup"><span data-stu-id="7c1f5-127">**Where you will see this message:** In Power BI, when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="7c1f5-128">**원인:** 테넌트 ID는 guid로, xxxxxxx-xxxx-xxxx-xxxx-xxxx-xx 형식을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f5-128">**Cause:** The tenant ID is a guid and has to be in the format of xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx.</span></span> <span data-ttu-id="7c1f5-129">테넌트 입력란에 다른 문자열을 입력하면 이 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f5-129">If you enter any other string in the tenant input box, you will get this error.</span></span> 
  
 <span data-ttu-id="7c1f5-130">**이 오류를 해결합니다.** 관리 센터 보고서 사용 현황으로 이동하여 기본 대시보드 페이지에서 \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a> Microsoft 365 사용 현황 분석 타일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f5-130">**To fix this error:** Go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="7c1f5-131">테넌트 ID가 타일에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f5-131">The tenant ID is listed on the tile.</span></span> <span data-ttu-id="7c1f5-132">여기에서 복사하여 템플릿 앱에 연결하기 위해 대화 상자에 붙여넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f5-132">You can copy it from here and paste it in the dialog box for connecting to the template app.</span></span> 
  
## <a name="the-tenant-id-you-provided-is-not-recognized-by-our-system"></a><span data-ttu-id="7c1f5-133">입력하신 테넌트 ID가 시스템에서 인식되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f5-133">The tenant ID you provided is not recognized by our system</span></span>

 <span data-ttu-id="7c1f5-134">**오류 코드:** 404</span><span class="sxs-lookup"><span data-stu-id="7c1f5-134">**Error Code:** 404</span></span> 
  
 <span data-ttu-id="7c1f5-135">**이 메시지가 표시될 위치:** Power BI에서 Microsoft 365 사용 현황 분석 템플릿 앱에 연결하거나 Microsoft 365 보고 API를 직접 호출할 때.</span><span class="sxs-lookup"><span data-stu-id="7c1f5-135">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="7c1f5-136">**원인:** 제공한 테넌트 ID가 유효하지 않은 경우 또는 존재하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f5-136">**Cause:** The tenant ID you provided is not valid or does not exist.</span></span> 
  
 <span data-ttu-id="7c1f5-137">**이 오류를 해결합니다.** 관리 센터 보고서 사용 현황으로 이동하여 기본 대시보드 페이지에서 \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a> Microsoft 365 사용 현황 분석 타일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f5-137">**To fix this error:** Go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="7c1f5-138">테넌트 ID가 타일에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f5-138">The tenant ID is listed on the tile.</span></span> <span data-ttu-id="7c1f5-139">여기에서 복사하여 템플릿 앱에 연결하기 위해 대화 상자에 붙여넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f5-139">You can copy it from here and paste it in the dialog box for connecting to the template app.</span></span> 
  
## <a name="please-re-enter-your-credentials-to-sign-in-to-power-bi-again"></a><span data-ttu-id="7c1f5-140">Power BI에 다시 로그인하려면 자격 증명을 다시 입력하세요.</span><span class="sxs-lookup"><span data-stu-id="7c1f5-140">Please re-enter your credentials to sign in to Power BI again</span></span>

<span data-ttu-id="7c1f5-141">오류 코드: 302</span><span class="sxs-lookup"><span data-stu-id="7c1f5-141">Error Code: 302</span></span>
  
 <span data-ttu-id="7c1f5-142">**이 메시지가 표시될 위치:** Power BI에서 Microsoft 365 사용 현황 분석 템플릿 앱에 연결하거나 Microsoft 365 보고 API를 직접 호출할 때.</span><span class="sxs-lookup"><span data-stu-id="7c1f5-142">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="7c1f5-143">**원인:** 인증 코드 확인에 실패하여 자격 증명을 다시 입력해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f5-143">**Cause:** The authorization code failed and may require you to enter your credentials again.</span></span> 
  
 <span data-ttu-id="7c1f5-144">**오류 수정 방법:** Power BI에서 로그아웃한 다음 다시 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f5-144">**To fix this error:** Sign out of Power BI, and then sign in again.</span></span> 
  
## <a name="you-do-not-have-the-right-authorization-to-access-to-this-data-to-be-able-to-gain-access-to-the-data-from-this-service-you-need-to-be-either-a-global-admin-or-any-one-of-the-product-admins"></a><span data-ttu-id="7c1f5-145">이 데이터에 액세스할 수 있는 권한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f5-145">You do not have the right authorization to access to this data.</span></span> <span data-ttu-id="7c1f5-146">이 서비스에서 데이터에 대한 액세스 권한을 얻으려면 전역 관리자 또는 제품 관리자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f5-146">To be able to gain access to the data from this service you need to be either a global admin or any one of the product admins</span></span>

 <span data-ttu-id="7c1f5-147">**오류 코드:** 403</span><span class="sxs-lookup"><span data-stu-id="7c1f5-147">**Error Code:** 403</span></span> 
  
 <span data-ttu-id="7c1f5-148">**이 메시지가 표시될 위치:** Power BI에서 Microsoft 365 사용 현황 분석 템플릿 앱에 연결하거나 Microsoft 365 보고 API를 직접 호출할 때.</span><span class="sxs-lookup"><span data-stu-id="7c1f5-148">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="7c1f5-149">**원인:** 템플릿 앱에 연결을 시도한 사용자에게 이 데이터에 액세스하기 위한 올바른 수준의 권한 부여가 없는 경우 권한 부여 코드가 실패했습니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f5-149">**Cause:** The authorization code failed because the user who tried connecting to the template app does not have the right level of authorization to access this data.</span></span> 
  
 <span data-ttu-id="7c1f5-150">**이 오류를 해결합니다.** 템플릿 앱에 연결할 전역 관리자,  **Exchange** 관리자, 비즈니스용 **Skype** 관리자, **SharePoint 관리자,** 전역 읽기 프로그램 또는 보고서 읽기 프로그램인 사용자의 자격 증명을 제공합니다.  </span><span class="sxs-lookup"><span data-stu-id="7c1f5-150">**To fix this error:** Provide the credentials of a user who is either a **Global admin**, **Exchange admin**, **Skype for Business admin**, **SharePoint admin**, **Global reader** or **Report reader** to connect to the template app.</span></span> <span data-ttu-id="7c1f5-151">자세한 [내용은 관리자 역할](../add-users/about-admin-roles.md) 정보를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7c1f5-151">See [About admin roles](../add-users/about-admin-roles.md) for more information.</span></span> 
  
## <a name="refresh-failed"></a><span data-ttu-id="7c1f5-152">새로 고치지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f5-152">Refresh failed</span></span>

 <span data-ttu-id="7c1f5-153">**이 메시지가 표시되는 위치:** Power BI 전자 메일 또는 새로 고침 기록의 실패 상태.</span><span class="sxs-lookup"><span data-stu-id="7c1f5-153">**Where you will see this message:** Email from Power BI or failed status in the refresh history.</span></span> 
  
 <span data-ttu-id="7c1f5-154">**원인:** 템플릿 앱에 연결된 사용자의 자격 증명이 다시 설정되고 템플릿 앱의 연결 설정에서 업데이트되지 않은 경우 사용자가 새로 고침 실패 오류를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f5-154">**Cause:** Sometimes the credentials of the user who connected to the template app are reset, and not updated in the connection settings of the template app causing the user to see refresh failure errors.</span></span> 
  
 <span data-ttu-id="7c1f5-155">**이 오류를 해결합니다.** Power BI에서 Microsoft 365 사용 현황 분석 템플릿 앱에 해당하는 데이터 집합을 찾고 새로 고침 예약을 선택하고 관리자 자격 증명을 제공합니다. </span><span class="sxs-lookup"><span data-stu-id="7c1f5-155">**To fix this error:** In Power BI, find the dataset corresponding to the Microsoft 365 Usage Analytics template app, select **schedule refresh** and provide your admin credentials.</span></span> 
  
<span data-ttu-id="7c1f5-156">그래도 문제가 해결되지 않는 경우 캐시를 지우고 템플릿 앱을 다시 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f5-156">If that doesn't work, clear the cache, and re-create the template app.</span></span>
  
  
