---
title: Microsoft 365 사용 현황 분석에서 보고서 사용자 지정
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
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9b76065f-29b9-4b89-8059-c5f9db9ddbf6
description: 브라우저 및 Power BI Desktop에서 보고서를 사용자 지정하는 방법을 학습합니다.
ms.openlocfilehash: d36e07a19b0ebda0d154b11723630e38b746eb8d
ms.sourcegitcommit: d4604e333507c6f57d5bf327531a241b649052de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/31/2021
ms.locfileid: "51471092"
---
# <a name="customize-the-reports-in-microsoft-365-usage-analytics"></a><span data-ttu-id="8e787-103">Microsoft 365 사용 현황 분석에서 보고서 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="8e787-103">Customize the reports in Microsoft 365 usage analytics</span></span>

<span data-ttu-id="8e787-104">Microsoft 365 사용 현황 분석은 사용자가 Microsoft 365를 채택하고 사용하는 방법에 대한 인사이트를 제공하는 Power BI의 대시보드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8e787-104">Microsoft 365 usage analytics provides a dashboard in Power BI that offers insights into how users adopt and use Microsoft 365.</span></span> <span data-ttu-id="8e787-105">대시보드는 사용 현황 데이터와 상호 작용하는 시작점입니다.</span><span class="sxs-lookup"><span data-stu-id="8e787-105">The dashboard is just a starting point to interact with the usage data.</span></span> <span data-ttu-id="8e787-106">보고서를 사용자 지정하여 더 개인화된 유용한 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e787-106">The reports can be customized for more personalized insights.</span></span>
  
<span data-ttu-id="8e787-107">또한 Power BI Desktop을 통해 보고서를 다른 데이터 원본에 연결하여 추가로 사용자 지정하고 비즈니스에 대한 풍부한 통찰력을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e787-107">You can also use the Power BI desktop to further customize your reports by connecting them to other data sources to gain richer insights about your business.</span></span>
  
## <a name="customizing-reports-in-the-browser"></a><span data-ttu-id="8e787-108">브라우저에서 보고서 사용자 지정하기</span><span class="sxs-lookup"><span data-stu-id="8e787-108">Customizing reports in the browser</span></span>

<span data-ttu-id="8e787-109">다음 두 가지 예에서는 기존 시각적 개체를 수정하고 새롭게 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8e787-109">The following two examples show how to modify an existing visual and how to create a new visual.</span></span>
  
### <a name="modify-an-existing-visual"></a><span data-ttu-id="8e787-110">기존 시각적 개체 수정</span><span class="sxs-lookup"><span data-stu-id="8e787-110">Modify an existing visual</span></span>

<span data-ttu-id="8e787-111">이 예에서는 정품  인증/라이선스 보고서 내에서 정품 인증 **탭을 수정하는 방법을 보여줍니다.**</span><span class="sxs-lookup"><span data-stu-id="8e787-111">This example shows how to modify the **Activation** tab within the **Activation/Licensing** report.</span></span> 
  
1. <span data-ttu-id="8e787-112">정품 **인증/라이선스 보고서에서** 정품 인증 **탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8e787-112">Within the **Activation/Licensing** report, select the **Activation** tab.</span></span>
    
2. <span data-ttu-id="8e787-113">Power BI 단추의  페이지 더하기 단추를 통해 맨 위에 있는 편집 단추를 선택하여 편집 모드를 ![ ](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="8e787-113">Enter the edit mode by choosing the **Edit** button on the top through the ![The more page button in Power BI](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) button.</span></span> 
    
    ![Click Edit report on the top right navigation](../../media/e2c16663-1fbd-4d7f-887c-0cbb891d3b3d.png)
  
3. <span data-ttu-id="8e787-115">On the top right, choose **Duplicate this page**.</span><span class="sxs-lookup"><span data-stu-id="8e787-115">On the top right, choose **Duplicate this page**.</span></span>
    
    ![Choose Duplicate this page](../../media/b2d18dcd-6b82-4ce7-ab79-1b24e3721309.png)
  
4. <span data-ttu-id="8e787-117">오른쪽 아래에서 Android, iOS, Mac 등의 OS를 기반으로 정비하는 사용자 수를 표시하는 막대형 차트를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="8e787-117">In the bottom right, choose any of the bar-charts showing the count of users activating based on the OS such as Android, iOS, Mac, etc.</span></span>
    
5. <span data-ttu-id="8e787-118">오른쪽의  시각화 영역에서 시각적 개체에서 **Mac 개수를** 제거하려면 옆에 **있는 X를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8e787-118">In the **Visualizations** area to the right, in order to remove **Mac Count** from the visual, select the **X** next to it.</span></span>

    ![Mac 개수 제거](../../media/ce3d8358-df57-4f64-bd25-ac5be7fc8713.png)    
    
### <a name="create-a-new-visual"></a><span data-ttu-id="8e787-120">새 시각적 개체 만들기</span><span class="sxs-lookup"><span data-stu-id="8e787-120">Create a new visual</span></span>

<span data-ttu-id="8e787-121">다음 예에서는 매월 사용자를 새로 정의하기 위해 새 시각적 개체를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8e787-121">The following example shows how to create a new visual to track new Yammer users on monthly basis.</span></span>
  
1. <span data-ttu-id="8e787-122">왼쪽 검색 **창을** 사용하여 제품 사용 현황 보고서로 이동하여 Yammer **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="8e787-122">Go to the **Product Usage** report using the left nav and select the **Yammer** tab.</span></span>
    
2. <span data-ttu-id="8e787-123">Power BI 및 Edit에서 더 많은 페이지 단추를 선택하여 편집 ![ ](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) 모드로 **전환합니다.**</span><span class="sxs-lookup"><span data-stu-id="8e787-123">Switch to edit mode by choosing ![The more page button in Power BI](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) and **Edit**.</span></span> 
    
3. <span data-ttu-id="8e787-124">At the bottom of the page, select the</span><span class="sxs-lookup"><span data-stu-id="8e787-124">At the bottom of the page, select the</span></span> ![Power BI의 페이지 추가 단추](../../media/d3b8c117-17d4-4f53-b078-8fefc2155b24.png) <span data-ttu-id="8e787-126">새 페이지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e787-126">to create a new page.</span></span>
  
4. <span data-ttu-id="8e787-127">오른쪽의  시각화 영역에서 누적  막대형 차트(왼쪽에서 맨 위 행)를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="8e787-127">In the **Visualizations** area to the right, choose the **Stacked bar chart** (top row, first from left).</span></span>

    ![막대형 차트 선택](../../media/214c3fed-6eae-43e6-83fb-708a2d74406e.png)
    
5. <span data-ttu-id="8e787-129">해당 시각화의 오른쪽 아래를 선택하고 끌어서 더 크게 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e787-129">Select the bottom right of that visualization and drag to make it larger.</span></span>

6. <span data-ttu-id="8e787-130">오른쪽의 **필드** 영역에서 일정 **테이블을 확장합니다.**</span><span class="sxs-lookup"><span data-stu-id="8e787-130">In the **Fields** area to the right, expand the **Calendar** table.</span></span>

7. <span data-ttu-id="8e787-131">**시각화** 영역의 **축** 머리글 바로 아래에 있는 필드로 **MonthName** 을 끌어다 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="8e787-131">Drag **MonthName** to the fields area, directly below the **Axis** heading in the **Visualizations** area.</span></span>
 
    ![월 이름 끌기](../../media/bff99987-8c4b-4618-89fd-47df557b0ed7.png)
    
8. <span data-ttu-id="8e787-133">오른쪽의 **필드** 영역에서 **TenantProductUsage** 테이블을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="8e787-133">In the **Fields** area to the right, expand the **TenantProductUsage** table.</span></span>

9. <span data-ttu-id="8e787-134">**FirstTimeUsers** 를 **값** 머리글 바로 아래에 있는 필드 영역으로 끌어다 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="8e787-134">Drag **FirstTimeUsers** to the fields area, directly below the **Value** heading.</span></span>

10. <span data-ttu-id="8e787-135">**제품** 을 **시각적 수준 필터** 머리글 바로 아래에 있는 **필터** 영역으로 끌어다 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="8e787-135">Drag **Product** to the **Filters** area, directly below the **Visual level filters** heading.</span></span>

11. <span data-ttu-id="8e787-136">**필터 형식** 영역이 표시되면 **Yammer** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8e787-136">In the **Filter Type** area that appears, select the **Yammer** check box.</span></span>

    ![선택 Yammer 선택](../../media/82e99730-0de9-42da-928a-76aab0c3e609.png)
  
12. <span data-ttu-id="8e787-138">시각화 목록 바로 아래에 있는  Power ![ BI Visualizaions의 서식 아이콘 서식 아이콘을 ](../../media/ee0602f3-3df5-4930-b862-db1d90ae4ae2.png) 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8e787-138">Just below the list of visualizations, choose the **Format** icon ![Format icon in Power BI Visualizaions](../../media/ee0602f3-3df5-4930-b862-db1d90ae4ae2.png).</span></span>

13. <span data-ttu-id="8e787-139">제목을 확장하고 **제목 텍스트** 값을 **First-Time Yammer Users by Month**(월별 Yammer 최초 사용자)로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="8e787-139">Expand Title and change the **Title Text** value to **First-Time Yammer Users by Month**.</span></span>
    
14. <span data-ttu-id="8e787-140">**텍스트 크기** 값을 **12** 로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="8e787-140">Change the **Text Size** value to **12**.</span></span>
    
15. <span data-ttu-id="8e787-141">오른쪽 아래에 있는 페이지의 이름을 편집하여 새 페이지의 제목을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="8e787-141">Change the title of the new page by editing the name of the page on bottom right.</span></span>

16.  <span data-ttu-id="8e787-142">맨 위에 있는 읽기  보기를 클릭한 다음 저장을 클릭하여 보고서를 **저장합니다.**</span><span class="sxs-lookup"><span data-stu-id="8e787-142">Save out the report by Clicking on **Reading View** on top and then **Save**.</span></span>
    
## <a name="customizing-the-reports-in-power-bi-desktop"></a><span data-ttu-id="8e787-143">Power BI Desktop에서 보고서 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="8e787-143">Customizing the reports in Power BI Desktop</span></span>

<span data-ttu-id="8e787-p102">대부분의 고객의 경우 Power BI Web에서 보고서 및 차트 시각적 개체를 수정하는 것만으로도 만족합니다. 그러나 일부 고객의 경우 자신의 비즈니스에 대한 더욱 풍부한 통찰력을 얻기 위해 이러한 데이터를 다른 데이터 원본과 연결하기를 원할 수 있습니다. 이 경우 Power BI Desktop을 사용하여 추가 보고서를 사용자 지정하고 만들 수 있습니다. [Power BI Desktop](https://go.microsoft.com/fwlink/p/?linkid=849797)은 무료로 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e787-p102">For most customers modifying the reports and chart visuals in Power BI web will be sufficient. For some however, there may be a need to join this data with other data sources to gain richer insights contextual to their own business, in which case they can customize and build additional reports using Power BI Desktop. You can download [Power BI Desktop](https://go.microsoft.com/fwlink/p/?linkid=849797) for free.</span></span> 
  
### <a name="use-the-reporting-apis"></a><span data-ttu-id="8e787-147">보고 API 사용</span><span class="sxs-lookup"><span data-stu-id="8e787-147">Use the reporting APIs</span></span>

<span data-ttu-id="8e787-148">먼저 Microsoft 365에서 ODATA 보고 API에 직접 연결하여 이러한 보고서를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e787-148">You can start by connecting directly to the ODATA reporting APIs from Microsoft 365 that power these reports.</span></span>
  
1. <span data-ttu-id="8e787-149">**데이터 가져오기** \> **기타** \> **ODATA 피드** \> **연결** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="8e787-149">Go to **get data** \> **Other** \> **ODATA Feed** \> **Connect**.</span></span>
    
2. <span data-ttu-id="8e787-150">URL 창에 "https:// <i></i> \<tenantid\> reports.office.com/pbi/v1.0/"를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="8e787-150">In the URL window enter "https://<i></i>reports.office.com/pbi/v1.0/\<tenantid\>"</span></span>
    
    <span data-ttu-id="8e787-151">**참고:** 보고 API는 미리 보기에 있으며 프로덕션으로 들어갈 때까지 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e787-151">**NOTE:** The reporting APIs are in preview and are subject to change until they go into production.</span></span> 
  
    ![OData feed URL for Power BI desktop](../../media/c0ef967e-a454-4eba-bc8e-61e113170053.png)
  
3. <span data-ttu-id="8e787-153">메시지가 표시될 때 Microsoft 365(조직 또는 학교) 관리자 자격 증명을 입력하여 Microsoft 365를 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="8e787-153">Enter your Microsoft 365 (organization or school) admin credentials to authenticate to Microsoft 365 when prompted.</span></span>
    
    <span data-ttu-id="8e787-154">Microsoft 365 채택 템플릿 앱 보고서에 액세스할 수 있는 사용자에 대한 자세한 내용은 [FAQ를](usage-analytics.md#faq) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8e787-154">See the [FAQ](usage-analytics.md#faq) for more information about who is allowed to access the Microsoft 365 Adoption template app reports.</span></span> 
    
4. <span data-ttu-id="8e787-155">연결이 승인되면 연결할 수 있는 데이터 집합을 보여주는 탐색 창이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e787-155">Once the connection is authorized, you will see the Navigator window that shows the datasets available to connect to.</span></span>
    
    <span data-ttu-id="8e787-156">모두를 선택하고 로드 **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="8e787-156">Select all and choose **Load**.</span></span>
    
    <span data-ttu-id="8e787-157">그러면 데이터가 Power BI Desktop으로 다운로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e787-157">This will download the data into your Power BI Desktop.</span></span> <span data-ttu-id="8e787-158">이 파일을 저장한 다음 필요한 보고서를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e787-158">Save this file and then you can start creating the reports you need.</span></span>
    
    ![보고 API에서 사용할 수 있는 ODATA 값](../../media/545b4d17-dbbd-4cfc-b75a-a8b27283d438.png)
  
### <a name="use-the-microsoft-365-usage-analytics-template"></a><span data-ttu-id="8e787-160">Microsoft 365 사용 현황 분석 템플릿 사용</span><span class="sxs-lookup"><span data-stu-id="8e787-160">Use the Microsoft 365 usage analytics template</span></span>

<span data-ttu-id="8e787-161">Microsoft 365 사용 현황 분석 보고서에 해당하는 Power BI 템플릿 파일을 데이터에 연결하는 시작점으로 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e787-161">You can also use the Power BI template file that corresponds to the Microsoft 365 usage analytics reports as a starting point to connect to the data.</span></span> <span data-ttu-id="8e787-162">pbit 파일을 사용하는 장점은 연결 문자열이 이미 설정되었다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="8e787-162">The advantage of using the pbit file is that it has the connection string already established.</span></span> <span data-ttu-id="8e787-163">기본 스키마가 반환하고 추가적으로 빌드하는 데이터의 맨 위에 만들어진 모든 사용자 지정 측정을 활용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e787-163">You can also take advantage of all the custom measures that are created, on top of the data that the base schema returns and build on it further.</span></span>
  
<span data-ttu-id="8e787-164">Power BI 템플릿 파일은 Microsoft 다운로드 센터에서 [다운로드할 수 있습니다.](https://download.microsoft.com/download/7/8/2/782ba8a7-8d89-4958-a315-dab04c3b620c/Microsoft%20365%20Usage%20Analytics.pbit)</span><span class="sxs-lookup"><span data-stu-id="8e787-164">You can download the Power BI template file from the [Microsoft Download Center](https://download.microsoft.com/download/7/8/2/782ba8a7-8d89-4958-a315-dab04c3b620c/Microsoft%20365%20Usage%20Analytics.pbit).</span></span> <span data-ttu-id="8e787-165">Power BI 템플릿 파일을 다운로드한 후 다음 단계에 따라 시작하세요.</span><span class="sxs-lookup"><span data-stu-id="8e787-165">After you download the Power BI template file, follow these steps to get started:</span></span>
  
1. <span data-ttu-id="8e787-166">pbit 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="8e787-166">Open the pbit file.</span></span>
    
2. <span data-ttu-id="8e787-167">대화 상자에 테넌트 ID 값을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="8e787-167">Enter your tenant id value in the dialog.</span></span>
    
    ![Enter your tenant ID to open the pbit file](../../media/071ed0bf-8b9d-49c6-81fc-fd4c6cc85bd3.png)
  
3. <span data-ttu-id="8e787-169">메시지가 표시될 때 관리자 자격 증명을 입력하여 Microsoft 365에 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="8e787-169">Enter your admin credentials to authenticate to Microsoft 365 when prompted.</span></span>
    
     <span data-ttu-id="8e787-170">Microsoft 365 사용 현황 분석 보고서에 액세스할 수 있는 사용자에 대한 자세한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8e787-170">for more information about who is allowed to access the Microsoft 365 usage analytics reports.</span></span> 
    
    <span data-ttu-id="8e787-171">권한이 부여되면 데이터가 Power BI 파일에서 새로 고쳐집니다.</span><span class="sxs-lookup"><span data-stu-id="8e787-171">Once authorized, the data will be refreshed in the Power BI file.</span></span>
    
    <span data-ttu-id="8e787-172">데이터를 로드하는 데 다소 시간이 걸릴 수 있으며 로드가 완료되면 파일을 .pbix 파일로 저장하고 계속하여 보고서를 사용자 지정하거나 추가 데이터 원본을 이 보고서로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e787-172">Data load may take some time, once complete, you can save the file as a .pbix file and continue to customize the reports or bring an additional data source into this report.</span></span>
    
4. <span data-ttu-id="8e787-p106">[Power BI 시작](/power-bi/fundamentals/desktop-getting-started) 문서를 확인하여 보고서를 만들고, Power BI 서비스에 게시하고 조직과 공유하는 방법을 알아봅니다. 사용자 지정 및 공유를 위한 이 방법에 따라 작업을 수행하기 위해 Power BI 라이선스가 추가로 필요할 수 있습니다. 자세한 내용은 Power BI [라이선싱 참고 자료](https://go.microsoft.com/fwlink/p/?linkid=849803)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8e787-p106">Follow [Getting started with Power BI](/power-bi/fundamentals/desktop-getting-started) documentation to understand how to build reports, publish them to the Power BI service, and share with your organization. Following this path for customization and sharing may require additional Power BI licenses. See Power BI [licensing guidance](https://go.microsoft.com/fwlink/p/?linkid=849803) for details.</span></span> 
