---
title: Microsoft 365 사용 현황 분석을 사용하도록 설정
f1.keywords:
- CSH
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
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9db96e9f-a622-4d5d-b134-09dcace55b6a
description: Power BI에서 Microsoft 365 사용 현황 분석 템플릿 앱을 사용하여 테넌트에 대한 데이터 수집을 시작하는 방법을 알아보십시오.
ms.openlocfilehash: 98ae107b6777ac97d0be3b37847117c6e20be63d
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114240"
---
# <a name="enable-microsoft-365-usage-analytics"></a><span data-ttu-id="4ddd9-103">Microsoft 365 사용 현황 분석을 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="4ddd9-103">Enable Microsoft 365 usage analytics</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="4ddd9-104">관리 센터가 변경되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ddd9-104">The admin center is changing.</span></span> <span data-ttu-id="4ddd9-105">사용자의 환경이 여기에 설명된 세부 정보와 맞지 않는 경우에는 [새 Microsoft 365 관리 센터 정보](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4ddd9-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="4ddd9-106">Microsoft 365 미국 정부 커뮤니티에서는 Microsoft 365 사용 현황 분석을 아직 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4ddd9-106">Microsoft 365 usage analytics is not yet available for Microsoft 365 US Government Community.</span></span>
  
## <a name="steps-to-enable-microsoft-365-usage-analytics"></a><span data-ttu-id="4ddd9-107">Microsoft 365 사용 현황 분석을 사용하도록 설정하는 단계</span><span class="sxs-lookup"><span data-stu-id="4ddd9-107">Steps to enable Microsoft 365 usage analytics</span></span>

<span data-ttu-id="4ddd9-108">Microsoft 365 사용 현황 분석을 시작하려면 먼저 Microsoft 365 관리 센터에서 데이터를 사용할 수 있도록 설정한 다음 Power BI에서 템플릿 앱을 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddd9-108">To get started with Microsoft 365 usage analytics you must first make the data available in the Microsoft 365 admin center, then initiate the template app in Power BI.</span></span>
  
### <a name="get-power-bi"></a><span data-ttu-id="4ddd9-109">Power BI 가져오기</span><span class="sxs-lookup"><span data-stu-id="4ddd9-109">Get Power BI</span></span>

<span data-ttu-id="4ddd9-110">Power BI가 아직 없는 경우 [Power BI Pro에 등록할 수 있습니다.](https://go.microsoft.com/fwlink/p/?linkid=845347)</span><span class="sxs-lookup"><span data-stu-id="4ddd9-110">If you don't already have Power BI, you can [sign up for Power BI Pro](https://go.microsoft.com/fwlink/p/?linkid=845347).</span></span> <span data-ttu-id="4ddd9-111">무료 **평가판에** 등록하거나 지금  구입하여 Power BI Pro를 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="4ddd9-111">Select **Try free** to sign up for a trial, or **Buy now** to get Power BI Pro.</span></span>
  
  
<span data-ttu-id="4ddd9-112">**제품** 을 확장하여 Power BI 버전을 구매할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ddd9-112">You can also expand **Products** to buy a version of Power BI.</span></span> 

> [!NOTE]
> <span data-ttu-id="4ddd9-113">템플릿 앱을 설치, 사용자 지정 및 배포하려면 Power BI Pro 라이선스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddd9-113">You need a Power BI Pro license to install, customize, and distribute a template app.</span></span> <span data-ttu-id="4ddd9-114">자세한 내용은 사전 [준비를 참조하세요.](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="4ddd9-114">For more information, please see [Prerequisites](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).</span></span>

<span data-ttu-id="4ddd9-115">데이터를 공유하려면 사용자와 데이터를 공유하는 사용자 모두 Power BI Pro 라이선스가 필요하거나, 콘텐츠가 Power BI Premium 서비스의 작업 영역이 [되거나,](https://docs.microsoft.com/power-bi/service-premium-what-is)</span><span class="sxs-lookup"><span data-stu-id="4ddd9-115">To share your data, both you and the people who you share the data with, need a Power BI Pro license, or the content needs to be in a workspace in a [Power BI premium service](https://docs.microsoft.com/power-bi/service-premium-what-is).</span></span> 
  
### <a name="enable-the-template-app"></a><span data-ttu-id="4ddd9-116">템플릿 앱 사용</span><span class="sxs-lookup"><span data-stu-id="4ddd9-116">Enable the template app</span></span>

<span data-ttu-id="4ddd9-117">템플릿 앱을 사용하도록 설정하려면 전역 **관리자로 설정해야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ddd9-117">To enable the template app, you have to be a **Global administrator**.</span></span>
  
<span data-ttu-id="4ddd9-118">자세한 [내용은 관리자 역할에](../add-users/about-admin-roles.md) 대해 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4ddd9-118">See [about admin roles](../add-users/about-admin-roles.md) for more information.</span></span> 
  
1. <span data-ttu-id="4ddd9-119">관리 센터에서 **보고서** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">사용 현황</a> 페이지를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4ddd9-119">In the admin center, go to the **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> page.</span></span> 
    
2. <span data-ttu-id="4ddd9-120">사용 **페이지에서** **Microsoft 365** 사용 현황 분석 카드를 찾고 **시작을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ddd9-120">On the **Usage** page, locate the **Microsoft 365 usage analytics** card, and select **Get started**.</span></span>
    
3. <span data-ttu-id="4ddd9-121">보고서 패널이 열리면 **Power BI에 대한 Microsoft 365** 사용 현황 분석에서 데이터를 사용할 수 있도록 **설정하여 저장합니다.** \> </span><span class="sxs-lookup"><span data-stu-id="4ddd9-121">On the Reports panel that opens, set **Make data available to Microsoft 365 usage analytics for Power BI** to **On** \> **Save**.</span></span> 
  
<span data-ttu-id="4ddd9-122">데이터 수집 프로세스는 테넌트의 크기에 따라 2~48시간이면 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ddd9-122">The data collection process will complete in two to 48 hours depending on the size of your tenant.</span></span> <span data-ttu-id="4ddd9-123">데이터 수집이 완료되면 **Power BI로** 이동 단추를 사용할 수 있습니다(더 이상 회색 아미기).</span><span class="sxs-lookup"><span data-stu-id="4ddd9-123">The **Go to Power BI** button will be enabled (no longer gray) when data collection is complete.</span></span> 
    
### <a name="start-the-template-app"></a><span data-ttu-id="4ddd9-124">템플릿 앱 시작</span><span class="sxs-lookup"><span data-stu-id="4ddd9-124">Start the template app</span></span>

<span data-ttu-id="4ddd9-125">템플릿 앱을 시작하기 위해 전역 **관리자,** 보고서 읽기 **프로그램,** **Exchange** 관리자, 비즈니스용 **Skype** 관리자 또는 **SharePoint 관리자 중 하나 이상이면 됩니다.**</span><span class="sxs-lookup"><span data-stu-id="4ddd9-125">To start the template app, you have to be either a **global administrator**, **report reader**, **Exchange administrator**, **Skype for Business administrator**, or **SharePoint administrator**.</span></span> 
  
1. <span data-ttu-id="4ddd9-126">테넌트 ID를 복사하고 **Power BI로 이동을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ddd9-126">Copy the tenant ID and select **Go to Power BI**.</span></span>
    
2.  <span data-ttu-id="4ddd9-127">Power BI로 이동하면 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddd9-127">When you get to Power BI, sign in.</span></span> <span data-ttu-id="4ddd9-128">그런 **다음 탐색** -> **메뉴에서 앱을** 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddd9-128">Then **Select Apps**->**Get apps** from the navigation menu.</span></span>    
  
3. <span data-ttu-id="4ddd9-129">앱 **탭에서** 검색 상자에 Microsoft 365를 입력한 다음 **Microsoft 365** 사용 현황 분석을 \> **지금 다운로드합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ddd9-129">In the **Apps** tab, type Microsoft 365 in the search box and then select **Microsoft 365 usage analytics** \> **Get it now**.</span></span>

    <span data-ttu-id="4ddd9-130">[![지금 사용 선택](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span><span class="sxs-lookup"><span data-stu-id="4ddd9-130">[![Select Get it now](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span></span>
    
4.  <span data-ttu-id="4ddd9-131">앱이 설치되면</span><span class="sxs-lookup"><span data-stu-id="4ddd9-131">Once the app is installed.</span></span> <span data-ttu-id="4ddd9-132">타일을 선택하여 열습니다.</span><span class="sxs-lookup"><span data-stu-id="4ddd9-132">Select the tile to open it.</span></span>

5.  <span data-ttu-id="4ddd9-133">샘플 **데이터가 있는** 앱을 보기 위해 탐색 앱을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddd9-133">Select **Explore app** to view the app with sample data.</span></span> <span data-ttu-id="4ddd9-134">**Connect를** 선택하면 앱을 조직의 데이터에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddd9-134">Choose **Connect** to connect the app to your organization’s data.</span></span>

6.  <span data-ttu-id="4ddd9-135">**Connect를** 선택하고 **Microsoft 365** 사용 현황 분석 화면에 연결 화면에서 복사한 테넌트 ID(대시 없이)를 입력하고(1단계) 다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ddd9-135">Choose **Connect**, on the **Connect to Microsoft 365 usage analytics** screen, then type in the tenant ID (without dashes) you copied in step (1), and select **Next**.</span></span>
    
7. <span data-ttu-id="4ddd9-136">다음 화면에서 인증 방법으로 로그인하여  **OAuth2를** \> **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ddd9-136">On the next screen, select **OAuth2** as the **Authentication method** \> **Sign in**.</span></span> <span data-ttu-id="4ddd9-137">다른 인증 방법을 선택하면 템플릿 앱에 대한 연결이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddd9-137">If you choose any other authentication method, the connection to the template app will fail.</span></span>
    
    ![인증 방법으로 Microsoft 계정 선택](../../media/ab6f0463-c3f7-4088-a605-67c699fa86adnew.png)
  
8. <span data-ttu-id="4ddd9-139">템플릿 앱이 인스턴스화된 후 Microsoft 365 사용 현황 분석 대시보드는 웹의 Power BI에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ddd9-139">After the template app is instantiated the Microsoft 365 usage analytics dashboard will be available in Power BI on the web.</span></span> <span data-ttu-id="4ddd9-140">대시보드의 초기 로드에는 2~30분 정도 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="4ddd9-140">The initial loading of the dashboard will take between 2 to 30 minutes.</span></span>
  
<span data-ttu-id="4ddd9-141">테넌트 수준 집계는 옵트인 후 모든 보고서에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ddd9-141">Tenant level aggregates will be available in all reports after opting in.</span></span> <span data-ttu-id="4ddd9-142">사용자 수준 세부 정보는 옵트인 후 다음 달 **5일 전후에만 사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="4ddd9-142">**User-level details will only become available around the 5th of the next calendar month after opting in**.</span></span> <span data-ttu-id="4ddd9-143">이는 사용자 활동의 모든 보고서에 영향을 줍니다(이러한 보고서를 보고 사용하는 방법에 대한 팁은 [Microsoft 365](navigate-and-utilize-reports.md) 사용 현황 분석의 보고서 탐색 및 활용 참조).</span><span class="sxs-lookup"><span data-stu-id="4ddd9-143">This will impact all reports under User Activity (See [Navigate and utilize the reports in Microsoft 365 usage analytics](navigate-and-utilize-reports.md) for tips on how to view and use these reports).</span></span>
    
## <a name="make-the-collected-data-anonymous"></a><span data-ttu-id="4ddd9-144">수집된 데이터를 익명으로 설정</span><span class="sxs-lookup"><span data-stu-id="4ddd9-144">Make the collected data anonymous</span></span>

<span data-ttu-id="4ddd9-145">모든 보고서에 대해 수집되는 데이터를 익명으로 만들려면 글로벌 관리자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddd9-145">To make the data that is collected for all reports anonymous, you have to be a global administrator.</span></span> <span data-ttu-id="4ddd9-146">이렇게 하면 보고서 및 템플릿 앱의 사용자, 그룹 및 사이트 이름과 같은 식별 가능한 정보가 숨겨지게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ddd9-146">This will hide identifiable information such as user, group and site names in reports and in the template app .</span></span>
  
1. <span data-ttu-id="4ddd9-147">관리 센터에서  설정 구성 설정으로 이동한 다음 서비스 탭에서 보고서를 \>  **선택합니다.** </span><span class="sxs-lookup"><span data-stu-id="4ddd9-147">In the admin center, go to the **Settings** \> **Org Settings**, and under **Services** tab, choose **Reports**.</span></span>
    
2. <span data-ttu-id="4ddd9-148">보고서를 **선택한** 다음 익명 식별자를 **표시하려면 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ddd9-148">Select **Reports**, and then choose to **Display anonymous identifiers**.</span></span> <span data-ttu-id="4ddd9-149">이 설정은 템플릿 앱뿐만 아니라 사용 현황 보고서에도 모두 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ddd9-149">This setting gets applied both to the usage reports as well as to the template app.</span></span>
  
3. <span data-ttu-id="4ddd9-150">**변경 내용 저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddd9-150">Select **Save changes**.</span></span>
