---
title: Microsoft 365 사용 현황 분석을 사용하도록 설정
f1.keywords:
- CSH
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
ms.assetid: 9db96e9f-a622-4d5d-b134-09dcace55b6a
description: Microsoft 365 사용 현황 분석 템플릿 앱을 사용하여 테넌트에 대한 데이터 수집을 시작하는 방법을 Power BI.
ms.openlocfilehash: 01923887b4af143d1490e14d59a6174700e6ae93
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635417"
---
# <a name="enable-microsoft-365-usage-analytics"></a><span data-ttu-id="53baa-103">Microsoft 365 사용 현황 분석을 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="53baa-103">Enable Microsoft 365 usage analytics</span></span>

<span data-ttu-id="53baa-104">Microsoft 365 미국 Government 2013에서는 아직 Microsoft 365 수 Community.</span><span class="sxs-lookup"><span data-stu-id="53baa-104">Microsoft 365 usage analytics is not yet available for Microsoft 365 US Government Community.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="53baa-105">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="53baa-105">Before you begin</span></span>

<span data-ttu-id="53baa-106">사용 현황 Microsoft 365 시작하려면 먼저 Microsoft 365 관리 센터에서 데이터를 사용할 수 있도록 설정한 다음 Power BI.</span><span class="sxs-lookup"><span data-stu-id="53baa-106">To get started with Microsoft 365 usage analytics you must first make the data available in the Microsoft 365 admin center, then initiate the template app in Power BI.</span></span>
  
## <a name="get-power-bi"></a><span data-ttu-id="53baa-107">Power BI 가져오기</span><span class="sxs-lookup"><span data-stu-id="53baa-107">Get Power BI</span></span>

<span data-ttu-id="53baa-108">아직 등록하지 않은 Power BI 에 등록할 [Power BI Pro.](https://go.microsoft.com/fwlink/p/?linkid=845347)</span><span class="sxs-lookup"><span data-stu-id="53baa-108">If you don't already have Power BI, you can [sign up for Power BI Pro](https://go.microsoft.com/fwlink/p/?linkid=845347).</span></span> <span data-ttu-id="53baa-109">무료 **평가판** 등록을 선택하거나  지금 구입을 선택하여 평가판을 Power BI Pro.</span><span class="sxs-lookup"><span data-stu-id="53baa-109">Select **Try free** to sign up for a trial, or **Buy now** to get Power BI Pro.</span></span>
  
  
<span data-ttu-id="53baa-110">**제품** 을 확장하여 Power BI 버전을 구매할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53baa-110">You can also expand **Products** to buy a version of Power BI.</span></span> 

> [!NOTE]
> <span data-ttu-id="53baa-111">템플릿 앱을 Power BI Pro 사용자 지정하고 배포하려면 라이선스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="53baa-111">You need a Power BI Pro license to install, customize, and distribute a template app.</span></span> <span data-ttu-id="53baa-112">자세한 내용은 [Prerequisites를 참조하세요.](/power-bi/service-template-apps-install-distribute?source=docs#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="53baa-112">For more information, please see [Prerequisites](/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).</span></span>

<span data-ttu-id="53baa-113">데이터를 공유하려면 사용자와 데이터를 공유하는 사람이 모두 Power BI Pro 라이선스가 필요하거나 콘텐츠가 Power BI 프리미엄 서비스의 작업 Power BI [합니다.](/power-bi/service-premium-what-is)</span><span class="sxs-lookup"><span data-stu-id="53baa-113">To share your data, both you and the people who you share the data with, need a Power BI Pro license, or the content needs to be in a workspace in a [Power BI premium service](/power-bi/service-premium-what-is).</span></span> 
  
## <a name="enable-the-template-app"></a><span data-ttu-id="53baa-114">템플릿 앱 사용</span><span class="sxs-lookup"><span data-stu-id="53baa-114">Enable the template app</span></span>

<span data-ttu-id="53baa-115">템플릿 앱을 사용하도록 설정하려면 전역 관리자 **를 으로 설정해야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="53baa-115">To enable the template app, you have to be a **Global administrator**.</span></span>
  
<span data-ttu-id="53baa-116">자세한 [내용은 관리자 역할](../add-users/about-admin-roles.md) 정보를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="53baa-116">See [about admin roles](../add-users/about-admin-roles.md) for more information.</span></span> 
  
1. <span data-ttu-id="53baa-117">관리 센터에서 관리 센터  설정 \> **서비스** \> **탭으로** 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="53baa-117">In the admin center, go to the **Settings** \> **Org settings** \> **Services** tab.</span></span> 
    
2. <span data-ttu-id="53baa-118">서비스 **탭에서** 보고서를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="53baa-118">On the **Services** tab, select  **Reports**.</span></span>
    
3. <span data-ttu-id="53baa-119">보고서 패널이 열리면 보고서에 대한 사용 현황 분석을 사용할 Microsoft 365 보고서 데이터를 **Power BI** **저장으로** \> **설정하십시오.**</span><span class="sxs-lookup"><span data-stu-id="53baa-119">On the Reports panel that opens, set **Make report data available to Microsoft 365 usage analytics for Power BI** to **On** \> **Save**.</span></span> 
  
<span data-ttu-id="53baa-120">데이터 수집 프로세스는 테넌트의 크기에 따라 2~48시간 만에 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="53baa-120">The data collection process will complete in two to 48 hours depending on the size of your tenant.</span></span> <span data-ttu-id="53baa-121">데이터 **수집이 Power BI** 이동 단추가 활성화됩니다(더 이상 회색 아 없음).</span><span class="sxs-lookup"><span data-stu-id="53baa-121">The **Go to Power BI** button will be enabled (no longer gray) when data collection is complete.</span></span> 
    
## <a name="start-the-template-app"></a><span data-ttu-id="53baa-122">템플릿 앱 시작</span><span class="sxs-lookup"><span data-stu-id="53baa-122">Start the template app</span></span>

<span data-ttu-id="53baa-123">템플릿 앱을 시작하기 위해 전역 관리자, 보고서 읽기 프로그램 관리자, Exchange  **관리자,** 비즈니스용 Skype 관리자 또는 SharePoint **합니다.**</span><span class="sxs-lookup"><span data-stu-id="53baa-123">To start the template app, you have to be either a **global administrator**, **report reader**, **Exchange administrator**, **Skype for Business administrator**, or **SharePoint administrator**.</span></span> 
  
1. <span data-ttu-id="53baa-124">테넌트 ID를 복사하고 으로 **이동을 Power BI.**</span><span class="sxs-lookup"><span data-stu-id="53baa-124">Copy the tenant ID and select **Go to Power BI**.</span></span>
    
2.  <span data-ttu-id="53baa-125">Power BI로 이동하면 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="53baa-125">When you get to Power BI, sign in.</span></span> <span data-ttu-id="53baa-126">그런 **다음 탐색** -> **메뉴에서 앱** 다운로드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="53baa-126">Then **Select Apps**->**Get apps** from the navigation menu.</span></span>    
  
3. <span data-ttu-id="53baa-127">앱 **탭에서** 검색 Microsoft 365 입력한 다음 사용 현황 Microsoft 365  \> **지금 다운로드를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="53baa-127">In the **Apps** tab, type Microsoft 365 in the search box and then select **Microsoft 365 usage analytics** \> **Get it now**.</span></span>

    <span data-ttu-id="53baa-128">[![지금 시작을 선택합니다.](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span><span class="sxs-lookup"><span data-stu-id="53baa-128">[![Select Get it now](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span></span>
    
4.  <span data-ttu-id="53baa-129">앱이 설치되면</span><span class="sxs-lookup"><span data-stu-id="53baa-129">Once the app is installed.</span></span> <span data-ttu-id="53baa-130">타일을 선택하여 열립니다.</span><span class="sxs-lookup"><span data-stu-id="53baa-130">Select the tile to open it.</span></span>

5.  <span data-ttu-id="53baa-131">샘플 **데이터로** 앱을 보기 위해 앱 탐색을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="53baa-131">Select **Explore app** to view the app with sample data.</span></span> <span data-ttu-id="53baa-132">앱을 **커넥트** 데이터에 연결하기 위해 앱을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="53baa-132">Choose **Connect** to connect the app to your organization’s data.</span></span>

6.  <span data-ttu-id="53baa-133">커넥트 를 선택하여 커넥트 사용 현황 분석 Microsoft 365 선택한 다음 1단계에서 복사한 테넌트 ID(대시 **없이)를** 입력하고 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="53baa-133">Choose **Connect**, on the **Connect to Microsoft 365 usage analytics** screen, then type in the tenant ID (without dashes) you copied in step (1), and select **Next**.</span></span>
    
7. <span data-ttu-id="53baa-134">다음 화면에서 인증 방법 **로그인으로 OAuth2를**  \> **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="53baa-134">On the next screen, select **OAuth2** as the **Authentication method** \> **Sign in**.</span></span> <span data-ttu-id="53baa-135">다른 인증 방법을 선택하면 템플릿 앱에 대한 연결이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="53baa-135">If you choose any other authentication method, the connection to the template app will fail.</span></span>
    
    ![인증 방법으로 Microsoft 계정 선택](../../media/ab6f0463-c3f7-4088-a605-67c699fa86adnew.png)
  
8. <span data-ttu-id="53baa-137">템플릿 앱을 인스턴스화한 후 Microsoft 365 사용 현황 분석 대시보드를 웹의 Power BI 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53baa-137">After the template app is instantiated the Microsoft 365 usage analytics dashboard will be available in Power BI on the web.</span></span> <span data-ttu-id="53baa-138">대시보드의 초기 로드에는 2~30분 정도 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="53baa-138">The initial loading of the dashboard will take between 2 to 30 minutes.</span></span>
  
<span data-ttu-id="53baa-139">테넌트 수준 집계는 옵트인 후 모든 보고서에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53baa-139">Tenant level aggregates will be available in all reports after opting in.</span></span> <span data-ttu-id="53baa-140">사용자 수준 세부 정보는 옵트인 후 다음 달 **5일 전후에만 사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="53baa-140">**User-level details will only become available around the 5th of the next calendar month after opting in**.</span></span> <span data-ttu-id="53baa-141">이는 사용자 활동의 모든 보고서에 영향을 줍니다(이러한 보고서를 보고 [사용하는 방법에 대한](navigate-and-utilize-reports.md) 팁은 Microsoft 365 사용 현황 분석에서 보고서 탐색 및 활용 참조).</span><span class="sxs-lookup"><span data-stu-id="53baa-141">This will impact all reports under User Activity (See [Navigate and utilize the reports in Microsoft 365 usage analytics](navigate-and-utilize-reports.md) for tips on how to view and use these reports).</span></span>
    
## <a name="make-the-collected-data-anonymous"></a><span data-ttu-id="53baa-142">수집된 데이터를 익명으로 설정</span><span class="sxs-lookup"><span data-stu-id="53baa-142">Make the collected data anonymous</span></span>

<span data-ttu-id="53baa-143">모든 보고서에 대해 수집되는 데이터를 익명으로 만들려면 글로벌 관리자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="53baa-143">To make the data that is collected for all reports anonymous, you have to be a global administrator.</span></span> <span data-ttu-id="53baa-144">이렇게 하면 보고서 및 템플릿 앱에서 사용자, 그룹 및 사이트 이름과 같은 식별 가능한 정보가 숨겨지게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="53baa-144">This will hide identifiable information such as user, group and site names in reports and in the template app .</span></span>
  
1. <span data-ttu-id="53baa-145">In the admin center, go to the **설정** \> **Org 설정**, and under **Services** tab, choose **Reports**.</span><span class="sxs-lookup"><span data-stu-id="53baa-145">In the admin center, go to the **Settings** \> **Org Settings**, and under **Services** tab, choose **Reports**.</span></span>
    
2. <span data-ttu-id="53baa-146">보고서를 **선택한** 다음 익명 식별자 **표시를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="53baa-146">Select **Reports**, and then choose to **Display anonymous identifiers**.</span></span> <span data-ttu-id="53baa-147">이 설정은 템플릿 앱뿐만 아니라 사용 현황 보고서에도 모두 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="53baa-147">This setting gets applied both to the usage reports as well as to the template app.</span></span>
  
3. <span data-ttu-id="53baa-148">**변경 내용 저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="53baa-148">Select **Save changes**.</span></span>

## <a name="related-content"></a><span data-ttu-id="53baa-149">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="53baa-149">Related content</span></span>

<span data-ttu-id="53baa-150">[사용 현황 분석(문서)\](usage-analytics.md)</span><span class="sxs-lookup"><span data-stu-id="53baa-150">[About usage analytics](usage-analytics.md) (article)\</span></span>
<span data-ttu-id="53baa-151">[최신 버전의 사용 현황 분석](get-the-latest-version-of-usage-analytics.md) 다운로드(문서)</span><span class="sxs-lookup"><span data-stu-id="53baa-151">[Get the latest version of usage analytics](get-the-latest-version-of-usage-analytics.md) (article)</span></span>\
<span data-ttu-id="53baa-152">[사용 현황 분석에서 보고서를 Microsoft 365](navigate-and-utilize-reports.md) 활용(문서)</span><span class="sxs-lookup"><span data-stu-id="53baa-152">[Navigate and utilize the reports in Microsoft 365 usage analytics](navigate-and-utilize-reports.md) (article)</span></span>