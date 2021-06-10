---
title: 사용자 환경 현지화
description: 사용자를 위해 디바이스를 지역화하는 방법
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 354f61284bbd95c1c7ca4cd50459a1644a89d090
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023264"
---
# <a name="localize-the-user-experience"></a><span data-ttu-id="d3600-104">사용자 환경 현지화</span><span class="sxs-lookup"><span data-stu-id="d3600-104">Localize the user experience</span></span>

<span data-ttu-id="d3600-105">장치 Microsoft Managed Desktop 설치 프로세스("첫 실행 경험") 또는 그 이후에 선택한 언어를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3600-105">Users of Microsoft Managed Desktop devices can select the language of their choice either during the setup process (the "out of box experience") or afterwards.</span></span>

## <a name="during-setup-the-out-of-box-experience"></a><span data-ttu-id="d3600-106">설치 중("첫 실행 경험")</span><span class="sxs-lookup"><span data-stu-id="d3600-106">During setup (the "out of box experience")</span></span>

<span data-ttu-id="d3600-107">설치를 완료하는 동안 사용자는 원하는 언어를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3600-107">During the process of completing setup, users can select the language of their choice.</span></span> <span data-ttu-id="d3600-108">이 선택은 다음 특성에 영향을 미치게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3600-108">This selection affects these attributes:</span></span>

- <span data-ttu-id="d3600-109">Windows 10 기능:</span><span class="sxs-lookup"><span data-stu-id="d3600-109">Windows 10 language features:</span></span>
    - <span data-ttu-id="d3600-110">표시 언어</span><span class="sxs-lookup"><span data-stu-id="d3600-110">Display language</span></span>
    - <span data-ttu-id="d3600-111">키보드 언어</span><span class="sxs-lookup"><span data-stu-id="d3600-111">Keyboard language</span></span>
    - <span data-ttu-id="d3600-112">언어 관련 요구 시 기능</span><span class="sxs-lookup"><span data-stu-id="d3600-112">Language-related Features on Demand</span></span>

- <span data-ttu-id="d3600-113">Microsoft 365 앱 언어 Enterprise 대한 자세한 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d3600-113">Microsoft 365 Apps for Enterprise language features:</span></span>
    - <span data-ttu-id="d3600-114">표시 언어</span><span class="sxs-lookup"><span data-stu-id="d3600-114">Display language</span></span>
    - <span data-ttu-id="d3600-115">교정 및 제작 도구</span><span class="sxs-lookup"><span data-stu-id="d3600-115">Proofing and authoring tools</span></span>

> [!NOTE]
> <span data-ttu-id="d3600-116">사용자는 설치 프로세스 중에 언어를 선택하여 언어 관련 기능만 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3600-116">Users can only get language-related Features On Demand by selecting the language during the setup process.</span></span>

## <a name="after-completing-setup"></a><span data-ttu-id="d3600-117">설치를 완료한 후</span><span class="sxs-lookup"><span data-stu-id="d3600-117">After completing setup</span></span>

<span data-ttu-id="d3600-118">사용자는 설치 프로세스가 완료된 후 Windows 10 Microsoft 365 앱 Enterprise 선택한 언어를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3600-118">Users can select the language of their choice for Windows 10 and Microsoft 365 Apps for Enterprise anytime after the setup process is complete.</span></span> <span data-ttu-id="d3600-119">특히 다음 사항에 유의합니다.</span><span class="sxs-lookup"><span data-stu-id="d3600-119">Specifically:</span></span>

- <span data-ttu-id="d3600-120">Windows 10 기능:</span><span class="sxs-lookup"><span data-stu-id="d3600-120">Windows 10 language features:</span></span>
    - <span data-ttu-id="d3600-121">표시 언어</span><span class="sxs-lookup"><span data-stu-id="d3600-121">Display language</span></span>
    - <span data-ttu-id="d3600-122">키보드 언어</span><span class="sxs-lookup"><span data-stu-id="d3600-122">Keyboard language</span></span>

- <span data-ttu-id="d3600-123">Microsoft 365 앱 언어 Enterprise 대한 자세한 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d3600-123">Microsoft 365 Apps for Enterprise language features:</span></span>
    - <span data-ttu-id="d3600-124">표시 언어</span><span class="sxs-lookup"><span data-stu-id="d3600-124">Display language</span></span>
    - <span data-ttu-id="d3600-125">교정 및 제작 도구</span><span class="sxs-lookup"><span data-stu-id="d3600-125">Proofing and authoring tools</span></span>

<span data-ttu-id="d3600-126">사용자가 설치할 [](#supported-languages) Microsoft 365 앱 Enterprise 지원되는 언어를 만들 수 있도록 최신 **Workplace-Office-Language_Packs** 그룹에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d3600-126">To make the [Supported languages](#supported-languages) for Microsoft 365 Apps for Enterprise available for your users to install, add the users to the **Modern Workplace-Office-Language_Packs** group.</span></span> <span data-ttu-id="d3600-127">언어는 다음 Intune 회사 포털.</span><span class="sxs-lookup"><span data-stu-id="d3600-127">The languages will be available in the Intune Company Portal.</span></span>


## <a name="supported-languages"></a><span data-ttu-id="d3600-128">지원되는 언어</span><span class="sxs-lookup"><span data-stu-id="d3600-128">Supported languages</span></span>

<span data-ttu-id="d3600-129">새 장치의 경우 제조업체에서 필요한 언어가 포함된 장치 이미지를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3600-129">For new devices, your manufacturer must provide device images that include the languages you require.</span></span> <span data-ttu-id="d3600-130">제조업체 이미지에 지원되는 언어 목록에 제공된 언어가 다른 언어가 포함되어 있는 경우 서비스에서 여전히 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3600-130">If your manufacturer's image includes languages other than those provided in the supported languages list it is still supported by the service.</span></span>

<span data-ttu-id="d3600-131">기존 장치를 다시 사용하려면 Microsoft 계정 담당자와 함께 적절한 이미지를 얻어야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3600-131">If you are reusing existing devices, you might need to work with your Microsoft account representative to obtain appropriate images.</span></span> <span data-ttu-id="d3600-132">자세한 내용은 장치 이미지를 [참조하세요.](../service-description/device-images.md)</span><span class="sxs-lookup"><span data-stu-id="d3600-132">For more information, see [Device images](../service-description/device-images.md).</span></span>

<span data-ttu-id="d3600-133">이러한 [언어 및](../service-description/device-images.md#universal-image) Microsoft Managed Desktop 이미지에 포함된 유니버설 이미지는 Windows 10.</span><span class="sxs-lookup"><span data-stu-id="d3600-133">The [universal image](../service-description/device-images.md#universal-image) provided by Microsoft Managed Desktop includes these languages and for Windows 10:</span></span>

- <span data-ttu-id="d3600-134">아랍어</span><span class="sxs-lookup"><span data-stu-id="d3600-134">Arabic</span></span>
- <span data-ttu-id="d3600-135">불가리아어</span><span class="sxs-lookup"><span data-stu-id="d3600-135">Bulgarian</span></span>
- <span data-ttu-id="d3600-136">Chinese Simplified</span><span class="sxs-lookup"><span data-stu-id="d3600-136">Chinese Simplified</span></span>
- <span data-ttu-id="d3600-137">Chinese Traditional</span><span class="sxs-lookup"><span data-stu-id="d3600-137">Chinese Traditional</span></span>
- <span data-ttu-id="d3600-138">크로아티아어</span><span class="sxs-lookup"><span data-stu-id="d3600-138">Croatian</span></span>
- <span data-ttu-id="d3600-139">체코어</span><span class="sxs-lookup"><span data-stu-id="d3600-139">Czech</span></span>
- <span data-ttu-id="d3600-140">덴마크어</span><span class="sxs-lookup"><span data-stu-id="d3600-140">Danish</span></span>  
- <span data-ttu-id="d3600-141">네덜란드어</span><span class="sxs-lookup"><span data-stu-id="d3600-141">Dutch</span></span>  
- <span data-ttu-id="d3600-142">영어(미국, GB, AU, CA, IN)</span><span class="sxs-lookup"><span data-stu-id="d3600-142">English (US, GB, AU, CA, IN)</span></span>
- <span data-ttu-id="d3600-143">에스토니아어</span><span class="sxs-lookup"><span data-stu-id="d3600-143">Estonian</span></span>
- <span data-ttu-id="d3600-144">핀란드어</span><span class="sxs-lookup"><span data-stu-id="d3600-144">Finnish</span></span> 
- <span data-ttu-id="d3600-145">프랑스어(프랑스, 캐나다)</span><span class="sxs-lookup"><span data-stu-id="d3600-145">French (France, Canada)</span></span>
- <span data-ttu-id="d3600-146">독일어</span><span class="sxs-lookup"><span data-stu-id="d3600-146">German</span></span>
- <span data-ttu-id="d3600-147">그리스어</span><span class="sxs-lookup"><span data-stu-id="d3600-147">Greek</span></span>
- <span data-ttu-id="d3600-148">히브리어</span><span class="sxs-lookup"><span data-stu-id="d3600-148">Hebrew</span></span>
- <span data-ttu-id="d3600-149">헝가리어</span><span class="sxs-lookup"><span data-stu-id="d3600-149">Hungarian</span></span>
- <span data-ttu-id="d3600-150">인도네시아어</span><span class="sxs-lookup"><span data-stu-id="d3600-150">Indonesian</span></span>
- <span data-ttu-id="d3600-151">이탈리아어</span><span class="sxs-lookup"><span data-stu-id="d3600-151">Italian</span></span>
- <span data-ttu-id="d3600-152">일본어</span><span class="sxs-lookup"><span data-stu-id="d3600-152">Japanese</span></span>
- <span data-ttu-id="d3600-153">한국어</span><span class="sxs-lookup"><span data-stu-id="d3600-153">Korean</span></span>
- <span data-ttu-id="d3600-154">라트비아어</span><span class="sxs-lookup"><span data-stu-id="d3600-154">Latvian</span></span>
- <span data-ttu-id="d3600-155">리투아니아어</span><span class="sxs-lookup"><span data-stu-id="d3600-155">Lithuanian</span></span>
- <span data-ttu-id="d3600-156">노르웨이어(복말)</span><span class="sxs-lookup"><span data-stu-id="d3600-156">Norwegian (Bokmål)</span></span>
- <span data-ttu-id="d3600-157">폴란드어</span><span class="sxs-lookup"><span data-stu-id="d3600-157">Polish</span></span>
- <span data-ttu-id="d3600-158">포르투갈어(브라질)</span><span class="sxs-lookup"><span data-stu-id="d3600-158">Portuguese (Brazil)</span></span>
- <span data-ttu-id="d3600-159">포르투갈어(포르투갈)</span><span class="sxs-lookup"><span data-stu-id="d3600-159">Portuguese (Portugal)</span></span>
- <span data-ttu-id="d3600-160">루마니아어</span><span class="sxs-lookup"><span data-stu-id="d3600-160">Romanian</span></span>
- <span data-ttu-id="d3600-161">러시아어</span><span class="sxs-lookup"><span data-stu-id="d3600-161">Russian</span></span> 
- <span data-ttu-id="d3600-162">세르비아어(라틴 문자 알파벳)</span><span class="sxs-lookup"><span data-stu-id="d3600-162">Serbian (Latin alphabet)</span></span>
- <span data-ttu-id="d3600-163">슬로바키아어</span><span class="sxs-lookup"><span data-stu-id="d3600-163">Slovak</span></span>
- <span data-ttu-id="d3600-164">슬로베니아어</span><span class="sxs-lookup"><span data-stu-id="d3600-164">Slovenian</span></span>
- <span data-ttu-id="d3600-165">스페인어(스페인, 멕시코)</span><span class="sxs-lookup"><span data-stu-id="d3600-165">Spanish (Spain, Mexico)</span></span>
- <span data-ttu-id="d3600-166">스웨덴어</span><span class="sxs-lookup"><span data-stu-id="d3600-166">Swedish</span></span>
- <span data-ttu-id="d3600-167">태국어</span><span class="sxs-lookup"><span data-stu-id="d3600-167">Thai</span></span>
- <span data-ttu-id="d3600-168">터키어</span><span class="sxs-lookup"><span data-stu-id="d3600-168">Turkish</span></span>
- <span data-ttu-id="d3600-169">우크라이나어</span><span class="sxs-lookup"><span data-stu-id="d3600-169">Ukrainian</span></span>
- <span data-ttu-id="d3600-170">베트남어</span><span class="sxs-lookup"><span data-stu-id="d3600-170">Vietnamese</span></span>

<span data-ttu-id="d3600-171">Microsoft 365 앱 대한 Enterprise 약간 다른 목록을 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3600-171">Microsoft 365 Apps for Enterprise might support a slightly different list.</span></span>

<span data-ttu-id="d3600-172">여기에 나열된 언어가 다른 언어가 필요한 경우 [](../working-with-managed-desktop/admin-support.md) 관리 포털을 사용하여 지원 요청을 [제출합니다.](access-admin-portal.md)</span><span class="sxs-lookup"><span data-stu-id="d3600-172">If your users need a language other than the ones listed here, file a [support request](../working-with-managed-desktop/admin-support.md) by using the [Admin portal](access-admin-portal.md).</span></span>

## <a name="languages-for-support-and-operations"></a><span data-ttu-id="d3600-173">지원 및 운영 언어</span><span class="sxs-lookup"><span data-stu-id="d3600-173">Languages for support and operations</span></span>

### <a name="user-support"></a><span data-ttu-id="d3600-174">사용자 지원</span><span class="sxs-lookup"><span data-stu-id="d3600-174">User support</span></span>
<span data-ttu-id="d3600-175">Microsoft Managed Desktop 지원은 영어로만 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3600-175">Microsoft Managed Desktop provides support only in English.</span></span> <span data-ttu-id="d3600-176">사용자가 도움말 앱에서 다른 언어를 선택하는 경우 해당 앱에서 직접 지원하지 않고 일반 Microsoft 지원 채널에서 지원을 Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="d3600-176">If users choose another language in the Get Help app, they will get support from the general Microsoft support channels, rather than support directly from Microsoft Managed Desktop.</span></span> <span data-ttu-id="d3600-177">자세한 내용은 [사용자에 대한 도움말 보기를 참조하세요.](../working-with-managed-desktop/end-user-support.md)</span><span class="sxs-lookup"><span data-stu-id="d3600-177">For more information, see [Getting help for users](../working-with-managed-desktop/end-user-support.md).</span></span>

<span data-ttu-id="d3600-178">사용자가 다른 언어로 지원을 필요로 하는 경우 Microsoft가 아닌 지원 원본이나 조직에서 지원을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3600-178">If your users need support in other languages, you'll have to provide that through non-Microsoft support sources or from your own organization.</span></span>

### <a name="admin-support-and-operations"></a><span data-ttu-id="d3600-179">관리자 지원 및 운영</span><span class="sxs-lookup"><span data-stu-id="d3600-179">Admin support and operations</span></span>
<span data-ttu-id="d3600-180">Microsoft Managed Desktop 영어로만 관리자 지원을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d3600-180">Microsoft Managed Desktop provides admin support only in English.</span></span> <span data-ttu-id="d3600-181">여기에는 관리 포털 및 관리 작업과의 Microsoft Managed Desktop 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3600-181">This includes the Admin portal and all communications with Microsoft Managed Desktop Operations.</span></span> <span data-ttu-id="d3600-182">달리 지정하지 않는 한 모든 관리자 관련 상호 작용 및 인터페이스가 영어로 제공된다고 가정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3600-182">You should assume that all admin-related interactions and interfaces will be in English, unless specified otherwise.</span></span>


