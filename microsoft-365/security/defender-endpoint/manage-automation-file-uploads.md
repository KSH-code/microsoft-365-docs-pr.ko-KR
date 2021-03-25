---
title: 자동화 파일 업로드 관리
description: 콘텐츠 분석을 사용하도록 설정하고 분석을 위해 제출할 파일 확장명 및 전자 메일 첨부 파일 확장명 구성
keywords: 자동화, 파일, 업로드, 콘텐츠, 분석, 파일, 확장명, 전자 메일, 첨부 파일
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: c8935368e4439221f2ce21cfa620e540c02165f8
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185852"
---
# <a name="manage-automation-file-uploads"></a><span data-ttu-id="cf48e-104">자동화 파일 업로드 관리</span><span class="sxs-lookup"><span data-stu-id="cf48e-104">Manage automation file uploads</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="cf48e-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="cf48e-105">**Applies to:**</span></span>
- [<span data-ttu-id="cf48e-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="cf48e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="cf48e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cf48e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="cf48e-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="cf48e-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="cf48e-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="cf48e-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-automationefileuploads-abovefoldlink)

<span data-ttu-id="cf48e-110">자동화된 조사에서 추가 검사를 위해 특정 파일 및 전자 메일 첨부 파일을 클라우드에 자동으로 업로드할 수 있도록 콘텐츠 분석 기능을 사용하도록 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="cf48e-110">Enable the content analysis capability so that certain files and email attachments can automatically be uploaded to the cloud for additional inspection in Automated investigation.</span></span>

<span data-ttu-id="cf48e-111">파일 확장명 이름과 전자 메일 첨부 파일 확장명을 지정하여 파일 및 전자 메일 첨부 파일을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="cf48e-111">Identify the files and email attachments by specifying the file extension names and email attachment extension names.</span></span> 

<span data-ttu-id="cf48e-112">예를 들어 *exe* 및 *bat을* 파일 또는 첨부 파일 확장명 이름으로 추가하는 경우 자동화된 조사 중에 추가 검사를 위해 해당 확장명을 가지는 모든 파일 또는 첨부 파일이 자동으로 클라우드로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf48e-112">For example, if you add *exe* and *bat* as file or attachment extension names, then all files or attachments with those extensions will automatically be sent to the cloud for additional inspection during Automated investigation.</span></span> 

## <a name="add-file-extension-names-and-attachment-extension-names"></a><span data-ttu-id="cf48e-113">파일 확장명 이름과 첨부 파일 확장명을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="cf48e-113">Add file extension names and attachment extension names.</span></span>

1. <span data-ttu-id="cf48e-114">탐색 창에서 설정 **자동화**  >  **파일 업로드 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="cf48e-114">In the navigation pane, select **Settings** > **Automation file uploads**.</span></span> 

2. <span data-ttu-id="cf48e-115">설정 및 해제 간에 콘텐츠 분석 **설정을** **전환합니다.**</span><span class="sxs-lookup"><span data-stu-id="cf48e-115">Toggle the content analysis setting between **On** and **Off**.</span></span>

3. <span data-ttu-id="cf48e-116">다음 내선 이름과 별도의 내선 이름을 각자 콤보로 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="cf48e-116">Configure the following extension names and separate extension names with a comma:</span></span>
   - <span data-ttu-id="cf48e-117">**파일 확장명** - 추가 검사를 위해 전자 메일 첨부 파일이 제출되는 것을 제외한 의심스러운 파일</span><span class="sxs-lookup"><span data-stu-id="cf48e-117">**File extension names** -  Suspicious files except email attachments will be submitted for additional inspection</span></span>
  

## <a name="related-topics"></a><span data-ttu-id="cf48e-118">관련 항목</span><span class="sxs-lookup"><span data-stu-id="cf48e-118">Related topics</span></span>
- [<span data-ttu-id="cf48e-119">자동화 폴더 제외 관리</span><span class="sxs-lookup"><span data-stu-id="cf48e-119">Manage automation folder exclusions</span></span>](manage-automation-folder-exclusions.md)
