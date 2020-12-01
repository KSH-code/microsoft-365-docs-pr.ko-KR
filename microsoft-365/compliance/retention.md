---
title: 콘텐츠를 자동으로 보존하거나 삭제하는 보존 정책과 레이블에 대해 자세히 알아보기
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
- m365solution-mig
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: 필요한 항목을 보존하고 필요하지 않은 항목을 삭제하는 데 도움을 주는 보존 정책과 보존 레이블에 대해 알아봅니다.
ms.openlocfilehash: e2833d966fb8a1fcc15cbeb02b781d9c0325b9c1
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519379"
---
# <a name="learn-about-retention-policies-and-retention-labels"></a><span data-ttu-id="95b55-103">보존 정책 및 보존 레이블에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="95b55-103">Learn about retention policies and retention labels</span></span>

><span data-ttu-id="95b55-104">*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD)*</span><span class="sxs-lookup"><span data-stu-id="95b55-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="95b55-p101">대부분의 조직에서는 전자 메일, 문서, 인스턴트 메시지 등을 비롯하여 데이터의 양과 복잡성이 계속해서 매일 증가하고 있습니다. 이러한 정보를 효과적으로 관리하거나 제어하는 일은 다음 작업을 수행해야 하므로 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-p101">For most organizations, the volume and complexity of their data is increasing daily—email, documents, instant messages, and more. Effectively managing or governing this information is important because you need to:</span></span>
  
- <span data-ttu-id="95b55-107">최소 기간 동안 콘텐츠를 보존하도록 요구하는 **산업 규정 및 내부 정책을 사전에 준수** 합니다. 예를 들어 Sarbanes-Oxley Act는 7년 동안 특정 유형의 콘텐츠를 보존하도록 요구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-107">**Comply proactively with industry regulations and internal policies** that require you to retain content for a minimum period of time—for example, the Sarbanes-Oxley Act might require you to retain certain types of content for seven years.</span></span> 

- <span data-ttu-id="95b55-108">**소송 또는 보안 위반 시 위험 감소** - 더 이상 보존할 필요가 없는 오래된 콘텐츠를 영구적으로 삭제</span><span class="sxs-lookup"><span data-stu-id="95b55-108">**Reduce your risk in the event of litigation or a security breach** by permanently deleting old content that you're no longer required to keep.</span></span> 
    
- <span data-ttu-id="95b55-109">**조직에서 효과적이면서 좀 더 민첩하게 지식을 공유하도록 지원** - 사용자가 관련이 있는 최신 콘텐츠만 사용하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-109">**Help your organization to share knowledge effectively and be more agile** by ensuring that your users work only with content that's current and relevant to them.</span></span> 
    
<span data-ttu-id="95b55-p102">구성하는 보존 설정은 이러한 모든 목표를 달성하는 데 도움이 됩니다. 일반적으로 내용을 관리하려면 다음 두 가지 작업이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-p102">Retention settings that you configure can help you achieve all these goals. Managing content commonly requires two actions:</span></span>
  
- <span data-ttu-id="95b55-112">**보존** - 콘텐츠가 보존 기간이 끝나기 전에 영구적으로 삭제되지 않도록 보존합니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-112">**Retaining** content so that it can't be permanently deleted before the end of the retention period.</span></span> 
    
- <span data-ttu-id="95b55-113">**삭제** - 보존 기간이 끝나면 콘텐츠를 영구적으로 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-113">**Deleting** content permanently at the end of the retention period.</span></span> 
    

<span data-ttu-id="95b55-114">이러한 두 가지 보존 작업을 통해 다음 결과에 대한 보존 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-114">With these two retention actions, you can configure retention settings for the following outcomes:</span></span>

- <span data-ttu-id="95b55-115">보존 전용: 콘텐츠를 영구적으로 또는 지정된 기간 동안 보존합니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-115">Retain-only: Retain content forever or for a specified period of time.</span></span>
- <span data-ttu-id="95b55-116">삭제 전용: 지정된 기간이 지난 후 콘텐츠를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-116">Delete-only: Delete content after a specified period of time.</span></span>
- <span data-ttu-id="95b55-117">보존한 다음 삭제: 지정된 기간 동안 콘텐츠를 보존한 다음 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-117">Retain and then delete: Retain content for a specified period of time and then delete it.</span></span>

<span data-ttu-id="95b55-p103">이러한 보존 설정은 규정 준수를 이유로 컨텐츠를 보존해야 할 때 추가 스토리지를 생성하고 구성하는 데 드는 추가 오버헤드를 덜어주는 사용 중인 컨텐츠와 함께 작동합니다. 또한 이 데이터를 복사하고 동기화하기 위해 사용자 지정된 프로세스를 구현할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-p103">These retention settings work with content in place that saves you the additional overheads of creating and configuring additional storage when you need to retain content for compliance reasons. In addition, you don't need to implement customized processes to copy and synchronize this data.</span></span>

## <a name="how-retention-settings-work-with-content-in-place"></a><span data-ttu-id="95b55-120">보존 설정이 콘텐츠와 함께 작동하는 방법</span><span class="sxs-lookup"><span data-stu-id="95b55-120">How retention settings work with content in place</span></span>

<span data-ttu-id="95b55-p104">콘텐츠에 할당된 보존 설정이 있는 경우 해당 콘텐츠는 원래 위치에 유지됩니다. 사용자는 문서 또는 메일을 변경하지 않은 것처럼 계속 작업할 수 있습니다. 그러나 보존 정책에 포함된 내용을 편집하거나 삭제하면 콘텐츠의 복사본이 자동으로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-p104">When content has retention settings assigned to it, that content remains in its original location. People can continue to work with their documents or mail as if nothing's changed. But if they edit or delete content that's included in the retention policy, a copy of the content is automatically retained.</span></span>
  
- <span data-ttu-id="95b55-124">SharePoint 및 OneDrive 사이트의 경우: 사본은 **자료 보존** 라이브러리에 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-124">For SharePoint and OneDrive sites: The copy is retained in the **Preservation Hold** library.</span></span>

- <span data-ttu-id="95b55-125">Exchange 사서함의 경우: **복구 가능한 항목** 폴더에 사본이 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-125">For Exchange mailboxes: The copy is retained in the **Recoverable Items** folder.</span></span> 

- <span data-ttu-id="95b55-126">Teams 및 채널 및 Yammer 메시지의 경우: 사본은 Exchange **복구 가능한 항목** 폴더 내에 하위 폴더로 **SubstrateHolds** 라는 이름의 숨겨진 폴더에 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-126">For Teams and Yammer messages: The copy is retained in a hidden folder named **SubstrateHolds** as a subfolder in the Exchange **Recoverable Items** folder.</span></span>

> [!NOTE]
> <span data-ttu-id="95b55-p105">보존 보류 라이브러리는 사이트의 스토리지 할당량에서 제외되지 않는 스토리지를 사용합니다. SharePoint 및 Microsoft 365 그룹에 대한 보존 설정을 사용할 경우 스토리지를 늘려야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-p105">The Preservation Hold library consumes storage that isn't exempt from a site's storage quota. You might need to increase your storage when you use retention settings for SharePoint and Microsoft 365 groups.</span></span>
> 
<span data-ttu-id="95b55-p106">이러한 보안 위치 및 보존 콘텐츠는 대부분의 사용자에게 표시되지 않습니다. 대부분의 경우, 사람들은 자신의 콘텐츠가 보존 설정의 영향을 받는다는 사실조차 알 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-p106">These secure locations and the retained content are not visible to most people. In most cases, people do not even need to know that their content is subject to retention settings.</span></span>

<span data-ttu-id="95b55-131">다양한 워크로드에 대해 보존 설정이 작동하는 방법에 대한 자세한 내용은 다음의 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95b55-131">For more detailed information about how retention settings work for different workloads, see the following articles:</span></span>

- [<span data-ttu-id="95b55-132">SharePoint 및 OneDrive의 보존에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="95b55-132">Learn about retention for SharePoint and OneDrive</span></span>](retention-policies-sharepoint.md)
- [<span data-ttu-id="95b55-133">Microsoft Teams의 보존에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="95b55-133">Learn about retention for Microsoft Teams</span></span>](retention-policies-teams.md)
- [<span data-ttu-id="95b55-134">Yammer의 보존에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="95b55-134">Learn about retention for Yammer</span></span>](retention-policies-yammer.md)
- [<span data-ttu-id="95b55-135">Exchange의 보존에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="95b55-135">Learn about retention for Exchange</span></span>](retention-policies-exchange.md)

## <a name="retention-policies-and-retention-labels"></a><span data-ttu-id="95b55-136">보존 정책 및 보존 레이블</span><span class="sxs-lookup"><span data-stu-id="95b55-136">Retention policies and retention labels</span></span>

<span data-ttu-id="95b55-137">레이블 정책과 함께 보존 정책 및 보존 레이블을 모두 사용하여 보존 설정을 콘텐츠에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-137">You can use both retention policies and retention labels with label policies to assign your retention settings to content.</span></span> 

<span data-ttu-id="95b55-138">보존 정책을 사용하여 사이트 또는 사서함 수준에서 콘텐츠에 대해 같은 보존 설정을 할당하고, 보존 레이블을 사용하여 항목 수준(폴더, 문서, 전자 메일)에 보존 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-138">Use a retention policy to assign the same retention settings for content at a site or mailbox level, and use a retention label to assign retention settings at an item level (folder, document, email).</span></span>

<span data-ttu-id="95b55-p107">예를 들어 SharePoint 사이트의 모든 문서를 5년 동안 보존해야 하는 경우 해당 사이트의 모든 문서에 동일한 보존 레이블을 적용하는 것보다 보존 정책을 사용하여 보존하는 것이 더 효율적입니다. 그러나 해당 사이트의 일부 문서를 5년 동안 보관하고 다른 문서는 10년 동안 보관해야 하는 경우 보존 정책은 이를 수행할 수 없습니다. 항목 수준에서 보존 설정을 지정해야 하는 경우 보존 레이블을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-p107">For example, if all documents in a SharePoint site should be retained for 5 years, it's more efficient to do this with a retention policy than apply the same retention label to all documents in that site. However, if some documents in that site should be retained for 5 years and others retained for 10 years, a retention policy wouldn't be able to do this. When you need to specify retention settings at the item level, use retention labels.</span></span> 

<span data-ttu-id="95b55-p108">보존 정책과 달리 보존 레이블의 보존 설정은 Microsoft 365 테넌트 내의 다른 위치로 이동하면 컨텐츠와 함께 이동합니다. 또한 보존 레이블에는 보존 정책이 지원하지 않는 다음과 같은 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-p108">Unlike retention policies, retention settings from retention labels travel with the content if it’s moved to a different location within your Microsoft 365 tenant. In addition, retention labels have the following capabilities that retention policies don't support:</span></span> 
 
- <span data-ttu-id="95b55-144">콘텐츠의 기간 또는 콘텐츠가 마지막으로 수정된 시간 외에도 콘텐츠에 레이블이 지정된 시간으로부터 또는 이벤트를 기반으로 보존 기간을 시작하는 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-144">Options to start the retention period from when the content was labeled or based on an event, in addition to the age of the content or when it was last modified.</span></span>

- <span data-ttu-id="95b55-145">[학습 가능한 분류자](classifier-learn-about.md)를 사용하여 콘텐츠를 레이블로 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-145">Use [trainable classifiers](classifier-learn-about.md) to identify content to label.</span></span>

- <span data-ttu-id="95b55-146">SharePoint 문서에 대해 기본 레이블을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-146">Apply a default label for SharePoint documents.</span></span>

- <span data-ttu-id="95b55-147">콘텐츠를 영구적으로 삭제하기 전에 검토할 수 있는 [처리 검토](disposition-reviews.md) 를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-147">Support [disposition review](disposition-reviews.md) to review the content before it's permanently deleted.</span></span>

- <span data-ttu-id="95b55-148">콘텐츠를 레이블 설정의 일부로 [레코드](records-management.md#records)로 표시하고, 보관 기간이 끝나 콘텐츠가 삭제된 경우 항상  [처리 증명](disposition.md#disposition-of-records) 이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-148">Mark the content as a [record](records-management.md#records) as part of the label settings, and always have [proof of disposition](disposition.md#disposition-of-records) when content is deleted at the end of its retention period.</span></span>

### <a name="retention-policies"></a><span data-ttu-id="95b55-149">보존 정책</span><span class="sxs-lookup"><span data-stu-id="95b55-149">Retention policies</span></span>

<span data-ttu-id="95b55-150">보존 정책은 다음 위치에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-150">Retention policies can be applied to the following locations:</span></span>
- <span data-ttu-id="95b55-151">Exchange 전자 메일</span><span class="sxs-lookup"><span data-stu-id="95b55-151">Exchange email</span></span>
- <span data-ttu-id="95b55-152">SharePoint 사이트</span><span class="sxs-lookup"><span data-stu-id="95b55-152">SharePoint site</span></span>
- <span data-ttu-id="95b55-153">OneDrive 계정</span><span class="sxs-lookup"><span data-stu-id="95b55-153">OneDrive accounts</span></span>
- <span data-ttu-id="95b55-154">Microsoft 365 그룹</span><span class="sxs-lookup"><span data-stu-id="95b55-154">Microsoft 365 Groups</span></span>
- <span data-ttu-id="95b55-155">비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="95b55-155">Skype for Business</span></span>
- <span data-ttu-id="95b55-156">Exchange 공용 폴더</span><span class="sxs-lookup"><span data-stu-id="95b55-156">Exchange public folders</span></span>
- <span data-ttu-id="95b55-157">Teams 채널 메시지</span><span class="sxs-lookup"><span data-stu-id="95b55-157">Teams channel messages</span></span>
- <span data-ttu-id="95b55-158">Teams 채팅</span><span class="sxs-lookup"><span data-stu-id="95b55-158">Teams chats</span></span>
- <span data-ttu-id="95b55-159">Yammer 커뮤니티 메시지</span><span class="sxs-lookup"><span data-stu-id="95b55-159">Yammer community messages</span></span>
- <span data-ttu-id="95b55-160">Yammer 개인 메시지</span><span class="sxs-lookup"><span data-stu-id="95b55-160">Yammer private messages</span></span>

<span data-ttu-id="95b55-161">단일 정책을 여러 위치 또는 특정 위치 또는 사용자에게 효율적으로 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-161">You can very efficiently apply a single policy to multiple locations, or to specific locations or users.</span></span>

<span data-ttu-id="95b55-162">보존 기간 시작 시 콘텐츠가 생성된 시기 또는 콘텐츠가 마지막으로 수정된시기(파일 및 SharePoint, OneDrive 및 Microsoft 365 그룹 위치에 대해서만 지원됨)를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-162">For the start of the retention period, you can choose when the content was created or, supported only for files and the SharePoint, OneDrive, and Microsoft 365 Groups locations, when the content was last modified.</span></span>

<span data-ttu-id="95b55-p109">항목은 보존 정책에 지정된 컨테이너의 보존 설정을 상속합니다. 해당 정책이 콘텐츠를 보존하도록 구성될 때 항목이 컨테이너 외부로 이동되는 경우 해당 항목의 사본은 작업의 보안 위치에 유지됩니다. 그러나 보존 설정은 새 위치의 콘텐츠와 함께 이동되지 않습니다. 필요한 경우 보존 정책 대신 보존 레이블을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-p109">Items inherit the retention settings from their container specified in the retention policy. If they are then moved outside that container when the policy is configured to retain content, a copy of that item is retained in the workload's secured location. However, the retention settings don't travel with the content in its new location. If that's required, use retention labels instead of retention policies.</span></span>

### <a name="retention-labels"></a><span data-ttu-id="95b55-167">보존 레이블</span><span class="sxs-lookup"><span data-stu-id="95b55-167">Retention labels</span></span>

<span data-ttu-id="95b55-p110">다른 보존 설정이 있어야 하는 다양한 유형의 콘텐츠에는 보존 레이블을 사용합니다. 예:</span><span class="sxs-lookup"><span data-stu-id="95b55-p110">Use retention labels for different types of content that require different retention settings. For example:</span></span>
  
- <span data-ttu-id="95b55-170">최소 기간 동안 보존해야 하는 세금 양식</span><span class="sxs-lookup"><span data-stu-id="95b55-170">Tax forms that need to be retained for a minimum period of time.</span></span> 
    
- <span data-ttu-id="95b55-171">특정 기간에 도달하면 영구적으로 삭제되어야 하는 보도 자료</span><span class="sxs-lookup"><span data-stu-id="95b55-171">Press materials that need to be permanently deleted when they reach a specific age.</span></span> 
    
- <span data-ttu-id="95b55-172">특정 기간 동안 보존되었다가 영구적으로 삭제되어야 하는 경쟁 연구 자료</span><span class="sxs-lookup"><span data-stu-id="95b55-172">Competitive research that needs to be retained for a specific period and then permanently deleted.</span></span> 
    
- <span data-ttu-id="95b55-173">편집하거나 삭제할 수 없게 레코드로 표시해야 하는 취업 비자</span><span class="sxs-lookup"><span data-stu-id="95b55-173">Work visas that must be marked as a record so that they can't be edited or deleted.</span></span> 
    
<span data-ttu-id="95b55-174">이 모든 경우 보존 레이블을 사용하여 항목 수준(문서 또는 전자 메일)에서 거버넌스 제어에 대한 보존 설정을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-174">In all these cases, retention labels let you apply retention settings for governance control at the item level (document or email).</span></span>
  
<span data-ttu-id="95b55-175">보존 레이블을 사용하여 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-175">With retention labels, you can:</span></span>
  
- <span data-ttu-id="95b55-p111">Outlook, 웹용 Outlook, OneDrive, SharePoint 및 Microsoft 365 그룹의 콘텐츠에 **조직의 사용자가 수동으로 보존 레이블을 적용할 수 있도록 합니다**. 대개 사용자가 자신이 작업 중인 콘텐츠의 유형을 가장 잘 알고 있으므로 사용자가 콘텐츠를 분류하고 적절한 보존 설정이 적용되도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-p111">**Enable people in your organization to apply a retention label manually** to content in Outlook and Outlook on the web, OneDrive, SharePoint, and Microsoft 365 groups. Users often know best what type of content they're working with, so they can classify it and have the appropriate retention settings applied.</span></span> 
    
- <span data-ttu-id="95b55-178">콘텐츠에 다음이 포함된 경우처럼 특정 조건과 일치하는 경우 **콘텐츠에 보존 레이블을 자동으로 적용** 합니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-178">**Apply retention labels to content automatically** if it matches specific conditions, such as when the content contains:</span></span> 
    - <span data-ttu-id="95b55-179">특정 중요한 정보 유형</span><span class="sxs-lookup"><span data-stu-id="95b55-179">Specific types of sensitive information.</span></span>
    - <span data-ttu-id="95b55-180">만든 쿼리와 일치하는 특정 키워드</span><span class="sxs-lookup"><span data-stu-id="95b55-180">Specific keywords that match a query you create.</span></span>
    - <span data-ttu-id="95b55-181">학습 가능한 분류자에 대한 패턴 일치</span><span class="sxs-lookup"><span data-stu-id="95b55-181">Pattern matches for a trainable classifier.</span></span>

- <span data-ttu-id="95b55-p112">**콘텐츠에 레이블이 지정된 시점부터 보존 기간 시작**(SharePoint 사이트 및 OneDrive 계정의 문서, 일정 항목을 제외한 전자 메일 항목). 이 구성과 함께 보존 레이블을 일정 항목에 적용하는 경우 해당 보존 기간은 보낸 날짜부터 시작됩니다. </span><span class="sxs-lookup"><span data-stu-id="95b55-p112">**Start the retention period from when the content was labeled** for documents in SharePoint sites and OneDrive accounts, and to email items with the exception of calendar items. If you apply a retention label with this configuration to a calendar item, the retention period starts from when it is sent.</span></span>

- <span data-ttu-id="95b55-184">**이벤트가 발생할 때 보존 기간 시작**(예: 직원 퇴사, 계약 만료)</span><span class="sxs-lookup"><span data-stu-id="95b55-184">**Start the retention period when an event occurs**, such as employees leave the organization, or contracts expire.</span></span>

- <span data-ttu-id="95b55-185">SharePoint의 **문서 라이브러리, 폴더 또는 문서 집합에 기본 보존 레이블을 적용** 하여 해당 위치에 저장된 모든 문서가 기본 보존 레이블을 상속하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-185">**Apply a default retention label to a document library, folder, or document set** in SharePoint, so that all documents that are stored in that location inherit the default retention label.</span></span>

<span data-ttu-id="95b55-p113">또한, 보존 레이블은 Microsoft 365 앱과 서비스에서 전자 메일 및 문서의 [레코드 관리](records-management.md)를 지원합니다. 보존 레이블을 사용하여 항목을 기록으로 표시할 수 있습니다. 이 문제가 발생하고 콘텐츠가 Microsoft 365에 남아 있는 경우 레이블은 규정상의 이유로 필요할 수 있는 콘텐츠에 대한 제한을 마련합니다. 자세한 내용은 [허용 또는 차단되는 작업에 대한 제한 사항 비교](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95b55-p113">Additionally, retention labels support [records management](records-management.md) for email and documents across Microsoft 365 apps and services. You can use a retention label to mark items as a record. When this happens and the content remains in Microsoft 365, the label places further restrictions on the content that might be needed for regulatory reasons. For more information, see [Compare restrictions for what actions are allowed or blocked](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked).</span></span>

<span data-ttu-id="95b55-190">보존 레이블은 [민감도 레이블](sensitivity-labels.md)과 달리 Microsoft 365 외부로 콘텐츠를 이동해도 유지되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-190">Retention labels, unlike [sensitivity labels](sensitivity-labels.md), do not persist if the content is moved outside Microsoft 365.</span></span>

<span data-ttu-id="95b55-p114">테넌트에 지원되는 보존 레이블 개수에는 제한이 없습니다. 그러나 10,000은 테넌트에 지원되는 최대 정책의 수이며, 여기에는 레이블뿐만 아니라 보존 정책이 적용되는 정책(보존 레이블 정책과 자동 적용 보존 정책)도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-p114">There is no limit to the number of retention labels that are supported for a tenant. However, 10,000 is the maximum number of policies that are supported for a tenant and these include the policies that apply the labels (retention label policies and auto-apply retention policies), as well as retention policies.</span></span>

#### <a name="classifying-content-without-applying-any-actions"></a><span data-ttu-id="95b55-193">작업을 적용하지 않고 콘텐츠 분류하기</span><span class="sxs-lookup"><span data-stu-id="95b55-193">Classifying content without applying any actions</span></span>

<span data-ttu-id="95b55-p115">보존 레이블의 주요 용도는 콘텐츠를 보존하거나 삭제하는 것이지만, 보존 또는 기타 작업을 설정하지 않고 보존 레이블을 사용할 수도 있습니다. 이 경우 작업을 적용하지 않고 보존 레이블을 단순히 텍스트 레이블로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-p115">Although the main purpose of retention labels is to retain or delete content, you can also use retention labels without turning on any retention or other actions. In this case, you can use a retention label simply as a text label, without enforcing any actions.</span></span>
  
<span data-ttu-id="95b55-196">예를 들어 작업이 없는 "나중에 검토"라는 보존 레이블을 만들고 적용한 다음 해당 레이블을 사용하여 나중에 해당 콘텐츠를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-196">For example, you can create and apply a retention label named "Review later" with no actions, and then use that label to find that content later.</span></span>
  
![분류 전용으로 레이블 설정](../media/retention-label-retentionoff.png)

#### <a name="using-a-retention-label-as-a-condition-in-a-dlp-policy"></a><span data-ttu-id="95b55-198">보존 레이블을 DLP 정책의 조건으로 사용하기</span><span class="sxs-lookup"><span data-stu-id="95b55-198">Using a retention label as a condition in a DLP policy</span></span>

<span data-ttu-id="95b55-p116">SharePoint의 문서에 대한 DLP(데이터 손실 방지) 정책에서 보존 레이블을 조건으로 지정할 수 있습니다. 예를 들어 문서에 지정된 보존 레이블이 적용된 경우, 문서를 조직 외부에 공유하지 못하도록 DLP 정책을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-p116">You can specify a retention label as a condition in a data loss prevention (DLP) policy for documents in SharePoint. For example, configure a DLP policy to prevent documents from being shared outside the organization if they have a specified retention label applied to it.</span></span>

<span data-ttu-id="95b55-201">자세한 내용은 [보존 레이블을 DLP 정책의 조건으로 사용하기](data-loss-prevention-policies.md#using-a-retention-label-as-a-condition-in-a-dlp-policy)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95b55-201">For more information, see [Using a retention label as a condition in a DLP policy](data-loss-prevention-policies.md#using-a-retention-label-as-a-condition-in-a-dlp-policy).</span></span>

#### <a name="retention-labels-and-policies-that-apply-them"></a><span data-ttu-id="95b55-202">보존 레이블과 보존 레이블을 적용하는 정책 </span><span class="sxs-lookup"><span data-stu-id="95b55-202">Retention labels and policies that apply them</span></span>

<span data-ttu-id="95b55-p117">보존 레이블은 독립적이고, 다시 사용할 수 있는 구성 요소입니다. 보존 레이블 정책의 기본 목적은 보존 레이블 집합을 그룹화하고 해당 레이블을 표시할 위치를 지정하는 것입니다. 그러면 관리자와 사용자가 해당 위치에 해당 레이블을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-p117">Retention labels are independent, reusable building blocks. The primary purpose of a retention label policy is to group a set of retention labels and specify the locations where you want those labels to appear. Then, admins and users can apply those labels to content in those locations.</span></span>
  
![레이블, 레이블 정책 및 위치 다이어그램](../media/eee42516-adf0-4664-b5ab-76727a9a3511.png)
  
<span data-ttu-id="95b55-207">보존 레이블을 게시하면 보존 레이블은 보존 레이블 정책에 포함되어 관리자와 사용자가 다음을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-207">When you publish retention labels, they're included in a retention label policy that make them available for admins and users to select:</span></span>

- <span data-ttu-id="95b55-208">하나의 보존 레이블이 여러 보존 레이블 정책에 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-208">A single retention label can be included in many retention label policies.</span></span>

- <span data-ttu-id="95b55-209">보존 레이블 정책이 보존 레이블을 게시할 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-209">Retention label policies specify the locations to publish the retention labels.</span></span>

- <span data-ttu-id="95b55-210">하나의 위치가 여러 보존 레이블 정책에 포함될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-210">A single location can also be included in many retention label policies.</span></span>

<span data-ttu-id="95b55-p118">보존 레이블 정책 외에도 하나의 보존 레이블을 사용하여 하나 이상의 자동 적용 정책을 만들 수 있습니다. 이 정책을 사용하면 정책에서 지정하는 조건이 충족될 경우 보존 레이블이 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-p118">In addition to retention label policies, you can also create one or more auto-apply policies, each with a single retention label. With this policy, a retention label is automatically applied when conditions that you specify in the policy are met.</span></span> 

#### <a name="retention-label-policies-and-locations"></a><span data-ttu-id="95b55-213">보존 레이블 정책 및 위치</span><span class="sxs-lookup"><span data-stu-id="95b55-213">Retention label policies and locations</span></span>

<span data-ttu-id="95b55-214">보존 레이블이 수행하는 작업에 따라, 다양한 유형의 보존 레이블을 여러 다른 위치에 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-214">Different types of retention labels can be published to different locations, depending on what the retention label does.</span></span>
  
| <span data-ttu-id="95b55-215">보존 레이블이</span><span class="sxs-lookup"><span data-stu-id="95b55-215">If the retention label is…</span></span> | <span data-ttu-id="95b55-216">레이블 정책을 적용할 수 있는 위치</span><span class="sxs-lookup"><span data-stu-id="95b55-216">Then the label policy can be applied to…</span></span> |
|:-----|:-----|
|<span data-ttu-id="95b55-217">관리자 및 최종 사용자에게 게시됨</span><span class="sxs-lookup"><span data-stu-id="95b55-217">Published to admins and end users</span></span>  <br/> |<span data-ttu-id="95b55-218">Exchange, SharePoint, OneDrive, Microsoft 365 그룹</span><span class="sxs-lookup"><span data-stu-id="95b55-218">Exchange, SharePoint, OneDrive, Microsoft 365 Groups</span></span>  <br/> |
|<span data-ttu-id="95b55-219">중요한 정보 유형 또는 학습 가능한 분류자를 기반으로 자동 적용됨</span><span class="sxs-lookup"><span data-stu-id="95b55-219">Auto-applied based on sensitive information types or trainable classifiers</span></span>  <br/> |<span data-ttu-id="95b55-220">Exchange(모든 사서함만), SharePoint, OneDrive</span><span class="sxs-lookup"><span data-stu-id="95b55-220">Exchange (all mailboxes only), SharePoint, OneDrive</span></span>  <br/> |
|<span data-ttu-id="95b55-221">쿼리에 따라 자동 적용</span><span class="sxs-lookup"><span data-stu-id="95b55-221">Auto-applied based on a query</span></span>  <br/> |<span data-ttu-id="95b55-222">Exchange, SharePoint, OneDrive, Microsoft 365 그룹</span><span class="sxs-lookup"><span data-stu-id="95b55-222">Exchange, SharePoint, OneDrive, Microsoft 365 Groups</span></span>  <br/> |
   
<span data-ttu-id="95b55-p119">Exchange에서 자동 적용 보존 레이블은 현재 사서함에 있는 모든 항목(미사용 데이터)이 아닌 새로 전송된 메시지(전송 중인 데이터)에만 적용됩니다. 또한, 중요한 정보 유형과 학습 가능한 분류자에 대한 자동 적용 보존 레이블은 모든 사서함에만 적용되며, 특정 사서함을 선택할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-p119">In Exchange, auto-apply retention labels are applied only to messages newly sent (data in transit), not to all items currently in the mailbox (data at rest). Also, auto-apply retention labels for sensitive information types and trainable classifiers apply to all mailboxes; you can't select specific mailboxes.</span></span>
  
<span data-ttu-id="95b55-p120">Exchange 공용 폴더, Skype, Teams 및 Yammer 메시지는 보존 레이블을 지원하지 않습니다. 해당 위치에서 콘텐츠를 보존하고 삭제하려면 보존 정책을 대신 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="95b55-p120">Exchange public folders, Skype, Teams and Yammer messages do not support retention labels. To retain and delete contain from these locations, use retention policies instead.</span></span>

#### <a name="only-one-retention-label-at-a-time"></a><span data-ttu-id="95b55-227">한 번에 하나의 보존 레이블만</span><span class="sxs-lookup"><span data-stu-id="95b55-227">Only one retention label at a time</span></span>

<span data-ttu-id="95b55-228">전자 메일 또는 문서에는 한 번에 하나의 보존 레이블만 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-228">An email or document can have only a single retention label applied to it at a time.</span></span> <span data-ttu-id="95b55-229">보존 레이블은 최종 사용자나 관리자가 [수동으로](create-apply-retention-labels.md#manually-apply-retention-labels) 적용하거나 다음 방법 중 하나를 사용하여 자동으로 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-229">A retention label can be applied [manually](create-apply-retention-labels.md#manually-apply-retention-labels) by an end user or admin, or automatically by using any of the following methods:</span></span>

- [<span data-ttu-id="95b55-230">자동 적용 레이블 정책</span><span class="sxs-lookup"><span data-stu-id="95b55-230">Auto-apply label policy</span></span>](apply-retention-labels-automatically.md)
- [<span data-ttu-id="95b55-231">SharePoint Syntex용 문서 이해 모델</span><span class="sxs-lookup"><span data-stu-id="95b55-231">Document understanding model for SharePoint Syntex</span></span>](https://docs.microsoft.com/microsoft-365/contentunderstanding/apply-a-retention-label-to-a-model)
- <span data-ttu-id="95b55-232">[SharePoint용 기본 레이블](create-apply-retention-labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set) 또는 [Outlook](create-apply-retention-labels.md#applying-a-default-retention-label-to-an-outlook-folder)</span><span class="sxs-lookup"><span data-stu-id="95b55-232">[Default label for SharePoint](create-apply-retention-labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set) or [Outlook](create-apply-retention-labels.md#applying-a-default-retention-label-to-an-outlook-folder)</span></span>
- [<span data-ttu-id="95b55-233">Outlook 규칙</span><span class="sxs-lookup"><span data-stu-id="95b55-233">Outlook rules</span></span>](create-apply-retention-labels.md#automatically-applying-a-retention-label-to-email-by-using-rules)

<span data-ttu-id="95b55-234">표준 보존 레이블의 경우(항목을 [레코드 또는 규제 레코드](records-management.md#records)로 표시하지 않음):</span><span class="sxs-lookup"><span data-stu-id="95b55-234">For standard retention labels (they don't mark items as a [record or regulatory record](records-management.md#records)):</span></span>

- <span data-ttu-id="95b55-235">관리자 및 최종 사용자는 콘텐츠에 적용된 기존 보존 레이블을 수동으로 변경하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-235">Admins and end users can manually change or remove an existing retention label that's applied on content.</span></span> 

- <span data-ttu-id="95b55-236">콘텐츠에 이미 보존 레이블이 적용된 경우 기존 레이블은 자동으로 제거되거나 다른 보존 레이블로 대체되지 않습니다. 한 가지 예외: 기존 레이블이 기본 레이블로 적용되었습니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-236">When content already has a retention label applied, the existing label won't be automatically removed or replaced by another retention label with one possible exception: The existing label was applied as a default label.</span></span>
    
    <span data-ttu-id="95b55-237">기본 레이블을 사용하여 적용될 때 레이블 동작에 대한 자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95b55-237">For more information about the label behavior when it's applied by using a default label:</span></span>
    - <span data-ttu-id="95b55-238">Sharepoint의 기본 레이블: [SharePoint에서 기본 레이블을 사용하는 경우 레이블 동작](create-apply-retention-labels.md#label-behavior-when-you-use-a-default-label-for-sharepoint)</span><span class="sxs-lookup"><span data-stu-id="95b55-238">Default label for SharePoint: [Label behavior when you use a default label for SharePoint](create-apply-retention-labels.md#label-behavior-when-you-use-a-default-label-for-sharepoint)</span></span>
    - <span data-ttu-id="95b55-239">Outlook의 기본 레이블: [Outlook 폴더에 기본 보존 레이블 적용](create-apply-retention-labels.md#applying-a-default-retention-label-to-an-outlook-folder)</span><span class="sxs-lookup"><span data-stu-id="95b55-239">Default label for Outlook: [Applying a default retention label to an Outlook folder](create-apply-retention-labels.md#applying-a-default-retention-label-to-an-outlook-folder)</span></span>

- <span data-ttu-id="95b55-240">보존 레이블을 적용할 수 있는 자동 적용 레이블 정책이 여러 개이고, 콘텐츠가 여러 정책의 조건을 충족하는 경우 가장 오래된 자동 적용 레이블 정책(작성 날짜 기준)의 보존 레이블이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-240">If there are multiple auto-apply label policies that could apply a retention label, and content meets the conditions of multiple policies, the retention label for the oldest auto-apply label policy (by date created) is applied.</span></span>

<span data-ttu-id="95b55-241">보존 레이블이 항목을 레코드 또는 규제 레코드로 표시하는 경우 이러한 레이블은 자동으로 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-241">When retention labels mark items as a record or a regulatory record, these labels are never automatically changed.</span></span> <span data-ttu-id="95b55-242">컨테이너 관리자만 항목을 레코드로 표시하는 보존 레이블을 수동으로 변경하거나 제거할 수 있지만, 규제 레코드는 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-242">Only admins for the container can manually change or remove retention labels that mark items as a record, but not regulatory records.</span></span> <span data-ttu-id="95b55-243">자세한 내용은 [허용 또는 차단되는 작업에 대한 제한 사항 비교](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95b55-243">For more information, see [Compare restrictions for what actions are allowed or blocked](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked).</span></span>

#### <a name="monitoring-retention-labels"></a><span data-ttu-id="95b55-244">보존 레이블 모니터링</span><span class="sxs-lookup"><span data-stu-id="95b55-244">Monitoring retention labels</span></span>

<span data-ttu-id="95b55-245">Microsoft 365 규정 준수 센터에서 **데이터 분류** > **개요** 를 사용하여 보존 레이블이 테넌트에게 어떻게 사용되고 있는지 모니터링 하고 레이블 항목의 위치를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-245">From the Microsoft 365 compliance center, use **Data classification** > **Overview** to monitor how your retention labels are being used in your tenant, and identify where your labeled items are located.</span></span> <span data-ttu-id="95b55-246">필수 구성 요소를 비롯한 더 자세한 내용은 [데이터 알기 - 데이터 분류 개요](data-classification-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95b55-246">For more information, including important prerequisites, see [Know your data - data classification overview](data-classification-overview.md).</span></span>

<span data-ttu-id="95b55-247">그런 다음 [콘텐츠 탐색기](data-classification-content-explorer.md) 및 [활동 탐색기](data-classification-activity-explorer.md)를 사용하여 세부 정보로 드릴 다운할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-247">You can then drill down into details by using [content explorer](data-classification-content-explorer.md) and [activity explorer](data-classification-activity-explorer.md).</span></span>

> [!TIP]
><span data-ttu-id="95b55-248">훈련가능한 분류자 및 민감한 정보 유형 등 다른 데이터 분류 인사이트를 사용하여 보존하거나 삭제 혹은 기록으로 관리해야 하는 콘텐츠를 식별 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-248">Consider using some of the other data classification insights, such as trainable classifiers and sensitive info types, to help you identify content that you might need to retain or delete, or manage as records.</span></span>

<span data-ttu-id="95b55-249">Office 365 보안 및 규정 준수 센터에는 **정보 거버넌스** > **대시보드** 및 **정보 거버넌스** > **레이블 활동 탐색기** 에서 더 자세한 정보에 보존 레이블에 해당하는 개요 정보가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-249">The Office 365 Security & Compliance Center has the equivalent overview information for retention labels from **Information governance** > **Dashboard**, and more detailed information from **Information governance** > **Label activity explorer**.</span></span> <span data-ttu-id="95b55-250">이 오래 된 관리 센터에서 보존 레이블을 모니터링 하는 방법에 대한 자세한 내용은 다음 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95b55-250">For more information about monitoring retention labels from this older admin center, see the following documentation:</span></span>
- [<span data-ttu-id="95b55-251">데이터 거버넌스 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="95b55-251">View the data governance reports</span></span>](view-the-data-governance-reports.md)
- [<span data-ttu-id="95b55-252">레이블 분석을 통한 레이블 사용량 보기</span><span class="sxs-lookup"><span data-stu-id="95b55-252">View label usage with label analytics</span></span>](label-analytics.md)
- [<span data-ttu-id="95b55-253">문서의 레이블 활동 보기</span><span class="sxs-lookup"><span data-stu-id="95b55-253">View label activity for documents</span></span>](view-label-activity-for-documents.md)

#### <a name="using-content-search-to-find-all-content-with-a-specific-retention-label"></a><span data-ttu-id="95b55-254">콘텐츠 검색을 사용하여 특정 보존 레이블을 사용하는 모든 콘텐츠 찾기</span><span class="sxs-lookup"><span data-stu-id="95b55-254">Using Content Search to find all content with a specific retention label</span></span>

<span data-ttu-id="95b55-255">사용자가 콘텐츠에 보존 레이블을 적용하거나 레이블이 자동 적용된 후에 콘텐츠 검색을 사용하여 특정 보존 레이블이 적용된 모든 콘텐츠를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-255">After retention labels are applied to content, either by users or auto-applied, you can use content search to find all items that have a specific retention label applied.</span></span>

<span data-ttu-id="95b55-256">콘텐츠 검색을 만들 때 **보존 레이블** 조건을 선택한 다음 보존 레이블 이름을 전체 또는 일부만 입력하고 와일드 카드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-256">When you create a content search, choose the **Retention label** condition, and then enter the complete retention label name or part of the label name and use a wildcard.</span></span> <span data-ttu-id="95b55-257">자세한 내용은 [콘텐츠 검색에 대한 키워드 쿼리 및 검색 조건](keyword-queries-and-search-conditions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95b55-257">For more information, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
![보존 레이블 조건](../media/retention-label-condition.png)


## <a name="compare-capabilities-for-retention-policies-and-retention-labels"></a><span data-ttu-id="95b55-259">보존 정책 및 보존 레이블의 기능 비교하기</span><span class="sxs-lookup"><span data-stu-id="95b55-259">Compare capabilities for retention policies and retention labels</span></span>

<span data-ttu-id="95b55-260">다음 표를 사용하여 기능을 기반으로 보존 정책을 사용할지 또는 보존 레이블을 사용할지를 식별하는 데 도움을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-260">Use the following table to help you identify whether to use a retention policy or retention label, based on capabilities.</span></span>

|<span data-ttu-id="95b55-261">기능</span><span class="sxs-lookup"><span data-stu-id="95b55-261">Capability</span></span>|<span data-ttu-id="95b55-262">보존 정책</span><span class="sxs-lookup"><span data-stu-id="95b55-262">Retention policy</span></span> |<span data-ttu-id="95b55-263">보존 레이블</span><span class="sxs-lookup"><span data-stu-id="95b55-263">Retention label</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="95b55-264">보존 후 삭제, 보존만 또는 삭제만 할 수 있는 보존 설정</span><span class="sxs-lookup"><span data-stu-id="95b55-264">Retention settings that can retain and then delete, retain-only, or delete-only</span></span> |<span data-ttu-id="95b55-265">예</span><span class="sxs-lookup"><span data-stu-id="95b55-265">Yes</span></span> |<span data-ttu-id="95b55-266">예</span><span class="sxs-lookup"><span data-stu-id="95b55-266">Yes</span></span> |
|<span data-ttu-id="95b55-267">워크로드 지원됨: </span><span class="sxs-lookup"><span data-stu-id="95b55-267">Workloads supported:</span></span> <br /><span data-ttu-id="95b55-268">- Exchange</span><span class="sxs-lookup"><span data-stu-id="95b55-268">- Exchange</span></span> <br /><span data-ttu-id="95b55-269">- SharePoint</span><span class="sxs-lookup"><span data-stu-id="95b55-269">- SharePoint</span></span> <br /><span data-ttu-id="95b55-270">- OneDrive</span><span class="sxs-lookup"><span data-stu-id="95b55-270">- OneDrive</span></span> <br /><span data-ttu-id="95b55-271">- Microsoft 365 그룹</span><span class="sxs-lookup"><span data-stu-id="95b55-271">- Microsoft 365 groups</span></span> <br /><span data-ttu-id="95b55-272">- 비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="95b55-272">- Skype for Business</span></span> <br /><span data-ttu-id="95b55-273">- Teams</span><span class="sxs-lookup"><span data-stu-id="95b55-273">- Teams</span></span><br /><span data-ttu-id="95b55-274">- Yammer</span><span class="sxs-lookup"><span data-stu-id="95b55-274">- Yammer</span></span>|<br /> <span data-ttu-id="95b55-275">예</span><span class="sxs-lookup"><span data-stu-id="95b55-275">Yes</span></span> <br /> <span data-ttu-id="95b55-276">예</span><span class="sxs-lookup"><span data-stu-id="95b55-276">Yes</span></span> <br /> <span data-ttu-id="95b55-277">예</span><span class="sxs-lookup"><span data-stu-id="95b55-277">Yes</span></span> <br /> <span data-ttu-id="95b55-278">예</span><span class="sxs-lookup"><span data-stu-id="95b55-278">Yes</span></span> <br /> <span data-ttu-id="95b55-279">예</span><span class="sxs-lookup"><span data-stu-id="95b55-279">Yes</span></span> <br /> <span data-ttu-id="95b55-280">예</span><span class="sxs-lookup"><span data-stu-id="95b55-280">Yes</span></span> <br /> <span data-ttu-id="95b55-281">예</span><span class="sxs-lookup"><span data-stu-id="95b55-281">Yes</span></span> | <br /> <span data-ttu-id="95b55-282">예, 공용 폴더 제외</span><span class="sxs-lookup"><span data-stu-id="95b55-282">Yes, except public folders</span></span> <br /> <span data-ttu-id="95b55-283">예</span><span class="sxs-lookup"><span data-stu-id="95b55-283">Yes</span></span> <br /> <span data-ttu-id="95b55-284">예</span><span class="sxs-lookup"><span data-stu-id="95b55-284">Yes</span></span> <br /> <span data-ttu-id="95b55-285">예</span><span class="sxs-lookup"><span data-stu-id="95b55-285">Yes</span></span> <br /> <span data-ttu-id="95b55-286">아니요</span><span class="sxs-lookup"><span data-stu-id="95b55-286">No</span></span> <br /> <span data-ttu-id="95b55-287">아니요</span><span class="sxs-lookup"><span data-stu-id="95b55-287">No</span></span> <br /> <span data-ttu-id="95b55-288">아니요</span><span class="sxs-lookup"><span data-stu-id="95b55-288">No</span></span> |
|<span data-ttu-id="95b55-289">자동으로 보존 적용됨</span><span class="sxs-lookup"><span data-stu-id="95b55-289">Retention applied automatically</span></span> | <span data-ttu-id="95b55-290">예</span><span class="sxs-lookup"><span data-stu-id="95b55-290">Yes</span></span> | <span data-ttu-id="95b55-291">예</span><span class="sxs-lookup"><span data-stu-id="95b55-291">Yes</span></span> |
|<span data-ttu-id="95b55-292">조건을 기준으로 보존 적용</span><span class="sxs-lookup"><span data-stu-id="95b55-292">Retention applied based on conditions</span></span> <br /> <span data-ttu-id="95b55-293">-중요한 정보 유형, KQL 쿼리, 교육 가능한 분류자</span><span class="sxs-lookup"><span data-stu-id="95b55-293">- sensitive info types, KQL queries, trainable classifiers</span></span>| <span data-ttu-id="95b55-294">아니요</span><span class="sxs-lookup"><span data-stu-id="95b55-294">No</span></span> | <span data-ttu-id="95b55-295">예</span><span class="sxs-lookup"><span data-stu-id="95b55-295">Yes</span></span> |
|<span data-ttu-id="95b55-296">수동으로 보존 적용됨</span><span class="sxs-lookup"><span data-stu-id="95b55-296">Retention applied manually</span></span> | <span data-ttu-id="95b55-297">아니요</span><span class="sxs-lookup"><span data-stu-id="95b55-297">No</span></span> | <span data-ttu-id="95b55-298">예</span><span class="sxs-lookup"><span data-stu-id="95b55-298">Yes</span></span> |
|<span data-ttu-id="95b55-299">최종 사용자를 위한 UI 존재</span><span class="sxs-lookup"><span data-stu-id="95b55-299">UI presence for end users</span></span> | <span data-ttu-id="95b55-300">아니요</span><span class="sxs-lookup"><span data-stu-id="95b55-300">No</span></span> | <span data-ttu-id="95b55-301">예</span><span class="sxs-lookup"><span data-stu-id="95b55-301">Yes</span></span> |
|<span data-ttu-id="95b55-302">콘텐츠를 이동해도 유지됨</span><span class="sxs-lookup"><span data-stu-id="95b55-302">Persists if the content is moved</span></span> | <span data-ttu-id="95b55-303">아니요</span><span class="sxs-lookup"><span data-stu-id="95b55-303">No</span></span> | <span data-ttu-id="95b55-304">예, Microsoft 365 테넌트 내에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-304">Yes, within your Microsoft 365 tenant</span></span> |
|<span data-ttu-id="95b55-305">항목을 레코드로 선언</span><span class="sxs-lookup"><span data-stu-id="95b55-305">Declare item as a record</span></span>| <span data-ttu-id="95b55-306">아니요</span><span class="sxs-lookup"><span data-stu-id="95b55-306">No</span></span> | <span data-ttu-id="95b55-307">예</span><span class="sxs-lookup"><span data-stu-id="95b55-307">Yes</span></span> |
|<span data-ttu-id="95b55-308">레이블이 지정되거나 이벤트를 기반으로 보존 기간 시작</span><span class="sxs-lookup"><span data-stu-id="95b55-308">Start the retention period when labeled or based on an event</span></span> | <span data-ttu-id="95b55-309">아니요</span><span class="sxs-lookup"><span data-stu-id="95b55-309">No</span></span> | <span data-ttu-id="95b55-310">예</span><span class="sxs-lookup"><span data-stu-id="95b55-310">Yes</span></span> |
|<span data-ttu-id="95b55-311">처리 검토</span><span class="sxs-lookup"><span data-stu-id="95b55-311">Disposition review</span></span> | <span data-ttu-id="95b55-312">아니요</span><span class="sxs-lookup"><span data-stu-id="95b55-312">No</span></span>| <span data-ttu-id="95b55-313">예</span><span class="sxs-lookup"><span data-stu-id="95b55-313">Yes</span></span> |
|<span data-ttu-id="95b55-314">최대 7년 동안 처리 증명</span><span class="sxs-lookup"><span data-stu-id="95b55-314">Proof of disposition for up to 7 years</span></span> | <span data-ttu-id="95b55-315">아니요</span><span class="sxs-lookup"><span data-stu-id="95b55-315">No</span></span> |<span data-ttu-id="95b55-316">예, 항목이 레코드로 선언되는 경우</span><span class="sxs-lookup"><span data-stu-id="95b55-316">Yes, when item is declared a record</span></span>|
|<span data-ttu-id="95b55-317">감사 관리 활동</span><span class="sxs-lookup"><span data-stu-id="95b55-317">Audit admin activities</span></span>| <span data-ttu-id="95b55-318">예</span><span class="sxs-lookup"><span data-stu-id="95b55-318">Yes</span></span> | <span data-ttu-id="95b55-319">예</span><span class="sxs-lookup"><span data-stu-id="95b55-319">Yes</span></span>|
|<span data-ttu-id="95b55-320">보존될 항목 식별:</span><span class="sxs-lookup"><span data-stu-id="95b55-320">Identify items subject to retention:</span></span> <br /> <span data-ttu-id="95b55-321">- 콘텐츠 검색</span><span class="sxs-lookup"><span data-stu-id="95b55-321">- Content Search</span></span> <br /> <span data-ttu-id="95b55-322">- 데이터 분류 페이지, 콘텐츠 탐색기, 활동 탐색기</span><span class="sxs-lookup"><span data-stu-id="95b55-322">- Data classification page, content explorer, activity explorer</span></span> | <br /> <span data-ttu-id="95b55-323">아니요</span><span class="sxs-lookup"><span data-stu-id="95b55-323">No</span></span> <br /> <span data-ttu-id="95b55-324">아니요</span><span class="sxs-lookup"><span data-stu-id="95b55-324">No</span></span> | <br /> <span data-ttu-id="95b55-325">예</span><span class="sxs-lookup"><span data-stu-id="95b55-325">Yes</span></span> <br /> <span data-ttu-id="95b55-326">예</span><span class="sxs-lookup"><span data-stu-id="95b55-326">Yes</span></span>|

<span data-ttu-id="95b55-327">보존 정책과 보존 레이블을 모두 보완 보존 방법으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-327">Note that you can use both retention policies and retention labels as complementary retention methods.</span></span> <span data-ttu-id="95b55-328">예제:</span><span class="sxs-lookup"><span data-stu-id="95b55-328">For example:</span></span>

1. <span data-ttu-id="95b55-329">콘텐츠를 마지막으로 수정한 후 5년이 지나면 콘텐츠를 자동으로 삭제하는 보존 정책을 만들고 구성하여, 모든 OneDrive 계정에 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-329">You create and configure a retention policy that automatically deletes content five years after it's last modified, and apply the policy to all OneDrive accounts.</span></span>

2. <span data-ttu-id="95b55-330">콘텐츠를 영구적으로 유지하는 보존 레이블을 만들고 구성하여, 모든 OneDrive 계정에 게시하는 레이블 정책에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-330">You create and configure a retention label that keeps content forever and add this to a label policy that you publish to all OneDrive accounts.</span></span> <span data-ttu-id="95b55-331">5년 후에 수정하지 않으면 자동 삭제에서 제외되어야 하는 특정 문서에 이 레이블을 수동으로 적용하는 방법을 사용자에게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-331">You explain to users how to manually apply this label to specific documents that should be excluded from automatic deletion if not modified after five years.</span></span>

<span data-ttu-id="95b55-332">보존 정책과 보존 레이블이 함께 작동하는 방식과 결합된 결과를 결정하는 방법에 대한 자세한 내용은 보존 원칙과 우선하는 항목을 설명하는 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95b55-332">For more information about how retention policies and retention labels work together and how to determine their combined outcome, see the next section that explains the principles of retention and what takes precedence.</span></span>

## <a name="the-principles-of-retention-or-what-takes-precedence"></a><span data-ttu-id="95b55-333">보존 원칙 또는 우선하는 항목</span><span class="sxs-lookup"><span data-stu-id="95b55-333">The principles of retention, or what takes precedence?</span></span>

<span data-ttu-id="95b55-334">콘텐츠에 작업(보존, 삭제 또는 보존 후 삭제) 및 보존 기간이 각기 다른 여러 보존 정책과 보존 레이블이 적용되어 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-334">It's possible or even likely that content might have several retention policies and retention labels applied to it, each with a different action (retain, delete, or retain and then delete) and retention period.</span></span> <span data-ttu-id="95b55-335">우선하는 항목</span><span class="sxs-lookup"><span data-stu-id="95b55-335">What takes precedence?</span></span> 

<span data-ttu-id="95b55-336">높은 수준에서는 보존이 항상 삭제보다 우선하며 가장 긴 보존 기간이 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-336">At a high level, you can be assured that retention always takes precedence over deletion, and then the longest retention period wins.</span></span> 

<span data-ttu-id="95b55-337">그러나 여기에 몇 가지 요소를 더해야 하므로, 다음 흐름을 사용하여 각 수준이 위에서 아래로의 타이 브레이커 역할을 하는 결과를 이해하세요. 결과가 첫 번째 수준에 의해 결정되면 다음 수준으로 진행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-337">However, there are a few more factors to throw into the mix, so use the following flow to understand the outcome where each level acts as a tie-breaker from top to bottom: If the outcome is determined by the first level, there's no need to progress to the next level, and so on.</span></span> <span data-ttu-id="95b55-338">해당 수준에 대한 규칙에 따라 결과를 확인할 수 없는 경우에만 흐름이 다음 수준으로 이동하여 보존 설정의 우선순위를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-338">Only if the outcome can't be determined by the rules for the level does the flow move down to the next level to determine the outcome for which retention settings take precedence.</span></span>

![보존 원칙 다이어그램](../media/1693d6ec-b340-4805-9da3-89aa41bc6afb.png)
  
<span data-ttu-id="95b55-340">네 가지 수준에 대한 설명:</span><span class="sxs-lookup"><span data-stu-id="95b55-340">Explanation for the four different levels:</span></span>
  
1. <span data-ttu-id="95b55-341">**삭제보다 보존 우선.**</span><span class="sxs-lookup"><span data-stu-id="95b55-341">**Retention wins over deletion.**</span></span> <span data-ttu-id="95b55-342">한 보존 정책에서는 3년 후 Exchange 전자 메일을 삭제하도록 구성하지만 다른 보존 정책에서는 5년 동안 Exchange 전자 메일을 보존한 다음 삭제하도록 구성한다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-342">Suppose that one retention policy is configured to delete Exchange email after three years, but another retention policy is configured to retain Exchange email for five years and then delete it.</span></span> <span data-ttu-id="95b55-343">3년에 도달하는 모든 콘텐츠는 삭제되고 사용자의 보기에서 숨겨지지만, 콘텐츠가 영구적으로 삭제되는 5년에 도달하기까지는 복구 가능한 항목 폴더에 여전히 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-343">Any content that reaches three years old will be deleted and hidden from the users' view, but still retained in the Recoverable Items folder until the content reaches five years old, when it is permanently deleted.</span></span> 
2. <span data-ttu-id="95b55-344">**가장 긴 보존 기간 우선.**</span><span class="sxs-lookup"><span data-stu-id="95b55-344">**The longest retention period wins.**</span></span> <span data-ttu-id="95b55-345">콘텐츠가 다른 기간 동안 콘텐츠를 보존하는 여러 보존 설정의 적용을 받는 경우, 가장 긴 보존 기간이 끝날 때까지 콘텐츠는 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-345">If content is subject to multiple retention settings that retain content for different periods of time, the content will be retained until the end of the longest retention period.</span></span>
    
3. <span data-ttu-id="95b55-346">**암시적 포함보다 명시적 포함 우선.**</span><span class="sxs-lookup"><span data-stu-id="95b55-346">**Explicit inclusion wins over implicit inclusion.**</span></span> <span data-ttu-id="95b55-347">의미는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-347">This means:</span></span> 
    
    1. <span data-ttu-id="95b55-348">보존 설정이 포함된 보존 레이블이 사용자에 의해 수동으로 항목(예: Exchange 전자 메일 또는 OneDrive 문서)에 할당된 경우, 해당 보존 레이블이 사이트 또는 사서함 수준에서 할당된 보존 정책이나 문서 라이브러리에 할당된 기본 보존 레이블보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-348">If a retention label with retention settings is manually assigned by a user to an item, such as an Exchange email or OneDrive document, that retention label takes precedence over both a retention policy assigned at the site or mailbox level and a default retention label assigned to the document library.</span></span> <span data-ttu-id="95b55-349">예를 들어 명시적 보존 레이블에서 10년 동안 콘텐츠를 보존하기로 구성하지만 사이트에 할당된 보존 정책에서 5년 동안만 콘텐츠를 보존하기로 구성한다면, 보존 레이블이 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-349">For example, if the explicit retention label is configured to retain content for ten years, but a retention policy assigned to the site is configured to retain content for only five years, the retention label takes precedence.</span></span>
    
    2. <span data-ttu-id="95b55-350">보존 정책에 특정 사용자의 사서함 또는 OneDrive 계정과 같이 특정 위치가 포함되는 경우 해당 보존 정책이 모든 사용자의 사서함 또는 OneDrive 계정에 적용되지만 특히 해당 사용자의 사서함을 포함하지 않는 다른 보존 정책보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-350">If a retention policy includes a specific location, such as a specific user's mailbox or OneDrive account, that retention policy takes precedence over another retention policy that applies to all users' mailboxes or OneDrive accounts but doesn't specifically include that user's mailbox.</span></span>
    
4. <span data-ttu-id="95b55-351">**가장 짧은 삭제 기간이 우선합니다.**</span><span class="sxs-lookup"><span data-stu-id="95b55-351">**The shortest deletion period wins.**</span></span> <span data-ttu-id="95b55-352">마찬가지로 콘텐츠에 보존 기간 없이 콘텐츠를 삭제하는 여러 보존 설정이 적용된 경우, 해당 콘텐츠는 가장 짧은 보존 기간이 끝나면 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-352">Similarly, if content is subject to multiple retention settings that delete content without a retention period, that content will be deleted at the end of the shortest retention period.</span></span> 

<span data-ttu-id="95b55-353">마지막으로, 보존 정책 또는 보존 레이블은 eDiscovery에 대해 보류된 모든 콘텐츠를 영구히 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-353">Finally, a retention policy or retention label cannot permanently delete any content that's on hold for eDiscovery.</span></span> <span data-ttu-id="95b55-354">보류가 해제되면 콘텐츠는 다시 워크로드의 보안 위치에서 정리 프로세스의 적용을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-354">When that hold is released, the content again becomes eligible for the cleanup process in the secured locations for the workload.</span></span>

## <a name="use-preservation-lock-to-restrict-changes-to-policies"></a><span data-ttu-id="95b55-355">유지 잠금을 사용하여 정책 변경 제한</span><span class="sxs-lookup"><span data-stu-id="95b55-355">Use Preservation Lock to restrict changes to policies</span></span>

<span data-ttu-id="95b55-356">일부 조직에서는 보존 정책을 설정한 후에 해제하거나 덜 제한적으로 설정할 수 없도록 SEC(증권 거래 위원회) 규칙 17a-4와 같은 규제 기구에서 정의한 규칙을 준수해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-356">Some organizations might need to comply with rules defined by regulatory bodies such as the Securities and Exchange Commission (SEC) Rule 17a-4, which requires that after a policy for retention is turned on, it cannot be turned off or made less restrictive.</span></span> 

<span data-ttu-id="95b55-357">유지 잠금은 조직이 관리자를 비롯하여 누구도 정책을 해제하거나 삭제하거나 덜 제한적으로 설정할 수 없도록 보존 정책 또는 보존 레이블 정책을 잠그므로 관련 규정 요구 사항을 충족할 수 있도록 보장합니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-357">Preservation Lock ensures your organization can meet such regulatory requirements because it locks a retention policy or retention label policy so that no one—including an administrator—can turn off the policy, delete the policy, or make it less restrictive.</span></span>
  
<span data-ttu-id="95b55-358">보존 정책 또는 보존 레이블 정책을 생성한 후에 유지 잠금을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-358">You apply Preservation Lock after the retention policy or retention label policy is created.</span></span> <span data-ttu-id="95b55-359">자세한 내용은 [보존 정책 및 보존 레이블 정책 변경을 제한하기 위한 유지 잠금 사용](retention-preservation-lock.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95b55-359">For more information and instructions, see [Use Preservation Lock to restrict changes to retention policies and retention label policies](retention-preservation-lock.md).</span></span>

## <a name="releasing-a-policy-for-retention"></a><span data-ttu-id="95b55-360">보존 정책 릴리스</span><span class="sxs-lookup"><span data-stu-id="95b55-360">Releasing a policy for retention</span></span>

<span data-ttu-id="95b55-361">보존 정책의 제공에는 유지 잠금이 포함되어 있지 않으므로 언제든지 정책을 삭제할 수 있어 이전에 적용된 보존 설정을 효과적으로 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-361">Providing your policies for retention don't have a Preservation Lock, you can delete your policies at any time, which effectively turns off the previously applied retention settings.</span></span> <span data-ttu-id="95b55-362">정책을 유지할 수 있지만 위치 상태를 설정 해제로 변경할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-362">You can also keep the policy but change the location status to off.</span></span>
 
<span data-ttu-id="95b55-363">해당 작업 중 하나를 수행하면 자료 보존 라이브러리에 보존되어 있는 모든 SharePoint 또는 OneDrive 콘텐츠가 즉시 및 영구적으로 삭제되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-363">When you do either of these actions, any SharePoint or OneDrive content that's being retained in the Preservation Hold library is not immediately and permanently deleted.</span></span> <span data-ttu-id="95b55-364">실수로 데이터가 손실되는 것을 방지하기 위해 30일간의 유예 기간이 있습니다. 이 기간에는 자료 보존 라이브러리에서 해당 정책에 대한 콘텐츠 만료가 발생하지 않으므로 필요한 경우 콘텐츠를 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-364">Instead, to help prevent inadvertent data loss, there is a 30-day grace period, during which content expiration for that policy does not happen in the Preservation Hold library, so that you can restore any content from there, if needed.</span></span> <span data-ttu-id="95b55-365">또한 유예 기간에 이 콘텐츠를 수동으로 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-365">Additionally, you can't manually delete this content during the grace period.</span></span>

<span data-ttu-id="95b55-366">유예 기간에 위치 상태를 다시 설정하도록 변경할 수 있으며 해당 정책에 대한 콘텐츠가 삭제되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-366">You can change the location status back to on during the grace period, and no content will be deleted for that policy.</span></span>

<span data-ttu-id="95b55-367">SharePoint 및 OneDrive의 30일간의 유예 기간은 Exchange의 30일 지연 기간에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-367">This 30-day grace period in SharePoint and OneDrive corresponds to the 30-day delay hold in Exchange.</span></span> <span data-ttu-id="95b55-368">자세한 내용은 [지연되는 사서함 관리](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95b55-368">For more information, see [Managing mailboxes on delay hold](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold).</span></span>

## <a name="auditing-retention-configuration"></a><span data-ttu-id="95b55-369">감사 보존 구성</span><span class="sxs-lookup"><span data-stu-id="95b55-369">Auditing retention configuration</span></span>

<span data-ttu-id="95b55-370">[감사가 설정되면](turn-audit-log-search-on-or-off.md) 보존 정책과 보존 레이블 관리자 작업이 감사 로그에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-370">Administrator actions for retention policies and retention labels are saved to the audit log when [auditing is enabled](turn-audit-log-search-on-or-off.md).</span></span> <span data-ttu-id="95b55-371">예를 들어, 보존 정책이나 레이블을 만들고, 구성하고 삭제 할 때 감사 이벤트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-371">For example, an audit event is created when a retention policy or label is created, configured, or deleted.</span></span> <span data-ttu-id="95b55-372">전체 목록은 [보존 정책 및 보존 레이블 활동](search-the-audit-log-in-security-and-compliance.md#retention-policy-and-retention-label-activities)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95b55-372">For the full list, see [Retention policy and retention label activities](search-the-audit-log-in-security-and-compliance.md#retention-policy-and-retention-label-activities).</span></span>

## <a name="powershell-cmdlets-for-retention-policies-and-retention-labels"></a><span data-ttu-id="95b55-373">보존 정책 및 보존 레이블의 PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="95b55-373">PowerShell cmdlets for retention policies and retention labels</span></span>

<span data-ttu-id="95b55-374">보존 정책 cmdlet을 사용하려면 먼저 [Office 365 보안 및 준수 센터 PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-374">To use the retention cmdlets, you must first [connect to the Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span> <span data-ttu-id="95b55-375">그런 다음, 다음 cmdlet 중 하나를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="95b55-375">Then, use any of the following cmdlets:</span></span>

- [<span data-ttu-id="95b55-376">Get-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="95b55-376">Get-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancetag)

- [<span data-ttu-id="95b55-377">New-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="95b55-377">New-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-compliancetag)

- [<span data-ttu-id="95b55-378">Remove-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="95b55-378">Remove-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/remove-compliancetag)

- [<span data-ttu-id="95b55-379">Set-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="95b55-379">Set-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-compliancetag)

- [<span data-ttu-id="95b55-380">Enable-ComplianceTagStorage</span><span class="sxs-lookup"><span data-stu-id="95b55-380">Enable-ComplianceTagStorage</span></span>](https://docs.microsoft.com/powershell/module/exchange/enable-compliancetagstorage)

- [<span data-ttu-id="95b55-381">Get-ComplianceTagStorage</span><span class="sxs-lookup"><span data-stu-id="95b55-381">Get-ComplianceTagStorage</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancetagstorage)

- [<span data-ttu-id="95b55-382">Get-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="95b55-382">Get-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancepolicy)

- [<span data-ttu-id="95b55-383">New-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="95b55-383">New-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancepolicy)

- [<span data-ttu-id="95b55-384">Remove-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="95b55-384">Remove-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancepolicy)

- [<span data-ttu-id="95b55-385">Set-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="95b55-385">Set-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy)

- [<span data-ttu-id="95b55-386">Get-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="95b55-386">Get-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancerule)

- [<span data-ttu-id="95b55-387">New-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="95b55-387">New-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancerule)

- [<span data-ttu-id="95b55-388">Remove-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="95b55-388">Remove-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancerule)

- [<span data-ttu-id="95b55-389">Set-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="95b55-389">Set-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancerule)

## <a name="when-to-use-retention-policies-and-retention-labels-or-ediscovery-holds"></a><span data-ttu-id="95b55-390">보존 정책 및 보존 레이블 또는 eDiscovery 보류를 사용하는 경우</span><span class="sxs-lookup"><span data-stu-id="95b55-390">When to use retention policies and retention labels or eDiscovery holds</span></span>

<span data-ttu-id="95b55-391">[eDiscovery 사례를 사용하여 생성한 보류](create-ediscovery-holds.md)와 보존 설정 둘 다에서 데이터가 영구적으로 삭제되는 것을 방지할 수 있지만 다른 시나리오에 맞게 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-391">Although retention settings and [holds that you create with an eDiscovery case](create-ediscovery-holds.md) can both prevent data from being permanently deleted, they are designed for different scenarios.</span></span> <span data-ttu-id="95b55-392">차이점을 이해하고 사용할 항목을 결정하는 데 도움을 받으려면 다음 지침을 활용하세요.</span><span class="sxs-lookup"><span data-stu-id="95b55-392">To help you understand the differences and decide which to use, use the following guidance:</span></span>

- <span data-ttu-id="95b55-393">보존 정책 및 보존 레이블에 지정할 보존 설정은 장기적인 정보 관리 전략에 맞게 설계되어 규정 준수 요구 사항에 대한 데이터를 보존하거나 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-393">Retention settings that you specify in retention policies and retention labels are designed for a long-term information governance strategy to retain or delete data for compliance requirements.</span></span> <span data-ttu-id="95b55-394">일반적으로 범위가 넓으며, 개별 사용자보다는 위치와 콘텐츠에 중점을 둡니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-394">The scope is usually broad with the main focus being the location and content rather than individual users.</span></span> <span data-ttu-id="95b55-395">추가 관리자 개입 없이 콘텐츠를 자동으로 삭제하는 옵션을 사용하여 보존 기간의 시작과 끝을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-395">The start and end of the retention period is configurable, with the option to automatically delete content without additional administrator intervention.</span></span>

- <span data-ttu-id="95b55-396">eDiscovery를 위한 보류(Core eDiscovery 또는 Advanced eDiscovery 사례)는 제한된 기간 동안 법적 조사를 위해 데이터를 보존하도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-396">Holds for eDiscovery (either Core eDiscovery or Advanced eDiscovery cases) are designed for a limited duration to preserve data for a legal investigation.</span></span> <span data-ttu-id="95b55-397">범위는 확인된 사용자가 소유한 콘텐츠에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-397">The scope is specific with the focus being content owned by identified users.</span></span> <span data-ttu-id="95b55-398">보존 기간의 시작과 끝은 구성할 수 없지만 보류가 해제될 때 콘텐츠를 자동으로 삭제하는 옵션이 없으면 개별 관리자 작업에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-398">The start and end of the preservation period isn't configurable but dependent on individual administrator actions, without an option to automatically delete content when the hold is released.</span></span>

<span data-ttu-id="95b55-399">보류와 보존을 비교하는 요약:</span><span class="sxs-lookup"><span data-stu-id="95b55-399">Summary to compare retention with holds:</span></span>

|<span data-ttu-id="95b55-400">고려 사항</span><span class="sxs-lookup"><span data-stu-id="95b55-400">Consideration</span></span>|<span data-ttu-id="95b55-401">보존</span><span class="sxs-lookup"><span data-stu-id="95b55-401">Retention</span></span> |<span data-ttu-id="95b55-402">eDiscovery 보존</span><span class="sxs-lookup"><span data-stu-id="95b55-402">eDiscovery holds</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="95b55-403">비즈니스 요구 사항:</span><span class="sxs-lookup"><span data-stu-id="95b55-403">Business need:</span></span> |<span data-ttu-id="95b55-404">규정 준수</span><span class="sxs-lookup"><span data-stu-id="95b55-404">Compliance</span></span> |<span data-ttu-id="95b55-405">법률 정보</span><span class="sxs-lookup"><span data-stu-id="95b55-405">Legal</span></span> |
|<span data-ttu-id="95b55-406">시간 범위:</span><span class="sxs-lookup"><span data-stu-id="95b55-406">Time scope:</span></span> |<span data-ttu-id="95b55-407">장기</span><span class="sxs-lookup"><span data-stu-id="95b55-407">Long-term</span></span> |<span data-ttu-id="95b55-408">단기</span><span class="sxs-lookup"><span data-stu-id="95b55-408">Short-term</span></span> |
|<span data-ttu-id="95b55-409">포커스:</span><span class="sxs-lookup"><span data-stu-id="95b55-409">Focus:</span></span> |<span data-ttu-id="95b55-410">광범위, 내용 기반</span><span class="sxs-lookup"><span data-stu-id="95b55-410">Broad, content-based</span></span> |<span data-ttu-id="95b55-411">특정, 사용자 기반</span><span class="sxs-lookup"><span data-stu-id="95b55-411">Specific, user-based</span></span> |
|<span data-ttu-id="95b55-412">시작 및 종료일 구성 가능:</span><span class="sxs-lookup"><span data-stu-id="95b55-412">Start and end date configurable:</span></span> |<span data-ttu-id="95b55-413">예</span><span class="sxs-lookup"><span data-stu-id="95b55-413">Yes</span></span> |<span data-ttu-id="95b55-414">아니요</span><span class="sxs-lookup"><span data-stu-id="95b55-414">No</span></span> |
|<span data-ttu-id="95b55-415">콘텐츠 삭제:</span><span class="sxs-lookup"><span data-stu-id="95b55-415">Content deletion:</span></span> |<span data-ttu-id="95b55-416">예(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="95b55-416">Yes (optional)</span></span> |<span data-ttu-id="95b55-417">아니요</span><span class="sxs-lookup"><span data-stu-id="95b55-417">No</span></span> |
|<span data-ttu-id="95b55-418">관리 오버 헤드:</span><span class="sxs-lookup"><span data-stu-id="95b55-418">Administrative overheads:</span></span> |<span data-ttu-id="95b55-419">낮음</span><span class="sxs-lookup"><span data-stu-id="95b55-419">Low</span></span> |<span data-ttu-id="95b55-420">높음</span><span class="sxs-lookup"><span data-stu-id="95b55-420">High</span></span> |

<span data-ttu-id="95b55-421">콘텐츠가 보존 설정과 eDiscovery 보류의 영향을 모두 받는 경우 eDiscovery 보류의 콘텐츠 보존이 항상 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-421">If content is subject to both retention settings and an eDiscovery hold, preserving content for the eDiscovery hold always takes precedence.</span></span> <span data-ttu-id="95b55-422">이렇게 하면 [보존 원칙](#the-principles-of-retention-or-what-takes-precedence)은 관리자가 보류를 수동으로 릴리스할 때까지 데이터가 유지되기 때문에 eDiscovery 보류로 확장됩니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-422">In this way, the [principles of retention](#the-principles-of-retention-or-what-takes-precedence) expand to eDiscovery holds because they preserve data until an administrator manually releases the hold.</span></span> <span data-ttu-id="95b55-423">그러나 이러한 우선 순위에도 불구하고 장기적인 정보 거버넌스에 eDiscovery 보류를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-423">However, despite this precedence, don't use eDiscovery holds for long-term information governance.</span></span> <span data-ttu-id="95b55-424">데이터 자동 삭제가 염려되는 경우 항목을 영구적으로 보존하도록 보존 설정을 구성하거나 보존 레이블과 함께 [처리 검토](disposition.md#disposition-reviews)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-424">If you are concerned about automatic deletion of data, you can configure retention settings to retain items forever, or use [disposition review](disposition.md#disposition-reviews) with retention labels.</span></span>

<span data-ttu-id="95b55-425">오래된 eDiscovery 도구를 사용하여 데이터를 보존하는 경우, 다음 리소스를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95b55-425">If you are using older eDiscovery tools to preserve data, see the following resources:</span></span>

- <span data-ttu-id="95b55-426">Exchange:</span><span class="sxs-lookup"><span data-stu-id="95b55-426">Exchange:</span></span> 
    - [<span data-ttu-id="95b55-427">원본 위치 유지 및 소송 보존</span><span class="sxs-lookup"><span data-stu-id="95b55-427">In-Place Hold and Litigation Hold</span></span>](https://go.microsoft.com/fwlink/?linkid=846124)
    - [<span data-ttu-id="95b55-428">Exchange Online 사서함의 보류 유형을 식별하는 방법</span><span class="sxs-lookup"><span data-stu-id="95b55-428">How to identify the type of hold placed on an Exchange Online mailbox</span></span>](https://docs.microsoft.com/microsoft-365/compliance/identify-a-hold-on-an-exchange-online-mailbox)

- <span data-ttu-id="95b55-429">SharePoint 및 OneDrive:</span><span class="sxs-lookup"><span data-stu-id="95b55-429">SharePoint and OneDrive:</span></span> 
    - [<span data-ttu-id="95b55-430">eDiscovery 센터에서 사례에 콘텐츠 추가 및 원본 우 위치 유지</span><span class="sxs-lookup"><span data-stu-id="95b55-430">Add content to a case and place sources on hold in the eDiscovery Center</span></span>](https://docs.microsoft.com/SharePoint/governance/add-content-to-a-case-and-place-sources-on-hold-in-the-ediscovery-center)

- [<span data-ttu-id="95b55-431">eDiscovery 도구의 사용 중지</span><span class="sxs-lookup"><span data-stu-id="95b55-431">Retirement of legacy eDiscovery tools</span></span>](legacy-ediscovery-retirement.md)

## <a name="use-retention-policies-and-retention-labels-instead-of-older-features"></a><span data-ttu-id="95b55-432">이전 기능 대신 보존 정책 및 보존 레이블 사용하기</span><span class="sxs-lookup"><span data-stu-id="95b55-432">Use retention policies and retention labels instead of older features</span></span>

<span data-ttu-id="95b55-433">정보 거버넌스를 위해 Microsoft 365에서 콘텐츠를 사전에 보존하거나 삭제해야 하는 경우에는 다음과 같은 이전 기능 대신 보존 정책 및 보존 레이블을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-433">If you need to proactively retain or delete content in Microsoft 365 for information governance, we recommend that you use retention policies and retention labels instead of the following older features.</span></span>

<span data-ttu-id="95b55-434">현재 이러한 이전 기능을 사용하는 경우 해당 기능은 보존 정책 및 레이블과 함께 계속해서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-434">If you currently use these older features, they will continue to work side-by-side with retention policies and retention labels.</span></span> <span data-ttu-id="95b55-435">하지만 앞으로는 보존 정책 및 보존 레이블을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-435">However, we recommend that going forward, you use retention policies and retention labels instead.</span></span> <span data-ttu-id="95b55-436">Microsoft 365 전체에서 콘텐츠의 보존 및 삭제를 중앙에서 관리하는 단일 메커니즘을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-436">They provide you with a single mechanism to centrally manage both retention and deletion of content across Microsoft 365.</span></span>

<span data-ttu-id="95b55-437">**Exchange Online의 이전 기능:**</span><span class="sxs-lookup"><span data-stu-id="95b55-437">**Older features from Exchange Online:**</span></span>

- <span data-ttu-id="95b55-438">[보존 태그 및 보존 정책](https://go.microsoft.com/fwlink/?linkid=846125), [[MRM(메시징 레코드 관리)](https://go.microsoft.com/fwlink/?linkid=846126)라고도 함(삭제만 해당)</span><span class="sxs-lookup"><span data-stu-id="95b55-438">[Retention tags and retention policies](https://go.microsoft.com/fwlink/?linkid=846125), also known as [messaging records management (MRM)](https://go.microsoft.com/fwlink/?linkid=846126) (deletion only)</span></span>

<span data-ttu-id="95b55-439">**SharePoint 및 OneDrive의 이전 기능:**</span><span class="sxs-lookup"><span data-stu-id="95b55-439">**Older features from SharePoint and OneDrive:**</span></span>

- <span data-ttu-id="95b55-440">[문서 삭제 정책](https://support.office.com/article/Create-a-document-deletion-policy-in-SharePoint-Server-2016-4fe26e19-4849-4eb9-a044-840ab47458ff)(삭제만 해당)</span><span class="sxs-lookup"><span data-stu-id="95b55-440">[Document deletion policies](https://support.office.com/article/Create-a-document-deletion-policy-in-SharePoint-Server-2016-4fe26e19-4849-4eb9-a044-840ab47458ff) (deletion only)</span></span>
    
- <span data-ttu-id="95b55-441">[현재 위치 레코드 관리 구성](https://support.office.com/article/7707a878-780c-4be6-9cb0-9718ecde050a) (보존만 해당)</span><span class="sxs-lookup"><span data-stu-id="95b55-441">[Configuring in place records management](https://support.office.com/article/7707a878-780c-4be6-9cb0-9718ecde050a) (retention only)</span></span> 
    
- <span data-ttu-id="95b55-442">[사이트 폐쇄 및 삭제에 대한 정책 사용](https://support.microsoft.com/ko-KR/office/use-policies-for-site-closure-and-deletion-a8280d82-27fd-48c5-9adf-8a5431208ba5) (삭제만 해당)</span><span class="sxs-lookup"><span data-stu-id="95b55-442">[Use policies for site closure and deletion](https://support.microsoft.com/ko-KR/office/use-policies-for-site-closure-and-deletion-a8280d82-27fd-48c5-9adf-8a5431208ba5) (deletion only)</span></span> 
    
- <span data-ttu-id="95b55-443">[정보 관리 정책](intro-to-info-mgmt-policies.md) (삭제만 해당)</span><span class="sxs-lookup"><span data-stu-id="95b55-443">[Information management policies](intro-to-info-mgmt-policies.md) (deletion only)</span></span>
     
<span data-ttu-id="95b55-444">콘텐츠 유형 정책 또는 정보 관리 정책에 대해 SharePoint 사이트를 구성하여 목록이나 라이브러리에 대한 콘텐츠를 보존하는 경우 보존 정책이 유효하는 동안 해당 정책은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="95b55-444">If you have configured SharePoint sites for content type policies or information management policies to retain content for a list or library, those policies are ignored while a retention policy is in effect.</span></span> 

## <a name="related-information"></a><span data-ttu-id="95b55-445">관련 정보</span><span class="sxs-lookup"><span data-stu-id="95b55-445">Related information</span></span>

- [<span data-ttu-id="95b55-446">SharePoint Online 제한 사항</span><span class="sxs-lookup"><span data-stu-id="95b55-446">SharePoint Online Limits</span></span>](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)
- [<span data-ttu-id="95b55-447">Microsoft Teams의 제한 사항 및 사양</span><span class="sxs-lookup"><span data-stu-id="95b55-447">Limits and specifications for Microsoft Teams</span></span>](https://docs.microsoft.com/microsoftteams/limits-specifications-teams) 
- [<span data-ttu-id="95b55-448">정보 거버넌스 및 레코드 관리를 위해 규정 요구 사항을 충족할 수 있도록 도움이 되는 리소스</span><span class="sxs-lookup"><span data-stu-id="95b55-448">Resources to help you meet regulatory requirements for information governance and records management</span></span>](retention-regulatory-requirements.md)

## <a name="next-steps"></a><span data-ttu-id="95b55-449">다음 단계</span><span class="sxs-lookup"><span data-stu-id="95b55-449">Next steps</span></span>

<span data-ttu-id="95b55-450">보존 정책을 만들 준비가 되었으면 [보존 정책 만들기 및 구성하기](create-retention-policies.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95b55-450">If you are ready to create retention policies, see [Create and configure retention policies](create-retention-policies.md).</span></span>

<span data-ttu-id="95b55-451">보존 레이블을 만들고 적용하려면:</span><span class="sxs-lookup"><span data-stu-id="95b55-451">To create and apply retention labels:</span></span>
- [<span data-ttu-id="95b55-452">보존 레이블을 만들고 앱에 적용하기</span><span class="sxs-lookup"><span data-stu-id="95b55-452">Create retention labels and apply them in apps</span></span>](create-apply-retention-labels.md)
- [<span data-ttu-id="95b55-453">보존 레이블을 콘텐츠에 자동으로 적용하기</span><span class="sxs-lookup"><span data-stu-id="95b55-453">Apply a retention label to content automatically</span></span>](apply-retention-labels-automatically.md)

