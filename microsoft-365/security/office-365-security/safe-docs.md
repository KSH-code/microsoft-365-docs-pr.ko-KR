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
ms.openlocfilehash: 8918c7da26a60c7cfd64b7148d0added82cc6642
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47949457"
---
# <a name="safe-documents-in-microsoft-365-e5"></a><span data-ttu-id="ed193-103">Microsoft 365 E5의 안전 문서</span><span class="sxs-lookup"><span data-stu-id="ed193-103">Safe Documents in Microsoft 365 E5</span></span>

<span data-ttu-id="ed193-104">안전한 문서는 microsoft [Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) 을 사용 하 여 [제한 된 보기](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)에서 열린 문서와 파일을 검사 하는 Microsoft 365 E5 또는 microsoft 365 e5 보안 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="ed193-104">Safe Documents is a feature in Microsoft 365 E5 or Microsoft 365 E5 Security that uses [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) to scan documents and files that are opened in [Protected View](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ed193-105">시작하기 전에 알아야 할 사항은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="ed193-105">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ed193-106">이제 Office 버전 2004 (12730) 이상이 있는 사용자는 안전한 문서를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed193-106">Safe Documents is now generally available to users with Office Version 2004 (12730.x) or greater!</span></span> <span data-ttu-id="ed193-107">이 기능은 기본적으로 해제 되어 있으며 보안 관리자가 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed193-107">This feature is off by default and will need to be enabled by the Security Administrator.</span></span>

- <span data-ttu-id="ed193-108">이 기능은 *microsoft 365 E5* 또는 *Microsoft 365 e5 보안* 라이선스가 있는 사용자만 사용할 수 있습니다 (Office 365 ATP 계획에 포함 되지 않음).</span><span class="sxs-lookup"><span data-stu-id="ed193-108">This feature is only available to users with the *Microsoft 365 E5* or *Microsoft 365 E5 Security* license (not included in Office 365 ATP plans).</span></span>

- <span data-ttu-id="ed193-109">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ed193-109">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="ed193-110">독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ed193-110">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="ed193-111">자세한 내용은</span><span class="sxs-lookup"><span data-stu-id="ed193-111">For more information about</span></span> 

- <span data-ttu-id="ed193-112">이 항목의 절차를 수행 하려면 먼저 사용 권한을 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed193-112">You need to be assigned permissions before you can perform the procedures in this topic.</span></span> <span data-ttu-id="ed193-113">안전한 문서를 사용 하도록 설정 하 고 구성 하려면 **조직 관리** 또는 **보안 관리자** 역할 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed193-113">To enable and configure Safe Documents, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="ed193-114">보안 및 규정 준수 센터의 역할 그룹에 대한 자세한 내용은 [보안 및 규정 준수 센터의 사용 권한](permissions-in-the-security-and-compliance-center.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ed193-114">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="how-does-microsoft-handle-your-data"></a><span data-ttu-id="ed193-115">Microsoft에서 데이터를 처리 하는 방법</span><span class="sxs-lookup"><span data-stu-id="ed193-115">How does Microsoft handle your data?</span></span>

<span data-ttu-id="ed193-116">보호를 유지 하기 위해 안전한 문서는 분석을 위해 [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) 클라우드로 파일을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="ed193-116">To keep you protected, Safe Documents sends files to the [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) cloud for analysis.</span></span>

- <span data-ttu-id="ed193-117">Microsoft Defender Advanced Threat Protection에서 데이터를 처리 하는 방법에 대 한 자세한 내용은 [여기](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed193-117">Details on how Microsoft Defender Advanced Threat Protection handles your data can be found [here](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span>
- <span data-ttu-id="ed193-118">위의 지침 외에도 안전 문서에서 보내는 파일은 분석에 필요한 시간을 초과 하 여 Defender에 보존 되지 않습니다 (일반적으로 24 시간 미만).</span><span class="sxs-lookup"><span data-stu-id="ed193-118">In addition to the guidelines above, files sent by Safe Documents are not retained in Defender beyond the time needed for analysis, which is typically less than 24 hours.</span></span>

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a><span data-ttu-id="ed193-119">보안 & 준수 센터를 사용 하 여 안전한 문서 구성</span><span class="sxs-lookup"><span data-stu-id="ed193-119">Use the Security & Compliance Center to configure Safe Documents</span></span>

1. <span data-ttu-id="ed193-120">보안 & 준수 센터를에서 엽니다 <https://protection.office.com> .</span><span class="sxs-lookup"><span data-stu-id="ed193-120">Open the Security & Compliance Center at <https://protection.office.com>.</span></span>

2. <span data-ttu-id="ed193-121">**위협 관리** \> **정책** \> **ATP 안전한 첨부 파일로**이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed193-121">Go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

3. <span data-ttu-id="ed193-122">**Office 응용 프로그램에서 제한 된 보기를 열 수 있도록 파일을 신뢰 하는 경우 사용자가 안전 하 게** 보호 섹션을 유지 하려면 다음 설정 중 하나를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed193-122">In the **Help people stay safe when trusting a file to open outside Protected View in Office applications** section, configure either of the following settings:</span></span>

   - <span data-ttu-id="ed193-123">**Office 클라이언트에 대 한 안전 문서 설정**</span><span class="sxs-lookup"><span data-stu-id="ed193-123">**Turn on Safe Documents for Office clients**</span></span>

   - <span data-ttu-id="ed193-124">**안전한 보기를 통해 클릭할 수 있도록 허용 문서가 악성 파일인 것으로 식별**되는 경우에도이 옵션을 사용 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ed193-124">**Allow people to click through Protected View even if Safe Documents identifies the file as malicious**: We recommend that you don't enable this option.</span></span>

4. <span data-ttu-id="ed193-125">작업을 마쳤으면 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ed193-125">When you're finished, click **Save**.</span></span>

![ATP 안전한 첨부 파일 페이지](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-documents"></a><span data-ttu-id="ed193-127">Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell을 사용 하 여 안전한 문서 구성</span><span class="sxs-lookup"><span data-stu-id="ed193-127">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Documents</span></span>

<span data-ttu-id="ed193-128">다음 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ed193-128">Use the following syntax:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- <span data-ttu-id="ed193-129">_EnableSafeDocs_ 매개 변수는 전체 조직에 대 한 안전한 문서를 사용 하거나 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed193-129">The _EnableSafeDocs_ parameter enables or disables Safe Documents for the entire organization.</span></span>

- <span data-ttu-id="ed193-130">문서가 악성으로 식별 된 경우에는 _AllowSafeDocsOpen_ 매개 변수를 사용 하 여 사용자가 문서를 여는 제한 된 보기를 끝낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed193-130">The _AllowSafeDocsOpen_ parameter allows or prevents users from leaving Protected View (that is, opening the document) if the document has been identified as malicious.</span></span>

<span data-ttu-id="ed193-131">이 예에서는 전체 조직에 대해 안전한 문서를 사용 하도록 설정 하 고 제한 된 보기에서 악의적으로 식별 된 문서를 사용자가 열지 못하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed193-131">This example enables Safe Documents for the entire organization, and prevents users from opening documents that have been identified as malicious from Protected View.</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

<span data-ttu-id="ed193-132">구문 및 매개 변수에 대 한 자세한 내용은 [AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ed193-132">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

### <a name="how-do-i-know-this-worked"></a><span data-ttu-id="ed193-133">작동 여부는 어떻게 확인합니까?</span><span class="sxs-lookup"><span data-stu-id="ed193-133">How do I know this worked?</span></span>

<span data-ttu-id="ed193-134">안전한 문서를 사용 하도록 설정 하 고 구성 했는지 확인 하려면 다음 단계 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed193-134">To verify that you've enabled and configured Safe Documents, do any of the following steps:</span></span>

- <span data-ttu-id="ed193-135">보안 & 준수 센터에서 **위협 관리** \> **정책** \> **ATP 안전한 첨부 파일로**이동한 다음, **Office 응용 프로그램에서 제한 된 보기 외부에서 열 수 있는 파일을 신뢰 하는 경우 도움말 사용자의 안전한 상태 유지** 를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed193-135">In the Security & Compliance Center go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, and verify the selections in the **Help people stay safe when trusting a file to open outside Protected View in Office applications** section.</span></span>

- <span data-ttu-id="ed193-136">Exchange Online PowerShell에서 다음 명령을 실행 하 고 속성 값을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed193-136">Run the following command in Exchange Online PowerShell and verify the property values:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```
