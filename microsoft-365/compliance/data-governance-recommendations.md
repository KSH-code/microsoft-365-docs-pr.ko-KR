---
title: 데이터 거버넌스 권장 사항을 표시하기 위해 콘텐츠가 식별되는 방법
f1.keywords:
- NOCSH
ms.author: brendonb
author: cabailey
manager: laurawi
ms.date: 1/15/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
ms.collection:
- SPO_Content
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ROBOTS: NOINDEX, NOFOLLOW
description: 'Microsoft 365 보안 센터 및 Microsoft 365 규정 준수 센터에서는 조직의 현재 설정을 기반으로 데이터 거버넌스 권장 사항을 제공하며, 몇 번의 클릭으로 설정을 완료할 수 있습니다. 이 권장 사항의 일부는 조직 내의 특정 콘텐츠를 검색한 후 해당 콘텐츠를 관리하는 단계별 방법을 권장합니다. 예를 들어, 권장 사항이 비즈니스 측면에서 중요한 콘텐츠(예: 비공개 유지 권한 또는 NDA 정보)가 포함된 항목을 검색할 수 있으며, 사용자는 해당 항목에 보존 레이블을 자동으로 적용하여 필요에 따라 해당 항목을 분류하고 보존할 수 있습니다. 이 항목에는 사용자가 확인할 수 있는 데이터 거버넌스 권장 사항이 나열되어 있으며, 각 권장 사항을 표시하기 위해 어떤 콘텐츠가 검색되는지 설명합니다.'
ms.openlocfilehash: 9a022369fb783a498971c91664fa6532472d8589
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922612"
---
# <a name="how-content-is-identified-for-data-governance-recommendations"></a><span data-ttu-id="42dda-106">데이터 거버넌스 권장 사항을 표시하기 위해 콘텐츠가 식별되는 방법</span><span class="sxs-lookup"><span data-stu-id="42dda-106">How content is identified for data-governance recommendations</span></span>

<span data-ttu-id="42dda-p102">Microsoft 365 보안 센터 및 Microsoft 365 규정 준수 센터에서는 조직의 현재 설정을 기반으로 데이터 거버넌스 권장 사항을 제공하며, 몇 번의 클릭으로 설정을 완료할 수 있습니다. 이 권장 사항의 일부는 조직 내의 특정 콘텐츠를 검색한 후 해당 콘텐츠를 관리하는 단계별 방법을 권장합니다. 예를 들어, 권장 사항이 비즈니스 측면에서 중요한 콘텐츠(예: 비공개 유지 권한 또는 NDA 정보)가 포함된 항목을 검색할 수 있으며, 사용자는 해당 항목에 보존 레이블을 자동으로 적용하여 필요에 따라 해당 항목을 분류하고 보존할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42dda-p102">The Microsoft 365 security center and Microsoft 365 compliance center provide recommendations for data governance based on your org's current setup and lets you set things up in a couple clicks. Some of these recommendations detect specific content in your organization and then provide recommended steps for managing that content. For example, a recommendation might detect items that contain business-critical content (such as attorney-client privilege or NDA info), and then let you automatically apply a retention label to those items to ensure that they're classified and retained as needed.</span></span>

<span data-ttu-id="42dda-110">이 항목에는 사용자가 확인할 수 있는 데이터 거버넌스 권장 사항이 나열되어 있으며 각 권장 사항을 표시하기 위해 어떤 콘텐츠가 검색되는지 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="42dda-110">This topic lists the data-governance recommendations you might see and describes what content is detected to trigger each one.</span></span>

## <a name="clean-up-voicemail"></a><span data-ttu-id="42dda-111">음성 사서함 정리</span><span class="sxs-lookup"><span data-stu-id="42dda-111">Clean up voicemail</span></span>

<span data-ttu-id="42dda-p103">‘음성 메일’ 메시지 유형으로 식별된 전자 메일 메시지가 사용자의 사서함에서 감지되었을 때 이 권장 사항이 표시됩니다. [Exchange에서의 메시지 속성](/exchange/policy-and-compliance/ediscovery/message-properties-and-search-operators?view=exchserver-2019#searchable-properties-in-exchange)에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="42dda-p103">This recommendation appears when email messages identified as the message type 'voicemail' are detected in users' mailboxes. Learn more about [message properties in Exchange](/exchange/policy-and-compliance/ediscovery/message-properties-and-search-operators?view=exchserver-2019#searchable-properties-in-exchange).</span></span>

## <a name="label-attorney-client-privilege-content"></a><span data-ttu-id="42dda-114">비공개 유지 권한 콘텐츠 레이블 지정</span><span class="sxs-lookup"><span data-stu-id="42dda-114">Label attorney-client privilege content</span></span> 

<span data-ttu-id="42dda-115">다음 중 한 가지 조건이 충족되면 이 권장 사항이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="42dda-115">This recommendation appears when either of the following criteria are met.</span></span>

- <span data-ttu-id="42dda-116">전자 메일 메시지의 본문에서 다음 키워드 조합이 검색되는 경우:</span><span class="sxs-lookup"><span data-stu-id="42dda-116">Any of combination of these keywords is detected in the body of an email message:</span></span>
    - <span data-ttu-id="42dda-117">ACP</span><span class="sxs-lookup"><span data-stu-id="42dda-117">ACP</span></span>
    - <span data-ttu-id="42dda-118">비공개 유지 권한</span><span class="sxs-lookup"><span data-stu-id="42dda-118">Attorney Client Privilege</span></span>
    - <span data-ttu-id="42dda-119">비공개 유지 권한</span><span class="sxs-lookup"><span data-stu-id="42dda-119">Attorney-Client Privilege</span></span>
    - <span data-ttu-id="42dda-120">비공개 유지 권한</span><span class="sxs-lookup"><span data-stu-id="42dda-120">Attorney-Client Privileged</span></span>

- <span data-ttu-id="42dda-121">SharePoint 또는 OneDrive 파일에서 다음 키워드 조합이 검색되는 경우:</span><span class="sxs-lookup"><span data-stu-id="42dda-121">Any combination of these keywords are detected in SharePoint or OneDrive files:</span></span>
    - <span data-ttu-id="42dda-122">ACP</span><span class="sxs-lookup"><span data-stu-id="42dda-122">ACP</span></span>
    - <span data-ttu-id="42dda-123">비공개 유지 권한\*</span><span class="sxs-lookup"><span data-stu-id="42dda-123">Attorney Client Privilege\*</span></span>
    - <span data-ttu-id="42dda-124">AC 권한</span><span class="sxs-lookup"><span data-stu-id="42dda-124">AC Privilege</span></span>

## <a name="retain-audio-files"></a><span data-ttu-id="42dda-125">오디오 파일 보존</span><span class="sxs-lookup"><span data-stu-id="42dda-125">Retain audio files</span></span>

<span data-ttu-id="42dda-126">SharePoint 또는 OneDrive에서 다음 파일 형식이 검색되면 이 권장 사항이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="42dda-126">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="42dda-127">.MP3</span><span class="sxs-lookup"><span data-stu-id="42dda-127">.MP3</span></span>
- <span data-ttu-id="42dda-128">.WMA</span><span class="sxs-lookup"><span data-stu-id="42dda-128">.WMA</span></span>
- <span data-ttu-id="42dda-129">.WAV</span><span class="sxs-lookup"><span data-stu-id="42dda-129">.WAV</span></span>
- <span data-ttu-id="42dda-130">.RA</span><span class="sxs-lookup"><span data-stu-id="42dda-130">.RA</span></span>
- <span data-ttu-id="42dda-131">.RAM</span><span class="sxs-lookup"><span data-stu-id="42dda-131">.RAM</span></span>
- <span data-ttu-id="42dda-132">.RM</span><span class="sxs-lookup"><span data-stu-id="42dda-132">.RM</span></span>
- <span data-ttu-id="42dda-133">.MID</span><span class="sxs-lookup"><span data-stu-id="42dda-133">.MID</span></span>
- <span data-ttu-id="42dda-134">.OGG</span><span class="sxs-lookup"><span data-stu-id="42dda-134">.OGG</span></span>
- <span data-ttu-id="42dda-135">.AIFF</span><span class="sxs-lookup"><span data-stu-id="42dda-135">.AIFF</span></span>
- <span data-ttu-id="42dda-136">.PCM</span><span class="sxs-lookup"><span data-stu-id="42dda-136">.PCM</span></span>
- <span data-ttu-id="42dda-137">.AAC</span><span class="sxs-lookup"><span data-stu-id="42dda-137">.AAC</span></span>
- <span data-ttu-id="42dda-138">.FLAC</span><span class="sxs-lookup"><span data-stu-id="42dda-138">.FLAC</span></span>
- <span data-ttu-id="42dda-139">.ALAC</span><span class="sxs-lookup"><span data-stu-id="42dda-139">.ALAC</span></span>

## <a name="retain-cad-files"></a><span data-ttu-id="42dda-140">CAD 파일 보존</span><span class="sxs-lookup"><span data-stu-id="42dda-140">Retain CAD files</span></span>

<span data-ttu-id="42dda-141">SharePoint 또는 OneDrive에서 다음 파일 형식이 검색되면 이 권장 사항이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="42dda-141">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="42dda-142">.3DXML</span><span class="sxs-lookup"><span data-stu-id="42dda-142">.3DXML</span></span>
- <span data-ttu-id="42dda-143">.ACIS</span><span class="sxs-lookup"><span data-stu-id="42dda-143">.ACIS</span></span>
- <span data-ttu-id="42dda-144">.ARC</span><span class="sxs-lookup"><span data-stu-id="42dda-144">.ARC</span></span>
- <span data-ttu-id="42dda-145">.ASM</span><span class="sxs-lookup"><span data-stu-id="42dda-145">.ASM</span></span>
- <span data-ttu-id="42dda-146">.CAT\*</span><span class="sxs-lookup"><span data-stu-id="42dda-146">.CAT\*</span></span>
- <span data-ttu-id="42dda-147">.CGR</span><span class="sxs-lookup"><span data-stu-id="42dda-147">.CGR</span></span>
- <span data-ttu-id="42dda-148">.DW\*</span><span class="sxs-lookup"><span data-stu-id="42dda-148">.DW\*</span></span>
- <span data-ttu-id="42dda-149">.DX\*</span><span class="sxs-lookup"><span data-stu-id="42dda-149">.DX\*</span></span>
- <span data-ttu-id="42dda-150">.EDRW</span><span class="sxs-lookup"><span data-stu-id="42dda-150">.EDRW</span></span>
- <span data-ttu-id="42dda-151">.IAM</span><span class="sxs-lookup"><span data-stu-id="42dda-151">.IAM</span></span>
- <span data-ttu-id="42dda-152">.IGES</span><span class="sxs-lookup"><span data-stu-id="42dda-152">.IGES</span></span>
- <span data-ttu-id="42dda-153">.IGS</span><span class="sxs-lookup"><span data-stu-id="42dda-153">.IGS</span></span>
- <span data-ttu-id="42dda-154">.IPT</span><span class="sxs-lookup"><span data-stu-id="42dda-154">.IPT</span></span>
- <span data-ttu-id="42dda-155">.JT</span><span class="sxs-lookup"><span data-stu-id="42dda-155">.JT</span></span>
- <span data-ttu-id="42dda-156">.MF1</span><span class="sxs-lookup"><span data-stu-id="42dda-156">.MF1</span></span>
- <span data-ttu-id="42dda-157">.NEU</span><span class="sxs-lookup"><span data-stu-id="42dda-157">.NEU</span></span>
- <span data-ttu-id="42dda-158">.PAR</span><span class="sxs-lookup"><span data-stu-id="42dda-158">.PAR</span></span>
- <span data-ttu-id="42dda-159">.PKG</span><span class="sxs-lookup"><span data-stu-id="42dda-159">.PKG</span></span>
- <span data-ttu-id="42dda-160">.PRC</span><span class="sxs-lookup"><span data-stu-id="42dda-160">.PRC</span></span>
- <span data-ttu-id="42dda-161">.PRT</span><span class="sxs-lookup"><span data-stu-id="42dda-161">.PRT</span></span>
- <span data-ttu-id="42dda-162">.PSM</span><span class="sxs-lookup"><span data-stu-id="42dda-162">.PSM</span></span>
- <span data-ttu-id="42dda-163">.PWD</span><span class="sxs-lookup"><span data-stu-id="42dda-163">.PWD</span></span>
- <span data-ttu-id="42dda-164">.SLD\*</span><span class="sxs-lookup"><span data-stu-id="42dda-164">.SLD\*</span></span>
- <span data-ttu-id="42dda-165">.STEP</span><span class="sxs-lookup"><span data-stu-id="42dda-165">.STEP</span></span>
- <span data-ttu-id="42dda-166">.STL</span><span class="sxs-lookup"><span data-stu-id="42dda-166">.STL</span></span>
- <span data-ttu-id="42dda-167">.STP</span><span class="sxs-lookup"><span data-stu-id="42dda-167">.STP</span></span>
- <span data-ttu-id="42dda-168">.U3D</span><span class="sxs-lookup"><span data-stu-id="42dda-168">.U3D</span></span>
- <span data-ttu-id="42dda-169">.UNV</span><span class="sxs-lookup"><span data-stu-id="42dda-169">.UNV</span></span>
- <span data-ttu-id="42dda-170">.VRML</span><span class="sxs-lookup"><span data-stu-id="42dda-170">.VRML</span></span>
- <span data-ttu-id="42dda-171">.WRL</span><span class="sxs-lookup"><span data-stu-id="42dda-171">.WRL</span></span>
- <span data-ttu-id="42dda-172">.X_\*</span><span class="sxs-lookup"><span data-stu-id="42dda-172">.X_\*</span></span>
- <span data-ttu-id="42dda-173">.XAS</span><span class="sxs-lookup"><span data-stu-id="42dda-173">.XAS</span></span>
- <span data-ttu-id="42dda-174">.XMT\*</span><span class="sxs-lookup"><span data-stu-id="42dda-174">.XMT\*</span></span>
- <span data-ttu-id="42dda-175">.XPR</span><span class="sxs-lookup"><span data-stu-id="42dda-175">.XPR</span></span>

## <a name="retain-image-files"></a><span data-ttu-id="42dda-176">이미지 파일 보존</span><span class="sxs-lookup"><span data-stu-id="42dda-176">Retain image files</span></span>

<span data-ttu-id="42dda-177">SharePoint 또는 OneDrive에서 다음 파일 형식이 검색되면 이 권장 사항이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="42dda-177">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="42dda-178">.JPEG</span><span class="sxs-lookup"><span data-stu-id="42dda-178">.JPEG</span></span>
- <span data-ttu-id="42dda-179">.GIF</span><span class="sxs-lookup"><span data-stu-id="42dda-179">.GIF</span></span>
- <span data-ttu-id="42dda-180">.TIF\*</span><span class="sxs-lookup"><span data-stu-id="42dda-180">.TIF\*</span></span>
- <span data-ttu-id="42dda-181">.BMP</span><span class="sxs-lookup"><span data-stu-id="42dda-181">.BMP</span></span>
- <span data-ttu-id="42dda-182">.PNG</span><span class="sxs-lookup"><span data-stu-id="42dda-182">.PNG</span></span>
- <span data-ttu-id="42dda-183">.RAW</span><span class="sxs-lookup"><span data-stu-id="42dda-183">.RAW</span></span>
- <span data-ttu-id="42dda-184">.PSD</span><span class="sxs-lookup"><span data-stu-id="42dda-184">.PSD</span></span>
- <span data-ttu-id="42dda-185">.PSP</span><span class="sxs-lookup"><span data-stu-id="42dda-185">.PSP</span></span>
- <span data-ttu-id="42dda-186">.JPG</span><span class="sxs-lookup"><span data-stu-id="42dda-186">.JPG</span></span>
- <span data-ttu-id="42dda-187">.EXIF</span><span class="sxs-lookup"><span data-stu-id="42dda-187">.EXIF</span></span>
- <span data-ttu-id="42dda-188">.PPM</span><span class="sxs-lookup"><span data-stu-id="42dda-188">.PPM</span></span>
- <span data-ttu-id="42dda-189">.PGM</span><span class="sxs-lookup"><span data-stu-id="42dda-189">.PGM</span></span>
- <span data-ttu-id="42dda-190">.PBM</span><span class="sxs-lookup"><span data-stu-id="42dda-190">.PBM</span></span>
- <span data-ttu-id="42dda-191">.PNM</span><span class="sxs-lookup"><span data-stu-id="42dda-191">.PNM</span></span>
- <span data-ttu-id="42dda-192">.WEBP</span><span class="sxs-lookup"><span data-stu-id="42dda-192">.WEBP</span></span>

## <a name="retain-nda-content"></a><span data-ttu-id="42dda-193">NDA 콘텐츠 보존</span><span class="sxs-lookup"><span data-stu-id="42dda-193">Retain NDA content</span></span> 

<span data-ttu-id="42dda-194">다음 중 한 가지 조건이 충족되면 이 권장 사항이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="42dda-194">This recommendation appears when either of the following criteria are met.</span></span>

- <span data-ttu-id="42dda-195">전자 메일 메시지의 본문에서 다음 키워드 조합이 검색되는 경우:</span><span class="sxs-lookup"><span data-stu-id="42dda-195">Any of combination of these keywords is detected in the body of an email message:</span></span>
    - <span data-ttu-id="42dda-196">NDA</span><span class="sxs-lookup"><span data-stu-id="42dda-196">NDA</span></span>
    - <span data-ttu-id="42dda-197">“비밀 유지 계약”</span><span class="sxs-lookup"><span data-stu-id="42dda-197">"Non-Disclosure Agreement"</span></span>
    - <span data-ttu-id="42dda-198">“비밀 유지 계약”</span><span class="sxs-lookup"><span data-stu-id="42dda-198">"Non Disclosure Agreement"</span></span>

- <span data-ttu-id="42dda-199">SharePoint 또는 OneDrive의 .PDF 또는 .DOC 파일에서 다음 키워드 조합이 검색되는 경우:</span><span class="sxs-lookup"><span data-stu-id="42dda-199">Any combination of these keywords are detected in .PDF or .DOC files in SharePoint or OneDrive:</span></span>
    - <span data-ttu-id="42dda-200">NDA</span><span class="sxs-lookup"><span data-stu-id="42dda-200">NDA</span></span>
    - <span data-ttu-id="42dda-201">비밀 유지 계약</span><span class="sxs-lookup"><span data-stu-id="42dda-201">Non Disclosure Agreement</span></span>

## <a name="retain-software-development-files"></a><span data-ttu-id="42dda-202">소프트웨어 개발 파일 보존</span><span class="sxs-lookup"><span data-stu-id="42dda-202">Retain software development files</span></span>

<span data-ttu-id="42dda-203">SharePoint 또는 OneDrive에서 다음 파일 형식이 검색되면 이 권장 사항이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="42dda-203">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="42dda-204">.ASAX</span><span class="sxs-lookup"><span data-stu-id="42dda-204">.ASAX</span></span>
- <span data-ttu-id="42dda-205">.ASM</span><span class="sxs-lookup"><span data-stu-id="42dda-205">.ASM</span></span>
- <span data-ttu-id="42dda-206">.ASP\*</span><span class="sxs-lookup"><span data-stu-id="42dda-206">.ASP\*</span></span>
- <span data-ttu-id="42dda-207">.BAT</span><span class="sxs-lookup"><span data-stu-id="42dda-207">.BAT</span></span>
- <span data-ttu-id="42dda-208">.CONFIG</span><span class="sxs-lookup"><span data-stu-id="42dda-208">.CONFIG</span></span>
- <span data-ttu-id="42dda-209">.CS</span><span class="sxs-lookup"><span data-stu-id="42dda-209">.CS</span></span>
- <span data-ttu-id="42dda-210">.CSS</span><span class="sxs-lookup"><span data-stu-id="42dda-210">.CSS</span></span>
- <span data-ttu-id="42dda-211">.DISCO</span><span class="sxs-lookup"><span data-stu-id="42dda-211">.DISCO</span></span>
- <span data-ttu-id="42dda-212">.HTM\*</span><span class="sxs-lookup"><span data-stu-id="42dda-212">.HTM\*</span></span>
- <span data-ttu-id="42dda-213">.INC</span><span class="sxs-lookup"><span data-stu-id="42dda-213">.INC</span></span>
- <span data-ttu-id="42dda-214">.JAD</span><span class="sxs-lookup"><span data-stu-id="42dda-214">.JAD</span></span>
- <span data-ttu-id="42dda-215">.JAVA</span><span class="sxs-lookup"><span data-stu-id="42dda-215">.JAVA</span></span>
- <span data-ttu-id="42dda-216">.JS\*</span><span class="sxs-lookup"><span data-stu-id="42dda-216">.JS\*</span></span>
- <span data-ttu-id="42dda-217">.LIB</span><span class="sxs-lookup"><span data-stu-id="42dda-217">.LIB</span></span>
- <span data-ttu-id="42dda-218">.O</span><span class="sxs-lookup"><span data-stu-id="42dda-218">.O</span></span>
- <span data-ttu-id="42dda-219">.PHP</span><span class="sxs-lookup"><span data-stu-id="42dda-219">.PHP</span></span>
- <span data-ttu-id="42dda-220">.RC</span><span class="sxs-lookup"><span data-stu-id="42dda-220">.RC</span></span>
- <span data-ttu-id="42dda-221">.RESX</span><span class="sxs-lookup"><span data-stu-id="42dda-221">.RESX</span></span>
- <span data-ttu-id="42dda-222">.RPT</span><span class="sxs-lookup"><span data-stu-id="42dda-222">.RPT</span></span>
- <span data-ttu-id="42dda-223">.RSS</span><span class="sxs-lookup"><span data-stu-id="42dda-223">.RSS</span></span>
- <span data-ttu-id="42dda-224">.SCPT</span><span class="sxs-lookup"><span data-stu-id="42dda-224">.SCPT</span></span>
- <span data-ttu-id="42dda-225">.SRC</span><span class="sxs-lookup"><span data-stu-id="42dda-225">.SRC</span></span>
- <span data-ttu-id="42dda-226">.VB\*</span><span class="sxs-lookup"><span data-stu-id="42dda-226">.VB\*</span></span>
- <span data-ttu-id="42dda-227">.WSF</span><span class="sxs-lookup"><span data-stu-id="42dda-227">.WSF</span></span>
- <span data-ttu-id="42dda-228">.XCODEPROJ</span><span class="sxs-lookup"><span data-stu-id="42dda-228">.XCODEPROJ</span></span>
- <span data-ttu-id="42dda-229">.XML</span><span class="sxs-lookup"><span data-stu-id="42dda-229">.XML</span></span>
- <span data-ttu-id="42dda-230">.XSD</span><span class="sxs-lookup"><span data-stu-id="42dda-230">.XSD</span></span>
- <span data-ttu-id="42dda-231">.XSL\*</span><span class="sxs-lookup"><span data-stu-id="42dda-231">.XSL\*</span></span>

## <a name="retain-video-files"></a><span data-ttu-id="42dda-232">비디오 파일 보존</span><span class="sxs-lookup"><span data-stu-id="42dda-232">Retain video files</span></span>

<span data-ttu-id="42dda-233">SharePoint 또는 OneDrive에서 다음 파일 형식이 검색되면 이 권장 사항이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="42dda-233">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="42dda-234">.AVCHD</span><span class="sxs-lookup"><span data-stu-id="42dda-234">.AVCHD</span></span>
- <span data-ttu-id="42dda-235">.AVI</span><span class="sxs-lookup"><span data-stu-id="42dda-235">.AVI</span></span>
- <span data-ttu-id="42dda-236">.FLV</span><span class="sxs-lookup"><span data-stu-id="42dda-236">.FLV</span></span>
- <span data-ttu-id="42dda-237">.MOV</span><span class="sxs-lookup"><span data-stu-id="42dda-237">.MOV</span></span>
- <span data-ttu-id="42dda-238">.MP2V</span><span class="sxs-lookup"><span data-stu-id="42dda-238">.MP2V</span></span>
- <span data-ttu-id="42dda-239">.MP4</span><span class="sxs-lookup"><span data-stu-id="42dda-239">.MP4</span></span>
- <span data-ttu-id="42dda-240">.MP4V</span><span class="sxs-lookup"><span data-stu-id="42dda-240">.MP4V</span></span>
- <span data-ttu-id="42dda-241">.MPE</span><span class="sxs-lookup"><span data-stu-id="42dda-241">.MPE</span></span>
- <span data-ttu-id="42dda-242">.MPEG</span><span class="sxs-lookup"><span data-stu-id="42dda-242">.MPEG</span></span>
- <span data-ttu-id="42dda-243">.MPEG1</span><span class="sxs-lookup"><span data-stu-id="42dda-243">.MPEG1</span></span>
- <span data-ttu-id="42dda-244">.MPEG2</span><span class="sxs-lookup"><span data-stu-id="42dda-244">.MPEG2</span></span>
- <span data-ttu-id="42dda-245">.MPEG4</span><span class="sxs-lookup"><span data-stu-id="42dda-245">.MPEG4</span></span>
- <span data-ttu-id="42dda-246">.MPG</span><span class="sxs-lookup"><span data-stu-id="42dda-246">.MPG</span></span>
- <span data-ttu-id="42dda-247">.MPG2</span><span class="sxs-lookup"><span data-stu-id="42dda-247">.MPG2</span></span>
- <span data-ttu-id="42dda-248">.MPG4</span><span class="sxs-lookup"><span data-stu-id="42dda-248">.MPG4</span></span>
- <span data-ttu-id="42dda-249">.WMV</span><span class="sxs-lookup"><span data-stu-id="42dda-249">.WMV</span></span>
- <span data-ttu-id="42dda-250">.XMV</span><span class="sxs-lookup"><span data-stu-id="42dda-250">.XMV</span></span>