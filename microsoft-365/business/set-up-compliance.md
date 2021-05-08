---
title: 보안 위협에 대한 위협 Microsoft 365 Business Premium
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: 규정 준수 기능을 설정하여 데이터 손실을 방지하고 사용자와 고객의 중요한 정보를 안전하게 보호합니다.
ms.openlocfilehash: 945f8a283b90b89da2fbe67a073e0807b80d198f
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245087"
---
# <a name="set-up-compliance-features"></a><span data-ttu-id="baa56-103">준수 기능 설정</span><span class="sxs-lookup"><span data-stu-id="baa56-103">Set up compliance features</span></span>

<span data-ttu-id="baa56-104">사용자 Microsoft 365 Business Premium 및 장치를 보호하고 사용자와 고객의 중요한 정보를 안전하게 유지하는 데 도움이 되는 기능이 함께 제공되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="baa56-104">Your Microsoft 365 Business Premium comes with features to protect your data and devices, and help you keep your and your customers' sensitive information secure.</span></span>

## <a name="set-up-dlp-features"></a><span data-ttu-id="baa56-105">DLP 기능 설정</span><span class="sxs-lookup"><span data-stu-id="baa56-105">Set up DLP features</span></span>

<span data-ttu-id="baa56-106">개인 [데이터 손실을](../compliance/create-a-dlp-policy-from-a-template.md) 방지하는 정책을 설정하는 방법에 대한 예제는 템플릿에서 DLP 정책 만들기를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="baa56-106">See [Create a DLP policy from a template](../compliance/create-a-dlp-policy-from-a-template.md) for an example on how to set up a policy to protect against protect loss of personal data.</span></span> 
  
<span data-ttu-id="baa56-107">DLP는 다양한 로 로컬에 대해 즉시 사용할 수 있는 많은 정책 템플릿과 함께 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="baa56-107">DLP comes with many ready-to-use policy templates for many different locales.</span></span> <span data-ttu-id="baa56-108">예를 들어 오스트레일리아 재무 데이터, 캐나다 개인 정보법, 미국 재무 데이터 등입니다.</span><span class="sxs-lookup"><span data-stu-id="baa56-108">For example, Australia Financial Data, Canada Personal Information Act, U.S. Financial Data, and so on.</span></span> <span data-ttu-id="baa56-109">전체 [목록은 DLP 정책 템플릿에](../compliance/what-the-dlp-policy-templates-include.md) 포함된 것을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="baa56-109">See [What the DLP policy templates include](../compliance/what-the-dlp-policy-templates-include.md) for a full list.</span></span> <span data-ttu-id="baa56-110">이러한 모든 템플릿은 PII 템플릿 예제와 유사하게 사용하도록 설정될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="baa56-110">All of these templates can be enabled similar to the PII template example.</span></span> 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a><span data-ttu-id="baa56-111">Exchange Online Archiving을 사용하여 전자 메일 보존 설정</span><span class="sxs-lookup"><span data-stu-id="baa56-111">Set up email retention with Exchange Online Archiving</span></span>

 <span data-ttu-id="baa56-112">**Exchange Online Archiving** 라이선스 기능은 eDiscovery에 대한 전자 메일 콘텐츠를 보존하여 규정 준수 및 규정 표준을 유지하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="baa56-112">**Exchange Online Archiving** license features help maintain compliance and regulatory standards by preserving email content for eDiscovery.</span></span> <span data-ttu-id="baa56-113">또한 소송이 있는 경우 위험을 줄이는 데 도움이 되고, 보안 위반 후 또는 삭제된 항목을 복구해야 할 때 데이터를 복구할 수 있는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="baa56-113">It also helps reduce your risk if there is a lawsuit, and provides a way to recover data after a security breach or when you need to recover deleted items.</span></span> <span data-ttu-id="baa56-114">소송 보존을 사용하여 사용자의 모든 콘텐츠를 보존하거나 보존 정책을 사용하여 보존할 콘텐츠를 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="baa56-114">You can use litigation hold to preserve all of a user's content, or use retention policies to customize what you want to preserve.</span></span>
  
<span data-ttu-id="baa56-115">**소송 보존:** 사용자의 전체 사서함에 소송 보존을 적용하여 삭제한 항목을 포함하는 모든 사서함 콘텐츠를 보존할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="baa56-115">**Litigation hold:** You can preserve all mailbox content including deleted items by putting a user's entire mailbox on litigation hold.</span></span> 
    
<span data-ttu-id="baa56-116">사서함에 소송 보존을 적용하려면 관리 센터에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="baa56-116">To place a mailbox on litigation hold, in the Admin center:</span></span>
    
1. <span data-ttu-id="baa56-117">왼쪽 탐색 영역에서 **사용자** \> **활성 사용자** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="baa56-117">In the left nav, go to **Users** \> **Active users**.</span></span>
    
2. <span data-ttu-id="baa56-118">사서함에 소송을 보류할 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="baa56-118">Select a user whose mailbox you want to place on litigation hold.</span></span> <span data-ttu-id="baa56-119">사용자 창에서 메일 설정 을 확장하고 추가 설정 옆에 **있는** 속성 **편집을 Exchange 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="baa56-119">In the user pane, expand **Mail settings**, and next to **More settings**, choose **Edit Exchange properties**.</span></span>
    
3. <span data-ttu-id="baa56-120">사용자의 사서함 페이지에서 왼쪽 탐색 영역의 \*\* 사서함 기능\*\*을 선택하고 **소송 보존** 아래의 **사용** 링크를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="baa56-120">On the mailbox page for the user, choose \*\* mailbox features \*\* on the left nav, and then choose the **Enable** link under **Litigation hold**.</span></span>
    
4. <span data-ttu-id="baa56-121">소송  보유 대화 상자에서 소송 보유 기간 필드에 소송 보유 기간을 **지정할 수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="baa56-121">In the **litigation hold** dialog box, you can specify the litigation hold duration in the **Litigation hold duration** field.</span></span> <span data-ttu-id="baa56-122">무한 보류를 하려는 경우 필드를 비워 두면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="baa56-122">Leave the field empty if you want to place an infinite hold.</span></span> <span data-ttu-id="baa56-123">또한 메모를 추가하고 사서함 소유자를 소송 보류에 대해 더 설명해야 할 수 있는 웹 사이트에 지시할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="baa56-123">You can also add notes and direct the mailbox owner to a website you might have to explain more about the litigation hold.</span></span> <span data-ttu-id="baa56-124">\>**를 저장합니다.**</span><span class="sxs-lookup"><span data-stu-id="baa56-124">\> **Save**.</span></span>
    
<span data-ttu-id="baa56-p105">**보존:** 특정 기간 동안 보존하거나 보존 기간이 끝나면 영구적으로 콘텐츠를 삭제하는 것과 같은 사용자 지정된 보존 정책을 사용하도록 설정할 수 있습니다. 자세한 내용은 [보존 정책 개요](../compliance/retention.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="baa56-p105">**Retention:** You can enable customized retention policies, for example, to preserve for a specific amount of time or delete content permanently at the end of the retention period. To learn more, see [Overview of retention policies](../compliance/retention.md).</span></span>

## <a name="set-up-sensitivity-labels"></a><span data-ttu-id="baa56-127">민감도 레이블 설정</span><span class="sxs-lookup"><span data-stu-id="baa56-127">Set up Sensitivity labels</span></span>

<span data-ttu-id="baa56-128">민감도 레이블은 AIP(Azure Information Protection) 플랜 1과 함께 제공되어 레이블을 적용하여 문서 및 전자 메일을 분류하고 선택적으로 보호하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="baa56-128">Sensitivity labels come with Azure Information Protection (AIP) Plan 1, and help you classify, and optionally protect your documents and emails, by applying labels.</span></span> <span data-ttu-id="baa56-129">규칙 및 조건을 정의하는 관리자가 레이블을 자동으로 적용하거나, 사용자가 수동으로 또는 사용자에게 권장 사항을 제공한 조합을 사용하여 레이블을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="baa56-129">Labels can be applied automatically by administrators who define rules and conditions, manually by users, or by using a combination where users are given recommendations.</span></span>

<span data-ttu-id="baa56-130">민감도 레이블을 설정하기 위해 민감도 레이블 비디오를 만들고 [관리합니다.](../business-video/create-sensitivity-labels.md)</span><span class="sxs-lookup"><span data-stu-id="baa56-130">To set up Sensitivity labels, view [create and manage sensitivity labels](../business-video/create-sensitivity-labels.md) video.</span></span>



### <a name="install-the-azure-information-protection-client-manually"></a><span data-ttu-id="baa56-131">수동으로 Azure Information Protection 클라이언트 설치</span><span class="sxs-lookup"><span data-stu-id="baa56-131">Install the Azure Information Protection client manually</span></span>

<span data-ttu-id="baa56-132">AIP 클라이언트를 수동으로 설치하려면</span><span class="sxs-lookup"><span data-stu-id="baa56-132">To manually install the AIP client:</span></span>

1. <span data-ttu-id="baa56-133">Microsoft **AzinfoProtection_UL.exe** [센터에서 다운로드할 수 있습니다.](https://www.microsoft.com/download/details.aspx?id=53018)</span><span class="sxs-lookup"><span data-stu-id="baa56-133">Download **AzinfoProtection_UL.exe** from [Microsoft download center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>
 
2. <span data-ttu-id="baa56-134">Word 문서를 보고 홈 탭에서 민감도 옵션을 사용할  수 있는지 확인하여 설치가 완료된지 **확인할 수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="baa56-134">You can verify that the installation worked by viewing a Word document and making sure that the **Sensitivity** option is available on the **Home** tab.</span></span>
<br/><span data-ttu-id="baa56-135">![Word 문서의 보호 탭 드롭다운](../media/word-sensitivity.png)</span><span class="sxs-lookup"><span data-stu-id="baa56-135">![Protection tab drop-down in a Word document.](../media/word-sensitivity.png)</span></span>

<span data-ttu-id="baa56-136">자세한 내용은 [클라이언트 설치를 참조하세요.](/azure/information-protection/infoprotect-tutorial-step3)</span><span class="sxs-lookup"><span data-stu-id="baa56-136">For more information, see [Install the client](/azure/information-protection/infoprotect-tutorial-step3).</span></span>