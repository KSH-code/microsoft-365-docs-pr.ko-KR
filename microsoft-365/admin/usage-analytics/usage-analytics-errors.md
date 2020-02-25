---
title: Microsoft 365 사용 현황 분석 문제 해결
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a73632a1-62c8-4a13-8115-913773b30f93
description: Microsoft 365 Usage Analytics 서식 파일 앱의 문제를 해결 하는 방법을 알아봅니다.
ms.openlocfilehash: a9da79a6d7760f7876de7a6321554545d411f6be
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42248183"
---
# <a name="troubleshooting-microsoft-365-usage-analytics"></a><span data-ttu-id="9db0f-103">Microsoft 365 사용 현황 분석 문제 해결</span><span class="sxs-lookup"><span data-stu-id="9db0f-103">Troubleshooting Microsoft 365 usage analytics</span></span>

<span data-ttu-id="9db0f-104">다음 오류 메시지 목록을 살펴보고 Microsoft 365 사용 현황 분석에서 가장 일반적인 문제에 대 한 도움말을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="9db0f-104">Explore the following list of error messages to get help with the most common issues with Microsoft 365 usage analytics.</span></span>
  
    
## <a name="we-are-unable-to-process-your-request-you-have-to-first-subscribe-to-this-data-from-the-microsoft-365-admin-center"></a><span data-ttu-id="9db0f-105">요청을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9db0f-105">We are unable to process your request.</span></span> <span data-ttu-id="9db0f-106">먼저 Microsoft 365 관리 센터에서이 데이터를 구독 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9db0f-106">You have to first subscribe to this data from the Microsoft 365 admin center</span></span>

 <span data-ttu-id="9db0f-107">**오류 코드:** 422</span><span class="sxs-lookup"><span data-stu-id="9db0f-107">**Error Code :** 422</span></span> 
  
 <span data-ttu-id="9db0f-108">**이 메시지가 표시 되는 위치:** Microsoft 365 사용 현황 분석 서식 파일 앱에 연결 하거나 Microsoft 365 보고 Api를 직접 호출 하는 경우 Power BI에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9db0f-108">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="9db0f-109">**원인:** 앱에 연결 하려면 먼저 Microsoft 365 관리 센터에서 데이터를 구독 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9db0f-109">**Cause:** Before you can connect to the app you have to subscribe to the data from the Microsoft 365 admin center.</span></span> <span data-ttu-id="9db0f-110">이 단계를 먼저 수행 하지 않으면 Microsoft 365 테 넌 트 id를 제공한 경우에도 서식 파일 앱에 연결할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9db0f-110">If this step isn't done first, you won't be able to connect to the template app, even if you provide your Microsoft 365 tenant id.</span></span> 
  
 <span data-ttu-id="9db0f-111">**이 오류를 해결 하려면** 데이터를 \> 구독 하려면 관리 센터의 <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">사용 현황</a> **보고서** \> 로 이동 하 여 기본 대시보드 페이지에서 Microsoft 365 Usage analytics 타일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="9db0f-111">**To fix this error:** To subscribe to the data, go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="9db0f-112">**시작** 단추를 선택 하 고 열리는 **보고서** 창에서 **Power BI 설정에 대 한 Microsoft 365 사용 현황 분석을 사용 하 여 데이터를 사용할 수 있도록** 설정 하 고 **저장**합니다.</span><span class="sxs-lookup"><span data-stu-id="9db0f-112">Select the **Get started** button and then in the **Reports** pane that opens, turn the **Make data available to Microsoft 365 usage analytics for Power BI** setting on and **Save**.</span></span>
  
## <a name="we-are-processing-your-data"></a><span data-ttu-id="9db0f-113">데이터를 처리하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9db0f-113">We are processing your data</span></span>

 <span data-ttu-id="9db0f-114">**이 메시지가 표시 되는 위치:** Microsoft 365 관리 센터에서 **사용** 대시보드의 **microsoft 365 usage analytics** 타일</span><span class="sxs-lookup"><span data-stu-id="9db0f-114">**Where you will see this message:** In the **Microsoft 365 usage analytics** tile on the **Usage** dashboard in the Microsoft 365 admin center.</span></span> 
  
 <span data-ttu-id="9db0f-115">**원인:** Microsoft 365 관리 센터에서 [서식 파일 앱의 데이터](enable-usage-analytics.md) 를 표시 하도록 선택 하면 microsoft 365 시스템에서 조직의 기록 사용 현황 데이터를 생성 하기 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="9db0f-115">**Cause:** When you [opt in to seeing data in the template app](enable-usage-analytics.md) from the Microsoft 365 admin center, the Microsoft 365 system starts generating historical usage data for your organization.</span></span> <span data-ttu-id="9db0f-116">테넌트의 크기에 따라 이 단계는 2시간에서 48시간까지 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9db0f-116">Depending on the size of your tenant, this step could take anywhere between 2 hours to 48 hours.</span></span> 
  
 <span data-ttu-id="9db0f-117">**이 문제를 해결 하려면** 하지만 3 일 후에 **데이터가** 변경 되지 않으면 [Microsoft 365에 문의 하 여 비즈니스 지원을](../contact-support-for-business-products.md)받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9db0f-117">**To fix this:** Just be patient, but if the message does not change to **Your data is ready** after 3 days, [contact Microsoft 365 for business support](../contact-support-for-business-products.md).</span></span>
  
## <a name="we-are-unable-to-process-your-request-at-this-time-we-are-still-preparing-the-data-for-your-organization"></a><span data-ttu-id="9db0f-118">현재 요청을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9db0f-118">We are unable to process your request at this time.</span></span> <span data-ttu-id="9db0f-119">아직 조직의 데이터를 준비하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9db0f-119">We are still preparing the data for your organization</span></span>

 <span data-ttu-id="9db0f-120">**오류 코드:** 423</span><span class="sxs-lookup"><span data-stu-id="9db0f-120">**Error Code:** 423</span></span> 
  
 <span data-ttu-id="9db0f-121">**이 메시지가 표시 되는 위치:** Microsoft 365 사용 현황 분석 서식 파일 앱에 연결 하거나 Microsoft 365 보고 Api를 직접 호출 하는 경우 Power BI에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9db0f-121">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="9db0f-122">**원인:** 관리 센터에서 [서식 파일 앱의 데이터](enable-usage-analytics.md) 를 표시 하도록 선택 하면 Microsoft 365 시스템에서 조직의 기록 사용 현황 데이터를 생성 하기 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="9db0f-122">**Cause:** When you [opt in to seeing data in the template app](enable-usage-analytics.md) from the admin center, the Microsoft 365 system starts generating historical usage data for your organization.</span></span> <span data-ttu-id="9db0f-123">테넌트의 크기에 따라 이 단계는 2시간에서 48시간까지 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9db0f-123">Depending on the size of your tenant, this step could take anywhere between 2 hours to 48 hours.</span></span> 
  
 <span data-ttu-id="9db0f-124">**이 문제를 해결 하려면** 단, 메시지가 시작 된 후 3 일 이내에 **데이터가** 변경 되지 않는 경우 [Microsoft 365에 문의 하 여 비즈니스 지원을](../contact-support-for-business-products.md)받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9db0f-124">**To fix this:** Just be patient, but if the message does not change to **Your data is ready** even 3 days since initiation, [contact Microsoft 365 for business support](../contact-support-for-business-products.md).</span></span>
  
## <a name="the-tenant-id-you-provided-is-not-in-the-correct-format"></a><span data-ttu-id="9db0f-125">입력하신 테넌트 ID의 형식이 올바르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9db0f-125">The tenant ID you provided is not in the correct format</span></span>

 <span data-ttu-id="9db0f-126">**오류 코드:** 4:00</span><span class="sxs-lookup"><span data-stu-id="9db0f-126">**Error Code:** 400</span></span> 
  
 <span data-ttu-id="9db0f-127">**이 메시지가 표시 되는 위치:** Microsoft 365 사용 현황 분석 서식 파일 앱에 연결 하거나 Microsoft 365 보고 Api를 직접 호출 하는 경우 Power BI에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9db0f-127">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="9db0f-p107">**원인:** 테넌트 ID는 GUID이며 xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx 형식이어야 합니다. 테넌트 입력 상자에 다른 문자열을 입력하면 이 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="9db0f-p107">**Cause:** The tenant id is a guid and has to be in the format of xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx. If you enter any other string in the tenant input box you will get this error.</span></span> 
  
 <span data-ttu-id="9db0f-130">**이 오류를 해결 하려면** 관리 센터 \> 의 <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">사용 현황</a> **보고서** \> 로 이동 하 여 기본 대시보드 페이지에서 Microsoft 365 Usage analytics 타일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="9db0f-130">**To fix this error:** Go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="9db0f-131">테넌트 ID가 타일에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="9db0f-131">The tenant id is listed on the tile.</span></span> <span data-ttu-id="9db0f-132">서식 파일 앱에 연결 하기 위해 여기에서 복사 하 여 대화 상자에 붙여 넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9db0f-132">You can copy it from here and paste it in the dialog box for connecting to the template app.</span></span> 
  
## <a name="the-tenant-id-you-provided-is-not-recognized-by-our-system"></a><span data-ttu-id="9db0f-133">입력하신 테넌트 ID가 시스템에서 인식되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9db0f-133">The tenant ID you provided is not recognized by our system</span></span>

 <span data-ttu-id="9db0f-134">**오류 코드:** 404</span><span class="sxs-lookup"><span data-stu-id="9db0f-134">**Error Code:** 404</span></span> 
  
 <span data-ttu-id="9db0f-135">**이 메시지가 표시 되는 위치:** Microsoft 365 사용 현황 분석 서식 파일 앱에 연결 하거나 Microsoft 365 보고 Api를 직접 호출 하는 경우 Power BI에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9db0f-135">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="9db0f-136">**원인:** 입력하신 테넌트 ID가 올바르지 않거나 존재하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9db0f-136">**Cause:** The tenant id you provided is not valid or does not exist.</span></span> 
  
 <span data-ttu-id="9db0f-137">**이 오류를 해결 하려면** 관리 센터 \> 의 <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">사용 현황</a> **보고서** \> 로 이동 하 여 기본 대시보드 페이지에서 Microsoft 365 Usage analytics 타일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="9db0f-137">**To fix this error:** Go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="9db0f-138">테넌트 ID가 타일에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="9db0f-138">The tenant id is listed on the tile.</span></span> <span data-ttu-id="9db0f-139">서식 파일 앱에 연결 하기 위해 여기에서 복사 하 여 대화 상자에 붙여 넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9db0f-139">You can copy it from here and paste it in the dialog box for connecting to the template app.</span></span> 
  
## <a name="please-re-enter-your-credentials-to-sign-in-to-power-bi-again"></a><span data-ttu-id="9db0f-140">Power BI에 다시 로그인하려면 자격 증명을 다시 입력하세요.</span><span class="sxs-lookup"><span data-stu-id="9db0f-140">Please re-enter your credentials to sign in to Power BI again</span></span>

<span data-ttu-id="9db0f-141">오류 코드: 302</span><span class="sxs-lookup"><span data-stu-id="9db0f-141">Error Code: 302</span></span>
  
 <span data-ttu-id="9db0f-142">**이 메시지가 표시 되는 위치:** Microsoft 365 사용 현황 분석 서식 파일 앱에 연결 하거나 Microsoft 365 보고 Api를 직접 호출 하는 경우 Power BI에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9db0f-142">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="9db0f-143">**원인:** 인증 코드 확인에 실패하여 자격 증명을 다시 입력해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9db0f-143">**Cause:** The authorization code failed and may require you to enter your credentials again.</span></span> 
  
 <span data-ttu-id="9db0f-144">**오류 수정 방법:** Power BI에서 로그아웃한 다음 다시 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="9db0f-144">**To fix this error:** Sign out of Power BI, and then sign in again.</span></span> 
  
## <a name="you-do-not-have-the-right-authorization-to-access-to-this-data-to-be-able-to-gain-access-to-the-data-from-this-service-you-need-to-be-either-a-global-admin-or-any-one-of-the-product-admins"></a><span data-ttu-id="9db0f-145">이 데이터에 액세스할 수 있는 권한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9db0f-145">You do not have the right authorization to access to this data.</span></span> <span data-ttu-id="9db0f-146">이 서비스에서 데이터에 대한 액세스 권한을 얻으려면 전역 관리자 또는 제품 관리자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9db0f-146">To be able to gain access to the data from this service you need to be either a global admin or any one of the product admins</span></span>

 <span data-ttu-id="9db0f-147">**오류 코드:** 403</span><span class="sxs-lookup"><span data-stu-id="9db0f-147">**Error Code:** 403</span></span> 
  
 <span data-ttu-id="9db0f-148">**이 메시지가 표시 되는 위치:** Microsoft 365 사용 현황 분석 서식 파일 앱에 연결 하거나 Microsoft 365 보고 Api를 직접 호출 하는 경우 Power BI에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9db0f-148">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="9db0f-149">**원인:** 서식 파일 앱에 연결을 시도한 사용자에 게이 데이터에 액세스 하기 위한 권한 부여 수준이 없기 때문에 인증 코드가 실패 했습니다.</span><span class="sxs-lookup"><span data-stu-id="9db0f-149">**Cause:** The authorization code failed because the user who tried connecting to the template app does not have the right level of authorization to access this data.</span></span> 
  
 <span data-ttu-id="9db0f-150">**이 오류를 해결 하려면** **전역 관리자**, **Exchange 관리자**, **비즈니스용 Skype 관리자**, **SharePoint 관리자**, **전역 독자** 또는 **보고서 구독자** 인 사용자 자격 증명을 제공 하 여 서식 파일 앱에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="9db0f-150">**To fix this error:** Provide the credentials of a user who is either a **Global admin**, **Exchange admin**, **Skype for Business admin**, **SharePoint admin**, **Global reader** or **Report reader** to connect to the template app.</span></span> <span data-ttu-id="9db0f-151">자세한 내용은 [관리자 역할 정보](../add-users/about-admin-roles.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9db0f-151">See [About admin roles](../add-users/about-admin-roles.md) for more information.</span></span> 
  
## <a name="refresh-failed"></a><span data-ttu-id="9db0f-152">새로 고치지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="9db0f-152">Refresh failed</span></span>

 <span data-ttu-id="9db0f-153">**이 메시지가 표시되는 위치:** Power BI 전자 메일 또는 새로 고침 기록의 실패 상태.</span><span class="sxs-lookup"><span data-stu-id="9db0f-153">**Where you will see this message:** Email from Power BI or failed status in the refresh history.</span></span> 
  
 <span data-ttu-id="9db0f-154">**원인:** 경우에 따라 서식 파일 앱에 연결 된 사용자의 자격 증명이 다시 설정 되 고 서식 파일 앱의 연결 설정에서 업데이트 되지 않아 사용자가 새로 고침 실패 오류가 표시 되는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9db0f-154">**Cause:** Sometimes the credentials of the user who connected to the template app are reset, and not updated in the connection settings of the template app causing the user to see refresh failure errors.</span></span> 
  
 <span data-ttu-id="9db0f-155">**이 오류를 해결 하려면** Power BI에서 Microsoft 365 사용 현황 분석 서식 파일 앱에 해당 하는 데이터 집합을 찾고 **새로 고침 예약** 및 관리자 자격 증명 제공을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9db0f-155">**To fix this error:** In Power BI, find the dataset corresponding to the Microsoft 365 Usage Analytics template app, select **schedule refresh** and provide your admin credentials.</span></span> 
  
<span data-ttu-id="9db0f-156">그래도 문제가 해결 되지 않으면 캐시를 지우고 서식 파일 앱을 다시 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9db0f-156">If that doesn't work, clear the cache, and re-create the template app.</span></span>
  
  
