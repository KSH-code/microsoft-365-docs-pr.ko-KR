---
title: '출시 예정: SharePoint Microsoft Viva Learning용 학습 콘텐츠 원본으로 구성(미리 보기)'
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 04/30/2021
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: None
description: Microsoft Viva Learning(미리 보기)SharePoint 학습 콘텐츠 원본으로 구성하는 방법을 알아보겠습니다.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: da75ec0573519ed73507994afeac995c0461de0c
ms.sourcegitcommit: d3f8c69519c593b1580cfa7187ce085a99b8a846
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/30/2021
ms.locfileid: "52101091"
---
# <a name="coming-soon-configure-sharepoint-as-a-learning-content-source-for-microsoft-viva-learning-preview"></a><span data-ttu-id="43c1f-103">출시 예정: SharePoint Microsoft Viva Learning용 학습 콘텐츠 원본으로 구성(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="43c1f-103">Coming soon: Configure SharePoint as a learning content source for Microsoft Viva Learning (Preview)</span></span>

> [!NOTE]
> <span data-ttu-id="43c1f-104">이 문서의 정보는 상업적으로 출시되기 전에 상당수 수정될 수 있는 미리 보기 제품과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43c1f-104">The information in this article relates to a preview product that may be substantially modified before it's commercially released.</span></span> 

<span data-ttu-id="43c1f-105">조직에서 SharePoint 콘텐츠를 Viva Learning(미리 보기)에서 사용할 수 있도록 학습 콘텐츠 원본으로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43c1f-105">You can configure SharePoint as a learning content source to make your organization's own content available in Viva Learning (Preview).</span></span>

## <a name="overview"></a><span data-ttu-id="43c1f-106">개요</span><span class="sxs-lookup"><span data-stu-id="43c1f-106">Overview</span></span>

<span data-ttu-id="43c1f-107">지식 관리자(또는 전역 관리자)는 학습 서비스가 구조화된 중앙 집중식 목록 형태로 빈 중앙 집중식 위치인 학습 앱 콘텐츠 저장소를 만들 수 있는 사이트 URL을 SharePoint 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43c1f-107">The knowledge admin (or global administrator) provides a site URL to where the Learning Service can create an empty centralized location—the Learning App Content Repository—in the form of a structured SharePoint list.</span></span> <span data-ttu-id="43c1f-108">이 목록은 조직에서 학습 콘텐츠가 포함된 폴더에 대한 교차 회사 SharePoint 링크를 포함하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43c1f-108">This list can be used by your organization to house links to cross-company SharePoint folders that contain learning content.</span></span> <span data-ttu-id="43c1f-109">관리자는 폴더의 URL 목록을 수집하고 큐레이터해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="43c1f-109">Admins are responsible for collecting and curating a list of URLs for folders.</span></span> <span data-ttu-id="43c1f-110">이러한 폴더에는 Viva Learning(미리 보기)에서 사용할 수 있는 콘텐츠만 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="43c1f-110">These folders should only include content that can be made available in Viva Learning (Preview).</span></span>

<span data-ttu-id="43c1f-111">Viva Learning(미리 보기)은 다음과 같은 문서 유형을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="43c1f-111">Viva Learning (Preview) supports the following document types:</span></span>

- <span data-ttu-id="43c1f-112">Word, PowerPoint, Excel, PDF</span><span class="sxs-lookup"><span data-stu-id="43c1f-112">Word, PowerPoint, Excel, PDF</span></span>
- <span data-ttu-id="43c1f-113">오디오(.m4a)</span><span class="sxs-lookup"><span data-stu-id="43c1f-113">Audio (.m4a)</span></span>
- <span data-ttu-id="43c1f-114">비디오(.mov, .mp4, .avi)</span><span class="sxs-lookup"><span data-stu-id="43c1f-114">Video (.mov, .mp4, .avi)</span></span>

<span data-ttu-id="43c1f-115">자세한 내용은 온라인 [설명서를 SharePoint 참조하세요.](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits?redirectSourcePath=%252farticle%252fSharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498)</span><span class="sxs-lookup"><span data-stu-id="43c1f-115">For more information, see the [SharePoint Online documentation](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits?redirectSourcePath=%252farticle%252fSharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).</span></span> 

## <a name="permissions"></a><span data-ttu-id="43c1f-116">사용 권한</span><span class="sxs-lookup"><span data-stu-id="43c1f-116">Permissions</span></span>

<span data-ttu-id="43c1f-117">문서 라이브러리 폴더 URL은 조직의 모든 SharePoint 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43c1f-117">Document library folder URLs can be collected from any SharePoint site in the organization.</span></span> <span data-ttu-id="43c1f-118">Viva Learning(미리 보기)은 모든 기존 콘텐츠 사용 권한을 따르게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="43c1f-118">Viva Learning (Preview) follows all existing content permissions.</span></span> <span data-ttu-id="43c1f-119">따라서 사용자에게 액세스 권한이 있는 콘텐츠만 Viva Learning(미리 보기) 내에서 검색 및 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43c1f-119">Therefore, only content for which a user has permission to access is searchable and visable within Viva Learning (Preview).</span></span> <span data-ttu-id="43c1f-120">이러한 폴더 내의 모든 콘텐츠는 검색할 수 있지만 개별 직원이 사용 권한을 가지는 콘텐츠만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43c1f-120">Any content within these folders will be searchable, but only content to which the individual employee has permissions can be used.</span></span>

<span data-ttu-id="43c1f-121">조직 리포지토리에서 콘텐츠 삭제는 현재 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="43c1f-121">Content deletion from your organization’s repository is not currently supported.</span></span>

<span data-ttu-id="43c1f-122">의도하지 않은 표면이 있는 콘텐츠를 제거하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="43c1f-122">To remove unintentionally surfaced content, follow these steps:</span></span>

1.  <span data-ttu-id="43c1f-123">문서 라이브러리에 대한 액세스를 제한하려면 작업 표시 옵션을 선택한 다음 액세스 **관리를 선택합니다.** </span><span class="sxs-lookup"><span data-stu-id="43c1f-123">To restrict access to the document library, select the **Show actions** option, and then select **Manage access**.</span></span>
     
     ![Access Highligted를 SharePoint 작업 표시 옵션을 표시하는 페이지의 문서 라이브러리 페이지입니다.](../media/learning/learning-sharepoint-permissions2.png)

2.  <span data-ttu-id="43c1f-125">문서 라이브러리 내에서 원본 문서를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="43c1f-125">Delete the original document within the document library.</span></span>

<span data-ttu-id="43c1f-126">자세한 내용은 최신 환경의 공유 및 SharePoint [참조하세요.](/sharepoint/modern-experience-sharing-permissions)</span><span class="sxs-lookup"><span data-stu-id="43c1f-126">For more information, see [Sharing and permissions in the SharePoint modern experience](/sharepoint/modern-experience-sharing-permissions).</span></span> 

## <a name="learning-service"></a><span data-ttu-id="43c1f-127">학습 서비스</span><span class="sxs-lookup"><span data-stu-id="43c1f-127">Learning Service</span></span>

<span data-ttu-id="43c1f-128">학습 서비스는 제공된 폴더 URL을 사용하여 해당 폴더에 저장된 모든 콘텐츠의 메타데이터를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="43c1f-128">The Learning Service uses the provided folder URLs to get metadata from all content stored in those folders.</span></span> <span data-ttu-id="43c1f-129">직원이 중앙 저장소에 폴더 URL을 제공한 후 24시간 이내에 Viva Learning(미리 보기) 내에서 조직의 콘텐츠를 검색하고 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43c1f-129">Within 24 hours of supplying the folder URL in the centralized repository, employees can search for and use your organization’s content within Viva Learning (Preview).</span></span> <span data-ttu-id="43c1f-130">업데이트된 메타데이터 및 사용 권한을 포함하여 콘텐츠에 대한 모든 변경 내용은 24시간 이내에 학습 서비스에도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="43c1f-130">All changes to content, including updated metadata and permissions, will also be applied in the Learning Service within 24 hours.</span></span>

## <a name="configure-sharepoint-as-a-source"></a><span data-ttu-id="43c1f-131">원본 SharePoint 구성</span><span class="sxs-lookup"><span data-stu-id="43c1f-131">Configure SharePoint as a source</span></span>

<span data-ttu-id="43c1f-132">이러한 작업을 수행하려면 Microsoft 365 관리자, SharePoint 관리자 또는 지식 관리자 중 한 명으로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="43c1f-132">You must be a Microsoft 365 global administrator, SharePoint administrator, or knowledge admin to perform these tasks.</span></span>

<span data-ttu-id="43c1f-133">Viva SharePoint(미리 보기)에서 학습 콘텐츠 원본으로 구성하기 위해 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="43c1f-133">To configure SharePoint as a learning content sources in for Viva Learning (Preview), follow these steps:</span></span>

1.  <span data-ttu-id="43c1f-134">Microsoft 365 센터의 왼쪽 탐색에서 설정   >  **설정으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="43c1f-134">In the left navigation of the Microsoft 365 admin center, go to **Settings** > **Org settings**.</span></span>
 
2.  <span data-ttu-id="43c1f-135">Org **설정 페이지의** 서비스 **탭에서** 학습 앱(미리 **보기)을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="43c1f-135">On the **Org settings** page, on the **Services** tab, select **Learning app (Preview)**.</span></span>

     ![설정 Viva Learning이 Microsoft 365 관리 센터의 페이지입니다.](../media/learning/learning-sharepoint-configure1.png)

3.  <span data-ttu-id="43c1f-137">학습 **앱(미리 보기)** 패널의 SharePoint Viva Learning에서 중앙 리포지토리를 만들 SharePoint 사이트 URL을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="43c1f-137">On the **Learning app (Preview)** panel, under SharePoint, provides the site URL to the SharePoint site where you want Viva Learning to create a centralized repository.</span></span>

     ![선택한 Microsoft 365 센터의 학습 SharePoint.](../media/learning/learning-sharepoint-configure2.png)

4.  <span data-ttu-id="43c1f-139">SharePoint 목록은 제공된 사이트 내에서 SharePoint 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="43c1f-139">A SharePoint list is created automatically within the provided SharePoint site.</span></span>

     ![사이트 SharePoint 새로 만든 SharePoint 목록입니다.](../media/learning/learning-sharepoint-configure3.png)

     <span data-ttu-id="43c1f-141">SharePoint 탐색 창에서 사이트 콘텐츠 학습 앱 콘텐츠 리포지토리  >  **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="43c1f-141">In the left navigation of the SharePoint site, select **Site contents** > **Learning App Content Repository**.</span></span> 

     ![SharePoint 탐색 및 학습 앱 콘텐츠 리포지토리 섹션을 보여주는 목록입니다.](../media/learning/learning-sharepoint-configure4.png) 

5. <span data-ttu-id="43c1f-143">학습 앱 **콘텐츠** 리포지토리 페이지에서 학습 콘텐츠 폴더에 SharePoint 목록으로 채우십시오.</span><span class="sxs-lookup"><span data-stu-id="43c1f-143">On the **Learning App Content Repository** page, populate the SharePoint list with URLs to the learning content folders.</span></span>

   1. <span data-ttu-id="43c1f-144">새로 **보기를** 선택하여 새 항목 **패널을** 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43c1f-144">Select **New** to view the **New item** panel.</span></span> 

       ![새 옵션을 보여 SharePoint 콘텐츠 저장소 페이지의 학습](../media/learning/learning-sharepoint-configure5.png)
 
   2. <span data-ttu-id="43c1f-146">새 **항목 패널의** **제목** 필드에 선택한 디렉터리 이름을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="43c1f-146">On the **New item** panel, in the **Title** field, add a directory name of your choice.</span></span> <span data-ttu-id="43c1f-147">폴더 **URL 필드에서** 학습 콘텐츠 폴더에 URL을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="43c1f-147">In the **Folder URL** field, add the URL to the learning content folder.</span></span> <span data-ttu-id="43c1f-148">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="43c1f-148">Select **Save**.</span></span>

       ![제목 및 폴더 URL SharePoint 표시하는 새 항목 패널](../media/learning/learning-sharepoint-configure6.png)

   3. <span data-ttu-id="43c1f-150">학습 **앱 콘텐츠 리포지토리** 페이지는 새 학습 콘텐츠로 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="43c1f-150">The **Learning App Content Repository** page is updated with the new learning content.</span></span>

       ![업데이트된 정보를 표시하는 SharePoint 리포지토리 학습 페이지](../media/learning/learning-sharepoint-configure7.png)

> [!NOTE]
> <span data-ttu-id="43c1f-152">학습 앱 콘텐츠 리포지토리에 대한 광범위한 액세스를 허용하기 위해 사용자가 액세스를 요청하고 궁극적으로 목록을 채우는 데 도움이 되는 Viva Learning(미리 보기) 인터페이스에서 목록에 대한 링크를 곧 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43c1f-152">To allow for broader access to the Learning App Content Repository, a link to the list soon will be available in the Viva Learning (Preview) interface where users can request access and ultimately help populate the list.</span></span> <span data-ttu-id="43c1f-153">사이트 소유자 및 전역 관리자는 목록에 대한 액세스 권한을 부여해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="43c1f-153">Site owners and global administrators will be required to grant access to the list.</span></span> <span data-ttu-id="43c1f-154">Access는 목록에만 해당하며 목록이 저장된 사이트에는 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="43c1f-154">Access is specific to the list only and does not apply to the site where the list is stored.</span></span> <span data-ttu-id="43c1f-155">자세한 내용은 이 문서 의 부분에 있는 자체 조직의 [콘텐츠](#provide-your-own-organizations-content) 제공을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="43c1f-155">For more information, see [Provide your own organization's content](#provide-your-own-organizations-content) later in this article.</span></span>

### <a name="folder-url-document-library-curation"></a><span data-ttu-id="43c1f-156">폴더 URL 문서 라이브러리 큐레이터</span><span class="sxs-lookup"><span data-stu-id="43c1f-156">Folder URL document library curation</span></span>

<span data-ttu-id="43c1f-157">Microsoft Graph API에 의해 수정된 날짜, 문서 이름, 콘텐츠 형식 및 조직 이름과 같은 기본 메타데이터가 Viva Learning(미리 보기)에 자동으로 Graph.</span><span class="sxs-lookup"><span data-stu-id="43c1f-157">Default metadata (such as modified date, created by, document name, content type, and organization name) is automatically pulled into Viva Learning (Preview) by the Microsoft Graph API.</span></span>
 
<span data-ttu-id="43c1f-158">콘텐츠의 전체 검색 및 검색 관련성을 개선하기 위해 설명 열을 **추가하는 것이** 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="43c1f-158">To improve overall discovery and search relevance of the content, we recommend adding a **Description** column.</span></span>

<span data-ttu-id="43c1f-159">문서 라이브러리 **페이지에 설명** 열을 추가하기 위해 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="43c1f-159">To add a **Description** column to the document library page, follow these steps:</span></span>

1.  <span data-ttu-id="43c1f-160">문서 **페이지에서** 열 **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="43c1f-160">On the **Documents** page, select **Add column**.</span></span>

2. <span data-ttu-id="43c1f-161">작업 **표시 옵션을** 선택한 다음 한 줄 **텍스트 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="43c1f-161">Select the **Show actions** option, and then select **Single line of text**.</span></span>

     ![텍스트 한 줄이 강조 SharePoint 작업 표시 옵션을 표시하는 페이지의 문서 페이지](../media/learning/learning-sharepoint-curation1.png)

3. <span data-ttu-id="43c1f-163">열 **만들기 패널의** 이름 **필드에** 열에 대한 설명적인 이름을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="43c1f-163">On the **Create a column** panel, in the **Name** field, add a descriptive name for the column.</span></span> <span data-ttu-id="43c1f-164">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="43c1f-164">Select **Save**.</span></span>

     ![이름 및 기타 필드를 SharePoint 열 패널을 만들 수 있습니다.](../media/learning/learning-sharepoint-curation2.png)
 
4. <span data-ttu-id="43c1f-166">문서 **페이지의** 설명 열에서  각 항목에 대한 사용자 지정 설명을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="43c1f-166">On the **Documents** page, in the **Description** column, add custom descriptions for each item.</span></span> <span data-ttu-id="43c1f-167">설명을 제공하지 못하면 Viva Learning(미리 보기)에서 콘텐츠가 사용자 지정 라이브러리의 콘텐츠로 강조 표시된 기본 SharePoint 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="43c1f-167">If no description is supplied, Viva Learning (Preview) will provide a default message that highlights the content as being from your own SharePoint library.</span></span> 

     ![설명 열의 SharePoint 설명을 표시하는 문서 페이지입니다.](../media/learning/learning-sharepoint-curation3.png)
 
### <a name="provide-your-own-organizations-content"></a><span data-ttu-id="43c1f-169">자체 조직의 콘텐츠 제공</span><span class="sxs-lookup"><span data-stu-id="43c1f-169">Provide your own organization's content</span></span>

<span data-ttu-id="43c1f-170">지식 관리자는 조직의 학습 앱 콘텐츠 저장소에 액세스할 수 SharePoint 조직 간 문서 라이브러리에 대한 참조를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43c1f-170">Knowledge admins can access their organization’s Learning App Content Repository in SharePoint, where they can provide references to cross-organization document libraries.</span></span> <span data-ttu-id="43c1f-171">이러한 라이브러리 내의 콘텐츠는 Viva Learning(미리 보기)에서 학습 콘텐츠로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="43c1f-171">Content within these libraries will be then surfaced as learning content in Viva Learning (Preview).</span></span>

1. <span data-ttu-id="43c1f-172">Viva Learning(미리 보기)에서 **추가** 옵션(**...**)을 선택한 다음 를 **설정.**</span><span class="sxs-lookup"><span data-stu-id="43c1f-172">In Viva Learning (Preview), select **More options** (**...**), and then select **Settings**.</span></span>

     ![SharePoint 및 추가 옵션 옵션을 보여 설정 페이지입니다.](../media/learning/learning-sharepoint-library-1.png)
     
2. <span data-ttu-id="43c1f-174">다음 **설정** **에서 사용 권한을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="43c1f-174">Under **Settings**, select **Permissions**.</span></span>

     ![설정 옵션 페이지의 SharePoint 및 액세스 확인 옵션이 표시됩니다.](../media/learning/learning-sharepoint-library-2.png)

3. <span data-ttu-id="43c1f-176">액세스 **확인을** 선택하여 조직의 중앙 집중식 라이브러리에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="43c1f-176">Select **Check access** to connect to your organization’s centralized library.</span></span>
     
