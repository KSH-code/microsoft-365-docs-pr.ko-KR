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
description: Power BI에서 Microsoft 365 사용 현황 분석 템플릿 앱을 사용하여 테넌트에 대한 데이터 수집을 시작하는 방법을 알아보십시오.
ms.openlocfilehash: 7c92fb643f9be6b5f1474f08df659c4f488a9a41
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579065"
---
# <a name="enable-microsoft-365-usage-analytics"></a><span data-ttu-id="e0daf-103">Microsoft 365 사용 현황 분석을 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="e0daf-103">Enable Microsoft 365 usage analytics</span></span>

<span data-ttu-id="e0daf-104">Microsoft 365 미국 정부 커뮤니티에서는 Microsoft 365 사용 현황 분석을 아직 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e0daf-104">Microsoft 365 usage analytics is not yet available for Microsoft 365 US Government Community.</span></span>
  
## <a name="steps-to-enable-microsoft-365-usage-analytics"></a><span data-ttu-id="e0daf-105">Microsoft 365 사용 현황 분석을 사용 설정 단계</span><span class="sxs-lookup"><span data-stu-id="e0daf-105">Steps to enable Microsoft 365 usage analytics</span></span>

<span data-ttu-id="e0daf-106">Microsoft 365 사용 현황 분석을 시작하려면 먼저 Microsoft 365 관리 센터에서 데이터를 사용할 수 있도록 설정한 다음 Power BI에서 템플릿 앱을 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0daf-106">To get started with Microsoft 365 usage analytics you must first make the data available in the Microsoft 365 admin center, then initiate the template app in Power BI.</span></span>
  
### <a name="get-power-bi"></a><span data-ttu-id="e0daf-107">Power BI 가져오기</span><span class="sxs-lookup"><span data-stu-id="e0daf-107">Get Power BI</span></span>

<span data-ttu-id="e0daf-108">Power BI가 아직 없는 경우 [Power BI Pro에 등록할 수 있습니다.](https://go.microsoft.com/fwlink/p/?linkid=845347)</span><span class="sxs-lookup"><span data-stu-id="e0daf-108">If you don't already have Power BI, you can [sign up for Power BI Pro](https://go.microsoft.com/fwlink/p/?linkid=845347).</span></span> <span data-ttu-id="e0daf-109">무료 **평가판** 등록을 선택하거나  지금 구입을 선택하여 Power BI Pro를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="e0daf-109">Select **Try free** to sign up for a trial, or **Buy now** to get Power BI Pro.</span></span>
  
  
<span data-ttu-id="e0daf-110">**제품** 을 확장하여 Power BI 버전을 구매할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0daf-110">You can also expand **Products** to buy a version of Power BI.</span></span> 

> [!NOTE]
> <span data-ttu-id="e0daf-111">템플릿 앱을 설치, 사용자 지정 및 배포하려면 Power BI Pro 라이선스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e0daf-111">You need a Power BI Pro license to install, customize, and distribute a template app.</span></span> <span data-ttu-id="e0daf-112">자세한 내용은 [Prerequisites를 참조하세요.](/power-bi/service-template-apps-install-distribute?source=docs#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="e0daf-112">For more information, please see [Prerequisites](/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).</span></span>

<span data-ttu-id="e0daf-113">데이터를 공유하려면 사용자와 데이터를 공유하는 사람이 모두 Power BI Pro 라이선스가 필요하거나 콘텐츠가 [Power BI Premium](/power-bi/service-premium-what-is)서비스의 작업 영역 에 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0daf-113">To share your data, both you and the people who you share the data with, need a Power BI Pro license, or the content needs to be in a workspace in a [Power BI premium service](/power-bi/service-premium-what-is).</span></span> 
  
### <a name="enable-the-template-app"></a><span data-ttu-id="e0daf-114">템플릿 앱 사용</span><span class="sxs-lookup"><span data-stu-id="e0daf-114">Enable the template app</span></span>

<span data-ttu-id="e0daf-115">템플릿 앱을 사용하도록 설정하려면 전역 관리자 **를 으로 설정해야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="e0daf-115">To enable the template app, you have to be a **Global administrator**.</span></span>
  
<span data-ttu-id="e0daf-116">자세한 [내용은 관리자 역할](../add-users/about-admin-roles.md) 정보를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e0daf-116">See [about admin roles](../add-users/about-admin-roles.md) for more information.</span></span> 
  
1. <span data-ttu-id="e0daf-117">관리 센터에서 **보고서** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">사용 현황</a> 페이지를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e0daf-117">In the admin center, go to the **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> page.</span></span> 
    
2. <span data-ttu-id="e0daf-118">사용 **페이지에서** **Microsoft 365** 사용 현황 분석 카드를 찾고 시작 **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e0daf-118">On the **Usage** page, locate the **Microsoft 365 usage analytics** card, and select **Get started**.</span></span>
    
3. <span data-ttu-id="e0daf-119">보고서 패널이 열리면 **Power BI에 대한 Microsoft 365** 사용 현황 분석을 사용할 수 있도록 설정 을 **저장으로** \> **설정하십시오.**</span><span class="sxs-lookup"><span data-stu-id="e0daf-119">On the Reports panel that opens, set **Make data available to Microsoft 365 usage analytics for Power BI** to **On** \> **Save**.</span></span> 
  
<span data-ttu-id="e0daf-120">데이터 수집 프로세스는 테넌트의 크기에 따라 2~48시간 만에 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0daf-120">The data collection process will complete in two to 48 hours depending on the size of your tenant.</span></span> <span data-ttu-id="e0daf-121">데이터 수집이 완료되면 **Power BI로** 이동 단추가 활성화됩니다(더 이상 회색 아 없음).</span><span class="sxs-lookup"><span data-stu-id="e0daf-121">The **Go to Power BI** button will be enabled (no longer gray) when data collection is complete.</span></span> 
    
### <a name="start-the-template-app"></a><span data-ttu-id="e0daf-122">템플릿 앱 시작</span><span class="sxs-lookup"><span data-stu-id="e0daf-122">Start the template app</span></span>

<span data-ttu-id="e0daf-123">템플릿 앱을 시작하기 위해 전역 **관리자,** 보고서 읽기 권한자,  **Exchange** 관리자, 비즈니스용 **Skype** 관리자 또는 SharePoint 관리자 중 **하나일 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="e0daf-123">To start the template app, you have to be either a **global administrator**, **report reader**, **Exchange administrator**, **Skype for Business administrator**, or **SharePoint administrator**.</span></span> 
  
1. <span data-ttu-id="e0daf-124">테넌트 ID를 복사하고 **Power BI로 이동을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e0daf-124">Copy the tenant ID and select **Go to Power BI**.</span></span>
    
2.  <span data-ttu-id="e0daf-125">Power BI로 이동하면 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="e0daf-125">When you get to Power BI, sign in.</span></span> <span data-ttu-id="e0daf-126">그런 **다음 탐색** -> **메뉴에서 앱** 다운로드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e0daf-126">Then **Select Apps**->**Get apps** from the navigation menu.</span></span>    
  
3. <span data-ttu-id="e0daf-127">앱 **탭의** 검색 상자에 Microsoft 365를 입력한 다음 **Microsoft 365** 사용 현황 분석 \> **지금 다운로드를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e0daf-127">In the **Apps** tab, type Microsoft 365 in the search box and then select **Microsoft 365 usage analytics** \> **Get it now**.</span></span>

    <span data-ttu-id="e0daf-128">[![지금 시작을 선택합니다.](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span><span class="sxs-lookup"><span data-stu-id="e0daf-128">[![Select Get it now](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span></span>
    
4.  <span data-ttu-id="e0daf-129">앱이 설치되면</span><span class="sxs-lookup"><span data-stu-id="e0daf-129">Once the app is installed.</span></span> <span data-ttu-id="e0daf-130">타일을 선택하여 열립니다.</span><span class="sxs-lookup"><span data-stu-id="e0daf-130">Select the tile to open it.</span></span>

5.  <span data-ttu-id="e0daf-131">샘플 **데이터로** 앱을 보기 위해 앱 탐색을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e0daf-131">Select **Explore app** to view the app with sample data.</span></span> <span data-ttu-id="e0daf-132">연결을 **선택하면** 앱을 조직의 데이터에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="e0daf-132">Choose **Connect** to connect the app to your organization’s data.</span></span>

6.  <span data-ttu-id="e0daf-133">Microsoft  **365에 연결** 사용 현황 분석 화면에서 연결을 선택한 다음 1단계에서 복사한 테넌트 ID(대시 없이)를 입력하고 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e0daf-133">Choose **Connect**, on the **Connect to Microsoft 365 usage analytics** screen, then type in the tenant ID (without dashes) you copied in step (1), and select **Next**.</span></span>
    
7. <span data-ttu-id="e0daf-134">다음 화면에서 인증 방법 **로그인으로 OAuth2를**  \> **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e0daf-134">On the next screen, select **OAuth2** as the **Authentication method** \> **Sign in**.</span></span> <span data-ttu-id="e0daf-135">다른 인증 방법을 선택하면 템플릿 앱에 대한 연결이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="e0daf-135">If you choose any other authentication method, the connection to the template app will fail.</span></span>
    
    ![인증 방법으로 Microsoft 계정 선택](../../media/ab6f0463-c3f7-4088-a605-67c699fa86adnew.png)
  
8. <span data-ttu-id="e0daf-137">템플릿 앱이 인스턴스화된 후 Microsoft 365 사용 현황 분석 대시보드는 웹의 Power BI에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0daf-137">After the template app is instantiated the Microsoft 365 usage analytics dashboard will be available in Power BI on the web.</span></span> <span data-ttu-id="e0daf-138">대시보드의 초기 로드에는 2~30분 정도 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="e0daf-138">The initial loading of the dashboard will take between 2 to 30 minutes.</span></span>
  
<span data-ttu-id="e0daf-139">테넌트 수준 집계는 옵트인 후 모든 보고서에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0daf-139">Tenant level aggregates will be available in all reports after opting in.</span></span> <span data-ttu-id="e0daf-140">사용자 수준 세부 정보는 옵트인 후 다음 달 **5일 전후에만 사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="e0daf-140">**User-level details will only become available around the 5th of the next calendar month after opting in**.</span></span> <span data-ttu-id="e0daf-141">이는 사용자 활동의 모든 보고서에 영향을 줍니다(이러한 보고서를 보고 사용하는 방법에 대한 팁은 [Microsoft 365](navigate-and-utilize-reports.md) 사용 현황 분석에서 보고서 탐색 및 활용 참조).</span><span class="sxs-lookup"><span data-stu-id="e0daf-141">This will impact all reports under User Activity (See [Navigate and utilize the reports in Microsoft 365 usage analytics](navigate-and-utilize-reports.md) for tips on how to view and use these reports).</span></span>
    
## <a name="make-the-collected-data-anonymous"></a><span data-ttu-id="e0daf-142">수집된 데이터를 익명으로 설정</span><span class="sxs-lookup"><span data-stu-id="e0daf-142">Make the collected data anonymous</span></span>

<span data-ttu-id="e0daf-143">모든 보고서에 대해 수집되는 데이터를 익명으로 만들려면 글로벌 관리자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0daf-143">To make the data that is collected for all reports anonymous, you have to be a global administrator.</span></span> <span data-ttu-id="e0daf-144">이렇게 하면 보고서 및 템플릿 앱에서 사용자, 그룹 및 사이트 이름과 같은 식별 가능한 정보가 숨겨지게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0daf-144">This will hide identifiable information such as user, group and site names in reports and in the template app .</span></span>
  
1. <span data-ttu-id="e0daf-145">관리 센터에서 설정 구성  설정으로 \> **이동하고** 서비스 **탭에서** 보고서를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e0daf-145">In the admin center, go to the **Settings** \> **Org Settings**, and under **Services** tab, choose **Reports**.</span></span>
    
2. <span data-ttu-id="e0daf-146">보고서를 **선택한** 다음 익명 식별자 **표시를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e0daf-146">Select **Reports**, and then choose to **Display anonymous identifiers**.</span></span> <span data-ttu-id="e0daf-147">이 설정은 템플릿 앱뿐만 아니라 사용 현황 보고서에도 모두 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0daf-147">This setting gets applied both to the usage reports as well as to the template app.</span></span>
  
3. <span data-ttu-id="e0daf-148">**변경 내용 저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e0daf-148">Select **Save changes**.</span></span>