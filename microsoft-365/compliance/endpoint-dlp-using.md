---
title: 끝점 데이터 손실 방지 사용
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
ms.openlocfilehash: 1bb4013069b8f4890ba420f13a0203eb63973121
ms.sourcegitcommit: 8b1bd7ca8cd81e4270f0c1e06d2b6ca81804a6aa
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "50820190"
---
# <a name="using-endpoint-data-loss-prevention"></a><span data-ttu-id="e2d78-103">끝점 데이터 손실 방지 사용</span><span class="sxs-lookup"><span data-stu-id="e2d78-103">Using Endpoint data loss prevention</span></span>

<span data-ttu-id="e2d78-104">이 문서에서는 장치를 위치로 사용하는 DLP 정책을 만들고 수정하는 3가지 시나리오를 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-104">This article walks you through three scenarios where you create and modify a DLP policy that uses devices as a location.</span></span>

## <a name="dlp-settings"></a><span data-ttu-id="e2d78-105">DLP 설정</span><span class="sxs-lookup"><span data-stu-id="e2d78-105">DLP settings</span></span>

<span data-ttu-id="e2d78-106">시작하기 전에 모든 장치에 대한 DLP 정책에 적용되는 DLP 설정을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-106">Before you get started you should set up your DLP settings which are applied to all DLP policies for devices.</span></span> <span data-ttu-id="e2d78-107">적용되는 정책을 만들려면 다음을 반드시 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-107">You must configure these if you intend to create policies that enforce:</span></span>

- <span data-ttu-id="e2d78-108">클라우드 송신 제한 사항</span><span class="sxs-lookup"><span data-stu-id="e2d78-108">cloud egress restrictions</span></span>
- <span data-ttu-id="e2d78-109">허용되지 않는 앱 제한 사항</span><span class="sxs-lookup"><span data-stu-id="e2d78-109">unallowed apps restrictions</span></span>

<span data-ttu-id="e2d78-110">또는</span><span class="sxs-lookup"><span data-stu-id="e2d78-110">Or</span></span>

- <span data-ttu-id="e2d78-111">모니터링에서 잡음이 있는 파일 경로를 제외하려는 경우</span><span class="sxs-lookup"><span data-stu-id="e2d78-111">If you want to exclude noisy file paths from monitoring</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="e2d78-112">![DLP 설정](../media/endpoint-dlp-1-using-dlp-settings.png)</span><span class="sxs-lookup"><span data-stu-id="e2d78-112">![DLP settings](../media/endpoint-dlp-1-using-dlp-settings.png)</span></span>

### <a name="file-path-exclusions"></a><span data-ttu-id="e2d78-113">파일 경로 제외</span><span class="sxs-lookup"><span data-stu-id="e2d78-113">File path exclusions</span></span>

<span data-ttu-id="e2d78-114">지나치게 잡음이 많거나 관심 있는 파일을 포함하지 않으므로 장치에서 DLP 모니터링, DLP 경고, DLP 정책 적용에서 특정 경로를 제외하고자 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-114">You may want to exclude certain paths from DLP monitoring, DLP alerting, and DLP policy enforcement on your devices because they are too noisy or don’t contain files you are interested in.</span></span> <span data-ttu-id="e2d78-115">해당 위치에서 파일을 감사하지 않으며 해당 위치에서 만들어지거나 수정된 모든 파일에 DLP 정책 적용이 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-115">Files in those locations will not be audited and any files that are created or modified in those locations will not be subject to DLP policy enforcement.</span></span> <span data-ttu-id="e2d78-116">DLP 설정에서 경로 제외를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-116">You can configure path exclusions in DLP settings.</span></span>

<span data-ttu-id="e2d78-117">이 논리를 사용하여 제외 경로를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-117">You can use this logic to construct your exclusion paths:</span></span>

- <span data-ttu-id="e2d78-118">‘\로 끝나는 올바른 파일 경로입니다. 이는 폴더 바로 아래에 있는 파일만을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-118">Valid file path that ends with ‘\’, which means only files directly under folder.</span></span> <br/><span data-ttu-id="e2d78-119">예시: C:\Temp</span><span class="sxs-lookup"><span data-stu-id="e2d78-119">For example: C:\Temp</span></span>\

- <span data-ttu-id="e2d78-120">‘\*’로 끝나는 올바른 파일 경로입니다. 이는 폴더 바로 아래에 있는 파일 외에 하위 폴더 바로 아래에 있는 파일만을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-120">Valid file path that ends with ‘\*’, which means only files under sub-folders, besides the files directly under the folder.</span></span> <br/><span data-ttu-id="e2d78-121">예시: C:\Temp\*</span><span class="sxs-lookup"><span data-stu-id="e2d78-121">For example: C:\Temp\*</span></span>

- <span data-ttu-id="e2d78-122">‘\’ 또는 ‘\*’로 끝나는 올바른 파일 경로입니다. 이는 폴더 및 모든 하위 폴더 바로 아래에 있는 모든 파일을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-122">Valid file path that ends without ‘\’ or ‘\*’, which means all files directly under folder and all sub-folders.</span></span> <br/><span data-ttu-id="e2d78-123">예시: C:\Temp</span><span class="sxs-lookup"><span data-stu-id="e2d78-123">For example: C:\Temp</span></span>

- <span data-ttu-id="e2d78-124">각 면의 '\' 사이에 와일드카드가 있는 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-124">A path with wildcard between ‘\’ from each side.</span></span> <br/><span data-ttu-id="e2d78-125">예시: C:\Users\*\Desktop</span><span class="sxs-lookup"><span data-stu-id="e2d78-125">For example: C:\Users\*\Desktop</span></span>\

- <span data-ttu-id="e2d78-126">정확한 하위 폴더 수를 제공하기 위해 각 면의 '\' 사이에 와일드카드와 '(숫자)'가 있는 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-126">A path with wildcard between ‘\’ from each side and with ‘(number)’ to give exact number of subfolders.</span></span> <br/><span data-ttu-id="e2d78-127">예시: C:\Users\*(1)\Downloads</span><span class="sxs-lookup"><span data-stu-id="e2d78-127">For example: C:\Users\*(1)\Downloads</span></span>\

- <span data-ttu-id="e2d78-128">시스템 환경 변수를 사용하는 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-128">A path with SYSTEM environment variables.</span></span> <br/><span data-ttu-id="e2d78-129">예시: %SystemDrive%\Test\*</span><span class="sxs-lookup"><span data-stu-id="e2d78-129">For example: %SystemDrive%\Test\*</span></span>

- <span data-ttu-id="e2d78-130">위의 모든 것을 혼합한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-130">A mix of all the above.</span></span> <br/><span data-ttu-id="e2d78-131">예시: %SystemDrive%\Users\*\Documents\*(2)\Sub</span><span class="sxs-lookup"><span data-stu-id="e2d78-131">For example: %SystemDrive%\Users\*\Documents\*(2)\Sub</span></span>\

### <a name="unallowed-apps"></a><span data-ttu-id="e2d78-132">허용되지 않는 앱</span><span class="sxs-lookup"><span data-stu-id="e2d78-132">Unallowed apps</span></span>

<span data-ttu-id="e2d78-133">정책의 **허용되지 않은 앱 및 브라우저에 의한 액세스** 설정이 켜져 있고 사용자가 이러한 앱을 사용하여 보호된 파일에 액세스하려고 하면, 활동이 허용 또는 차단되거나, 아니면 차단되지만 사용자가 제한을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-133">When a policy's **Access by unallowed apps and browsers** setting is turned on and users attempt to use these apps to access a protected file, the activity will be allowed, blocked, or blocked but users can override the restriction.</span></span> <span data-ttu-id="e2d78-134">모든 활동을 감사하며 활동 탐색기에서 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-134">All activity is audited and available to review in activity explorer.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e2d78-135">실행 파일 이름(예: 브라우저.exe)은 포함해야 하지만 실행 파일 경로는 포함하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-135">Do not include the path to the executable, but only the executable name (such as browser.exe).</span></span>


### <a name="browser-and-domain-restrictions"></a><span data-ttu-id="e2d78-136">브라우저 및 도메인 제한:</span><span class="sxs-lookup"><span data-stu-id="e2d78-136">Browser and domain restrictions</span></span>
<span data-ttu-id="e2d78-137">정책과 일치하는 중요한 파일을 무제한 클라우드 서비스 도메인에 공유하지 못하도록 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-137">Restrict sensitive files that match your policies from being shared with unrestricted cloud service domains.</span></span>

#### <a name="service-domains"></a><span data-ttu-id="e2d78-138">서비스 도메인</span><span class="sxs-lookup"><span data-stu-id="e2d78-138">Service domains</span></span>

<span data-ttu-id="e2d78-139">정책으로 보호되는 중요한 파일을 Microsoft Edge의 특정 서비스 도메인에 업로드할 수 있는지 여부를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-139">You can control whether sensitive files protected by your policies can be uploaded to specific service domains from Microsoft Edge.</span></span>

<span data-ttu-id="e2d78-140">목록 모드가 **차단** 으로 설정되어 있으면 사용자는 해당 도메인에 중요한 항목을 업로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-140">If the list mode is set to **Block**, then user will not be able to upload sensitive items to those domains.</span></span> <span data-ttu-id="e2d78-141">항목이 DLP 정책과 일치하여 업로드 작업이 차단되면 DLP가 경고를 생성하거나 중요한 항목의 업로드를 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-141">When an upload action is blocked because an item matches a DLP policy, DLP will either generate a warning or block the upload of the sensitive item.</span></span>

<span data-ttu-id="e2d78-142">목록 모드가 **허용** 으로 설정되어 있으면 사용자는 해당 도메인에 **_오직_** 중요한 항목만을 업로드할 수 있으며 다른 모든 도메인에 대한 업로드 액세스는 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-142">If the list mode is set to **Allow**, then users will be able to upload sensitive items **_only_** to those domains, and upload access to all other domains is not allowed.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e2d78-143">서비스 제한 모드를 "허용"으로 설정한 경우 제한이 적용되기 전에 하나 이상의 서비스 도메인을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-143">When the service restriction mode is set to "Allow", you must have at least one service domain configured before restrictions are enforced.</span></span>

#### <a name="unallowed-browsers"></a><span data-ttu-id="e2d78-144">허용되지 않는 브라우저</span><span class="sxs-lookup"><span data-stu-id="e2d78-144">Unallowed browsers</span></span>

<span data-ttu-id="e2d78-145">클라우드 서비스 제한에 업로드가 차단 또는 재설정을 차단하는 것으로 설정되어 있는 적용된 DLP 정책의 조건과 일치하는 파일에 액세스하지 못하도록 차단된 실행 파일 이름으로 식별되는 브라우저를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-145">You add browsers, identified by their executable names, that will be blocked from accessing files that match the conditions of an enforced a DLP policy where the upload to cloud services restriction is set to block or block override.</span></span> <span data-ttu-id="e2d78-146">이 브라우저가 파일에 액세스하지 못하도록 차단되면 최종 사용자에게 Edge Chromium를 통해 파일을 열도록 요청하는 알림 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-146">When these browsers are blocked from accessing a file, the end users will see a toast notification asking them to open the file through Edge Chromium.</span></span>

### <a name="business-justification-in-policy-tips"></a><span data-ttu-id="e2d78-147">정책 팁의 비즈니스 타당성</span><span class="sxs-lookup"><span data-stu-id="e2d78-147">Business justification in policy tips</span></span>

<span data-ttu-id="e2d78-148">DLP 정책 팁 알림에서 사용자가 비즈니스 타당성 옵션과 상호 작용하는 방법을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-148">You can control how users interact with the business justification option in DLP policy tip notifications.</span></span> <span data-ttu-id="e2d78-149">이 옵션은 사용자가 DLP 정책에서 **재정의로 차단** 설정으로 보호되는 활동을 수행하는 경우 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-149">This option appears when users perform an activity that's protected by the **Block with override** setting in a DLP policy.</span></span> <span data-ttu-id="e2d78-150">다음 옵션 중 하나를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-150">You can choose from one the following options:</span></span>

- <span data-ttu-id="e2d78-151">기본적으로 사용자는 기본 제공 사유를 선택하거나 텍스트를 직접 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-151">By default, users can select either a built-in justification, or enter their own text.</span></span>
- <span data-ttu-id="e2d78-152">사용자는 기본 제공 사유만 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-152">Users can only select a built-in justification.</span></span>
- <span data-ttu-id="e2d78-153">사용자는 고유의 사유만 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-153">Users can only enter their own justification.</span></span>


## <a name="tying-dlp-settings-together"></a><span data-ttu-id="e2d78-154">DLP 설정 함께 연결</span><span class="sxs-lookup"><span data-stu-id="e2d78-154">Tying DLP settings together</span></span>

<span data-ttu-id="e2d78-155">끝점 DLP 및 Edge Chromium 웹 브라우저를 사용하여 중요한 항목이 허용되지 않는 클라우드 앱 및 서비스에 대한 의도하지 않은 공유를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-155">With Endpoint DLP and Edge Chromium Web browser, you can restrict unintentional sharing of sensitive items to unallowed cloud apps and services.</span></span> <span data-ttu-id="e2d78-156">Edge Chromium은 항목이 끝점 DLP 정책으로 제한되는 경우에 대해 이해하고 액세스 제한을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-156">Edge Chromium understands when an item is restricted by an Endpoint DLP policy and enforces access restrictions.</span></span>

<span data-ttu-id="e2d78-157">올바르게 구성된 DLP 정책 및 Edge Chromium 브라우저에서 끝점 DLP를 위치로 사용하는 경우 이러한 설정에 정의된 허용되지 않는 브라우저는 DLP 정책 컨트롤과 일치하는 중요한 항목에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-157">When you use Endpoint DLP as a location in a properly configured DLP policy and the Edge Chromium browser, the unallowed browsers that you've defined in these settings will be prevented from accessing the sensitive items that match your DLP policy controls.</span></span> <span data-ttu-id="e2d78-158">대신 사용자는 Edge Chromium을 사용하도록 리디렉션되며 Edge Chromium이 DLP 적용 제한 사항을 이해하여 DLP 정책의 조건을 충족하는 경우 활동을 차단하거나 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-158">Instead, users will be redirected to use Edge Chromium and Edge Chromium, with its understanding of DLP imposed restrictions, can block or restrict activities when the conditions in the DLP policy are met.</span></span>

<span data-ttu-id="e2d78-159">이 제한을 사용하려면 중요한 3가지 부분을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-159">To use this restriction you’ll need to configure three important pieces:</span></span>

1. <span data-ttu-id="e2d78-160">중요한 항목이 공유되지 않도록 하려는 위치(서비스, 도메인, IP 주소)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-160">Specify the places – services, domains, IP addresses – that you want to prevent sensitive items from being shared to.</span></span>

2. <span data-ttu-id="e2d78-161">DLP 정책이 일치하는 경우 특정 중요한 항목에 액세스할 수 없는 브라우저를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-161">Add the browsers that aren’t allowed to access certain sensitive items when a DLP policy match occurs.</span></span>

3. <span data-ttu-id="e2d78-162">**클라우드 서비스 업로드** 와 **허용되지 않은 브라우저에서 액세스** 설정을 사용하여 업로드가 해당 위치로 제한되어야 하는 중요한 항목의 종류를 정의하는 DLP 정책 구성</span><span class="sxs-lookup"><span data-stu-id="e2d78-162">Configure DLP policies to define the kinds of sensitive items for which upload should be restricted to these places by turning on **Upload to cloud services** and **Access from unallowed browser**.</span></span>

<span data-ttu-id="e2d78-163">새 서비스, 앱 및 정책을 계속 추가하여 비즈니스 요구 사항을 충족하고 중요한 데이터를 보호하는 데 필요한 제한을 확장하고 강화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-163">You can continue to add new services, apps, and policies to extend and augment your restrictions to meet your business needs and protect sensitive data.</span></span> 

<span data-ttu-id="e2d78-164">이 구성은 사용자가 중요하지 않은 항목에 액세스하고 공유하지 못하도록 하는 불필요한 제한을 피하는 동시에 데이터를 안전하게 유지하는 데도 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-164">This configuration will help ensure your data remains safe while also avoiding unnecessary restrictions that prevent or restrict users from accessing and sharing non-sensitive items.</span></span>

## <a name="endpoint-dlp-policy-scenarios"></a><span data-ttu-id="e2d78-165">끝점 DLP 정책 시나리오</span><span class="sxs-lookup"><span data-stu-id="e2d78-165">Endpoint DLP policy scenarios</span></span>

<span data-ttu-id="e2d78-166">끝점 DLP 기능과 해당 기능이 DLP 정책에 나오는 방법에 대한 자세한 내용은 다음 몇 가지 시나리오를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e2d78-166">To help familiarize you with Endpoint DLP features and how they surface in DLP policies, we've put together some scenarios for you to follow.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e2d78-167">이러한 끝점 DLP 시나리오는 DLP 정책을 만들고 조정하는 공식 절차가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-167">These Endpoint DLP scenarios are not the official procedures for creating and tuning DLP policies.</span></span> <span data-ttu-id="e2d78-168">일반적으로 DLP 정책을 사용해야 하는 경우 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e2d78-168">Refer to the below topics when you need to work with DLP policies in general situations:</span></span>
>- [<span data-ttu-id="e2d78-169">데이터 손실 방지의 개요</span><span class="sxs-lookup"><span data-stu-id="e2d78-169">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
>- [<span data-ttu-id="e2d78-170">기본 DLP 정책을 사용하여 시작</span><span class="sxs-lookup"><span data-stu-id="e2d78-170">Get started with the default DLP policy</span></span>](get-started-with-the-default-dlp-policy.md)
>- [<span data-ttu-id="e2d78-171">템플릿에서 DLP 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="e2d78-171">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
>- [<span data-ttu-id="e2d78-172">DLP 정책 만들기, 테스트 및 조정</span><span class="sxs-lookup"><span data-stu-id="e2d78-172">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)

### <a name="scenario-1-create-a-policy-from-a-template-audit-only"></a><span data-ttu-id="e2d78-173">시나리오 1: 템플릿으로 정책 만들기, 감사 전용</span><span class="sxs-lookup"><span data-stu-id="e2d78-173">Scenario 1: Create a policy from a template, audit only</span></span>

<span data-ttu-id="e2d78-174">이 시나리오에서는 이미 장치가 온보딩되어 활동 탐색기에 보고되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-174">These scenarios require that you already have devices onboarded and reporting into Activity explorer.</span></span> <span data-ttu-id="e2d78-175">아직 장치를 온보딩하지 않은 경우 [끝점 데이터 손실 방지(미리 보기)](endpoint-dlp-getting-started.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e2d78-175">If you haven't onboarded devices yet, see [Get started with Endpoint data loss prevention](endpoint-dlp-getting-started.md).</span></span>

1. <span data-ttu-id="e2d78-176">[데이터 손실 방지 페이지](https://compliance.microsoft.com/datalossprevention?viewid=policies)를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-176">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span></span>

2. <span data-ttu-id="e2d78-177">**정책 만들기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-177">Choose **Create policy**.</span></span>

3. <span data-ttu-id="e2d78-178">이 시나리오에서는 **개인 정보** 를 선택한 다음 **미국 PII(개인 식별 정보) 데이터** 를 선택하고 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-178">For this scenario, choose **Privacy**, then **U.S. Personally Identifiable Information (PII) Data** and choose **Next**.</span></span>

4. <span data-ttu-id="e2d78-179">**장치** 를 제외한 모든 위치에서 **상태** 필드를 해제로 전환합니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-179">Toggle the **Status** field to off for all locations except **Devices**.</span></span> <span data-ttu-id="e2d78-180">**다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-180">Choose **Next**.</span></span>

5. <span data-ttu-id="e2d78-181">기본 설정인 **템플릿에서 설정 검토 및 사용자 지정** 선택을 그대로 사용하고 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-181">Accept the default **Review and customize settings from the template** selection and choose **Next**.</span></span>

6. <span data-ttu-id="e2d78-182">기본 설정인 **보호 작업** 값을 적용하고 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-182">Accept the default **Protection actions** values and choose **Next**.</span></span>

7. <span data-ttu-id="e2d78-183">**Windows 장치에서 활동 감사 또는 제한** 을 선택하고 작업을 **감사 전용** 으로 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-183">Select **Audit or restrict activities on Windows devices** and leave the actions set to **Audit only**.</span></span> <span data-ttu-id="e2d78-184">**다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-184">Choose **Next**.</span></span>

8. <span data-ttu-id="e2d78-185">기본 설정인 **먼저 테스트하고 싶습니다** 를 적용하고 **테스트 모드에서 정책 팁 표시** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-185">Accept the default **I'd like to test it out first** value and choose **Show policy tips while in test mode**.</span></span> <span data-ttu-id="e2d78-186">**다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-186">Choose **Next**.</span></span>

9. <span data-ttu-id="e2d78-187">설정을 검토하고 **제출** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-187">Review your settings and choose **Submit**.</span></span>

10. <span data-ttu-id="e2d78-188">새 DLP 정책이 정책 목록에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-188">The new DLP policy will appear in the policy list.</span></span>

11. <span data-ttu-id="e2d78-189">모니터링되는 끝점에서 데이터에 대한 활동 탐색기를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-189">Check Activity explorer for data from the monitored endpoints.</span></span> <span data-ttu-id="e2d78-190">장치에 대한 위치 필터를 설정하고 정책을 추가한 다음 정책 이름을 기준으로 필터링하여 정책의 영향을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-190">Set the location filter for devices and add the policy, then filter by policy name to see the impact of this policy.</span></span> <span data-ttu-id="e2d78-191">필요한 경우 [활동 탐색기로 시작](data-classification-activity-explorer.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e2d78-191">See, [Get started with activity explorer](data-classification-activity-explorer.md) if needed.</span></span>

12. <span data-ttu-id="e2d78-192">조직 외부의 사용자와 미국 PII(개인 식별 정보) 데이터 조건을 트리거하는 콘텐츠가 포함된 테스트를 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-192">Attempt to share a test that contains content that will trigger the U.S. Personally Identifiable Information (PII) Data condition with someone outside your organization.</span></span> <span data-ttu-id="e2d78-193">이 경우 정책이 트리거되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-193">This should trigger the policy.</span></span>

13. <span data-ttu-id="e2d78-194">이벤트에 대한 활동 탐색기를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-194">Check Activity explorer for the event.</span></span>

### <a name="scenario-2-modify-the-existing-policy-set-an-alert"></a><span data-ttu-id="e2d78-195">시나리오 2: 기존 정책 수정, 알림 설정</span><span class="sxs-lookup"><span data-stu-id="e2d78-195">Scenario 2: Modify the existing policy, set an alert</span></span>

1. <span data-ttu-id="e2d78-196">[데이터 손실 방지 페이지](https://compliance.microsoft.com/datalossprevention?viewid=policies)를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-196">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span></span>

2. <span data-ttu-id="e2d78-197">시나리오 1에서 만든 **미국 PII(개인 식별 정보) 데이터** 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-197">Choose the **U.S. Personally Identifiable Information (PII) Data** policy that you created in scenario 1.</span></span>

3. <span data-ttu-id="e2d78-198">**정책 편집** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-198">Choose **edit policy**.</span></span>

4. <span data-ttu-id="e2d78-199">**고급 DLP 규칙** 페이지로 이동하여 **적은 양의 콘텐츠가 미국 개인 식별 정보를 감지함** 을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-199">Go to the **Advanced DLP rules** page and edit the **Low volume of content detected U.S. Personally Identifiable Inf**.</span></span>

5. <span data-ttu-id="e2d78-200">**사고 보고서** 섹션이 나올 때까지 아래로 스크롤한 다음 **켜기** 에 대한 **규칙 일치 오류가 발생하면 관리자에게 알림 보내기** 를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-200">Scroll down to the **Incident reports** section and set **Send an alert to admins when a rule match occurs** to **On**.</span></span> <span data-ttu-id="e2d78-201">전자 메일 알림은 관리자와 받는 사람 목록에 추가된 모든 사용자에게 자동으로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-201">Email alerts will be automatically sent to the administrator and anyone else you add to the list of recipients.</span></span> 

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e2d78-202">![turn-on-incident-reports](../media/endpoint-dlp-2-using-dlp-incident-reports.png)</span><span class="sxs-lookup"><span data-stu-id="e2d78-202">![turn-on-incident-reports](../media/endpoint-dlp-2-using-dlp-incident-reports.png)</span></span>
   
6. <span data-ttu-id="e2d78-203">이 시나리오의 목적을 위해 **활동이 규칙에 일치할 때마다 알림 보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-203">For the purposes of this scenario, choose **Send alert every time an activity matches the rule**.</span></span>

7. <span data-ttu-id="e2d78-204">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-204">Choose **Save**.</span></span>

8. <span data-ttu-id="e2d78-205">**다음** 을 선택하여 이전 설정을 모두 유지한 다음 정책 변경 **제출** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-205">Retain all your previous settings by choosing **Next** and then **Submit** the policy changes.</span></span>

9. <span data-ttu-id="e2d78-206">조직 외부의 사용자와 미국 PII(개인 식별 정보) 데이터 조건을 트리거하는 콘텐츠가 포함된 테스트를 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-206">Attempt to share a test that contains content that will trigger the U.S. Personally Identifiable Information (PII) Data condition with someone outside your organization.</span></span> <span data-ttu-id="e2d78-207">이 경우 정책이 트리거되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-207">This should trigger the policy.</span></span>

10. <span data-ttu-id="e2d78-208">이벤트에 대한 활동 탐색기를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-208">Check Activity explorer for the event.</span></span>

### <a name="scenario-3-modify-the-existing-policy-block-the-action-with-allow-override"></a><span data-ttu-id="e2d78-209">시나리오 3: 기존 정책 수정, 재정의 허용으로 작업 차단</span><span class="sxs-lookup"><span data-stu-id="e2d78-209">Scenario 3: Modify the existing policy, block the action with allow override</span></span>

1. <span data-ttu-id="e2d78-210">[데이터 손실 방지 페이지](https://compliance.microsoft.com/datalossprevention?viewid=policies)를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-210">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span></span>

2. <span data-ttu-id="e2d78-211">시나리오 1에서 만든 **미국 PII(개인 식별 정보) 데이터** 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-211">Choose the **U.S. Personally Identifiable Information (PII) Data** policy that you created in scenario 1.</span></span>

3. <span data-ttu-id="e2d78-212">**정책 편집** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-212">Choose **edit policy**.</span></span>

4. <span data-ttu-id="e2d78-213">**고급 DLP 규칙** 페이지로 이동하여 **적은 양의 콘텐츠가 미국 개인 식별 정보를 감지함** 을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-213">Go to the **Advanced DLP rules** page and edit the **Low volume of content detected U.S. Personally Identifiable Inf**.</span></span>

5. <span data-ttu-id="e2d78-214">아래로 스크롤하여 **Windows 장치에서 활동 감사 또는 제한** 섹션으로 이동하여 각 활동에 대한 해당 작업을 **재정의로 차단** 으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-214">Scroll down to the **Audit or restrict activities on Windows device** section and for each activity set the corresponding action to  **Block with override**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e2d78-215">![재정의 작업으로 차단 설정](../media/endpoint-dlp-6-using-dlp-set-blocked-with-override.png)</span><span class="sxs-lookup"><span data-stu-id="e2d78-215">![set block with override action](../media/endpoint-dlp-6-using-dlp-set-blocked-with-override.png)</span></span>
   
6. <span data-ttu-id="e2d78-216">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-216">Choose **Save**.</span></span>

7. <span data-ttu-id="e2d78-217">**대량의 콘텐츠가 미국 개인 식별 가능한 정보를 감지함** 에 대해 4-7단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-217">Repeat steps 4-7 for the **High volume of content detected U.S. Personally Identifiable Inf**.</span></span>

8. <span data-ttu-id="e2d78-218">**다음** 을 선택하여 이전 설정을 모두 유지한 다음 정책 변경 **제출** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-218">Retain all your previous settings by choosing **Next** and then **Submit** the policy changes.</span></span>

9. <span data-ttu-id="e2d78-219">조직 외부의 사용자와 미국 PII(개인 식별 정보) 데이터 조건을 트리거하는 콘텐츠가 포함된 테스트를 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-219">Attempt to share a test that contains content that will trigger the U.S. Personally Identifiable Information (PII) Data condition with someone outside your organization.</span></span> <span data-ttu-id="e2d78-220">이 경우 정책이 트리거되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-220">This should trigger the policy.</span></span>

   <span data-ttu-id="e2d78-221">클라이언트 장치에 다음과 같은 팝업이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-221">You'll see a popup like this on the client device:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e2d78-222">![끝점 DLP 클라이언트가 차단 재정의 알림](../media/endpoint-dlp-3-using-dlp-client-blocked-override-notification.png)</span><span class="sxs-lookup"><span data-stu-id="e2d78-222">![endpoint dlp client blocked override notification](../media/endpoint-dlp-3-using-dlp-client-blocked-override-notification.png)</span></span>

10. <span data-ttu-id="e2d78-223">이벤트에 대한 활동 탐색기를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e2d78-223">Check Activity explorer for the event.</span></span>

## <a name="see-also"></a><span data-ttu-id="e2d78-224">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e2d78-224">See also</span></span>

- [<span data-ttu-id="e2d78-225">끝점 데이터 손실 방지에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="e2d78-225">Learn about Endpoint data loss prevention</span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="e2d78-226">끝점 데이터 손실 방지 시작</span><span class="sxs-lookup"><span data-stu-id="e2d78-226">Get started with Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="e2d78-227">데이터 손실 방지 개요</span><span class="sxs-lookup"><span data-stu-id="e2d78-227">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="e2d78-228">DLP 정책 생성, 테스트 및 조정</span><span class="sxs-lookup"><span data-stu-id="e2d78-228">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="e2d78-229">활동 탐색기 시작하기</span><span class="sxs-lookup"><span data-stu-id="e2d78-229">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="e2d78-230">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="e2d78-230">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="e2d78-231">Windows 10 컴퓨터용 온보딩 도구 및 방법</span><span class="sxs-lookup"><span data-stu-id="e2d78-231">Onboarding tools and methods for Windows 10 machines</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [<span data-ttu-id="e2d78-232">Microsoft 365 구독</span><span class="sxs-lookup"><span data-stu-id="e2d78-232">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [<span data-ttu-id="e2d78-233">Azure Active Directory(AAD) 가입</span><span class="sxs-lookup"><span data-stu-id="e2d78-233">Azure Active Directory (AAD) joined</span></span>](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join)
- [<span data-ttu-id="e2d78-234">Chromium 기반 새 Microsoft Edge 다운로드</span><span class="sxs-lookup"><span data-stu-id="e2d78-234">Download the new Microsoft Edge based on Chromium</span></span>](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
- [<span data-ttu-id="e2d78-235">기본 DLP 정책을 사용하여 시작</span><span class="sxs-lookup"><span data-stu-id="e2d78-235">Get started with the default DLP policy</span></span>](get-started-with-the-default-dlp-policy.md)
- [<span data-ttu-id="e2d78-236">서식 파일에서 DLP 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="e2d78-236">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
