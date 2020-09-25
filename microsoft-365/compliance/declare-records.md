---
title: 보존 레이블을 사용하여 레코드 선언
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
search.appverid:
- MOE150
- MET150
description: 보존 레이블을 사용하여 레코드 선언
ms.openlocfilehash: 490f81ba9c1d2d291539107650ec3c3f5938eba8
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198927"
---
# <a name="declare-records-by-using-retention-labels"></a><span data-ttu-id="1332d-103">보존 레이블을 사용하여 레코드 선언</span><span class="sxs-lookup"><span data-stu-id="1332d-103">Declare records by using retention labels</span></span>

><span data-ttu-id="1332d-104">*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="1332d-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="1332d-105">문서 및 전자 메일을 [레코드](records-management.md#records)로 선언하려면 콘텐츠를 **레코드** 또는 **규제 레코드**로 표시하는 [보존 레이블](retention.md#retention-labels)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1332d-105">To declare documents and emails as [records](records-management.md#records), you use [retention labels](retention.md#retention-labels) that mark the content as a **record** or a **regulatory record**.</span></span>

> [!NOTE]
> <span data-ttu-id="1332d-106">규제 레코드는 현재 미리 보기 중입니다.</span><span class="sxs-lookup"><span data-stu-id="1332d-106">Regulatory records are currently in preview.</span></span>

<span data-ttu-id="1332d-107">레코드 또는 규제 레코드를 사용할지 확실하지 않은 경우 [허용되거나 차단된 작업에 대한 제한을 비교](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1332d-107">If you're not sure whether to use a record or a regulatory record, see [Compare restrictions for what actions are allowed or blocked](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked).</span></span> <span data-ttu-id="1332d-108">규제 레코드를 사용해야 하는 경우 먼저 다음 섹션에 설명된 대로 PowerShell 명령을 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1332d-108">If you need to use regulatory records, you must first run a PowerShell command, as described in the next section.</span></span>

<span data-ttu-id="1332d-109">그런 다음 이러한 레이블을 보존 레이블 정책에 게시하여 사용자와 관리자가 컨텐츠에 적용할 수 있도록 하거나 항목을 레코드(규제 레코드는 아님)로 표시하는 레이블의 경우 레코드를 선언할 컨텐츠에 레이블을 자동으로 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1332d-109">You can then either publish those labels in a retention label policy so that users and administrators can apply them to content, or for labels that mark items as records (but not regulatory records), auto-apply those labels to content that you want to declare a record.</span></span>

## <a name="how-to-display-the-option-to-mark-content-as-a-regulatory-record"></a><span data-ttu-id="1332d-110">콘텐츠를 규제 레코드로 표시하는 옵션을 표시하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="1332d-110">How to display the option to mark content as a regulatory record</span></span>

>[!NOTE] 
> <span data-ttu-id="1332d-111">다음 절차는 감사 로그의 [보존 정책 및 보존 레이블 활동](search-the-audit-log-in-security-and-compliance.md#retention-policy-and-retention-label-activities) 섹션에 있는 **보존 레이블에 대해 사용 설정된 규제 레코드 옵션**을 로깅하는 감사 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="1332d-111">The following procedure is an auditable action, logging **Enabled regulatory record option for retention labels** in the [Retention policy and retention label activities](search-the-audit-log-in-security-and-compliance.md#retention-policy-and-retention-label-activities) section of the audit log.</span></span>

<span data-ttu-id="1332d-112">기본적으로 내용을 규제 레코드로 표시하는 보존 레이블 옵션은 보존 레이블 마법사에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1332d-112">By default, the retention label option to mark content as a regulatory record isn't displayed in the retention label wizard.</span></span> <span data-ttu-id="1332d-113">이 옵션을 표시하려면 먼저 PowerShell 명령을 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1332d-113">To display this option, you must first run a PowerShell command:</span></span>

1. <span data-ttu-id="1332d-114">[Office 365 보안 및 준수 센터 PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)합니다.</span><span class="sxs-lookup"><span data-stu-id="1332d-114">[Connect to the Office 365 Security & Compliance Center Powershell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="1332d-115">다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1332d-115">Run the following cmdlet:</span></span>
    
    ```powershell
    Set-RegulatoryComplianceUI -Enabled $true
    ````
    <span data-ttu-id="1332d-116">확인할 메시지가 없으며 설정이 즉시 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1332d-116">There is no prompt to confirm and the setting takes effect immediately.</span></span>

<span data-ttu-id="1332d-117">보존 레이블 마법사에서 이 옵션을 보는 것에 대한 생각을 변경하면 **false** 값과 동일한 cmdlet을 실행하여 이 옵션을 다시 숨길 수 있습니다. `Set-RegulatoryComplianceUI -Enabled $false`</span><span class="sxs-lookup"><span data-stu-id="1332d-117">If you change your mind about seeing this option in the retention label wizard, you can hide it again by running the same cmdlet with the **false** value: `Set-RegulatoryComplianceUI -Enabled $false`</span></span> 

## <a name="configuring-retention-labels-to-declare-records"></a><span data-ttu-id="1332d-118">레코드를 선언하도록 보존 레이블을 구성하는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="1332d-118">Configuring retention labels to declare records</span></span>

<span data-ttu-id="1332d-119">Microsoft 365 규정 준수 센터의 **레코드 관리** 솔루션에서 보존 레이블을 생성하거나 편집할 때 항목을 레코드로 표시하는 옵션이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="1332d-119">When you create or edit a retention label from the **Records Management** solution in the Microsoft 365 compliance center, you have the option to mark items as a record.</span></span> <span data-ttu-id="1332d-120">이전 섹션에서 PowerShell 명령을 실행한 경우 또는 항목을 규정 레코드로 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1332d-120">If you ran the PowerShell command from the previous section, you can alternatively mark items as a regulatory record.</span></span>

<span data-ttu-id="1332d-121">예를 들어 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1332d-121">For example:</span></span>

![콘텐츠를 레코드 또는 규정으로 표시하도록 보존 레이블을 구성합니다.](../media/recordversioning6.png)

<span data-ttu-id="1332d-123">이 보존 레이블을 사용하여 필요에 따라 SharePoint 또는 OneDrive 문서 및 Exchange 전자 메일에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1332d-123">Using this retention label, you can now apply it to SharePoint or OneDrive documents and Exchange emails, as needed.</span></span> 

<span data-ttu-id="1332d-124">전체 지침은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1332d-124">For full instructions:</span></span>

- [<span data-ttu-id="1332d-125">보존 레이블을 만들어 앱에 적용합니다</span><span class="sxs-lookup"><span data-stu-id="1332d-125">Create retention labels and apply them in apps</span></span>](create-apply-retention-labels.md)

- <span data-ttu-id="1332d-126">[내용에 보존 레이블을 자동으로 적용합니다](apply-retention-labels-automatically.md)(규제 레코드에 지원되지 않음).</span><span class="sxs-lookup"><span data-stu-id="1332d-126">[Apply a retention label to content automatically](apply-retention-labels-automatically.md) (not supported for regulatory records)</span></span>


## <a name="applying-the-configured-retention-label-to-content"></a><span data-ttu-id="1332d-127">구성된 보존 레이블을 내용에 적용하는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="1332d-127">Applying the configured retention label to content</span></span>

<span data-ttu-id="1332d-128">항목을 기록 또는 규제 레코드로 표시하는 보존 레이블을 앱에서 적용할 수 있는 경우 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="1332d-128">When retention labels that mark items as a record or regulatory record are made available for users to apply them in apps:</span></span>

- <span data-ttu-id="1332d-129">Exchange의 경우 사서함에 대한 쓰기 권한이 있는 사용자는 이러한 레이블을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1332d-129">For Exchange, any user with write-access to the mailbox can apply these labels.</span></span> 
- <span data-ttu-id="1332d-130">SharePoint 및 OneDrive의 경우 기본 구성원 그룹에 있는 모든 사용자(참가 권한 수준)는 이러한 레이블을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1332d-130">For SharePoint and OneDrive, any user in the default Members group (the Contribute permission level) can apply these labels.</span></span>

<span data-ttu-id="1332d-131">보존 레이블을 사용하여 레코드로 표시된 문서 예제:</span><span class="sxs-lookup"><span data-stu-id="1332d-131">Example of a document marked as record by using a retention label:</span></span>

![레코드로 태그가 지정된 문서에 대한 세부 정보 창](../media/recordversioning7.png)

## <a name="next-steps"></a><span data-ttu-id="1332d-133">다음 단계</span><span class="sxs-lookup"><span data-stu-id="1332d-133">Next steps</span></span>

<span data-ttu-id="1332d-134">레코드 관리에서 지원되는 기타 시나리오 목록은 [레코드 관리에 대한 일반적인 시나리오](get-started-with-records-management.md#common-scenarios-for-records-management)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1332d-134">For a list of scenarios supported by records management, see [Common scenarios for records management](get-started-with-records-management.md#common-scenarios-for-records-management).</span></span>
