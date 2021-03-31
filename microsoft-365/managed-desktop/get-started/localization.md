---
title: 사용자 환경 지역화
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
ms.openlocfilehash: 20456ce837be60b707569ae07d4fb00b695b3a98
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445984"
---
# <a name="localize-the-user-experience"></a><span data-ttu-id="59af1-104">사용자 환경 지역화</span><span class="sxs-lookup"><span data-stu-id="59af1-104">Localize the user experience</span></span>

<span data-ttu-id="59af1-105">Microsoft Managed Desktop 장치 사용자는 설치 프로세스("첫 실행 경험") 또는 그 이후에 원하는 언어를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59af1-105">Users of Microsoft Managed Desktop devices can select the language of their choice either during the setup process (the "out of box experience") or afterwards.</span></span>

## <a name="during-setup-the-out-of-box-experience"></a><span data-ttu-id="59af1-106">설치 중("첫 실행 경험")</span><span class="sxs-lookup"><span data-stu-id="59af1-106">During setup (the "out of box experience")</span></span>

<span data-ttu-id="59af1-107">설치를 완료하는 동안 사용자는 원하는 언어를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59af1-107">During the process of completing setup, users can select the language of their choice.</span></span> <span data-ttu-id="59af1-108">이 선택은 다음 특성에 영향을 미치게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="59af1-108">This selection affects these attributes:</span></span>

- <span data-ttu-id="59af1-109">Windows 10 언어 기능:</span><span class="sxs-lookup"><span data-stu-id="59af1-109">Windows 10 language features:</span></span>
    - <span data-ttu-id="59af1-110">표시 언어</span><span class="sxs-lookup"><span data-stu-id="59af1-110">Display language</span></span>
    - <span data-ttu-id="59af1-111">키보드 언어</span><span class="sxs-lookup"><span data-stu-id="59af1-111">Keyboard language</span></span>
    - <span data-ttu-id="59af1-112">언어 관련 요구 시 기능</span><span class="sxs-lookup"><span data-stu-id="59af1-112">Language-related Features on Demand</span></span>

- <span data-ttu-id="59af1-113">엔터프라이즈용 Microsoft 365 앱 언어 기능:</span><span class="sxs-lookup"><span data-stu-id="59af1-113">Microsoft 365 Apps for Enterprise language features:</span></span>
    - <span data-ttu-id="59af1-114">표시 언어</span><span class="sxs-lookup"><span data-stu-id="59af1-114">Display language</span></span>
    - <span data-ttu-id="59af1-115">교정 및 제작 도구</span><span class="sxs-lookup"><span data-stu-id="59af1-115">Proofing and authoring tools</span></span>

> [!NOTE]
> <span data-ttu-id="59af1-116">사용자는 설치 프로세스 중에 언어를 선택하여 언어 관련 기능만 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59af1-116">Users can only get language-related Features On Demand by selecting the language during the setup process.</span></span>

## <a name="after-completing-setup"></a><span data-ttu-id="59af1-117">설치를 완료한 후</span><span class="sxs-lookup"><span data-stu-id="59af1-117">After completing setup</span></span>

<span data-ttu-id="59af1-118">사용자는 설치 프로세스가 완료된 후 언제든지 Windows 10 및 엔터프라이즈용 Microsoft 365 앱에 대해 원하는 언어를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59af1-118">Users can select the language of their choice for Windows 10 and Microsoft 365 Apps for Enterprise anytime after the setup process is complete.</span></span> <span data-ttu-id="59af1-119">특히 다음 사항에 유의합니다.</span><span class="sxs-lookup"><span data-stu-id="59af1-119">Specifically:</span></span>

- <span data-ttu-id="59af1-120">Windows 10 언어 기능:</span><span class="sxs-lookup"><span data-stu-id="59af1-120">Windows 10 language features:</span></span>
    - <span data-ttu-id="59af1-121">표시 언어</span><span class="sxs-lookup"><span data-stu-id="59af1-121">Display language</span></span>
    - <span data-ttu-id="59af1-122">키보드 언어</span><span class="sxs-lookup"><span data-stu-id="59af1-122">Keyboard language</span></span>

- <span data-ttu-id="59af1-123">엔터프라이즈용 Microsoft 365 앱 언어 기능:</span><span class="sxs-lookup"><span data-stu-id="59af1-123">Microsoft 365 Apps for Enterprise language features:</span></span>
    - <span data-ttu-id="59af1-124">표시 언어</span><span class="sxs-lookup"><span data-stu-id="59af1-124">Display language</span></span>
    - <span data-ttu-id="59af1-125">교정 및 제작 도구</span><span class="sxs-lookup"><span data-stu-id="59af1-125">Proofing and authoring tools</span></span>

<span data-ttu-id="59af1-126">사용자가 설치할 [](#supported-languages) 수 있는 엔터프라이즈용 Microsoft 365 앱의 지원되는 언어를 만들 수 있도록 최신 **Workplace-Office-Language_Packs** 그룹에 사용자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="59af1-126">To make the [Supported languages](#supported-languages) for Microsoft 365 Apps for Enterprise available for your users to install, add the users to the **Modern Workplace-Office-Language_Packs** group.</span></span> <span data-ttu-id="59af1-127">언어는 Intune 회사 포털에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59af1-127">The languages will be available in the Intune Company Portal.</span></span>


## <a name="supported-languages"></a><span data-ttu-id="59af1-128">지원되는 언어</span><span class="sxs-lookup"><span data-stu-id="59af1-128">Supported languages</span></span>

<span data-ttu-id="59af1-129">새 장치의 경우 제조업체에서 필요한 언어가 포함된 장치 이미지를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="59af1-129">For new devices, your manufacturer must provide device images that include the languages you require.</span></span> <span data-ttu-id="59af1-130">제조업체 이미지에 지원되는 언어 목록에 제공된 언어가 다른 언어가 포함되어 있는 경우 서비스에서 여전히 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="59af1-130">If your manufacturer's image includes languages other than those provided in the supported languages list it is still supported by the service.</span></span>

<span data-ttu-id="59af1-131">기존 장치를 다시 사용하려면 Microsoft 계정 담당자와 함께 적절한 이미지를 얻어야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59af1-131">If you are reusing existing devices, you might need to work with your Microsoft account representative to obtain appropriate images.</span></span> <span data-ttu-id="59af1-132">자세한 내용은 장치 이미지를 [참조하세요.](../service-description/device-images.md)</span><span class="sxs-lookup"><span data-stu-id="59af1-132">For more information, see [Device images](../service-description/device-images.md).</span></span>

<span data-ttu-id="59af1-133">Microsoft Managed [Desktop에서](../service-description/device-images.md#universal-image) 제공하는 유니버설 이미지에는 다음 언어와 Windows 10용이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59af1-133">The [universal image](../service-description/device-images.md#universal-image) provided by Microsoft Managed Desktop includes these languages and for Windows 10:</span></span>

- <span data-ttu-id="59af1-134">영어(미국, GB, AU, CA, IN)</span><span class="sxs-lookup"><span data-stu-id="59af1-134">English (US, GB, AU, CA, IN)</span></span>
- <span data-ttu-id="59af1-135">스페인어(스페인, 멕시코)</span><span class="sxs-lookup"><span data-stu-id="59af1-135">Spanish (Spain, Mexico)</span></span>
- <span data-ttu-id="59af1-136">일본어</span><span class="sxs-lookup"><span data-stu-id="59af1-136">Japanese</span></span>
- <span data-ttu-id="59af1-137">프랑스어(프랑스, 캐나다)</span><span class="sxs-lookup"><span data-stu-id="59af1-137">French (France, Canada)</span></span>
- <span data-ttu-id="59af1-138">독일어</span><span class="sxs-lookup"><span data-stu-id="59af1-138">German</span></span>
- <span data-ttu-id="59af1-139">포르투갈어(브라질)</span><span class="sxs-lookup"><span data-stu-id="59af1-139">Portuguese (Brazil)</span></span>
- <span data-ttu-id="59af1-140">이탈리아어</span><span class="sxs-lookup"><span data-stu-id="59af1-140">Italian</span></span>
- <span data-ttu-id="59af1-141">Chinese Simplified</span><span class="sxs-lookup"><span data-stu-id="59af1-141">Chinese Simplified</span></span>
- <span data-ttu-id="59af1-142">네덜란드어</span><span class="sxs-lookup"><span data-stu-id="59af1-142">Dutch</span></span>  
- <span data-ttu-id="59af1-143">스웨덴어</span><span class="sxs-lookup"><span data-stu-id="59af1-143">Swedish</span></span>
- <span data-ttu-id="59af1-144">덴마크어</span><span class="sxs-lookup"><span data-stu-id="59af1-144">Danish</span></span>  
- <span data-ttu-id="59af1-145">핀란드어</span><span class="sxs-lookup"><span data-stu-id="59af1-145">Finnish</span></span> 
- <span data-ttu-id="59af1-146">러시아어</span><span class="sxs-lookup"><span data-stu-id="59af1-146">Russian</span></span> 
- <span data-ttu-id="59af1-147">노르웨이어(복말)</span><span class="sxs-lookup"><span data-stu-id="59af1-147">Norwegian (Bokmal)</span></span>
- <span data-ttu-id="59af1-148">한국어</span><span class="sxs-lookup"><span data-stu-id="59af1-148">Korean</span></span>
- <span data-ttu-id="59af1-149">Chinese Traditional</span><span class="sxs-lookup"><span data-stu-id="59af1-149">Chinese Traditional</span></span>
- <span data-ttu-id="59af1-150">폴란드어</span><span class="sxs-lookup"><span data-stu-id="59af1-150">Polish</span></span>
- <span data-ttu-id="59af1-151">터키어</span><span class="sxs-lookup"><span data-stu-id="59af1-151">Turkish</span></span>
- <span data-ttu-id="59af1-152">아랍어</span><span class="sxs-lookup"><span data-stu-id="59af1-152">Arabic</span></span>
- <span data-ttu-id="59af1-153">히브리어</span><span class="sxs-lookup"><span data-stu-id="59af1-153">Hebrew</span></span>
- <span data-ttu-id="59af1-154">포르투갈어(포르투갈)</span><span class="sxs-lookup"><span data-stu-id="59af1-154">Portuguese (Portugal)</span></span>
- <span data-ttu-id="59af1-155">체코어</span><span class="sxs-lookup"><span data-stu-id="59af1-155">Czech</span></span>
- <span data-ttu-id="59af1-156">헝가리어</span><span class="sxs-lookup"><span data-stu-id="59af1-156">Hungarian</span></span>
- <span data-ttu-id="59af1-157">태국어</span><span class="sxs-lookup"><span data-stu-id="59af1-157">Thai</span></span>
- <span data-ttu-id="59af1-158">인도네시아어</span><span class="sxs-lookup"><span data-stu-id="59af1-158">Indonesian</span></span>
- <span data-ttu-id="59af1-159">그리스어</span><span class="sxs-lookup"><span data-stu-id="59af1-159">Greek</span></span>
- <span data-ttu-id="59af1-160">슬로바키아어</span><span class="sxs-lookup"><span data-stu-id="59af1-160">Slovak</span></span>
- <span data-ttu-id="59af1-161">베트남어</span><span class="sxs-lookup"><span data-stu-id="59af1-161">Vietnamese</span></span>
- <span data-ttu-id="59af1-162">슬로베니아어</span><span class="sxs-lookup"><span data-stu-id="59af1-162">Slovenian</span></span>
- <span data-ttu-id="59af1-163">크로아티아어</span><span class="sxs-lookup"><span data-stu-id="59af1-163">Croatian</span></span>
- <span data-ttu-id="59af1-164">루마니아어</span><span class="sxs-lookup"><span data-stu-id="59af1-164">Romanian</span></span>
- <span data-ttu-id="59af1-165">리투아니아어</span><span class="sxs-lookup"><span data-stu-id="59af1-165">Lithuanian</span></span>
- <span data-ttu-id="59af1-166">불가리아어</span><span class="sxs-lookup"><span data-stu-id="59af1-166">Bulgarian</span></span>
- <span data-ttu-id="59af1-167">세르비아어(라틴 문자 알파벳)</span><span class="sxs-lookup"><span data-stu-id="59af1-167">Serbian (Latin alphabet)</span></span>
- <span data-ttu-id="59af1-168">라트비아어</span><span class="sxs-lookup"><span data-stu-id="59af1-168">Latvian</span></span>
- <span data-ttu-id="59af1-169">우크라이나어</span><span class="sxs-lookup"><span data-stu-id="59af1-169">Ukrainian</span></span>
- <span data-ttu-id="59af1-170">에스토니아어</span><span class="sxs-lookup"><span data-stu-id="59af1-170">Estonian</span></span>

<span data-ttu-id="59af1-171">엔터프라이즈용 Microsoft 365 앱은 약간 다른 목록을 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59af1-171">Microsoft 365 Apps for Enterprise might support a slightly different list.</span></span>

<span data-ttu-id="59af1-172">여기에 나열된 언어가 다른 언어가 필요한 경우 [](../working-with-managed-desktop/admin-support.md) 관리 포털을 사용하여 지원 요청을 [제출합니다.](access-admin-portal.md)</span><span class="sxs-lookup"><span data-stu-id="59af1-172">If your users need a language other than the ones listed here, file a [support request](../working-with-managed-desktop/admin-support.md) by using the [Admin portal](access-admin-portal.md).</span></span>

## <a name="languages-for-support-and-operations"></a><span data-ttu-id="59af1-173">지원 및 운영 언어</span><span class="sxs-lookup"><span data-stu-id="59af1-173">Languages for support and operations</span></span>

### <a name="user-support"></a><span data-ttu-id="59af1-174">사용자 지원</span><span class="sxs-lookup"><span data-stu-id="59af1-174">User support</span></span>
<span data-ttu-id="59af1-175">Microsoft Managed Desktop은 영어로만 지원을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="59af1-175">Microsoft Managed Desktop provides support only in English.</span></span> <span data-ttu-id="59af1-176">사용자가 도움말 보기 앱에서 다른 언어를 선택하면 Microsoft Managed Desktop에서 직접 지원하지 않고 일반 Microsoft 지원 채널에서 지원을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59af1-176">If users choose another language in the Get Help app, they will get support from the general Microsoft support channels, rather than support directly from Microsoft Managed Desktop.</span></span> <span data-ttu-id="59af1-177">자세한 내용은 [사용자에 대한 도움말 보기를 참조하세요.](../working-with-managed-desktop/end-user-support.md)</span><span class="sxs-lookup"><span data-stu-id="59af1-177">For more information, see [Getting help for users](../working-with-managed-desktop/end-user-support.md).</span></span>

<span data-ttu-id="59af1-178">사용자가 다른 언어로 지원을 필요로 하는 경우 Microsoft가 아닌 지원 원본이나 조직에서 지원을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="59af1-178">If your users need support in other languages, you'll have to provide that through non-Microsoft support sources or from your own organization.</span></span>

### <a name="admin-support-and-operations"></a><span data-ttu-id="59af1-179">관리자 지원 및 운영</span><span class="sxs-lookup"><span data-stu-id="59af1-179">Admin support and operations</span></span>
<span data-ttu-id="59af1-180">Microsoft Managed Desktop은 영어로만 관리자 지원을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="59af1-180">Microsoft Managed Desktop provides admin support only in English.</span></span> <span data-ttu-id="59af1-181">여기에는 관리 포털 및 Microsoft Managed Desktop 작업과의 모든 통신이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="59af1-181">This includes the Admin portal and all communications with Microsoft Managed Desktop Operations.</span></span> <span data-ttu-id="59af1-182">달리 지정하지 않는 한 모든 관리자 관련 상호 작용 및 인터페이스가 영어로 제공된다고 가정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="59af1-182">You should assume that all admin-related interactions and interfaces will be in English, unless specified otherwise.</span></span>


