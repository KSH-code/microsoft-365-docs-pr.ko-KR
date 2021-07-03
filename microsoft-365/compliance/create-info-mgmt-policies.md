---
title: 정보 관리 정책 만들기 및 적용
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 5/16/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- OSU150
- OSU160
- MET150
ms.assetid: 8ccac9e4-3a50-49fa-a95b-d186032a6ee3
ms.collection:
- M365-security-compliance
- SPO_Content
ms.custom:
- seo-marvel-apr2020
description: 정보의 보관 기간을 제어하고 정보를 사용하는 사용자 추적을 위해 정보 관리 정책을 설정하는 방법을 학습합니다.
ms.openlocfilehash: 626549401f463ca7a28a0cdd8948f710a5128f08
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287518"
---
# <a name="create-and-apply-information-management-policies"></a><span data-ttu-id="67695-103">정보 관리 정책 만들기 및 적용</span><span class="sxs-lookup"><span data-stu-id="67695-103">Create and apply information management policies</span></span>

<span data-ttu-id="67695-104">조직에서는 정보 관리 정책을 사용하여 콘텐츠를 보존하는 기간을 제어하고, 사용자가 콘텐츠를 사용하여 하는 작업을 감사하고, 문서에 바코드 또는 레이블을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67695-104">Information management policies enable your organization to control how long to retain content, to audit what people do with content, and to add barcodes or labels to documents.</span></span> <span data-ttu-id="67695-105">정책은 법률 및 정부 규정 또는 내부 비즈니스 프로세스를 준수하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67695-105">A policy can help enforce compliance with legal and governmental regulations or internal business processes.</span></span> <span data-ttu-id="67695-106">관리자는 문서를 추적하는 방법과 문서를 보존하는 기간을 제어하는 정책을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67695-106">As an administrator, you can set up a policy to control how to track documents and how long to retain documents.</span></span>

<span data-ttu-id="67695-107">정보 관리 정책은 가장 넓은 위치부터 가장 좁은 위치까지 사이트 계층 구조의 세 가지 위치에 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67695-107">You can create an information management policy can at three different locations in the site hierarchy, from the broadest to the narrowest:</span></span>

- <span data-ttu-id="67695-108">사이트 모음 내의 여러 콘텐츠 형식에 사용할 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67695-108">Create a policy to use on multiple content types within a site collection.</span></span>
- <span data-ttu-id="67695-109">사이트 콘텐츠 형식에 대한 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67695-109">Create a policy for a site content type.</span></span>
- <span data-ttu-id="67695-110">목록 또는 라이브러리에 대한 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67695-110">Create a policy for a list or library.</span></span>

<span data-ttu-id="67695-111">자세한 내용은 정보 관리 정책 [소개를 참조하세요.](intro-to-info-mgmt-policies.md)</span><span class="sxs-lookup"><span data-stu-id="67695-111">For more information, see [Introduction to information management policies](intro-to-info-mgmt-policies.md).</span></span>

## <a name="create-a-policy-for-multiple-content-types-within-a-site-collection"></a><span data-ttu-id="67695-112">사이트 모음 내의 여러 콘텐츠 형식에 대한 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="67695-112">Create a policy for multiple content types within a site collection</span></span>
<span data-ttu-id="67695-113"><a name="__toc261001590"> </a></span><span class="sxs-lookup"><span data-stu-id="67695-113"><a name="__toc261001590"> </a></span></span>

<span data-ttu-id="67695-114">사이트 모음 내의 특정 형식의 모든 문서에 정보 정책을 적용하도록 보장하기 위해 사이트 모음 수준에서 정책을 만들고 나중에 콘텐츠 형식에 정책을 적용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="67695-114">To ensure that an information policy is applied to all documents of a certain type within a site collection, consider creating the policy at the site collection level and then later apply the policy to content types.</span></span> <span data-ttu-id="67695-115">이러한 정책을 사이트 모음 정책이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="67695-115">These are referred to as site collection policies.</span></span>

1. <span data-ttu-id="67695-116">사이트 모음 홈 페이지의 설정 \> **SharePoint** ![ 2016 설정 단추를 클릭합니다.](../media/1c22d2d8-39e0-4930-82c6-c3eee44211d3.png)</span><span class="sxs-lookup"><span data-stu-id="67695-116">On the site collection home page \> **Settings**![SharePoint 2016 Settings button on title bar.](../media/1c22d2d8-39e0-4930-82c6-c3eee44211d3.png)</span></span> <span data-ttu-id="67695-117">\> **사이트 설정**.</span><span class="sxs-lookup"><span data-stu-id="67695-117">\> **Site Settings**.</span></span>

    <span data-ttu-id="67695-118">그룹 SharePoint 사이트에서 설정 **를** **클릭한** 다음 사이트 콘텐츠 **설정.**</span><span class="sxs-lookup"><span data-stu-id="67695-118">In a SharePoint group-connected site, click **Settings**, click **Site Contents**, and then click **Site Settings**.</span></span>

2. <span data-ttu-id="67695-119">사이트 설정 페이지의 **사이트 모음 관리** 콘텐츠 형식 정책 템플릿 \> **에서 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="67695-119">On the Site Settings page, under **Site Collection Administration** \> **Content Type Policy Templates**.</span></span>

   ![사이트 정책 페이지의 콘텐츠 형식 정책 설정 링크](../media/26d3466a-23ec-443f-88f0-2aaff38e992b.png)

3. <span data-ttu-id="67695-121">정책 페이지에서 만들기 \> **를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="67695-121">On the Policies page \> **Create**.</span></span>

4. <span data-ttu-id="67695-122">정책의 이름과 설명을 입력한 다음 사용자에게 정책의 이름을 설명하는 간단한 정책 설명을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="67695-122">Enter a name and description for the policy, and then write a brief policy statement that explains to users what the policy is for.</span></span>

5. <span data-ttu-id="67695-123">정책과 연결하려는 기능을 설정하는 방법에 대한 자세한 내용은 사이트 콘텐츠 형식에 대한 정책 만들기에 대한 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="67695-123">See the next section on creating policies for a site content type to learn how to set up the features you want to associate with the policy.</span></span>

6. <span data-ttu-id="67695-124">**확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="67695-124">Choose **OK**.</span></span>

## <a name="create-a-policy-for-a-site-content-type"></a><span data-ttu-id="67695-125">사이트 콘텐츠 형식에 대한 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="67695-125">Create a policy for a site content type</span></span>
<span data-ttu-id="67695-126"><a name="__create_a_policy"> </a></span><span class="sxs-lookup"><span data-stu-id="67695-126"><a name="__create_a_policy"> </a></span></span>

<span data-ttu-id="67695-127">콘텐츠 형식에 정보 관리 정책을 추가하면 정책 기능을 여러 목록 또는 라이브러리와 쉽게 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67695-127">Adding an information management policy to a content type makes it easy to associate policy features with multiple lists or libraries.</span></span> <span data-ttu-id="67695-128">콘텐츠 형식에 기존 정보 관리 정책을 추가하거나 개별 콘텐츠 형식에 고유한 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67695-128">You can choose to add an existing information management policy to a content type or create a unique policy specific to an individual content type.</span></span>

 <span data-ttu-id="67695-129">목록과 관련이 있는 콘텐츠 형식에 정보 관리 정책을 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67695-129">You can also add an information management policy to a content type that is specific to lists.</span></span> <span data-ttu-id="67695-130">이는 콘텐츠 형식을 사용하는 해당 목록의 항목에만 정책을 적용하는 효과가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67695-130">This has the effect of applying the policy only to items in that list that are using the content type.</span></span>

1. <span data-ttu-id="67695-131">사이트 모음 홈 페이지의 설정 \> **SharePoint** ![ 2016 설정 단추를 클릭합니다.](../media/1c22d2d8-39e0-4930-82c6-c3eee44211d3.png)</span><span class="sxs-lookup"><span data-stu-id="67695-131">On the site collection home page \> **Settings**![SharePoint 2016 Settings button on title bar.](../media/1c22d2d8-39e0-4930-82c6-c3eee44211d3.png)</span></span> <span data-ttu-id="67695-132">\> **사이트 설정**.</span><span class="sxs-lookup"><span data-stu-id="67695-132">\> **Site Settings**.</span></span>

    <span data-ttu-id="67695-133">그룹 SharePoint 사이트에서 설정 **를** **클릭한** 다음 사이트 콘텐츠 **설정.**</span><span class="sxs-lookup"><span data-stu-id="67695-133">In a SharePoint group-connected site, click **Settings**, click **Site Contents**, and then click **Site Settings**.</span></span>

2. <span data-ttu-id="67695-134">사이트 설정 페이지의 웹 디자이너 갤러리 **사이트 콘텐츠** \> **형식 에서**</span><span class="sxs-lookup"><span data-stu-id="67695-134">On the Site Settings page, under **Web Designer Galleries** \> **Site content types**.</span></span>

   ![사이트 콘텐츠 형식 페이지의 사이트 설정 링크](../media/6f6fa51f-15d7-4782-b06f-a7b36e874cd3.png)

3. <span data-ttu-id="67695-136">사이트 콘텐츠 형식 설정 페이지에서 정책을 추가할 콘텐츠 형식을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="67695-136">On the Site Content Type Settings page, select the content type that you want to add a policy to.</span></span>

4. <span data-ttu-id="67695-137">사이트 콘텐츠 형식 페이지의  사이트 설정 \> **정책 설정 을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="67695-137">On the Site Content Type page, under **Settings** \> **Information management policy settings**.</span></span>

5. <span data-ttu-id="67695-138">정책 편집 페이지에서 정책의 이름과 설명을 입력한 다음 사용자에게 정책의 이름을 설명하는 간단한 설명을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="67695-138">On the Edit Policy page, enter a name and description for the policy, and then write a brief description that explains to users what the policy is for.</span></span>

6. <span data-ttu-id="67695-139">다음 섹션에서 정보 관리 정책에 추가할 개별 정책 기능을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="67695-139">In the next sections, select the individual policy features that you want to add to your information management policy.</span></span>

   ![콘텐츠 정책 유형](../media/19fcb8a3-974b-40d3-a13f-b76088d122f8.png)

7. <span data-ttu-id="67695-141">해당 정책이 적용된 문서 및 항목에 대한 보존 기간을 지정하려면 보존 사용 을 선택한 다음 보존 기간 및 항목이 만료될 때 발생할 작업을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="67695-141">To specify a retention period for documents and items that are subject to this policy, choose **Enable Retention**, and then specify the retention period and the actions that you want to occur when the items expire.</span></span>

   <span data-ttu-id="67695-142">보존 기간을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="67695-142">To specify a retention period:</span></span>

   1. <span data-ttu-id="67695-143">레코드에 **대한 보존 단계 추가를 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="67695-143">Choose **Add a retention stage for records**.</span></span>

   2. <span data-ttu-id="67695-144">문서 또는 항목이 만료되는 시기를 지정하려면 보존 기간 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="67695-144">Select a retention period option to specify when documents or items are set to expire.</span></span> <span data-ttu-id="67695-145">다음 단계 중 하나를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="67695-145">Do one of the following steps:</span></span>
      - <span data-ttu-id="67695-146">날짜 속성에 따라 만료 날짜를  설정하려면 이벤트 아래에서 항목의 날짜 속성을 기반으로 하고 문서 또는 항목 작업(예: 만든 날짜 또는 수정) 및 이 작업 이후의 시간 증분(예: 항목을 만료할 일, 월 또는 년 수)을 \> 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="67695-146">To set the expiration date based on a date property, under **Event** \> **This stage is based off a date property on the item**, and then select the document or item action (for example, Created or Modified) and the increment of time after this action (for example, the number of days, months, or years) when you want the item to expire.</span></span>
      - <span data-ttu-id="67695-147">사용자 지정 보존 수식을 사용하여 만료를 결정하기 위해 이 서버에 설치된 사용자 지정 보존 **수식으로 설정 을 선택하십시오.**</span><span class="sxs-lookup"><span data-stu-id="67695-147">To use a custom retention formula to determine expiration, choose **Set by a custom retention formula installed on this server**.</span></span>

        > [!NOTE]
        > <span data-ttu-id="67695-148">이 옵션은 관리자가 사용자 지정 수식을 설정한 경우만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67695-148">This option is only available if a custom formula has been set up by your administrator.</span></span>

   3. <span data-ttu-id="67695-149">워크플로 **시작 옵션은** 이미 워크플로가 연결된 목록, 라이브러리 또는 콘텐츠 형식에 대한 정책을 정의하는 경우 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67695-149">The **Start a workflow** option is available only if you are defining a policy for a list, library, or content type that already has a workflow associated with it.</span></span> <span data-ttu-id="67695-150">그런 다음 선택할 워크플로를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67695-150">You will then be given a choice of workflows to choose from.</span></span>

   4. <span data-ttu-id="67695-151">**되풀이 섹션에서** 이 단계의 작업 **반복... 을 선택합니다.** 작업을 다시 실행하려는 자주 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="67695-151">In the **Recurrence** section, select **Repeat this stage's action…** and enter how often you want the action to reoccur.</span></span>

      > [!NOTE]
      >  <span data-ttu-id="67695-152">이 옵션은 선택한 작업을 반복할 수 있는 경우만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67695-152">This option is only available if the action you selected can be repeated.</span></span> <span data-ttu-id="67695-153">예를 들어 영구 삭제 작업의 경우 에 대해 **재발을 설정할 수 없습니다.**</span><span class="sxs-lookup"><span data-stu-id="67695-153">For example, you cannot set recurrence for the action **Permanently Delete**.</span></span>

   5. <span data-ttu-id="67695-154">확인을 **선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="67695-154">Chose **OK**.</span></span>

8. <span data-ttu-id="67695-155">해당 정책이 적용된 문서 및 항목에 대한 감사를 사용하도록 설정하려면 감사 사용 을 선택한 다음 감사할 이벤트를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="67695-155">To enable auditing for the documents and items that are subject to this policy, choose **Enable Auditing**, and then specify the events you want to audit.</span></span>

   <span data-ttu-id="67695-156">감사를 사용하도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="67695-156">To enable auditing:</span></span>

   1. <span data-ttu-id="67695-157">감사의 정책 편집  페이지에서 감사 사용 을 선택한 다음 감사 내게 필요한 이벤트 옆에 있는 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="67695-157">On the Edit Policy page under **Auditing** select **Enable auditing**, and then select the check boxes next to the events you want to keep an audit trail for.</span></span>

   2. <span data-ttu-id="67695-158">이러한 바코드를 문서에 삽입할지 묻는 메시지를 표시하기 위해 저장하거나 인쇄하기 전에 사용자에게 바코드를 **삽입하라는 메시지를 선택해야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="67695-158">To prompt users to insert these barcodes into documents, choose **Prompt users to insert a barcode before saving or printing**.</span></span>

   3. <span data-ttu-id="67695-159">**확인을** 선택하면 정책에 감사 기능을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="67695-159">Choose **OK** to apply the auditing feature to the policy.</span></span>

   <span data-ttu-id="67695-160">감사 정책 기능을 사용하면 조직에서 문서에 대한 감사 내역을 만들고 분석하고 작업 목록, 문제점 목록, 토론 그룹 및 일정과 같은 항목을 나열할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67695-160">The Auditing Policy feature enables organizations to create and analyze audit trails for documents and to list items such as task lists, issues lists, discussion groups, and calendars.</span></span> <span data-ttu-id="67695-161">이 정책 기능은 콘텐츠를 보거나 편집 또는 삭제하는 경우와 같은 이벤트를 기록하는 감사 로그를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="67695-161">This policy feature provides an audit log that records events, such as when content is viewed, edited, or deleted.</span></span>

   <span data-ttu-id="67695-162">감사를 정보 관리 정책의 일부로 사용하도록 설정하면 관리자는 감사 데이터를 현재 사용 현황을 요약하여 Microsoft Excel 정책 사용 현황 보고서에서 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67695-162">When auditing is enabled as part of an information management policy, administrators can view the audit data in policy usage reports that are based in Microsoft Excel and that summarize current usage.</span></span> <span data-ttu-id="67695-163">관리자는 이러한 보고서를 사용하여 조직 내에서 정보가 사용되는 방식을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67695-163">Administrators can use these reports to determine how information is being used within the organization.</span></span> <span data-ttu-id="67695-164">이러한 보고서는 조직이 규정 준수를 확인하고 문서화하거나 잠재적인 문제를 조사하는 데에도 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67695-164">These reports can also help organizations to verify and document their regulatory compliance or to investigate potential concerns.</span></span>

   <span data-ttu-id="67695-165">감사 로그에는 이벤트 이름, 이벤트의 날짜 및 시간, 해당 작업을 수행한 사용자의 시스템 이름과 같은 정보가 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="67695-165">The audit log records the following information: event name, date and time of the event, and system name of the user who performed the action.</span></span>

9. <span data-ttu-id="67695-166">바코드를 정책의 일부로 사용하도록 설정하면 문서 속성에 추가되고 바코드가 적용되는 문서의 헤더 영역에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="67695-166">When barcodes are enabled as part of a policy, they are added to document properties and displayed in the header area of the document to which the barcode is applied.</span></span> <span data-ttu-id="67695-167">레이블과 마찬가지로 문서에서 바코드를 수동으로 제거할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67695-167">Like labels, barcodes can also be manually removed from a document.</span></span> <span data-ttu-id="67695-168">항목을 인쇄하거나 저장하는 경우 사용자에게 바코드를 포함하라는 메시지가 표시될지 또는 2010년 릴리스 프로그램에서 삽입 탭을 사용하여 바코드를 수동으로 삽입할지 여부를 지정할 Office 있습니다. </span><span class="sxs-lookup"><span data-stu-id="67695-168">You can specify whether users should be prompted to include the barcode when printing or saving an item or if the barcode should be inserted manually using the **Insert** tab in 2010 Office release programs.</span></span>

   <span data-ttu-id="67695-169">바코드를 사용하도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="67695-169">To enable barcodes:</span></span>

   1. <span data-ttu-id="67695-170">정책 **편집 페이지의** 바코드 **아래에서** 바코드 **사용 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="67695-170">On the **Edit Policy** page under **Barcodes**, select **Enable Barcodes**.</span></span>

   2. <span data-ttu-id="67695-171">이러한 바코드를 문서에 삽입할지 묻는 메시지를 표시하기 위해 저장하거나 인쇄하기 전에 사용자에게 바코드를 **삽입하라는 메시지를 선택해야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="67695-171">To prompt users to insert these barcodes into documents, choose **Prompt users to insert a barcode before saving or printing**.</span></span>

   3. <span data-ttu-id="67695-172">**확인을** 선택하면 바코드 기능을 정책에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="67695-172">Choose **OK** to apply the barcode feature to the policy.</span></span>

   <span data-ttu-id="67695-173">바코드 정책은 코드 39 표준 바코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="67695-173">The barcode policy generates Code 39 standard barcodes.</span></span> <span data-ttu-id="67695-174">각 바코드 이미지에는 바코드 값을 나타내는 바코드 기호 아래에 있는 텍스트가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67695-174">Each barcode image includes text below the barcode symbol that represents the barcode value.</span></span> <span data-ttu-id="67695-175">이렇게 하면 스캔 하드웨어를 사용할 수 없는 경우에도 바코드 데이터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67695-175">This enables the barcode data to be used even when scanning hardware is not available.</span></span> <span data-ttu-id="67695-176">사용자는 검색 상자에 바코드 번호를 수동으로 입력하여 사이트에서 항목을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67695-176">Users can manually type the barcode number into the search box to locate the item on a site.</span></span>  <br/> |

10. <span data-ttu-id="67695-177">해당 정책이 적용된 문서에 레이블이 있도록 설정하려면 레이블 사용 을 선택한 다음 레이블에 대해 원하는 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="67695-177">To require that documents that are subject to this policy have labels, choose **Enable Labels**, and then specify the settings that you want for the labels.</span></span>

    <span data-ttu-id="67695-178">레이블을 사용하도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="67695-178">To enable labels:</span></span>

    1. <span data-ttu-id="67695-179">사용자가 문서에 레이블을 추가해야 하려면 저장하거나 인쇄하기 전에 레이블을 삽입하라는 메시지 **표시를 선택하십시오.**</span><span class="sxs-lookup"><span data-stu-id="67695-179">To require users to add a label to a document, choose **Prompt users to insert a label before saving or printing**.</span></span>

       > [!NOTE]
       > <span data-ttu-id="67695-180">레이블을 선택적으로 지정할 수 있도록 하려면 이 확인란을 선택하지 않습니다. </span><span class="sxs-lookup"><span data-stu-id="67695-180">If you want labels to be optional, do not select this check box.</span></span>

    2. <span data-ttu-id="67695-181">레이블을 삽입한 후 변경할 수 없는 레이블을 잠그기 위해 레이블을 추가한 후 변경 **금지를 선택하십시오.**</span><span class="sxs-lookup"><span data-stu-id="67695-181">To lock a label so that it cannot be changed after it has been inserted, choose **Prevent changes to labels after they are added**.</span></span>

       <span data-ttu-id="67695-182">이 설정은 Word, Excel 또는 클라이언트 응용 프로그램 내의 항목에 레이블을 삽입한 후 레이블 텍스트가 업데이트되지 PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="67695-182">This setting prevents the label text from updating once the label has been inserted into an item within a client application such as Word, Excel, or PowerPoint.</span></span> <span data-ttu-id="67695-183">이 문서나 항목의 속성이 업데이트될 때 레이블을 업데이트하려면 이 확인란을 선택하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="67695-183">If you want the label to be updated when the properties for this document or item are updated, do not select this check box.</span></span>

    3. <span data-ttu-id="67695-184">레이블 형식 상자에 레이블을 표시할 텍스트를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="67695-184">In the Label format box, enter the text for the label as you want it to be displayed.</span></span> <span data-ttu-id="67695-185">레이블에는 최대 10개 열 참조가 포함될 수 있습니다. 각 참조는 최대 255자까지 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67695-185">Labels can contain up to 10 column references, each of which can be up to 255 characters long.</span></span> <span data-ttu-id="67695-186">레이블의 형식을 만들 수 있도록 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="67695-186">To create the format for your label, do the following steps:</span></span>
       - <span data-ttu-id="67695-187">레이블에 포함할 열의 이름을 표시하려는 순서대로 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="67695-187">Type the names of the columns that you want to include in the label in the order in which you want them to appear.</span></span> <span data-ttu-id="67695-188">정책 편집 페이지의 예제와 같이 열 이름을 중괄호()로 {} 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="67695-188">Enclose the column names in curly brackets ({}), as shown in the example on the Edit Policy page.</span></span>
       - <span data-ttu-id="67695-189">정책 편집 페이지의 예제와 같이 단어를 입력하여 괄호 외부의 열을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="67695-189">Type words to identify the columns outside the brackets, as shown in the example on the Edit Policy page.</span></span>

    4. <span data-ttu-id="67695-190">줄을 추가하기 위해 줄 **\n** 줄을 표시하려는 위치를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="67695-190">To add a line break, enter **\n** where you want the line break to appear.</span></span>

    5. <span data-ttu-id="67695-191">원하는 글꼴 크기와 스타일을 선택하고 문서 내에서 레이블을 왼쪽, 가운데 또는 오른쪽으로 배치할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="67695-191">Select the font size and style that you want, and specify whether you want the label positioned left, center, or right within the document.</span></span>

       <span data-ttu-id="67695-192">사용자의 컴퓨터에서 사용할 수 있는 글꼴 및 스타일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="67695-192">Select a font and style that are available on the users' computers.</span></span> <span data-ttu-id="67695-193">글꼴 크기에 따라 레이블에 표시할 수 있는 텍스트의 양이 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="67695-193">The size of the font affects how much text can be displayed on the label.</span></span>

    6. <span data-ttu-id="67695-194">레이블의 높이와 너비를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="67695-194">Enter the height and width of the label.</span></span> <span data-ttu-id="67695-195">레이블의 높이와 너비로는 0.625센티미터에서 50센티미터 사이의 값을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67695-195">Label height can range from .25 inches to 20 inches, and label width can range from .25 inches to 20 inches.</span></span> <span data-ttu-id="67695-196">레이블 텍스트는 항상 레이블 이미지 내에서 세로 가운데에 맞춰집니다.</span><span class="sxs-lookup"><span data-stu-id="67695-196">Label text is always vertically centered within the label image.</span></span>

    7. <span data-ttu-id="67695-197">새로 **고침을** 선택하면 레이블 콘텐츠를 미리 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67695-197">Choose **Refresh** to preview the label content.</span></span>

11. <span data-ttu-id="67695-198">**확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="67695-198">Choose **OK**.</span></span>

## <a name="create-a-policy-for-a-list-library-or-folder-location-based-retention-policy"></a><span data-ttu-id="67695-199">목록, 라이브러리 또는 폴더에 대한 정책(위치 기반 보존 정책) 만들기</span><span class="sxs-lookup"><span data-stu-id="67695-199">Create a policy for a list, library or folder (location-based retention policy)</span></span>
<span data-ttu-id="67695-200"><a name="__create_a_policy"> </a></span><span class="sxs-lookup"><span data-stu-id="67695-200"><a name="__create_a_policy"> </a></span></span>

<span data-ttu-id="67695-201">특정 목록, 라이브러리 또는 폴더에만 적용되는 보존 정책을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67695-201">You can define a retention policy that applies only to a specific list, library or folder.</span></span> <span data-ttu-id="67695-202">그러나 이러한 방식으로 보존 정책을 만드는 경우 다른 목록, 라이브러리, 폴더 또는 사이트에서 이 정책을 다시 사용할 수 없습니다. 사이트 모음 정책을 위치 기반 정책에 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="67695-202">However, if you create a retention policy this way, you cannot reuse this policy on other lists, libraries, folders or sites, and you cannot apply a site collection policy to a location based policy.</span></span>

<span data-ttu-id="67695-203">단일 위치의 모든 콘텐츠 유형에 단일 보존 정책을 적용하려는 경우 위치 기반 보존을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="67695-203">If you want to apply a single retention policy to all types of content in a single location, you will most likely want to use location-based retention.</span></span> <span data-ttu-id="67695-204">대부분의 경우 모든 콘텐츠 형식에 대해 보존 정책이 지정되어 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67695-204">In most other cases, you will want to verify that a retention policy is specified for all content types.</span></span>

<span data-ttu-id="67695-205">상속을 중단하고 하위 수준에서 새 보존 정책을 정의하지 않는 한 각 하위폴더는 상위의 보존 정책을 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="67695-205">Each subfolder inherits the retention policy of its parent, unless you choose to break inheritance and define a new retention policy at the child level.</span></span>

<span data-ttu-id="67695-206">목록 또는 라이브러리에 대한 보존이 아니라 정보 관리 정책을 정의하려면 해당 목록 또는 라이브러리와 연결된 각 개별 목록 콘텐츠 형식에 대한 정보 관리 정책을 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="67695-206">If you want to define an information management policy other than retention to a list or library, you need to define an information management policy for each individual list content type associated with that list or library.</span></span>

<span data-ttu-id="67695-207">콘텐츠 형식에서 목록 또는 라이브러리에 대한 위치 기반 정책으로 전환하기로 결정한 경우 보존 정책만 위치 기반 정책으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="67695-207">If at any point you decide to switch from content type to location-based policies for a list or library, only the retention policy will be used as the location-based policy.</span></span> <span data-ttu-id="67695-208">다른 모든 관리 정책(감사, 바코드 및 바코드)은 연결된 콘텐츠 형식에서 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="67695-208">All other management policies (audits, barcodes, and barcodes) will be inherited from the associated content types.</span></span>

<span data-ttu-id="67695-209">라이브러리 및 폴더 기반 보존 기능을 비활성화하여 사이트 모음에 대해 위치 기반 정책을 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67695-209">Location based policies can be disabled for a site collection by deactivating the Library and Folder Based Retention feature.</span></span> <span data-ttu-id="67695-210">이를 통해 사이트 모음 관리자는 목록 관리자의 위치 기반 정책에 의해 해당 콘텐츠 형식 정책이 재배치되지 않도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67695-210">This enables site collection administrators to ensure that their content type policies are not overridden by a list administrator's location based policies.</span></span>

<span data-ttu-id="67695-211">목록 또는 라이브러리에 대한 정보 관리 정책 설정을 변경하려면 최소한 목록 관리 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="67695-211">You need at least the Manage Lists permission to change the information management policy settings for a list or library.</span></span>

1. <span data-ttu-id="67695-212">정보 관리 정책을 지정할 목록 또는 라이브러리로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="67695-212">Navigate to the list or library for which you want to specify an information management policy.</span></span>

2. <span data-ttu-id="67695-213">리본 메뉴에서  라이브러리  또는 목록 탭 라이브러리 설정 \>  **또는 목록** 설정.</span><span class="sxs-lookup"><span data-stu-id="67695-213">On the ribbon, choose the **Library** or **List** tab \> **Library Settings** or **List Settings**.</span></span>

   <span data-ttu-id="67695-214">SharePoint Online에서 **설정** 클릭한 다음 목록 설정  또는 라이브러리 설정 **을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="67695-214">In SharePoint Online, click **Settings** and then click **List settings** or **Library settings**.</span></span>

3. <span data-ttu-id="67695-215">사용 **권한 및 관리 정보 관리** 정책 \> **설정에서 을(를) 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="67695-215">Under **Permissions and Management**\> **Information management policy settings**.</span></span>

   ![문서 라이브러리의 설정 페이지의 정보 관리 정책 링크](../media/9fa6d366-6aab-49e1-a05c-898ac6f536e6.png)

4. <span data-ttu-id="67695-217">정보 관리 정책 설정 목록 또는 라이브러리의 보존 원본이 라이브러리 및 폴더로 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="67695-217">On the Information Management Policy Settings page, make sure that the source of retention for the list or library is set to Library and Folders.</span></span>

   <span data-ttu-id="67695-218">콘텐츠 **형식이** 원본으로 나타나면 원본 변경을 **클릭한** 다음 라이브러리 및 폴더 **를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="67695-218">If **Content Type** appears as the source, click **Change Source**, and then click **Library and Folders**.</span></span> <span data-ttu-id="67695-219">콘텐츠 형식 보존 정책은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="67695-219">You are alerted that content type retention policies will be ignored.</span></span> <span data-ttu-id="67695-220">**확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="67695-220">Choose **OK**.</span></span>

5. <span data-ttu-id="67695-221">정책 편집 페이지의 라이브러리 **기반** 보존 일정에서 만들 정책에 대한 간단한 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="67695-221">On the Edit Policy page, under **Library Based Retention Schedule**, enter a brief description for the policy you are creating.</span></span>

6. <span data-ttu-id="67695-222">보존 **단계 추가... 를 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="67695-222">Choose **Add a retention stage…**</span></span>

   <span data-ttu-id="67695-223">레코드 아래에서 레코드에 대한 다른 보존 단계 정의 옵션을 선택하여 레코드에 대한 다른 보존 정책을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67695-223">Note that under Records, you can choose to define different retention policies for records by selecting the Define different retention stages for records option.</span></span>

7. <span data-ttu-id="67695-224">Stage properties(스테이지 속성) 대화 상자에서 보존 기간 옵션을 선택하여 문서 또는 항목이 만료되는 시기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="67695-224">In the Stage properties dialog, select a retention period option to specify when documents or items are set to expire.</span></span> <span data-ttu-id="67695-225">다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="67695-225">Do one of the following:</span></span>

   - <span data-ttu-id="67695-226">날짜 속성에 따라 만료 날짜를  설정하려면 이벤트 아래에서 항목의 날짜 속성을 기반으로 하고 문서 또는 항목 작업(예: 만든 날짜 또는 수정) 및 이 작업 이후의 시간 증분(예: 항목을 만료할 일, 월 또는 년 수)을 \> 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="67695-226">To set the expiration date based on a date property, under **Event** \> **This stage is based off a date property on the item**, and then select the document or item action (for example, Created or Modified) and the increment of time after this action (for example, the number of days, months, or years) when you want the item to expire.</span></span>

   - <span data-ttu-id="67695-227">사용자 지정 보존 수식을 사용하여 만료를 결정하기 위해 이 서버에 설치된 사용자 지정 보존 **수식으로 설정 을 선택하십시오.**</span><span class="sxs-lookup"><span data-stu-id="67695-227">To use a custom retention formula to determine expiration, choose **Set by a custom retention formula installed on this server**.</span></span>

     > [!NOTE]
     >  <span data-ttu-id="67695-228">이 옵션은 관리자가 사용자 지정 수식을 설정한 경우만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67695-228">This option is only available if a custom formula has been set up by your administrator.</span></span>

   - <span data-ttu-id="67695-229">**작업에서** 문서 또는 항목이 만료될 때 수행될 작업을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="67695-229">Under **Action**, specify what you want to happen when the document or item expires.</span></span> <span data-ttu-id="67695-230">문서 또는 항목에 대해 특정 작업이 수행될 수 있도록 설정하려면(예: 지우기) 목록에서 작업을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="67695-230">To enable a specific action to happen to the document or item (such as deletion), select an action from the list.</span></span>

8. <span data-ttu-id="67695-231">워크플로 **시작 옵션은** 이미 워크플로가 연결된 목록, 라이브러리 또는 콘텐츠 형식에 대한 정책을 정의하는 경우 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67695-231">The **Start a workflow** option is available only if you are defining a policy for a list, library, or content type that already has a workflow associated with it.</span></span> <span data-ttu-id="67695-232">그런 다음 선택할 워크플로를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67695-232">You will then be given a choice of workflows to choose from.</span></span>

9. <span data-ttu-id="67695-233">**되풀이에서** 이 단계의 작업 **반복... 을 선택 합니다.** 작업을 다시 실행하려는 자주 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="67695-233">Under **Recurrence**, choose **Repeat this stage's action…** and enter how often you want the action to reoccur.</span></span>

   > [!NOTE]
   >  <span data-ttu-id="67695-234">이 옵션은 선택한 작업을 반복할 수 있는 경우만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67695-234">This option is only available if the action you selected can be repeated.</span></span> <span data-ttu-id="67695-235">예를 들어 영구 삭제 작업의 경우 에 대해 **재발을 설정할 수 없습니다.**</span><span class="sxs-lookup"><span data-stu-id="67695-235">For example, you cannot set recurrence for the action **Permanently Delete**.</span></span>

10. <span data-ttu-id="67695-236">**확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="67695-236">Choose **OK**.</span></span>

## <a name="apply-a-site-collection-policy-to-a-content-type"></a><span data-ttu-id="67695-237">콘텐츠 형식에 사이트 모음 정책 적용</span><span class="sxs-lookup"><span data-stu-id="67695-237">Apply a site collection policy to a content type</span></span>
<span data-ttu-id="67695-238"><a name="__apply_a_site"> </a></span><span class="sxs-lookup"><span data-stu-id="67695-238"><a name="__apply_a_site"> </a></span></span>

<span data-ttu-id="67695-239">사이트에 대한 정보 관리 정책이 사이트 모음 정책으로 이미 만들어진 경우 정책 중 하나를 콘텐츠 형식에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67695-239">If information management policies have already been created for your site as site collection policies, you can apply one of the policies to a content type.</span></span> <span data-ttu-id="67695-240">이렇게 하면 동일한 상위 콘텐츠 형식을 공유하지 않는 사이트 모음의 여러 콘텐츠 형식에 동일한 정책을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67695-240">By doing this, you can apply the same policy to multiple content types in a site collection that do not share the same parent content type.</span></span>

 <span data-ttu-id="67695-241">사이트 모음의 여러 콘텐츠 형식에 정책을 적용하고 Managed Metadata Service를 구성한 경우 콘텐츠 형식 게시를 사용하여 여러 사이트 모음에 정보 관리 정책을 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67695-241">If you want to apply policies to multiple content types in a site collection, and you have a Managed Metadata Service configured, you can use Content Type Publishing to publish out information management polices to multiple site collections.</span></span> <span data-ttu-id="67695-242">자세한 내용은 사이트 모음 [전체에](#apply-a-policy-across-site-collections) 정책 적용 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="67695-242">See the section [Apply a policy across site collections](#apply-a-policy-across-site-collections) for more information.</span></span>

1. <span data-ttu-id="67695-243">정책을 적용할 콘텐츠 형식이 포함된 목록 또는 라이브러리로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="67695-243">Navigate to the list or library that contains the content type to which you want to apply a policy.</span></span>

2. <span data-ttu-id="67695-244">리본 메뉴에서  라이브러리  또는 목록 탭 라이브러리 설정 \>  **또는 목록** 설정.</span><span class="sxs-lookup"><span data-stu-id="67695-244">On the ribbon, choose the **Library** or **List** tab \> **Library Settings** or **List Settings**.</span></span>

   <span data-ttu-id="67695-245">SharePoint Online에서 **설정** 클릭한 다음 목록 설정  또는 라이브러리 설정 **을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="67695-245">In SharePoint Online, click **Settings** and then click **List settings** or **Library settings**.</span></span>

3. <span data-ttu-id="67695-246">사용 **권한 및 관리 정보 관리** 정책 \> **설정에서 을(를) 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="67695-246">Under **Permissions and Management** \> **Information management policy settings**.</span></span>

   ![문서 라이브러리의 설정 페이지의 정보 관리 정책 링크](../media/9fa6d366-6aab-49e1-a05c-898ac6f536e6.png)

4. <span data-ttu-id="67695-248">정책 원본이 콘텐츠 형식으로 설정되어  있는지 확인하고 **콘텐츠** 형식 정책에서 정책을 적용할 콘텐츠 형식을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="67695-248">Verify that the policy source is set to **Content Types**, and under **Content Type Policies** select the content type you want to apply the policy to.</span></span>

5. <span data-ttu-id="67695-249">정책 **지정에서** 사이트 모음 정책 사용 \> **을 선택한** 다음 목록에서 적용할 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="67695-249">Under **Specify the Policy** \> **Use a site collection policy**, and then select the policy that you want to apply from the list.</span></span>

   > [!NOTE]
   >  <span data-ttu-id="67695-250">사이트 **모음 정책** 사용 옵션을 사용할 수 없는 경우 사이트 모음에 대해 사이트 모음 정책이 정의되지 않은 것입니다.</span><span class="sxs-lookup"><span data-stu-id="67695-250">If the **Use a site collection policy** option is not available, no site collection policies have been defined for the site collection.</span></span>

6. <span data-ttu-id="67695-251">**확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="67695-251">Choose **OK**.</span></span>

   <span data-ttu-id="67695-252">사용하려는 목록 또는 라이브러리가 여러 콘텐츠 형식의 관리를  지원하는 경우 콘텐츠 형식에서 정보 관리 정책을 지정할 콘텐츠 형식을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67695-252">If the list or library you are working with supports the management of multiple content types, under **Content Types** you can choose the content type for which you want to specify an information management policy.</span></span> <span data-ttu-id="67695-253">그러면 위 5단계로 바로 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="67695-253">This will take you directly to Step 5 above.</span></span>

## <a name="apply-a-policy-across-site-collections"></a><span data-ttu-id="67695-254">사이트 모음에 정책 적용</span><span class="sxs-lookup"><span data-stu-id="67695-254">Apply a policy across site collections</span></span>
<span data-ttu-id="67695-255"><a name="__toc260646789"> </a></span><span class="sxs-lookup"><span data-stu-id="67695-255"><a name="__toc260646789"> </a></span></span>

<span data-ttu-id="67695-256">Managed Metadata Service 응용 프로그램을 사용하여 콘텐츠 형식 게시를 설정하여 사이트 모음에서 콘텐츠 형식을 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="67695-256">Share content types across site collections by using a Managed Metadata service application to set up content type publishing.</span></span> <span data-ttu-id="67695-257">콘텐츠 형식 게시를 사용하면 콘텐츠 형식을 중앙에서 만들어 업데이트할 수 있고 여러 하위 사이트 모음 또는 웹 응용 프로그램에 업데이트를 게시할 수 있기 때문에 사이트 전체에서 콘텐츠 및 메타데이터를 일관되게 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67695-257">Content type publishing helps you manage content and metadata consistently across your sites because content types can be created and updated centrally, and updates can be published out to multiple subscribing site collections or Web applications.</span></span>

## <a name="create-a-template-from-an-existing-policy-to-use-across-site-collections"></a><span data-ttu-id="67695-258">기존 정책에서 여러 사이트 모음에 사용할 서식 파일 만들기</span><span class="sxs-lookup"><span data-stu-id="67695-258">Create a template from an existing policy to use across site collections</span></span>
<span data-ttu-id="67695-259"><a name="__toc262125409"> </a></span><span class="sxs-lookup"><span data-stu-id="67695-259"><a name="__toc262125409"> </a></span></span>

<span data-ttu-id="67695-260">정보 관리 정책을 정의한 다음 여러 사이트 모음에서 필요한 경우 사용할 서식 파일을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67695-260">You can define an information management policy and then create a template from it to use as needed across multiple site collections.</span></span> <span data-ttu-id="67695-261">이 방법은 정보 정책을 백업하려는 경우 또는 콘텐츠 형식 게시를 사용하여 사이트 모음에 하나의 정책을 적용하는 대체 방법으로 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67695-261">This method can be used if you want to have a backup of your information policies, or it can also be used as an alternate method to using content type publishing for applying one policy across site collections.</span></span> <span data-ttu-id="67695-262">정책을 한 사이트 모음에서 내보낼 수 있는 다음 저장된 위치나 다른 사이트 모음으로 가져와서 정책의 서식 파일 또는 백업을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="67695-262">You create a template or backup of the policy by exporting the policy from one site collection and then importing it to a saved location or to another site collection.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="67695-263">정책 템플릿 집합을 만드는 방법으로 내보내기/가져오기 기능을 사용하는 경우 정책 파일에서 고유한 식별자가 .xml 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67695-263">If you using the export/import feature as a way to make a set of policy templates, keep in mind that a unique identifier exists in the policy .xml file.</span></span> <span data-ttu-id="67695-264">따라서 이 고유 식별자를 변경하지 않으면 해당 정책을 사이트로 두 번 이상 가져올 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="67695-264">Because of this, you cannot import that policy into a site more than once without changing this unique identifier.</span></span>

### <a name="export-a-policy"></a><span data-ttu-id="67695-265">정책 내보내기</span><span class="sxs-lookup"><span data-stu-id="67695-265">Export a policy</span></span>
<span data-ttu-id="67695-266"><a name="__toc260646790"> </a></span><span class="sxs-lookup"><span data-stu-id="67695-266"><a name="__toc260646790"> </a></span></span>

1. <span data-ttu-id="67695-267">사이트 모음 홈 페이지에서 사이트 설정 설정 이동된 작은 기어를 ![ 설정. ](../media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png) \> **사이트** 설정.</span><span class="sxs-lookup"><span data-stu-id="67695-267">On the site collection home page, choose **Settings**![Small Settings gear that took the place of Site Settings.](../media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png)\> **Site Settings**.</span></span>

   <span data-ttu-id="67695-268">그룹 SharePoint 사이트에서 설정 **를** **클릭한** 다음 사이트 콘텐츠 **설정.**</span><span class="sxs-lookup"><span data-stu-id="67695-268">In a SharePoint group-connected site, click **Settings**, click **Site Contents**, and then click **Site Settings**.</span></span>

2. <span data-ttu-id="67695-269">사이트 설정 페이지의 **사이트 모음 관리** 콘텐츠 형식 정책 템플릿 \> **에서 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="67695-269">On the Site Settings page, under **Site Collection Administration** \> **Content Type Policy Templates**.</span></span>

   ![사이트 정책 페이지의 콘텐츠 형식 정책 설정 링크](../media/26d3466a-23ec-443f-88f0-2aaff38e992b.png)

3. <span data-ttu-id="67695-271">내보낼 정책을 선택 합니다. 아래쪽 내보내기 \> 으로 스크롤 \> **합니다.**</span><span class="sxs-lookup"><span data-stu-id="67695-271">Choose the policy you want to export \> scroll to the bottom \> **Export**.</span></span>

4. <span data-ttu-id="67695-272">파일을 저장하거나 열지 묻는 메시지에서 저장 을 선택한 다음 파일을 저장할 위치를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="67695-272">At the prompt to save or open the file, choose **Save**, and then select a location to save the file to.</span></span> <span data-ttu-id="67695-273">정책을 가져오는 사이트 모음에서 사용할 수 있는 위치를 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="67695-273">Be sure to select a location that is available to the site collections that are importing the policy.</span></span>

5. <span data-ttu-id="67695-274">전체 다운로드 대화 상자가 표시되면 닫기 를 **선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="67695-274">When the Download Complete dialog is displayed, choose **Close**.</span></span>

### <a name="import-a-policy-to-a-different-site-collection"></a><span data-ttu-id="67695-275">다른 사이트 모음으로 정책 가져오기</span><span class="sxs-lookup"><span data-stu-id="67695-275">Import a policy to a different site collection</span></span>
<span data-ttu-id="67695-276"><a name="__toc260646791"> </a></span><span class="sxs-lookup"><span data-stu-id="67695-276"><a name="__toc260646791"> </a></span></span>

<span data-ttu-id="67695-277">정보 관리 정책을 가져오면 특정 사이트 모음 내의 사이트 또는 목록 수준에서 여러 콘텐츠 형식에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67695-277">Importing an information management policy enables you to apply it to multiple content types at the site or list level within any given site collection.</span></span> <span data-ttu-id="67695-278">이렇게 하면 두 가지 이점이 있습니다. 즉, 각 콘텐츠 형식에 정책을 다시 정의하고 적용할 필요가 없습니다. 정책을 한 곳만 변경하여 정책 수정을 보다 쉽게 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67695-278">The benefits of doing this are twofold: you don't have to re-define and apply the policy on each content type, and you can more easily manage policy modifications by making changes to the policy in just one place.</span></span>

1. <span data-ttu-id="67695-279">정책을 적용할 사이트 모음 홈 페이지에서 Site 설정 설정 이동한 작은 기어를 ![ 선택합니다. 설정. ](../media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png) \> **사이트** 설정.</span><span class="sxs-lookup"><span data-stu-id="67695-279">On the home page of the site collection to which you want to apply the policy, choose **Settings**![Small Settings gear that took the place of Site Settings.](../media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png)\> **Site Settings**.</span></span>

   <span data-ttu-id="67695-280">그룹 SharePoint 사이트에서 설정 **를** **클릭한** 다음 사이트 콘텐츠 **설정.**</span><span class="sxs-lookup"><span data-stu-id="67695-280">In a SharePoint group-connected site, click **Settings**, click **Site Contents**, and then click **Site Settings**.</span></span>

2. <span data-ttu-id="67695-281">사이트 설정 페이지의 **사이트 모음 관리** 콘텐츠 형식 정책 템플릿 \> **에서 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="67695-281">On the Site Settings page, under **Site Collection Administration** \> **Content Type Policy Templates**.</span></span>

3. <span data-ttu-id="67695-282">정책 페이지에서 \> **찾아보기를** \> **가져와서** 정책의 XML 파일을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67695-282">On the Policies page \> **Import** \> **Browse** to find the XML file for the policy.</span></span>

4. <span data-ttu-id="67695-283">정책이 저장된 XML 파일을 열기 를 \> **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="67695-283">Select the XML file in which the policy has been saved \> **Open**.</span></span>

5. <span data-ttu-id="67695-284">사이트 모음 정책 가져오기 페이지에서 가져오기에서 사이트 모음에 정책을 \>  추가합니다.</span><span class="sxs-lookup"><span data-stu-id="67695-284">On the Import a Site Collection Policy page \> **Import** to add the policy to the site collection.</span></span>

<span data-ttu-id="67695-285">이제 가져온 정책을 사이트 또는 목록 수준에서 하나 또는 여러 콘텐츠 형식에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67695-285">Your imported policy can now be applied to one or many content types at the site or list level.</span></span>

<span data-ttu-id="67695-286">조직에서는 정보 관리 정책을 사용하여 콘텐츠를 보존하는 기간을 제어하고, 사용자가 콘텐츠를 사용하여 하는 작업을 감사하고, 문서에 바코드 또는 레이블을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67695-286">Information management policies enable your organization to control how long to retain content, to audit what people do with content, and to add barcodes or labels to documents.</span></span> <span data-ttu-id="67695-287">정책은 법률 및 정부 규정 또는 내부 비즈니스 프로세스를 준수하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67695-287">A policy can help enforce compliance with legal and governmental regulations or internal business processes.</span></span> <span data-ttu-id="67695-288">관리자는 문서를 추적하는 방법과 문서를 보존하는 기간을 제어하는 정책을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67695-288">As an administrator, you can set up a policy to control how to track documents and how long to retain documents.</span></span>

<span data-ttu-id="67695-289">정보 관리 정책은 가장 넓은 위치부터 가장 좁은 위치까지 사이트 계층 구조의 세 가지 위치에 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67695-289">You can create an information management policy can at three different locations in the site hierarchy, from the broadest to the narrowest:</span></span>

- <span data-ttu-id="67695-290">사이트 모음 내의 여러 콘텐츠 형식에 사용할 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67695-290">Create a policy to use on multiple content types within a site collection.</span></span>
- <span data-ttu-id="67695-291">사이트 콘텐츠 형식에 대한 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67695-291">Create a policy for a site content type.</span></span>
- <span data-ttu-id="67695-292">목록 또는 라이브러리에 대한 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67695-292">Create a policy for a list or library.</span></span>

<span data-ttu-id="67695-293">자세한 내용은 정보 관리 정책 [소개를 참조하세요.](intro-to-info-mgmt-policies.md)</span><span class="sxs-lookup"><span data-stu-id="67695-293">For more information, see [Introduction to information management policies](intro-to-info-mgmt-policies.md).</span></span>
