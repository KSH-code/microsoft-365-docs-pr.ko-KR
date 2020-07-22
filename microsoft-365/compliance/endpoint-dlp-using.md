---
title: 끝점 데이터 손실 방지(미리 보기) 사용
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
description: DLP(데이터 손실 방지) 정책을 구성하여 Microsoft 365 끝점 데이터 손실 방지(EPDLP) 위치를 사용하는 방법을 알아봅니다.
ms.openlocfilehash: c65b1f7ed97fc0400d88eecadfa2081a940bac41
ms.sourcegitcommit: a08103bc120bdec7cfeaf67c1be4e221241e69ad
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/21/2020
ms.locfileid: "45199964"
---
# <a name="using-endpoint-data-loss-prevention-preview"></a><span data-ttu-id="3540a-103">끝점 데이터 손실 방지(미리 보기) 사용</span><span class="sxs-lookup"><span data-stu-id="3540a-103">Using Endpoint data loss prevention (preview)</span></span>

<span data-ttu-id="3540a-104">이 문서에서는 장치를 위치로 사용하는 DLP 정책을 만들고 수정하는 3가지 시나리오를 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-104">This article walks you through three scenarios where you create and modify a DLP policy that uses devices as a location.</span></span>

## <a name="dlp-settings"></a><span data-ttu-id="3540a-105">DLP 설정</span><span class="sxs-lookup"><span data-stu-id="3540a-105">DLP settings</span></span>

<span data-ttu-id="3540a-106">시작하기 전에 모든 장치에 대한 DLP 정책에 적용되는 DLP 설정을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-106">Before you get started you should set up your DLP settings which are applied to all DLP policies for devices.</span></span> <span data-ttu-id="3540a-107">적용되는 정책을 만들려면 다음을 반드시 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-107">You must configure these if you intend to create policies that enforce:</span></span>

- <span data-ttu-id="3540a-108">클라우드 송신 제한 사항</span><span class="sxs-lookup"><span data-stu-id="3540a-108">cloud egress restrictions</span></span>
- <span data-ttu-id="3540a-109">허용되지 않는 앱 제한 사항</span><span class="sxs-lookup"><span data-stu-id="3540a-109">unallowed apps restrictions</span></span>

<span data-ttu-id="3540a-110">또는</span><span class="sxs-lookup"><span data-stu-id="3540a-110">Or</span></span>

- <span data-ttu-id="3540a-111">모니터링에서 잡음이 있는 파일 경로를 제외해야 하는 경우</span><span class="sxs-lookup"><span data-stu-id="3540a-111">If you what to exclude noisy file paths from monitoring</span></span>

![DLP 설정](../media/endpoint-dlp-1-using-dlp-settings.png)

### <a name="file-path-exclusions"></a><span data-ttu-id="3540a-113">파일 경로 제외</span><span class="sxs-lookup"><span data-stu-id="3540a-113">File path exclusions</span></span>

<span data-ttu-id="3540a-114">지나치게 잡음이 많거나 관심 있는 파일을 포함하지 않으므로 장치에서 DLP 모니터링, DLP 경고, DLP 정책 적용에서 특정 경로를 제외하고자 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-114">You may want to exclude certain paths from DLP monitoring, DLP alerting, and DLP policy enforcement on your devices because they are too noisy or don’t contain files you are interested in.</span></span> <span data-ttu-id="3540a-115">해당 위치에서 파일을 감사하지 않으며 해당 위치에서 만들어지거나 수정된 모든 파일에 DLP 정책 적용이 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-115">Files in those locations will not be audited and any files that are created or modified in those locations will not be subject to DLP policy enforcement.</span></span> <span data-ttu-id="3540a-116">DLP 설정에서 경로 제외를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-116">You can configure path exclusions in DLP settings.</span></span>

<span data-ttu-id="3540a-117">이 논리를 사용하여 제외 경로를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-117">You can use this logic to construct your exclusion paths:</span></span>

- <span data-ttu-id="3540a-118">‘\로 끝나는 올바른 파일 경로입니다. 이는 폴더 바로 아래에 있는 파일만을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-118">Valid file path that ends with ‘\’, which means only files directly under folder.</span></span> <span data-ttu-id="3540a-119">예시: C:\Temp</span><span class="sxs-lookup"><span data-stu-id="3540a-119">For example: C:\Temp</span></span>\
- <span data-ttu-id="3540a-120">‘\*’로 끝나는 올바른 파일 경로입니다. 이는 폴더 바로 아래에 있는 파일 외에 하위 폴더 바로 아래에 있는 파일만을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-120">Valid file path that ends with ‘\*’, which means only files under sub-folders, besides the files directly under the folder.</span></span> <span data-ttu-id="3540a-121">예시: C:\Temp\*</span><span class="sxs-lookup"><span data-stu-id="3540a-121">For example: C:\Temp\*</span></span>
- <span data-ttu-id="3540a-122">‘\’ 또는 ‘\*’로 끝나는 올바른 파일 경로입니다. 이는 폴더 및 모든 하위 폴더 바로 아래에 있는 모든 파일을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-122">Valid file path that ends without ‘\’ or ‘\*’, which means all files directly under folder and all sub-folders.</span></span> <span data-ttu-id="3540a-123">예시: C:\Temp</span><span class="sxs-lookup"><span data-stu-id="3540a-123">For example: C:\Temp</span></span>
- <span data-ttu-id="3540a-124">각 면의 '\' 사이에 와일드카드가 있는 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-124">A path with wildcard between ‘\’ from each side.</span></span> <span data-ttu-id="3540a-125">예시: C:\Users\*\Desktop</span><span class="sxs-lookup"><span data-stu-id="3540a-125">For example: C:\Users\*\Desktop</span></span>\
- <span data-ttu-id="3540a-126">정확한 하위 폴더 수를 제공하기 위해 각 면의 '\' 사이에 와일드카드와 '(숫자)'가 있는 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-126">A path with wildcard between ‘\’ from each side and with ‘(number)’ to give exact number of subfolders.</span></span> <span data-ttu-id="3540a-127">예시: C:\Users\*(1)\Downloads</span><span class="sxs-lookup"><span data-stu-id="3540a-127">For example: C:\Users\*(1)\Downloads</span></span>\
- <span data-ttu-id="3540a-128">시스템 환경 변수를 사용하는 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-128">A path with SYSTEM environment variables.</span></span> <span data-ttu-id="3540a-129">예시: %SystemDrive%\Test\*</span><span class="sxs-lookup"><span data-stu-id="3540a-129">For example: %SystemDrive%\Test\*</span></span>
- <span data-ttu-id="3540a-130">위의 모든 것을 혼합한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-130">A mix of all the above.</span></span> <span data-ttu-id="3540a-131">예시: %SystemDrive%\Users\*\Documents\*(2)\Sub</span><span class="sxs-lookup"><span data-stu-id="3540a-131">For example: %SystemDrive%\Users\*\Documents\*(2)\Sub</span></span>\

### <a name="service-domains"></a><span data-ttu-id="3540a-132">서비스 도메인</span><span class="sxs-lookup"><span data-stu-id="3540a-132">Service domains</span></span>

<span data-ttu-id="3540a-133">Edge Chromium이 끝점 DLP 정책 클라우드 업로드 액세스 제한을 적용할 때 참조하는 도메인을 이 목록에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-133">You can add domains to this list that Edge Chromium will refer to when enforcing the Endpoint DLP policy cloud upload access restriction.</span></span> 

<span data-ttu-id="3540a-134">목록 모드가 **차단**으로 설정되어 있으면 사용자는 해당 도메인에 중요한 항목을 업로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-134">If the list mode is set to **Block**, then user will not be able to upload sensitive items to those domains.</span></span> <span data-ttu-id="3540a-135">항목이 DLP 정책과 일치하여 업로드 작업이 차단되면 DLP가 경고를 생성하거나 중요한 항목의 업로드를 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-135">When an upload action is blocked because an item matches a DLP policy, DLP will either generate a warning or block the upload of the sensitive item.</span></span>

<span data-ttu-id="3540a-136">목록 모드가 **허용**으로 설정되어 있으면 사용자가 ***오직*** 해당 도메인에만 중요한 항목을 업로드할 수 있으며, 다른 모든 도메인에 대한 업로드는 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-136">If the list mode is set to **Allow**, then users will be able to upload sensitive items ***only*** to those domains, and upload access to all other domains is not allowed.</span></span>

### <a name="unallowed-apps"></a><span data-ttu-id="3540a-137">허용되지 않는 앱</span><span class="sxs-lookup"><span data-stu-id="3540a-137">Unallowed apps</span></span>

<span data-ttu-id="3540a-138">정책의 **허용되지 않은 앱 및 브라우저에 의한 액세스** 설정이 켜져 있고 사용자가 이러한 앱을 사용하여 보호된 파일에 액세스하려고 하면, 활동이 허용 또는 차단되거나, 아니면 차단되지만 사용자가 제한을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-138">When a policy's **Access by unallowed apps and browsers** setting is turned on and users attempt to use these apps to access a protected file, the activity will be allowed, blocked, or blocked but users can override the restriction.</span></span> <span data-ttu-id="3540a-139">모든 활동을 감사하며 활동 탐색기에서 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-139">All activity is audited and available to review in activity explorer.</span></span>

### <a name="unallowed-browsers"></a><span data-ttu-id="3540a-140">허용되지 않는 브라우저</span><span class="sxs-lookup"><span data-stu-id="3540a-140">Unallowed browsers</span></span>

<span data-ttu-id="3540a-141">클라우드 서비스 제한에 업로드가 차단 또는 재설정을 차단하는 것으로 설정되어 있는 적용된 DLP 정책의 조건과 일치하는 파일에 액세스하지 못하도록 차단된 프로세스 이름으로 식별되는 브라우저를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-141">You add browsers, identified by their process names, that will be blocked from accessing files that match the conditions of an enforced  a DLP policy where the upload to cloud services restriction is set to block or block override.</span></span> <span data-ttu-id="3540a-142">이 브라우저가 파일에 액세스하지 못하도록 차단되면 최종 사용자에게 Edge Chromium를 통해 파일을 열도록 요청하는 알림 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-142">When these browsers are blocked from accessing a file, the end users will see a toast notification asking them to open the file through Edge Chromium.</span></span>

## <a name="tying-dlp-settings-together"></a><span data-ttu-id="3540a-143">DLP 설정 함께 연결</span><span class="sxs-lookup"><span data-stu-id="3540a-143">Tying DLP settings together</span></span>

<span data-ttu-id="3540a-144">끝점 DLP 및 Edge Chromium 웹 브라우저를 사용하여 중요한 항목이 허용되지 않는 클라우드 앱 및 서비스에 대한 의도하지 않은 공유를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-144">With Endpoint DLP and Edge Chromium Web browser, you can restrict unintentional sharing of sensitive items to unallowed cloud apps and services.</span></span> <span data-ttu-id="3540a-145">Edge Chromium은 항목이 끝점 DLP 정책으로 제한되는 경우에 대해 이해하고 액세스 제한을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-145">Edge Chromium understands when an item is restricted by an Endpoint DLP policy and enforces access restrictions.</span></span>

<span data-ttu-id="3540a-146">올바르게 구성된 DLP 정책 및 Edge Chromium 브라우저에서 끝점 DLP를 위치로 사용하는 경우 이러한 설정에 정의된 허용되지 않는 브라우저는 DLP 정책 컨트롤과 일치하는 중요한 항목에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-146">When you use Endpoint DLP as a location in a properly configured DLP policy and the Edge Chromium browser, the unallowed browsers that you've defined in these settings will be prevented from accessing the sensitive items that match your DLP policy controls.</span></span> <span data-ttu-id="3540a-147">대신 사용자는 Edge Chromium을 사용하도록 리디렉션되며 Edge Chromium이 DLP 적용 제한 사항을 이해하여 DLP 정책의 조건을 충족하는 경우 활동을 차단하거나 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-147">Instead, users will be redirected to use Edge Chromium and Edge Chromium, with its understanding of DLP imposed restrictions, can block or restrict activities when the conditions in the DLP policy are met.</span></span>

<span data-ttu-id="3540a-148">이 제한을 사용하려면 중요한 3가지 부분을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-148">To use this restriction you’ll need to configure three important pieces:</span></span>

1. <span data-ttu-id="3540a-149">중요한 항목이 공유되지 않도록 하려는 위치(서비스, 도메인, IP 주소) 지정 </span><span class="sxs-lookup"><span data-stu-id="3540a-149">Specify the places – services, domains, IP addresses – that you want to prevent sensitive items from being shared to</span></span>
2. <span data-ttu-id="3540a-150">DLP 정책이 일치하는 경우 특정 중요한 항목에 액세스할 수 없는 브라우저 추가</span><span class="sxs-lookup"><span data-stu-id="3540a-150">Add the browsers that aren’t allowed to access certain sensitive items when a DLP policy match occurs</span></span>
3. <span data-ttu-id="3540a-151">**클라우드 서비스 업로드**와 **허용되지 않은 브라우저에서 액세스** 설정을 사용하여 업로드가 해당 위치로 제한되어야 하는 중요한 항목의 종류를 정의하는 DLP 정책 구성</span><span class="sxs-lookup"><span data-stu-id="3540a-151">Configure DLP policies to define the kinds of sensitive items for which upload should be restricted to these places by turning on **Upload to cloud services** and **Access from unallowed browser**.</span></span>

<span data-ttu-id="3540a-152">새 서비스, 앱 및 정책을 계속 추가하여 비즈니스 요구 사항을 충족하고 중요한 데이터를 보호하는 데 필요한 제한을 확장하고 강화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-152">You can continue to add new services, apps, and policies to extend and augment your restrictions to meet your business needs and protect sensitive data.</span></span> 

<span data-ttu-id="3540a-153">이 구성은 사용자가 중요하지 않은 항목에 액세스하고 공유하지 못하도록 하는 불필요한 제한을 피하는 동시에 데이터를 안전하게 유지하는 데도 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-153">This configuration will help ensure your data remains safe while also avoiding unnecessary restrictions that prevent or restrict users from accessing and sharing non-sensitive items.</span></span>

## <a name="endpoint-dlp-policy-scenarios"></a><span data-ttu-id="3540a-154">끝점 DLP 정책 시나리오</span><span class="sxs-lookup"><span data-stu-id="3540a-154">Endpoint DLP policy scenarios</span></span>

<span data-ttu-id="3540a-155">끝점 DLP 기능과 해당 기능이 DLP 정책에 나오는 방법에 대한 자세한 내용은 다음 몇 가지 시나리오를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3540a-155">To help familiarize you with Endpoint DLP features and how they surface in DLP policies, we've put together some scenarios for you to follow.</span></span> <span data-ttu-id="3540a-156">끝점 DLP를 일반적으로 사용할 수 있을 때 모든 끝점 DLP 콘텐츠는 기본 DLP 콘텐츠 집합에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-156">All the Endpoint DLP content will be folded in to the main DLP content set when Endpoint DLP becomes generally available.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3540a-157">이러한 끝점 DLP 시나리오는 DLP 정책을 만들고 조정하는 공식 절차가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-157">These Endpoint DLP scenarios are not the official procedures for creating and tuning DLP policies.</span></span> <span data-ttu-id="3540a-158">일반적으로 DLP 정책을 사용해야 하는 경우 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3540a-158">Refer to the below topics when you need to work with DLP policies in general situations:</span></span>
>- [<span data-ttu-id="3540a-159">데이터 손실 방지의 개요</span><span class="sxs-lookup"><span data-stu-id="3540a-159">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
>- [<span data-ttu-id="3540a-160">기본 DLP 정책을 사용하여 시작</span><span class="sxs-lookup"><span data-stu-id="3540a-160">Get started with the default DLP policy</span></span>](get-started-with-the-default-dlp-policy.md)
>- [<span data-ttu-id="3540a-161">템플릿에서 DLP 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="3540a-161">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
>- [<span data-ttu-id="3540a-162">DLP 정책 만들기, 테스트 및 조정</span><span class="sxs-lookup"><span data-stu-id="3540a-162">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)

### <a name="scenario-1-create-a-policy-from-a-template-audit-only"></a><span data-ttu-id="3540a-163">시나리오 1: 템플릿으로 정책 만들기, 감사 전용</span><span class="sxs-lookup"><span data-stu-id="3540a-163">Scenario 1: Create a policy from a template, audit only</span></span>

<span data-ttu-id="3540a-164">이 시나리오에서는 이미 장치가 온보딩되어 활동 탐색기에 보고되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-164">These scenarios require that you already have devices onboarded and reporting into Activity explorer.</span></span> <span data-ttu-id="3540a-165">아직 장치를 온보딩하지 않은 경우 [끝점 데이터 손실 방지(미리 보기)](endpoint-dlp-getting-started.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3540a-165">If you haven't onboarded devices yet, see [Get started with Endpoint data loss prevention (preview)](endpoint-dlp-getting-started.md).</span></span>

1. <span data-ttu-id="3540a-166">[데이터 손실 방지 페이지](https://compliance.microsoft.com/datalossprevention?viewid=policies)를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-166">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span></span>
2. <span data-ttu-id="3540a-167">**정책 만들기(미리 보기)** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-167">Choose **Create policy (preview)**.</span></span>
3. <span data-ttu-id="3540a-168">이 시나리오에서는 **개인 정보**를 선택한 다음 **미국 PII(개인 식별 정보) 데이터**를 선태한 후 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-168">For this scenario, choose **Privacy**, then **U.S. Personally Identifiable Information (PII) Data** and choose **Next**.</span></span>
4. <span data-ttu-id="3540a-169">**장치**를 제외한 모든 위치에서 **상태** 필드를 해제로 전환합니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-169">Toggle the **Status** field to off for all locations except **Devices**.</span></span> <span data-ttu-id="3540a-170">**다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-170">Choose **Next**.</span></span>
5. <span data-ttu-id="3540a-171">기본 설정인 **템플릿에서 설정 검토 및 사용자 지정** 선택을 그대로 사용하고 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-171">Accept the default **Review and customize settings from the template** selection and choose **Next**.</span></span>
6. <span data-ttu-id="3540a-172">기본 설정인 **이 콘텐츠가 공유되는 경우에 검색**과 **조직 외부의 사용자와** 선택을 사용하고 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-172">Accept the default **Detect when this content is shared** and **With people outside my organization** selections and choose **Next**.</span></span>
7. <span data-ttu-id="3540a-173">기본 설정인 **보호 작업** 값을 적용하고 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-173">Accept the default **Protection actions** values and choose **Next**.</span></span>
8. <span data-ttu-id="3540a-174">**Windows 장치에서 활동 감사 또는 제한**을 선택하고 작업을 **감사 전용**으로 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-174">Select **Audit or restrict activities on Windows devices** and leave the actions set to **Audit only**.</span></span> <span data-ttu-id="3540a-175">**다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-175">Choose **Next**.</span></span>
9. <span data-ttu-id="3540a-176">기본 설정인 **먼저 테스트하고 싶습니다**를 적용하고 **테스트 모드에서 정책 팁 표시**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-176">Accept the default **I'd like to test it out first** value and choose **Show policy tips while in test mode**.</span></span> <span data-ttu-id="3540a-177">**다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-177">Choose **Next**.</span></span>
10. <span data-ttu-id="3540a-178">설정을 검토하고 **제출**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-178">Review your settings and choose **Submit**.</span></span>
11. <span data-ttu-id="3540a-179">새 DLP 정책이 정책 목록에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-179">The new DLP policy will appear in the policy list.</span></span>
12. <span data-ttu-id="3540a-180">모니터링되는 끝점에서 데이터에 대한 활동 탐색기를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-180">Check Activity explorer for data from the monitored endpoints.</span></span> <span data-ttu-id="3540a-181">장치에 대한 위치 필터를 설정하고 정책을 추가한 다음 정책 이름을 기준으로 필터링하여 정책의 영향을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-181">Set the location filter for devices and add the policy, then filter by policy name to see the impact of this policy.</span></span> <span data-ttu-id="3540a-182">필요한 경우 [활동 탐색기로 시작](data-classification-activity-explorer.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3540a-182">See, [Get started with activity explorer](data-classification-activity-explorer.md) if needed.</span></span>
13. <span data-ttu-id="3540a-183">조직 외부의 사용자와 미국 PII(개인 식별 정보) 데이터 조건을 트리거하는 콘텐츠가 포함된 테스트를 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-183">Attempt to share a test that contains content that will trigger the U.S. Personally Identifiable Information (PII) Data condition with someone outside your organization.</span></span> <span data-ttu-id="3540a-184">이 경우 정책이 트리거되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-184">This should trigger the policy.</span></span>
14. <span data-ttu-id="3540a-185">이벤트에 대한 활동 탐색기를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-185">Check Activity explorer for the event.</span></span>

### <a name="scenario-2-modify-the-existing-policy-set-an-alert"></a><span data-ttu-id="3540a-186">시나리오 2: 기존 정책 수정, 알림 설정</span><span class="sxs-lookup"><span data-stu-id="3540a-186">Scenario 2: Modify the existing policy, set an alert</span></span>

1. <span data-ttu-id="3540a-187">[데이터 손실 방지 페이지](https://compliance.microsoft.com/datalossprevention?viewid=policies)를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-187">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span></span>
2. <span data-ttu-id="3540a-188">시나리오 1에서 만든 **미국 PII(개인 식별 정보) 데이터** 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-188">Choose the **U.S. Personally Identifiable Information (PII) Data** policy that you created in scenario 1.</span></span>
3. <span data-ttu-id="3540a-189">**정책 편집(미리 보기)** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-189">Choose **edit policy (preview)**.</span></span>
4. <span data-ttu-id="3540a-190">**고급 DLP 규칙** 페이지로 이동하여 **적은 양의 콘텐츠가 미국 개인 식별 가능한 정보를 감지함**을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-190">Go to the **Advanced DLP rules** page and edit the **Low volume of content detected U.S. Personally Identifiable Inf**</span></span>
5. <span data-ttu-id="3540a-191">**사고 보고서** 섹션이 나올 때까지 아래로 스크롤한 다음 **켜기**에 대한 **규칙 일치 오류가 발생하면 관리자에게 알림 보내기**를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-191">Scroll down to the **Incident reports** section and set **Send an alert to admins when a rule match occurs** to **On**.</span></span> <span data-ttu-id="3540a-192">전자 메일 알림은 관리자와 받는 사람 목록에 추가된 모든 사용자에게 자동으로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-192">Email alerts will be automatically sent to the administrator and anyone else you add to the list of recipients.</span></span> 
<span data-ttu-id="3540a-193">![turn-on-incident-reports](../media/endpoint-dlp-2-using-dlp-incident-reports.png)</span><span class="sxs-lookup"><span data-stu-id="3540a-193">![turn-on-incident-reports](../media/endpoint-dlp-2-using-dlp-incident-reports.png)</span></span>
6. <span data-ttu-id="3540a-194">이 시나리오의 목적을 위해 **활동이 규칙에 일치할 때마다 알림 보내기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-194">For the purposes of this scenario, choose **Send alert every time an activity matches the rule**.</span></span>
7. <span data-ttu-id="3540a-195">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-195">Choose **Save**.</span></span>
8. <span data-ttu-id="3540a-196">**다음**을 선택하여 이전 설정을 모두 유지한 다음 정책 변경 **제출**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-196">Retain all your previous settings by choosing **Next** and then **Submit** the policy changes.</span></span>
9. <span data-ttu-id="3540a-197">조직 외부의 사용자와 미국 PII(개인 식별 정보) 데이터 조건을 트리거하는 콘텐츠가 포함된 테스트를 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-197">Attempt to share a test that contains content that will trigger the U.S. Personally Identifiable Information (PII) Data condition with someone outside your organization.</span></span> <span data-ttu-id="3540a-198">이 경우 정책이 트리거되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-198">This should trigger the policy.</span></span>
10. <span data-ttu-id="3540a-199">이벤트에 대한 활동 탐색기를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-199">Check Activity explorer for the event.</span></span>

### <a name="scenario-3-modify-the-existing-policy-block-the-action-with-allow-override"></a><span data-ttu-id="3540a-200">시나리오 3: 기존 정책 수정, 재정의 허용으로 작업 차단</span><span class="sxs-lookup"><span data-stu-id="3540a-200">Scenario 3: Modify the existing policy, block the action with allow override</span></span>

1. <span data-ttu-id="3540a-201">[데이터 손실 방지 페이지](https://compliance.microsoft.com/datalossprevention?viewid=policies)를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-201">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span></span>
2. <span data-ttu-id="3540a-202">시나리오 1에서 만든 **미국 PII(개인 식별 정보) 데이터** 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-202">Choose the **U.S. Personally Identifiable Information (PII) Data** policy that you created in scenario 1.</span></span>
3. <span data-ttu-id="3540a-203">**정책 편집(미리 보기)** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-203">Choose **edit policy (preview)**.</span></span>
4. <span data-ttu-id="3540a-204">**고급 DLP 규칙** 페이지로 이동하여 **적은 양의 콘텐츠가 미국 개인 식별 가능한 정보를 감지함**을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-204">Go to the **Advanced DLP rules** page and edit the **Low volume of content detected U.S. Personally Identifiable Inf**</span></span>
5. <span data-ttu-id="3540a-205">아래로 스크롤하여 **Windows 장치에서 활동 감사 또는 제한** 섹션으로 이동하여 각 활동에 대한 해당 작업을 **재정의로 차단**으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-205">Scroll down to the **Audit or restrict activities on Windows device** section and for each activity set the corresponding action to  **Block with override**.</span></span>
<span data-ttu-id="3540a-206">![재정의 작업으로 차단 설정](../media/endpoint-dlp-6-using-dlp-set-blocked-with-override.png)</span><span class="sxs-lookup"><span data-stu-id="3540a-206">![set block with override action](../media/endpoint-dlp-6-using-dlp-set-blocked-with-override.png)</span></span>
6. <span data-ttu-id="3540a-207">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-207">Choose **Save**.</span></span>
7. <span data-ttu-id="3540a-208">**대량의 콘텐츠가 미국 개인 식별 가능한 정보를 감지함**에 대해 4-7단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-208">Repeat steps 4-7 for the **High volume of content detected U.S. Personally Identifiable Inf**.</span></span>
8. <span data-ttu-id="3540a-209">**다음**을 선택하여 이전 설정을 모두 유지한 다음 정책 변경 **제출**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-209">Retain all your previous settings by choosing **Next** and then **Submit** the policy changes.</span></span>
9. <span data-ttu-id="3540a-210">조직 외부의 사용자와 미국 PII(개인 식별 정보) 데이터 조건을 트리거하는 콘텐츠가 포함된 테스트를 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-210">Attempt to share a test that contains content that will trigger the U.S. Personally Identifiable Information (PII) Data condition with someone outside your organization.</span></span> <span data-ttu-id="3540a-211">이 경우 정책이 트리거되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-211">This should trigger the policy.</span></span>

<span data-ttu-id="3540a-212">클라이언트 장치에 다음과 같은 팝업이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-212">You'll see a popup like this on the client device:</span></span>

![끝점 DLP 클라이언트가 차단한 재정의 알림](../media/endpoint-dlp-3-using-dlp-client-blocked-override-notification.png)

10. <span data-ttu-id="3540a-214">이벤트에 대한 활동 탐색기를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3540a-214">Check Activity explorer for the event.</span></span>

## <a name="see-also"></a><span data-ttu-id="3540a-215">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3540a-215">See also</span></span>

- [<span data-ttu-id="3540a-216">끝점 데이터 손실 방지(미리 보기)에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="3540a-216">Learn about Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="3540a-217">끝점 데이터 손실 방지(미리 보기) 시작</span><span class="sxs-lookup"><span data-stu-id="3540a-217">Get started with Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="3540a-218">데이터 손실 방지의 개요</span><span class="sxs-lookup"><span data-stu-id="3540a-218">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="3540a-219">DLP 정책 만들기, 테스트 및 조정</span><span class="sxs-lookup"><span data-stu-id="3540a-219">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="3540a-220">활동 탐색기 시작하기</span><span class="sxs-lookup"><span data-stu-id="3540a-220">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="3540a-221">Microsoft Defender Advanced Threat Protection(Microsoft Defender ATP)</span><span class="sxs-lookup"><span data-stu-id="3540a-221">Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP)</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="3540a-222">Windows 10 컴퓨터에 대한 온보딩 도구 및 방법</span><span class="sxs-lookup"><span data-stu-id="3540a-222">Onboarding tools and methods for Windows 10 machines</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [<span data-ttu-id="3540a-223">Microsoft 365 구독</span><span class="sxs-lookup"><span data-stu-id="3540a-223">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [<span data-ttu-id="3540a-224">Azure Active Directory(AAD) 가입</span><span class="sxs-lookup"><span data-stu-id="3540a-224">Azure Active Directory (AAD) joined</span></span>](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join)
- [<span data-ttu-id="3540a-225">Chromium 기반 새 Microsoft Edge 다운로드</span><span class="sxs-lookup"><span data-stu-id="3540a-225">Download the new Microsoft Edge based on Chromium</span></span>](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
- [<span data-ttu-id="3540a-226">기본 DLP 정책을 사용하여 시작</span><span class="sxs-lookup"><span data-stu-id="3540a-226">Get started with the default DLP policy</span></span>](get-started-with-the-default-dlp-policy.md)
- [<span data-ttu-id="3540a-227">서식 파일에서 DLP 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="3540a-227">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)