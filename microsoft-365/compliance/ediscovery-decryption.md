---
title: EDiscovery에서 암호 해독
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Microsoft 365 eDiscovery 도구에서 전자 메일 메시지에 첨부 되는 암호화 된 문서를 처리 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 3a4a094f1da28c9a017836c099507f5af739b0b9
ms.sourcegitcommit: 9bf6a4f77f9af5fd988f6795bad3b240213a51fc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/10/2020
ms.locfileid: "48951121"
---
# <a name="decryption-in-microsoft-365-ediscovery-tools"></a><span data-ttu-id="976ad-103">Microsoft 365 eDiscovery 도구에서 암호 해독</span><span class="sxs-lookup"><span data-stu-id="976ad-103">Decryption in Microsoft 365 eDiscovery tools</span></span>

<span data-ttu-id="976ad-104">암호화는 파일 보호 및 정보 보호 전략의 중요 한 부분입니다.</span><span class="sxs-lookup"><span data-stu-id="976ad-104">Encryption is an important part of your file protection and information protection strategy.</span></span> <span data-ttu-id="976ad-105">모든 유형의 조직은 암호화 기술을 사용 하 여 조직 내의 중요 한 콘텐츠를 보호 하 고 적절 한 사용자 에게만 해당 콘텐츠에 대 한 액세스 권한이 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="976ad-105">Organizations of all types use encryption technology to protect sensitive content within their organization and ensure that only the right people have access to that content.</span></span>

<span data-ttu-id="976ad-106">암호화 된 콘텐츠에 대 한 일반적인 eDiscovery 작업을 실행 하려면 eDiscovery 관리자가 콘텐츠 검색, 핵심 eDiscovery 사례 및 고급 eDiscovery 사례에서 내보낸 것 처럼 전자 메일 메시지 콘텐츠를 해독 해야 했습니다.</span><span class="sxs-lookup"><span data-stu-id="976ad-106">To execute common eDiscovery tasks on encrypted content, eDiscovery managers were required to decrypt email message content as it was exported from content searches, Core eDiscovery cases, and Advanced eDiscovery cases.</span></span> <span data-ttu-id="976ad-107">Microsoft 암호화 기술을 사용 하 여 암호화 된 콘텐츠는 내보낼 때까지 검토에 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="976ad-107">Content encrypted with Microsoft encryption technologies was not available for review until after it was exported.</span></span>

<span data-ttu-id="976ad-108">EDiscovery 워크플로에서 암호화 된 콘텐츠를 보다 쉽게 관리할 수 있도록 하기 위해 Microsoft 365 eDiscovery 도구는 전자 메일 메시지에 첨부 되 고 Exchange Online에서 전송 되는 암호화 된 파일의 암호 해독이 통합 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="976ad-108">To make it easier to manage encrypted content in the eDiscovery workflow, Microsoft 365 eDiscovery tools now incorporate decryption of encrypted files that are attached to email messages and sent in Exchange Online.</span></span> <span data-ttu-id="976ad-109">이 새로운 기능을 수행 하기 전에는 권한 관리로 보호 되는 전자 메일 메시지의 콘텐츠 (연결 된 파일 아님)만 암호 해독 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="976ad-109">Prior to this new capability, only the content of an email message protected by rights management (and not attached files) were decrypted.</span></span> <span data-ttu-id="976ad-110">이제 Microsoft 암호화 기술로 암호화 된 파일이 검색 조건과 일치 하는 전자 메일 메시지에 첨부 되는 경우 검색 결과를 검토할 준비가 되 면 암호화 된 파일의 암호가 해독 됩니다.</span><span class="sxs-lookup"><span data-stu-id="976ad-110">Now, if a file that's encrypted with a Microsoft encryption technology is attached to an email message that matches the search criteria, the encrypted file will be decrypted when the search results are prepared for review.</span></span> <span data-ttu-id="976ad-111">이를 통해 eDiscovery 관리자는 검색 결과를 미리 볼 때 암호화 된 전자 메일 첨부 파일의 콘텐츠를 보고 고급 eDiscovery의 검토 집합에 추가한 후 검토를 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="976ad-111">This allows eDiscovery managers to view the content of encrypted email attachments when previewing search results, and review them once they have been added to a review set in Advanced eDiscovery.</span></span>

> [!NOTE]
> <span data-ttu-id="976ad-112">시작 하기 위해 Microsoft 365 eDiscovery 도구는 SharePoint Online 및 비즈니스용 OneDrive에 저장 되어 있는 암호화 된 문서를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="976ad-112">Starting soon Microsoft 365 eDiscovery tools will support encrypted documents stored in SharePoint Online and OneDrive for Business.</span></span>

## <a name="supported-encryption-technologies"></a><span data-ttu-id="976ad-113">지원 되는 암호화 기술</span><span class="sxs-lookup"><span data-stu-id="976ad-113">Supported encryption technologies</span></span>

<span data-ttu-id="976ad-114">Microsoft eDiscovery 도구는 Microsoft 암호화 기술로 암호화 된 항목을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="976ad-114">Microsoft eDiscovery tools support items encrypted with Microsoft encryption technologies.</span></span> <span data-ttu-id="976ad-115">이러한 기술에는 Office 메시지 암호화, Microsoft Information Protection (출시 예정) 및 Azure 권한 관리가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="976ad-115">These technologies include Office Message Encryption, Microsoft Information Protection (coming soon), and Azure Rights Management.</span></span> <span data-ttu-id="976ad-116">Microsoft 암호화 기술에 대 한 자세한 내용은 [encryption](encryption.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="976ad-116">For more information about Microsoft encryption technologies, see [Encryption](encryption.md).</span></span> <span data-ttu-id="976ad-117">타사 암호화 기술로 암호화 된 콘텐츠는 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="976ad-117">Content encrypted by third-party encryption technologies isn't supported.</span></span> <span data-ttu-id="976ad-118">여기에는 Microsoft 제품이 아닌 기술로 암호화 된 콘텐츠를 미리 보거나 내보낼 때 지원 되는 기능이 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="976ad-118">This includes no support when previewing or exporting content encrypted with non-Microsoft technologies.</span></span>

## <a name="ediscovery-activities-that-support-encrypted-items"></a><span data-ttu-id="976ad-119">암호화 된 항목을 지 원하는 eDiscovery 활동</span><span class="sxs-lookup"><span data-stu-id="976ad-119">eDiscovery activities that support encrypted items</span></span>

<span data-ttu-id="976ad-120">다음 표에는 전자 메일 massages에 첨부 되어 있는 암호화 된 파일의 암호 해독이 지원 되는 Microsoft 365 eDiscovery 도구에서 수행 하는 작업이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="976ad-120">The following table identifies the tasks performed in Microsoft 365 eDiscovery tools that support decryption of encrypted files attached to email massages.</span></span> <span data-ttu-id="976ad-121">검색 조건과 일치 하는 전자 메일 메시지에 첨부 된 암호화 된 파일에서 지원 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="976ad-121">The support tasks can be performed on an encrypted file that's attached to an email message that matches the criteria of a search.</span></span> <span data-ttu-id="976ad-122">값이 "N/A" 이면 해당 eDiscovery 도구에서 해당 함수를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="976ad-122">A value of "N/A" indicates that the function isn't available in the corresponding eDiscovery tool.</span></span>

|<span data-ttu-id="976ad-123">eDiscovery 작업</span><span class="sxs-lookup"><span data-stu-id="976ad-123">eDiscovery task</span></span>  |<span data-ttu-id="976ad-124">콘텐츠 검색</span><span class="sxs-lookup"><span data-stu-id="976ad-124">Content search</span></span>  |<span data-ttu-id="976ad-125">핵심 eDiscovery</span><span class="sxs-lookup"><span data-stu-id="976ad-125">Core eDiscovery</span></span>  |<span data-ttu-id="976ad-126">Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="976ad-126">Advanced eDiscovery</span></span>  |
|:---------|:---------|:---------|:---------|
|<span data-ttu-id="976ad-127">암호화 된 파일에서 콘텐츠 검색</span><span class="sxs-lookup"><span data-stu-id="976ad-127">Search for content in encrypted files</span></span>     |<span data-ttu-id="976ad-128">예</span><span class="sxs-lookup"><span data-stu-id="976ad-128">Yes</span></span>      |<span data-ttu-id="976ad-129">예</span><span class="sxs-lookup"><span data-stu-id="976ad-129">Yes</span></span>      |<span data-ttu-id="976ad-130">예</span><span class="sxs-lookup"><span data-stu-id="976ad-130">Yes</span></span>      |
|<span data-ttu-id="976ad-131">암호화 된 파일 미리 보기</span><span class="sxs-lookup"><span data-stu-id="976ad-131">Preview encrypted files</span></span>     |<span data-ttu-id="976ad-132">예</span><span class="sxs-lookup"><span data-stu-id="976ad-132">Yes</span></span>      |<span data-ttu-id="976ad-133">예</span><span class="sxs-lookup"><span data-stu-id="976ad-133">Yes</span></span>     |<span data-ttu-id="976ad-134">예</span><span class="sxs-lookup"><span data-stu-id="976ad-134">Yes</span></span>       |
|<span data-ttu-id="976ad-135">검토 집합에서 암호화 된 파일 검토</span><span class="sxs-lookup"><span data-stu-id="976ad-135">Review encrypted files in a review set</span></span>    |<span data-ttu-id="976ad-136">해당 없음</span><span class="sxs-lookup"><span data-stu-id="976ad-136">N/A</span></span>      |<span data-ttu-id="976ad-137">해당 없음</span><span class="sxs-lookup"><span data-stu-id="976ad-137">N/A</span></span>        | <span data-ttu-id="976ad-138">예</span><span class="sxs-lookup"><span data-stu-id="976ad-138">Yes</span></span>        |
|<span data-ttu-id="976ad-139">암호화 된 파일 내보내기</span><span class="sxs-lookup"><span data-stu-id="976ad-139">Export encrypted files</span></span>    |<span data-ttu-id="976ad-140">예</span><span class="sxs-lookup"><span data-stu-id="976ad-140">Yes</span></span>       |<span data-ttu-id="976ad-141">예</span><span class="sxs-lookup"><span data-stu-id="976ad-141">Yes</span></span>  |<span data-ttu-id="976ad-142">예</span><span class="sxs-lookup"><span data-stu-id="976ad-142">Yes</span></span>    |

## <a name="requirements-for-decryption-in-ediscovery"></a><span data-ttu-id="976ad-143">EDiscovery의 암호 해독 요구 사항</span><span class="sxs-lookup"><span data-stu-id="976ad-143">Requirements for decryption in eDiscovery</span></span>

<span data-ttu-id="976ad-144">Microsoft 암호화 기술로 암호화 된 첨부 파일을 미리 보고 검토 하 고 내보내려면 RMS 암호 해독 역할을 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="976ad-144">You have to be assigned the RMS Decrypt role to preview, review, and export attached files encrypted with Microsoft encryption technologies.</span></span> <span data-ttu-id="976ad-145">또한 고급 eDiscovery에서 검토 집합에 추가 된 암호화 된 전자 메일 첨부 파일을 검토 하 고 쿼리 하려면이 역할을 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="976ad-145">You also have to be assigned this role to review and query encrypted email attachments that are added to a review set in Advanced eDiscovery.</span></span>

<span data-ttu-id="976ad-146">이 역할은 Office 365 보안 & 준수 센터의 eDiscovery 관리자 역할 그룹에 기본적으로 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="976ad-146">This role is assigned by default to the eDiscovery Manager role group in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="976ad-147">RMS 암호 해독 역할에 대 한 자세한 내용은 [eDiscovery 사용 권한 할당](assign-ediscovery-permissions.md#rms-decrypt)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="976ad-147">For more information about the RMS Decrypt role, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md#rms-decrypt).</span></span>
