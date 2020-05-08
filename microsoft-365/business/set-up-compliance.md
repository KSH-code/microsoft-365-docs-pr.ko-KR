---
title: Microsoft 365 Business Premium에 대 한 위협 보호 강화
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
search.appverid:
- BCS160
- MET150
description: 규정 준수 기능을 설정 하 여 데이터 손실을 방지 하 고 및 고객의 중요 한 정보를 안전 하 게 유지 합니다.
ms.openlocfilehash: a3405207cd7d2d6565807ef0f3a51acbcb80409a
ms.sourcegitcommit: 46644f9778bc70ab6d62783e0a1e60ba2eccc27f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2020
ms.locfileid: "44165740"
---
# <a name="set-up-compliance-features"></a><span data-ttu-id="39327-103">준수 기능 설정</span><span class="sxs-lookup"><span data-stu-id="39327-103">Set up compliance features</span></span>

<span data-ttu-id="39327-104">Microsoft 365 Business Premium에는 데이터와 장치를 보호 하는 기능이 제공 되며, 고객의 중요 한 정보를 안전 하 게 유지 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39327-104">Your Microsoft 365 Business Premium comes with features to protect your data and devices, and help you keep your and your customers' sensitive information secure.</span></span>

## <a name="set-up-dlp-features"></a><span data-ttu-id="39327-105">DLP 기능 설정</span><span class="sxs-lookup"><span data-stu-id="39327-105">Set up DLP features</span></span>

<span data-ttu-id="39327-106">PII(개인 식별 정보)를 보호하도록 정책을 설정하는 방법의 예제를 보려면 [템플릿에서 DLP 정책 만들기](https://docs.microsoft.com/microsoft-365/compliance/create-a-dlp-policy-from-a-template)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="39327-106">See [Create a DLP policy from a template](https://docs.microsoft.com/microsoft-365/compliance/create-a-dlp-policy-from-a-template) for an example on how to set up a policy to protect against personally identifiable information (PII).</span></span> 
  
<span data-ttu-id="39327-107">DLP에는 다양 한 로캘에 대 한 다양 한 사용 가능 정책 템플릿이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39327-107">DLP comes with many ready-to-use policy templates for many different locales.</span></span> <span data-ttu-id="39327-108">예를 들어 오스트레일리아 재무 데이터, 캐나다 개인 정보 Act, 미국 재무 데이터 등이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39327-108">For example, Australia Financial Data, Canada Personal Information Act, U.S. Financial Data, and so on.</span></span> <span data-ttu-id="39327-109">전체 목록에 대해 [DLP 정책 템플릿에 포함 된 내용을](https://docs.microsoft.com/microsoft-365/compliance/what-the-dlp-policy-templates-include) 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="39327-109">See [What the DLP policy templates include](https://docs.microsoft.com/microsoft-365/compliance/what-the-dlp-policy-templates-include) for a full list.</span></span> <span data-ttu-id="39327-110">이러한 서식 파일은 모두 PII 서식 파일 예제와 비슷하게 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39327-110">All of these templates can be enabled similar to the PII template example.</span></span> 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a><span data-ttu-id="39327-111">Exchange Online Archiving을 사용하여 전자 메일 보존 설정</span><span class="sxs-lookup"><span data-stu-id="39327-111">Set up email retention with Exchange Online Archiving</span></span>

 <span data-ttu-id="39327-112">**Exchange Online 보관** 라이선스 기능은 eDiscovery에 대 한 전자 메일 콘텐츠를 보존 하 여 준수 및 규제 표준을 유지 관리 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39327-112">**Exchange Online Archiving** license features help maintain compliance and regulatory standards by preserving email content for eDiscovery.</span></span> <span data-ttu-id="39327-113">또한 서 소송이가 있는 경우 위험을 줄이고, 보안 위반 후 또는 삭제 된 항목을 복구 해야 하는 경우 데이터를 복구할 수 있는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="39327-113">It also helps reduce your risk if there is a lawsuit, and provides a way to recover data after a security breach or when you need to recover deleted items.</span></span> <span data-ttu-id="39327-114">소송 보존을 사용 하 여 모든 사용자의 콘텐츠를 보존 하거나 보존 정책을 사용 하 여 보존 하려는 항목을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39327-114">You can use litigation hold to preserve all of a user's content, or use retention policies to customize what you want to preserve.</span></span>
  
<span data-ttu-id="39327-115">**소송 보존:** 사용자의 전체 사서함에 소송 보존을 적용하여 삭제한 항목을 포함하는 모든 사서함 콘텐츠를 보존할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39327-115">**Litigation hold:** You can preserve all mailbox content including deleted items by putting a user's entire mailbox on litigation hold.</span></span> 
    
<span data-ttu-id="39327-116">사서함에 소송 보존을 적용하려면 관리 센터에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="39327-116">To place a mailbox on litigation hold, in the Admin center:</span></span>
    
1. <span data-ttu-id="39327-117">왼쪽 탐색 영역에서 **사용자** \> **활성 사용자**로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="39327-117">In the left nav, go to **Users** \> **Active users**.</span></span>
    
2. <span data-ttu-id="39327-118">사서함에 소송 보존을 적용 하려는 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="39327-118">Select a user whose mailbox you want to place on litigation hold.</span></span> <span data-ttu-id="39327-119">사용자 창에서 **메일 설정을**확장 하 고 **기타 설정**옆에 있는 **Exchange 속성 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="39327-119">In the user pane, expand **Mail settings**, and next to **More settings**, choose **Edit Exchange properties**.</span></span>
    
3. <span data-ttu-id="39327-120">사용자의 사서함 페이지에서 왼쪽 탐색 영역의 \*\* 사서함 기능\*\*을 선택하고 **소송 보존** 아래의 **사용** 링크를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="39327-120">On the mailbox page for the user, choose \*\* mailbox features \*\* on the left nav, and then choose the **Enable** link under **Litigation hold**.</span></span>
    
4. <span data-ttu-id="39327-121">**소송** 보존 대화 상자의 소송 보존 **기간** 필드에 소송 보존 기간을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39327-121">In the **litigation hold** dialog box, you can specify the litigation hold duration in the **Litigation hold duration** field.</span></span> <span data-ttu-id="39327-122">무기한 유지 하려면 필드를 비워 둡니다.</span><span class="sxs-lookup"><span data-stu-id="39327-122">Leave the field empty if you want to place an infinite hold.</span></span> <span data-ttu-id="39327-123">메모를 추가 하 고 사서함 소유자에 게 소송 보존에 대 한 자세한 내용을 설명 해야 할 수 있는 웹 사이트로 지시할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39327-123">You can also add notes and direct the mailbox owner to a website you might have to explain more about the litigation hold.</span></span> <span data-ttu-id="39327-124">\>**저장**을 합니다.</span><span class="sxs-lookup"><span data-stu-id="39327-124">\> **Save**.</span></span>
    
<span data-ttu-id="39327-p105">**보존:** 특정 기간 동안 보존하거나 보존 기간이 끝나면 영구적으로 콘텐츠를 삭제하는 것과 같은 사용자 지정된 보존 정책을 사용하도록 설정할 수 있습니다. 자세한 내용은 [보존 정책 개요](https://docs.microsoft.com/microsoft-365/compliance/retention-policies)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="39327-p105">**Retention:** You can enable customized retention policies, for example, to preserve for a specific amount of time or delete content permanently at the end of the retention period. To learn more, see [Overview of retention policies](https://docs.microsoft.com/microsoft-365/compliance/retention-policies).</span></span>

## <a name="set-up-sensitivity-labels"></a><span data-ttu-id="39327-127">민감도 레이블 설정</span><span class="sxs-lookup"><span data-stu-id="39327-127">Set up Sensitivity labels</span></span>

<span data-ttu-id="39327-128">민감도 레이블은 Azure Information Protection (AIP) 계획 1에 제공 되며, 레이블을 적용 하 여 문서와 전자 메일을 분류 하 고 필요에 따라 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39327-128">Sensitivity labels come with Azure Information Protection (AIP) Plan 1, and help you classify, and optionally protect your documents and emails, by applying labels.</span></span> <span data-ttu-id="39327-129">규칙 및 조건을 정의 하는 관리자가 사용자에 의해 수동으로 또는 사용자에 게 권장 사항을 제공 하는 조합을 사용 하 여 레이블을 자동으로 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39327-129">Labels can be applied automatically by administrators who define rules and conditions, manually by users, or by using a combination where users are given recommendations.</span></span>

<span data-ttu-id="39327-130">민감도 레이블을 설정 하려면 [만들기 및 관리 민감도 레이블](https://support.office.com/article/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) 비디오를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="39327-130">To set up Sensitivity labels, view [create and manage sensitivity labels](https://support.office.com/article/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) video.</span></span>



### <a name="install-the-azure-information-protection-client-manually"></a><span data-ttu-id="39327-131">수동으로 Azure Information Protection 클라이언트 설치</span><span class="sxs-lookup"><span data-stu-id="39327-131">Install the Azure Information Protection client manually</span></span>

<span data-ttu-id="39327-132">AIP 클라이언트를 수동으로 설치하려면</span><span class="sxs-lookup"><span data-stu-id="39327-132">To manually install the AIP client:</span></span>

1. <span data-ttu-id="39327-133">[Microsoft 다운로드 센터](https://www.microsoft.com/download/details.aspx?id=53018)에서 **AzinfoProtection_UL** 를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="39327-133">Download **AzinfoProtection_UL.exe** from [Microsoft download center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>
 
2. <span data-ttu-id="39327-134">Word 문서를 보고 **홈** 탭에서 **민감도** 옵션을 사용할 수 있는지 확인 하 여 설치가 제대로 되었는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39327-134">You can verify that the installation worked by viewing a Word document and making sure that the **Sensitivity** option is available on the **Home** tab.</span></span>
<br/><span data-ttu-id="39327-135">![Word 문서의 보호 탭 드롭다운](../media/word-sensitivity.png)</span><span class="sxs-lookup"><span data-stu-id="39327-135">![Protection tab drop-down in a Word document.](../media/word-sensitivity.png)</span></span>

<span data-ttu-id="39327-136">자세한 내용은 [클라이언트 설치](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="39327-136">For more information, see [Install the client](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).</span></span>
