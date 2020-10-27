---
title: Office 365 ATP의 안전한 문서
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: kshi
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Microsoft 365 E5 또는 Microsoft 365 E5 보안의 안전 문서에 대해 알아봅니다.
ms.openlocfilehash: baa04f74388b702b42a0bdb83a7f0797ace09883
ms.sourcegitcommit: 45c0afcf958069c5c1b31f9b6c762d8dd806e1e9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48773952"
---
# <a name="safe-documents-in-microsoft-365-e5"></a><span data-ttu-id="326b1-103">Microsoft 365 E5에서 안전한 문서</span><span class="sxs-lookup"><span data-stu-id="326b1-103">Safe Documents in Microsoft 365 E5</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="326b1-104">안전한 문서는 microsoft [Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) 을 사용 하 여 [제한 된 보기](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)에서 열린 문서와 파일을 검사 하는 Microsoft 365 E5 또는 microsoft 365 e5 보안 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="326b1-104">Safe Documents is a feature in Microsoft 365 E5 or Microsoft 365 E5 Security that uses [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) to scan documents and files that are opened in [Protected View](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="326b1-105">시작하기 전에 알아야 할 사항은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="326b1-105">What do you need to know before you begin?</span></span>

- <span data-ttu-id="326b1-106">안전한 문서는 *microsoft 365 e5* 또는 *Microsoft 365 e5 보안* 라이선스가 있는 사용자만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="326b1-106">Safe Documents is available only to users with *Microsoft 365 E5* or *Microsoft 365 E5 Security* licenses.</span></span> <span data-ttu-id="326b1-107">이러한 라이선스는 Office 365 ATP (Advanced Threat Protection) 계획에 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="326b1-107">These licenses are not included in Office 365 Advanced Threat Protection (ATP) plans.</span></span>

- <span data-ttu-id="326b1-108">안전한 문서는 Microsoft 365 Apps for enterprise (이전 명칭: Office 365 ProPlus) 버전 2004 이상에서 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="326b1-108">Safe Documents is supported in Microsoft 365 Apps for enterprise (formerly known as Office 365 ProPlus) version 2004 or later.</span></span>

- <span data-ttu-id="326b1-109"><https://protection.office.com>에서 보안 및 준수 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="326b1-109">You open the Security & Compliance Center at <https://protection.office.com>.</span></span> <span data-ttu-id="326b1-110">**ATP 안전한 첨부 파일** 페이지로 바로 이동 하려면를 엽니다 <https://protection.office.com/safeattachmentv2> .</span><span class="sxs-lookup"><span data-stu-id="326b1-110">To go directly to the **ATP Safe Attachments** page, open <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="326b1-111">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="326b1-111">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="326b1-112">이 항목의 절차를 수행 하려면 먼저 사용 권한을 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="326b1-112">You need to be assigned permissions before you can perform the procedures in this topic.</span></span> <span data-ttu-id="326b1-113">안전한 문서를 사용 하도록 설정 하 고 구성 하려면 **조직 관리** 또는 **보안 관리자** 역할 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="326b1-113">To enable and configure Safe Documents, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="326b1-114">보안 및 규정 준수 센터의 역할 그룹에 대한 자세한 내용은 [보안 및 규정 준수 센터의 사용 권한](permissions-in-the-security-and-compliance-center.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="326b1-114">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

### <a name="how-does-microsoft-handle-your-data"></a><span data-ttu-id="326b1-115">Microsoft에서 데이터를 처리 하는 방법</span><span class="sxs-lookup"><span data-stu-id="326b1-115">How does Microsoft handle your data?</span></span>

<span data-ttu-id="326b1-116">보호를 유지 하기 위해 안전한 문서는 분석을 위해 [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) 클라우드로 파일을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="326b1-116">To keep you protected, Safe Documents sends files to the [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) cloud for analysis.</span></span> <span data-ttu-id="326b1-117">Microsoft Defender ATP에서 데이터를 처리 하는 방법에 대 한 자세한 내용은 [Microsoft DEFENDER atp 데이터 저장 및 개인 정보](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="326b1-117">Details on how Microsoft Defender ATP handles your data can be found here: [Microsoft Defender ATP data storage and privacy](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span>

<span data-ttu-id="326b1-118">안전한 문서로 보낸 파일은 분석에 필요한 시간 외에는 Defender에 보존 되지 않습니다 (일반적으로 24 시간 미만).</span><span class="sxs-lookup"><span data-stu-id="326b1-118">Files sent by Safe Documents are not retained in Defender beyond the time needed for analysis (typically, less than 24 hours).</span></span>

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a><span data-ttu-id="326b1-119">보안 & 준수 센터를 사용 하 여 안전한 문서 구성</span><span class="sxs-lookup"><span data-stu-id="326b1-119">Use the Security & Compliance Center to configure Safe Documents</span></span>

1. <span data-ttu-id="326b1-120">보안 & 준수 센터에서 **위협 관리** \> **정책** \> **ATP 안전한 첨부 파일로** 이동한 후 **전역 설정을** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="326b1-120">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments** , and then click **Global settings** .</span></span>

2. <span data-ttu-id="326b1-121">**전체 설정이** 표시 되 면 다음 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="326b1-121">In the **Global settings** fly out that appears, configure the following settings:</span></span>

   - <span data-ttu-id="326b1-122">**Office 클라이언트에 대 한 안전 문서 설정** : 오른쪽으로 이동을 이동 하 여 기능을 설정 합니다. ![ ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)</span><span class="sxs-lookup"><span data-stu-id="326b1-122">**Turn on Safe Documents for Office clients** : Move the toggle to the right to turn on the feature: ![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).</span></span>

   - <span data-ttu-id="326b1-123">**안전한 보기를 클릭 하는 것을 허용 하는 경우에도 안전 문서에서 해당 파일을 악성으로 식별** 함:이 옵션을 해제 하는 것이 좋습니다 (왼쪽으로 전환: 설정/해제 상태 그대로 둠 ![ ](../../media/scc-toggle-off.png) ).</span><span class="sxs-lookup"><span data-stu-id="326b1-123">**Allow people to click through Protected View even if Safe Documents identifies the file as malicious** : We recommend that you leave this option turned off (leave the toggle to the left: ![Toggle off](../../media/scc-toggle-off.png)).</span></span>

   <span data-ttu-id="326b1-124">작업을 마쳤으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="326b1-124">When you're finished, click **Save** .</span></span>

   ![ATP 안전한 첨부 파일 페이지에서 전역 설정을 선택한 후에 안전한 문서 설정을 선택 합니다.](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a><span data-ttu-id="326b1-126">Exchange Online PowerShell을 사용 하 여 안전한 문서 구성</span><span class="sxs-lookup"><span data-stu-id="326b1-126">Use Exchange Online PowerShell to configure Safe Documents</span></span>

<span data-ttu-id="326b1-127">다음 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="326b1-127">Use the following syntax:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- <span data-ttu-id="326b1-128">_EnableSafeDocs_ 매개 변수는 전체 조직에 대 한 안전한 문서를 사용 하거나 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="326b1-128">The _EnableSafeDocs_ parameter enables or disables Safe Documents for the entire organization.</span></span>
- <span data-ttu-id="326b1-129">문서가 악성으로 식별 된 경우에는 _AllowSafeDocsOpen_ 매개 변수를 사용 하 여 사용자가 문서를 여는 제한 된 보기를 끝낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="326b1-129">The _AllowSafeDocsOpen_ parameter allows or prevents users from leaving Protected View (that is, opening the document) if the document has been identified as malicious.</span></span>

<span data-ttu-id="326b1-130">이 예에서는 전체 조직에 대해 안전한 문서를 사용 하도록 설정 하 고 제한 된 보기에서 악의적으로 식별 된 문서를 사용자가 열지 못하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="326b1-130">This example enables Safe Documents for the entire organization, and prevents users from opening documents that have been identified as malicious from Protected View.</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

<span data-ttu-id="326b1-131">구문 및 매개 변수에 대 한 자세한 내용은 [AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="326b1-131">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

### <a name="how-do-i-know-this-worked"></a><span data-ttu-id="326b1-132">작동 여부는 어떻게 확인합니까?</span><span class="sxs-lookup"><span data-stu-id="326b1-132">How do I know this worked?</span></span>

<span data-ttu-id="326b1-133">안전한 문서를 사용 하도록 설정 하 고 구성 했는지 확인 하려면 다음 단계 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="326b1-133">To verify that you've enabled and configured Safe Documents, do any of the following steps:</span></span>

- <span data-ttu-id="326b1-134">보안 & 준수 센터에서 **위협 관리** \> **정책** \> **ATP 안전한 첨부 파일로** 이동 하 여 **전역 설정을** 클릭 하 고, **안전한 문서에서 해당 파일을 악성 설정으로 식별 하는 경우에도 사용자가 제한 된 보기를 클릭할 수 있도록** 합니다. **Turn on Safe Documents for Office clients**</span><span class="sxs-lookup"><span data-stu-id="326b1-134">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments** , click **Global settings** , and verify the **Turn on Safe Documents for Office clients** and **Allow people to click through Protected View even if Safe Documents identifies the file as malicious** settings.</span></span>

- <span data-ttu-id="326b1-135">Exchange Online PowerShell에서 다음 명령을 실행 하 고 속성 값을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="326b1-135">Run the following command in Exchange Online PowerShell and verify the property values:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- <span data-ttu-id="326b1-136">안전한 문서 보호를 테스트 하는 데 사용할 수 있는 파일은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="326b1-136">The following files are available to test Safe Documents protection.</span></span> <span data-ttu-id="326b1-137">이러한 문서는 맬웨어 방지 및 바이러스 백신 솔루션을 테스트 하기 위한 EICAR.TXT 파일과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="326b1-137">These documents are similar to the EICAR.TXT file for testing anti-malware and anti-virus solutions.</span></span> <span data-ttu-id="326b1-138">파일이 손상 되는 것은 아니지만 안전한 문서 보호를 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="326b1-138">The files are not harmful, but they will trigger Safe Documents protection.</span></span>

  - [<span data-ttu-id="326b1-139">SafeDocsDemo.docx</span><span class="sxs-lookup"><span data-stu-id="326b1-139">SafeDocsDemo.docx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [<span data-ttu-id="326b1-140">SafeDocsDemo.pptx</span><span class="sxs-lookup"><span data-stu-id="326b1-140">SafeDocsDemo.pptx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [<span data-ttu-id="326b1-141">SafeDocsDemo.xlsx</span><span class="sxs-lookup"><span data-stu-id="326b1-141">SafeDocsDemo.xlsx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)
