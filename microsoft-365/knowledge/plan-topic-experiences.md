---
title: Microsoft Viva 항목 계획
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: Microsoft Viva 항목 계획 방법 학습
ms.openlocfilehash: 19baf8bdcfdd1fe38d64e3c2f259ace1ceab5a4b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925979"
---
# <a name="plan-for-microsoft-viva-topics"></a><span data-ttu-id="a60e9-103">Microsoft Viva 항목 계획</span><span class="sxs-lookup"><span data-stu-id="a60e9-103">Plan for Microsoft Viva Topics</span></span>

<span data-ttu-id="a60e9-104">조직에서 주제가 어떻게 경험하는지 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a60e9-104">You're in control of how topics are experienced in your organization.</span></span> <span data-ttu-id="a60e9-105">항목에 대한 계획 결정은 사용자에게 고품질 항목을 표시하고 지식을 소비하고 기여할 수 있는 올바른 권한을 가지게 합니다.</span><span class="sxs-lookup"><span data-stu-id="a60e9-105">Your planning decisions for Topics ensures that high quality topics are shown to your users and they have the right permissions to consume and contribute knowledge.</span></span>

<span data-ttu-id="a60e9-106">이 문서에서는 이러한 계획 결정에 대해 살펴보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a60e9-106">In this article we'll examine these planning decisions:</span></span>

- <span data-ttu-id="a60e9-107">항목에 대해 크롤링할 SharePoint 사이트</span><span class="sxs-lookup"><span data-stu-id="a60e9-107">Which SharePoint sites you want to crawl for topics</span></span>
- <span data-ttu-id="a60e9-108">항목 환경에서 제외하려는 항목(있는 경우)</span><span class="sxs-lookup"><span data-stu-id="a60e9-108">Which topics, if any, you want to exclude from topic experiences</span></span>
- <span data-ttu-id="a60e9-109">항목을 표시하려는 사용자</span><span class="sxs-lookup"><span data-stu-id="a60e9-109">Which users you want to make topics visible to</span></span>
- <span data-ttu-id="a60e9-110">항목 센터에서 항목을 관리할 수 있는 권한을 부여하려는 사용자</span><span class="sxs-lookup"><span data-stu-id="a60e9-110">Which users you want to give permissions to manage topics in the topic center</span></span>
- <span data-ttu-id="a60e9-111">항목 센터에서 항목을 만들거나 편집할 수 있는 권한을 부여하려는 사용자</span><span class="sxs-lookup"><span data-stu-id="a60e9-111">Which users you want to give permissions to create or edit topics in the topic center</span></span>
- <span data-ttu-id="a60e9-112">주제 센터에 제공하려는 이름</span><span class="sxs-lookup"><span data-stu-id="a60e9-112">What name you want to give your topic center</span></span>

<span data-ttu-id="a60e9-113">데이터의 보안 및 개인 정보는 준수하며, 항목 환경은 사용자에게 권한이 없는 파일에 대한 추가 액세스 권한을 부여하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a60e9-113">Security and privacy of your data is respected, and topic experiences does not grant users additional access to files they don’t have rights to.</span></span> <span data-ttu-id="a60e9-114">또한 계획 프로세스의 일부로 [Microsoft Viva 항목](topic-experiences-security-privacy.md) 보안 및 개인 정보 보호를 읽어보는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a60e9-114">We recommend you also read [Microsoft Viva Topics security and privacy](topic-experiences-security-privacy.md) as part of your planning process.</span></span>

## <a name="requirements"></a><span data-ttu-id="a60e9-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a60e9-115">Requirements</span></span>

<span data-ttu-id="a60e9-116">Microsoft 365 관리 센터에 액세스하고 항목을 설정하려면 [Viva](https://www.microsoft.com/microsoft-viva/topics) 항목을 구독하고 전역 관리자 또는 SharePoint 관리자 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a60e9-116">You must be [subscribed to Viva Topics](https://www.microsoft.com/microsoft-viva/topics) and be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up Topics.</span></span>

<span data-ttu-id="a60e9-117">항목을 사용하려면 모든 사용자에게 항목 환경 **라이선스가** 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a60e9-117">All users who are going to use Topics require a **Topic Experiences** license.</span></span> <span data-ttu-id="a60e9-118">라이선스 할당은 Microsoft [Viva 항목 설정에서 다를 수 있습니다.](set-up-topic-experiences.md)</span><span class="sxs-lookup"><span data-stu-id="a60e9-118">Assigning licenses is covered in [Set up Microsoft Viva Topics](set-up-topic-experiences.md).</span></span>

## <a name="topic-discovery"></a><span data-ttu-id="a60e9-119">항목 검색</span><span class="sxs-lookup"><span data-stu-id="a60e9-119">Topic discovery</span></span>

<span data-ttu-id="a60e9-120">항목 검색 설정은 항목의 원본으로 사용되는 SharePoint 사이트를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a60e9-120">The topic discovery settings specify which SharePoint sites are used as sources for topics.</span></span> <span data-ttu-id="a60e9-121">모든 SharePoint 사이트, 특정 사이트 목록 또는 사이트를 포함하지하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a60e9-121">You can choose to include all SharePoint sites, a specific list of sites, or no sites.</span></span> <span data-ttu-id="a60e9-122">항목 환경이 사용자에게 많은 좋은 항목을 검색할 수 있도록 모든 사이트를 선택하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a60e9-122">We recommend that you choose all sites so that topic experiences can discover a large number of good topics for your users.</span></span>

<span data-ttu-id="a60e9-123">항목을 설정할 때 다음 옵션 중 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a60e9-123">When you set up Topics, you can choose from the following options:</span></span>

- <span data-ttu-id="a60e9-124">**모든 사이트:** 조직의 모든 SharePoint 사이트</span><span class="sxs-lookup"><span data-stu-id="a60e9-124">**All sites**: All SharePoint sites in your organization.</span></span> <span data-ttu-id="a60e9-125">여기에는 현재 및 향후 사이트가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a60e9-125">This includes current and future sites.</span></span>
- <span data-ttu-id="a60e9-126">**선택한 사이트를 제외한** 모든 사이트: 지정한 사이트를 제외한 모든 사이트</span><span class="sxs-lookup"><span data-stu-id="a60e9-126">**All, except selected sites**: All sites except for the ones you specify.</span></span> <span data-ttu-id="a60e9-127">향후 만들어진 사이트는 항목 검색을 위한 원본으로 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a60e9-127">Sites created in future will be included as sources for topic discovery.</span></span> 
- <span data-ttu-id="a60e9-128">**선택한 사이트만:** 지정한 사이트만</span><span class="sxs-lookup"><span data-stu-id="a60e9-128">**Only selected sites**: Only the sites that you specify.</span></span> <span data-ttu-id="a60e9-129">향후 만들어진 사이트는 항목 검색을 위한 원본으로 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a60e9-129">Sites created in the future will not be included as sources for topic discovery.</span></span>
- <span data-ttu-id="a60e9-130">**사이트 없음:** SharePoint 사이트를 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a60e9-130">**No sites**: Do not include any SharePoint sites.</span></span>

<span data-ttu-id="a60e9-131">선택한 사이트 또는  선택한 사이트만 제외한 모두를 선택하는 경우 사이트 목록이 있는 .csv 파일을 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a60e9-131">If you choose either **All, except selected sites** or **Only selected sites**, you can upload a .csv file with a list of sites.</span></span> <span data-ttu-id="a60e9-132">이러한 옵션은 파일럿을 수행 중일 때 시작할 제한된 수의 사이트를 포함하려는 경우 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="a60e9-132">These options are useful if you're doing a pilot and you want to include a limited number of sites to start.</span></span>

<span data-ttu-id="a60e9-133">아래 .csv 템플릿을 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a60e9-133">You can copy the .csv template below:</span></span>

``` csv
Site name,URL
```

<span data-ttu-id="a60e9-134">항목을 자동으로 **만들거나** 업데이트할 수 없는 사이트는 선택하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a60e9-134">We don't recommend choosing **No sites** because it prevents topics from being automatically created or updated.</span></span> <span data-ttu-id="a60e9-135">그러나 항목을 설정한 다음 나중에 사이트를 추가하려는 경우 이 옵션을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a60e9-135">However, you can choose this option if you want to set up Topics and then add sites later.</span></span>

<span data-ttu-id="a60e9-136">조직에서 필요한 경우 사용자 또는 기술 관리자가 항목 검색에서 개별 사이트를 제거할 것을 요청하는 프로세스를 만드는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a60e9-136">We recommend you create a process for users or knowledge managers to request individual sites be removed from topic discovery if needed in your organization.</span></span>

### <a name="multi-geo"></a><span data-ttu-id="a60e9-137">Multi-geo</span><span class="sxs-lookup"><span data-stu-id="a60e9-137">Multi-geo</span></span>

<span data-ttu-id="a60e9-138">조직에서 [Microsoft 365 Multi-Geo를](/microsoft-365/enterprise/microsoft-365-multi-geo)배포한 경우 항목 센터가 중앙 위치에 프로비전됩니다. 이 항목 센터는 중앙 위치에 있는 SharePoint 사이트만 항목의 원본으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a60e9-138">If your organization has deployed [Microsoft 365 Multi-Geo](/microsoft-365/enterprise/microsoft-365-multi-geo), the topic center is provisioned in the central location and only SharePoint sites in the central location are available to use as sources for topics.</span></span> <span data-ttu-id="a60e9-139">(모든 **사이트를** 선택하면 Viva 항목은 중앙 위치의 모든 사이트를 사용하게 됩니다.)</span><span class="sxs-lookup"><span data-stu-id="a60e9-139">(If you select **All sites**, Viva Topics will use all site in the central location.)</span></span>

<span data-ttu-id="a60e9-140">콘텐츠의 모든 처리 및 저장은 중앙 위치에서 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="a60e9-140">All processing and storage of content is done in the central location.</span></span>

## <a name="user-permissions"></a><span data-ttu-id="a60e9-141">사용자 권한</span><span class="sxs-lookup"><span data-stu-id="a60e9-141">User permissions</span></span>

<span data-ttu-id="a60e9-142">사용자가 지정하는 사용자 권한에 따라 조직의 사용자가 항목과 상호 작용하는 사용자와 사용자가 할 수 있는 작업을 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a60e9-142">The user permissions that you specify determine which people in your organization interact with topics and what they can do.</span></span>

<span data-ttu-id="a60e9-143">*항목 관리*</span><span class="sxs-lookup"><span data-stu-id="a60e9-143">*Manage topics*</span></span>

<span data-ttu-id="a60e9-144">지식 관리자는 정보의 품질, 정보의 구조화 방법 및 조직에서 기타 모범 사례를 감독합니다.</span><span class="sxs-lookup"><span data-stu-id="a60e9-144">Knowledge managers oversee the quality of information, how its structured, and other best practices in your organization.</span></span> <span data-ttu-id="a60e9-145">항목을 확인하고 거부할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a60e9-145">They can confirm and reject topics.</span></span>

<span data-ttu-id="a60e9-146">개별 항목 관리자를 지정할 수 있는 경우 지식 관리자로 지정할 사용자가 포함된 보안 그룹을 만들거나 기존 항목을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a60e9-146">While you can specify individual topic managers, we recommend that you create a security group (or use an existing one) that contains the people who you want to be knowledge managers.</span></span> <span data-ttu-id="a60e9-147">설치 프로세스 중에 이 보안 그룹을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a60e9-147">You can specify this security group during the setup process.</span></span>

<span data-ttu-id="a60e9-148">*항목 만들기 및 편집*</span><span class="sxs-lookup"><span data-stu-id="a60e9-148">*Create and edit topics*</span></span>

<span data-ttu-id="a60e9-149">주제 참가자는 조직의 챔피언이자 주제 전문가입니다.</span><span class="sxs-lookup"><span data-stu-id="a60e9-149">Topic contributors are the champions and subject matter experts in your organization.</span></span> <span data-ttu-id="a60e9-150">항목을 만들고 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a60e9-150">They can create and edit topics.</span></span> 

<span data-ttu-id="a60e9-151">모든 사용자가 정보를 공유할 수 있는 경우 항목 환경이 가장 잘 작동하기 때문에 조직의 모든 사용자가 항목을 만들고 편집할 수 있도록 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a60e9-151">We recommend that you allow everyone in your organization to create and edit topics because topic experiences work best when all users can share information.</span></span>

<span data-ttu-id="a60e9-152">특정 사용자 또는 그룹으로 항목을 만들고 편집하도록 제한하려면 해당 사용자에 대한 보안 그룹을 만들고 설치 프로세스 중에 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a60e9-152">If you want to limit creating and editing topics to specific people or groups, create a security group for them and specify it during the setup process.</span></span>

<span data-ttu-id="a60e9-153">누구도 항목에 참여하지 못하도록 선택할 수 있습니다. 그러나 이는 권장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a60e9-153">You can choose to not allow anyone to contribute to topics, however this is not recommended.</span></span> <span data-ttu-id="a60e9-154">이 옵션을 선택하는 경우 지식 관리자는 여전히 항목을 편집하고 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a60e9-154">Knowledge managers will still be able to edit and create topics if you choose this option.</span></span>

<span data-ttu-id="a60e9-155">*주제 뷰어*</span><span class="sxs-lookup"><span data-stu-id="a60e9-155">*Topic viewers*</span></span>

<span data-ttu-id="a60e9-156">항목 뷰어는 항목 페이지, 검색 결과 및 SharePoint 페이지와 같은 콘텐츠에서 항목을 강조 표시하는 경우의 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a60e9-156">Topic viewers can see information on topic pages, in search results and when topics are highlighted in the content like SharePoint pages.</span></span> <span data-ttu-id="a60e9-157">사용자는 항목에서 검색된 파일 및 페이지에 액세스할 수 있는 경우 검색된 항목만 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a60e9-157">Users can only see discovered topics when they have access to the files and pages the topic was discovered in.</span></span>

<span data-ttu-id="a60e9-158">주제 뷰어를 설정할 때 다음 중 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a60e9-158">When setting up topic viewers, you can choose from:</span></span>

- <span data-ttu-id="a60e9-159">**조직의 모든 사용자**</span><span class="sxs-lookup"><span data-stu-id="a60e9-159">**Everyone in my organization**</span></span>
- <span data-ttu-id="a60e9-160">**선택한 사용자 또는 보안 그룹만**</span><span class="sxs-lookup"><span data-stu-id="a60e9-160">**Only selected people or security groups**</span></span>
- <span data-ttu-id="a60e9-161">**아무도 없어**</span><span class="sxs-lookup"><span data-stu-id="a60e9-161">**No one**</span></span>

<span data-ttu-id="a60e9-162">조직의 모든 **사용자가** 권장되지만 파일럿을 수행하고 있는 경우 선택한 사용자 또는 보안 그룹만 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a60e9-162">We recommend **Everyone in my organization**, but if you're doing a pilot you may want to choose only selected people or security groups.</span></span> <span data-ttu-id="a60e9-163">항목을 설정하겠지만  사용자가 아직 항목을 볼 수 있도록 허용하지 않을 경우 아니요를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a60e9-163">You can also choose **No one** if you want to set up Topics, but not allow people to see topics yet.</span></span> <span data-ttu-id="a60e9-164">(지식 관리자는 여전히 항목을 보고 항목을 광범위하게 사용할 수 있도록 결정을 내리는 데 도움을 줄 수 있는 액세스 권한이 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="a60e9-164">(Knowledge managers will still have access to allow them view the topics and help with the decision to make Topics broadly available.)</span></span>

## <a name="knowledge-rules"></a><span data-ttu-id="a60e9-165">지식 규칙</span><span class="sxs-lookup"><span data-stu-id="a60e9-165">Knowledge rules</span></span>

<span data-ttu-id="a60e9-166">관리자는 항목 환경에서 특정 항목을 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a60e9-166">As an administrator, you can exclude certain topics from topic experiences.</span></span> <span data-ttu-id="a60e9-167">이 기능은 중요한 데이터가 항목에 나타나지 못하게 하려는 경우 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="a60e9-167">This is useful if you want to keep sensitive data from appearing in topics.</span></span> <span data-ttu-id="a60e9-168">지식 관리자는 항목 센터에서 항목을 제외할 수 있는 반면, 관리자가 제외한 항목은 지식 관리자에게도 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a60e9-168">While knowledge managers can exclude topics in the topic center, topics excluded by the administrator are not even visible to knowledge managers.</span></span> <span data-ttu-id="a60e9-169">(기술 관리자는 검색 후 항목 센터에서 항목을 제거할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="a60e9-169">(Knowledge managers can also remove topics in the topic center after discovery.)</span></span>

<span data-ttu-id="a60e9-170">관리자 수준에서 항목을 제외하려면 .csv 파일에 항목을 추가하고 파일을 업로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a60e9-170">If you want to exclude topics at the administrator level, you must add them to a .csv file and upload the file.</span></span> <span data-ttu-id="a60e9-171">설치하는 동안 또는 나중에 이 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a60e9-171">You can do this during setup or later.</span></span>

<span data-ttu-id="a60e9-172">.csv 파일에는 다음 매개 변수가 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a60e9-172">The .csv file must contain the following parameters:</span></span>

- <span data-ttu-id="a60e9-173">**이름:** 제외할 항목의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="a60e9-173">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="a60e9-174">이 작업은 다음 두 가지 방법으로 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a60e9-174">There are two ways to do this:</span></span>
- <span data-ttu-id="a60e9-175">**MatchType-Exact/Partial**: 입력한 이름이 정확히  일치 유형인지 또는 부분 일치 *유형인지 여부를* 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="a60e9-175">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>
    - <span data-ttu-id="a60e9-176">정확한 일치: 정확한 이름 또는 약어(예: *Contoso* 또는 ATL)를 포함할 *수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="a60e9-176">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
    - <span data-ttu-id="a60e9-177">부분 일치: 특정 단어가 있는 모든 항목을 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a60e9-177">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="a60e9-178">예를 들어 *호는* 호 원, 4도분의 호, 교육 호 등 호 단어가 있는 모든 항목을 *제외합니다.*  아키텍처와 같이 텍스트가 단어의 일부로 포함된 항목은 제외되지 *않습니다.*</span><span class="sxs-lookup"><span data-stu-id="a60e9-178">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
- <span data-ttu-id="a60e9-179">**(선택 사항)**: (확장) 약어를 제외하려는 경우 약어가 서 있는 단어를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="a60e9-179">**Stands for (optional)**: (Also known as *expansion*) If you want to exclude an acronym, type the words the acronym stands for.</span></span>

    ![CSV 템플릿에서 항목 제외](../media/exclude-topics-csv.png) 

<span data-ttu-id="a60e9-181">아래 csv 템플릿을 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a60e9-181">You can copy the csv template below:</span></span>

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

## <a name="administration"></a><span data-ttu-id="a60e9-182">관리</span><span class="sxs-lookup"><span data-stu-id="a60e9-182">Administration</span></span>

<span data-ttu-id="a60e9-183">항목을 설정할 때 설치 프로세스의 일부로 항목 센터가 자동으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="a60e9-183">When you set up Topics, as part of the setup process, a topic center is automatically created.</span></span> <span data-ttu-id="a60e9-184">항목 센터의 이름을 지정하는 항목과 URL을 지정하려는 항목을 생각해 세요.</span><span class="sxs-lookup"><span data-stu-id="a60e9-184">Think about what you want to name the topic center and what you want the URL to be.</span></span> <span data-ttu-id="a60e9-185">설치 프로세스의 일부로 이름과 URL을 설정할 수 있으며, 나중에 Microsoft 365 관리 센터에서 이름(URL은 아미는 것)을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a60e9-185">You can set both the name and URL as part of the setup process, and you can change the name (but not URL) later in the Microsoft 365 admin center.</span></span> <span data-ttu-id="a60e9-186">하나의 항목 센터만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a60e9-186">You can only have one topic center.</span></span>

## <a name="setup-checklist"></a><span data-ttu-id="a60e9-187">설치 검사 목록</span><span class="sxs-lookup"><span data-stu-id="a60e9-187">Setup checklist</span></span>

<span data-ttu-id="a60e9-188">항목 환경을 설정할 때 설정 마법사를 진행할 때 다음 항목이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a60e9-188">When you set up topic experiences, you'll need the following items as you go through the setup wizard:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="a60e9-189">항목 검색을 위한 모든 사이트를 포함하지 않을 경우 포함하거나 제외할 사이트 목록</span><span class="sxs-lookup"><span data-stu-id="a60e9-189">List of sites to include or exclude if not including all sites for topic discovery</span></span>
> * <span data-ttu-id="a60e9-190">모든 사용자가 항목을 볼 수 있도록 허용하지 않는 경우 항목 보기를 위한 보안 그룹</span><span class="sxs-lookup"><span data-stu-id="a60e9-190">Security group for topic viewers if not allowing all users to view topics</span></span>
> * <span data-ttu-id="a60e9-191">모든 사용자가 항목을 만들고 편집할 수 있도록 허용하지 않는 경우 항목 참가자를 위한 보안 그룹</span><span class="sxs-lookup"><span data-stu-id="a60e9-191">Security group for topic contributors if not allowing all users to create and edit topics</span></span>
> * <span data-ttu-id="a60e9-192">모든 사용자가 항목을 관리할 수 있도록 허용하지 않는 경우 항목 지식 관리자를 위한 보안 그룹</span><span class="sxs-lookup"><span data-stu-id="a60e9-192">Security group for topic knowledge managers if not allowing all users to manage topics</span></span>
> * <span data-ttu-id="a60e9-193">항목 검색에서 제외할 중요한 항목 목록</span><span class="sxs-lookup"><span data-stu-id="a60e9-193">List of sensitive topics to exclude from topic discovery</span></span>
> * <span data-ttu-id="a60e9-194">항목 센터 사이트의 이름</span><span class="sxs-lookup"><span data-stu-id="a60e9-194">A name for your topic center site</span></span>

## <a name="see-also"></a><span data-ttu-id="a60e9-195">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a60e9-195">See also</span></span>

[<span data-ttu-id="a60e9-196">주제 경험 설정</span><span class="sxs-lookup"><span data-stu-id="a60e9-196">Set up topic experiences</span></span>](set-up-topic-experiences.md)

[<span data-ttu-id="a60e9-197">Microsoft 365에서 항목 검색 관리</span><span class="sxs-lookup"><span data-stu-id="a60e9-197">Manage topic discovery in Microsoft 365</span></span>](topic-experiences-discovery.md)

[<span data-ttu-id="a60e9-198">Microsoft 365에서 항목 표시 관리</span><span class="sxs-lookup"><span data-stu-id="a60e9-198">Manage topic visibility in Microsoft 365</span></span>](topic-experiences-knowledge-rules.md)

[<span data-ttu-id="a60e9-199">Microsoft 365에서 항목 사용 권한 관리</span><span class="sxs-lookup"><span data-stu-id="a60e9-199">Manage topic permissions in Microsoft 365</span></span>](topic-experiences-user-permissions.md)

[<span data-ttu-id="a60e9-200">Microsoft 365에서 항목 센터의 이름 변경</span><span class="sxs-lookup"><span data-stu-id="a60e9-200">Change the name of the topic center in Microsoft 365</span></span>](topic-experiences-administration.md)
